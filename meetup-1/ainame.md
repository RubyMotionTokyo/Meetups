# RubyMotionTokyo Meetup#1

議事録的なファイルです。

## 成果や出た話題
* fmdbをつかってRubyでSequelのサブセットをつくった(yuumi3さん)
* Objective-Cで小文字始まりの定数を参照しようとした時にハマる
 * kDBSDKVersionという定数はRubyでは定数として扱われない(cocoapodsのDropBoxSDKをいじってた時の話)
 * KDBSDKVersionでREPLからアクセスするも存在してない？
 * どうやらビルド時にヘッダーから使えそうな定数を集めて定数に扱いにするらしく、いちどコード中putsでもなんでも良いので触っておくと良い
* motion-supportはやっぱりハマる
 * 2.1で依存関係周りは良くなったらしい(watsonさん談)
* Objective-Cで存在しているクラスを継承したクラスでnewメソッドを使うとハマる
 * Objective-Cのnewはalloc.initを使う
 * 素のnewはRubyのnew
 * 継承してるとinitがあること前提で動いちゃう
 * newに引数を渡すかどうかでも変わる
 * 要検証！！！
* WatsonさんがRubyMotion2.1で追加されたドキュメントの翻訳をしてくれた！
* 効率よく開発するためにどうするか？
 * IntefaceBuilder使う？
  * ib gemあるよ！
  * https://github.com/Pixate/RubyMotion-Pixate これ使う？
  * コードベタ書きが良い？
* autolayoutどうする？
 * motion-layoutで出来るよ！
* ボーカロイド百人一首アプリ！(Takahashiさん)
* 新しいMacBookAirのセットアップだけで終わってしまった！(iwaserさん）
