# 事前準備

watsonさんの協力により簡単なiOSラッパーをRubyMotionから実際に動かすことに成功。

# meetupでの作業

次のサンプルを追加するにあたってOpenCVで定義されている定数を、いちいち調べて再定義するのが面倒なのでOpenCV C APIのヘッダファイルからenumやdefineをBridge Supportに入れようとしていたが、なかなかうまくいっていなかった…

[rubymotion.jp＞Project Managementドキュメント＞Vendoring 3rd-Party Libraries](http://rubymotion.jp/RubyMotionDocumentation/guides/project-management/index.html#_vendoring_3rd_party_libraries)のstaticライブラリオプションが間違っているのに気付き、rubymotion.comの方を参照してRakefileを修正。

https://github.com/iwazer/motioncv-test/commit/c906af06e36948897bed34df1d237b3c125358c3

_元の指定も間違っていたのだが…_

うまくいったので別のサンプルを作成している途中で時間切れ。

# 次回の予定

ラッパーを追加しやすいようなサンプルプログラム構成を考え中。

まずは用意されたフィルター機能(`opencv2/imgproc`にあるメソッド)を追加していく予定ですが、１つ追加する毎にRubyMotion側の画面をコピペで増やすのもどうかな〜という感じなので。

次回までにうまい構成にできてある程度フィルター実装が増やせてたら、人気のマンガ風フィルタを実装してみたい。

あと、rubymotion.jpのドキュメントは修正プルリクエストdone
