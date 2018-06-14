# XamarinAutoSizeFitEditorSample

Xamarin.Form で高さを可変にできる Editor コントロールのサンプル

# 実現したいこと(やりたいこと)

- 簡単に言うと LINE アプリの Chat 入力画面みたいな感じの入力欄
- 複数行(改行を含む)入力することが出来る
- 入力内容に応じて入力欄の高さを変化させる(ただし上限は設ける)
- ソフトウェアキーボードの表示/非表示にも対応する
- 入力が完了(例えばフォーカスが外れたとか)したらソフトウェアキーボードは非表示にしたい
- 送信ボタンみたいなものとセットにした CustomControl でもいいのかもしれない

# 前提とか

1.  基本的には Xamarin.Form で実装する(UI を共通にしたいので)
1.  CustomRenderer は使う
1.  Prism for Xamarin を使う(MVVM で作りたいので)

# 最初の一歩

1.  Prism for Xamarin の Template でソリューションとプロジェクトを作成する
1.  各プロジェクトのプロパティを変更する(csproj ファイルに反映)
    1.  共通プロジェクト
        1.  基本的には変更するところない(はず) … パッケージの情報くらいは直すかも
    1.  Android
        1.  ターゲットフレームワークを Oreo(Android8.1)に変更する
        1.  パッケージ名の部分は Google Play Store にリリースする時に重要(1 回使ったらもう使えない)
    1.  iOS
        1.  ほげほげ
1.  ソリューションの NuGet パッケージの管理で各種パッケージをバージョンアップする
    1.  2018/06/14 時点だと以下のパッケージがとりあえずバージョンアップできる
        - NETStandard.Library (2.0.3)
        - Prism.Unity.Form(7.0.0.396)
        - Xamarin.Forms(3.0.0.561731)
        - Xamarin.Android.Support.Design(27.0.2.1)
        - Xamarin.Android.Support.v4(27.0.2.1)
        - Xamarin.Android.Support.v7.AppCompat(27.0.2.1)
        - Xamarin.Android.Support.v7.CardView(27.0.2.1)
        - Xamarin.Android.Support.v7.MediaRouter(27.0.2.1)
    1.  Xamarin.Android で始まるパッケージは Mono.AndroidVersion が v8.1 じゃないと使えない
        1.  だから Android プロジェクトのターゲットフレームワークを Oreo にする

# メモ

- 気づいたことをここにどんどん書いていく
