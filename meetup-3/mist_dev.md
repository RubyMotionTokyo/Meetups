# 議事録
## やること

* 後藤 佑輔
 * Railsで仕事をしている
 * Rubykaigi期間中に買ってみたもののiOSがぜんぜんわからず
 * 今日はmedia player frameworkの勉強Ruby gem?
* 外村和仁
 * 仕事: JavaScript 趣味: Rails
 * その延長で RubyMotion を始める
 * なぜかObjective-Cの文法に詳しくなる
 * タスク管理アプリをつくります
* Hiroyuki MORITA
 * 仕事: プログラマじゃないよくわからないこと
 * 外部のAPIをたたいて飲食店をリストアップするアプリ
* 伊藤直也
 * DevOpsエンジニアという名前に反抗するために(?)アプリを作成
 * こないだも作っていたアプリができそうなので最後の仕上げを
* yuumi3
 * Rails iPhone 教育
 * できたらLTします
 * iOSの上で動くRailsの RubyMotion2.4で動かなくなったのでなんとかします
* iwazar
 * openci ビルドできるようになった
 * RubymotionようのモジュールとかC**とかcmakeとかできるようになった
 * ヘッダファイルがまだ見えない
* まつむら
 * ここ数ヶ月Rubymotionのアプリを作っている
 * iOSアプリの開発がはじめて
 * iOS的なものではまっている
 * 2ヶ月前にリリースした将棋の手は見える？
* mist(あいさか)
 * 先々週の録音アプリを引き続き
* hirocaster
 * babble-wrap のテスト? を引き続き
* Toshiwo
 * ライブラリとかを触っているので引き続き
* @ainame
  * RubyMotionでテストを書くときのパターンをまとめる

yuumi3LT
---

SmallWebFrameworkを作った話
Sinatra + Sequel + ERB っぽいもの

成果報告
---

* @ainame
 * テストのまとめを作ってました 今週中くらいにスライドまとめられるように
* mist 
 * 多重再生はできたけど謎のスピードで再生される
* まつむら
 * 将棋の棋譜再生アプリ
 * お気に入り棋譜機能をつける
 * appleに申請しました
* Toshiwo
 * ProMotion1.0にあげたら挙動がかわってたので
 * proc lambda あたりの挙動がかわったことを聞いたので調べた
* iwazar
 * ヘッダファイルは見えるようになりました
 * Objective-Cが見えないと意味がないので続
* watson
 * 2.3 まではいったんインスタンス変数に入れておかないとっていうのを
 * 2.4 で retain されるように
 * 不具合がありそうなので
 * ラスト10分で手書きのブログ?! を書きました
* 伊藤直也
 * githubにスクショあげました
 * 誰か画像つくって
* 後藤 佑輔
 * mac を引っ越したときの provisioning file 作り直してなくてしんだ(´・ω・`)
 * watson > Dropbox に証明書いれてますよ(?!)
* 外村和仁
 * タスク管理アプリのリファクタリング
 * API呼ぶところを bubble-wrap で mvc っぽくしたくて未完成
 * ainame > motion-resource active-model-serializer あたりのライブラリをくみあわせるとよさげ
* morita
 * APIからデータを取るところまではできた
 * APIKeyの扱いはどうするのがよいのか
 * iwazar > 環境変数で設定して info.plist でごにょごにょ
 * watson > configuration file を別に作成するのはみんなやるよね
 * Toshiwo > motion-config-vars‎ とか ほかにもライブラリあるよ 
