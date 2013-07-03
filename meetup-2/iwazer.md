# OpenCV本で慣れる

[OS XとiOSのためのOpenCV環境構築ガイド](http://www.amazon.co.jp/OS-X%E3%81%A8iOS%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AEOpenCV%E7%92%B0%E5%A2%83%E6%A7%8B%E7%AF%89%E3%82%AC%E3%82%A4%E3%83%89-%E9%85%92%E4%BA%95-%E9%9B%85%E8%A3%95/dp/4877833099)のサンプル動かしながら読み進め。

* OSX上のサンプル
* iOS上のサンプル

下記は面白そうだけど今回はパス

* GPU使ったサンプル（iOSでは使えない）
* kinectのサンプル（趣旨が違うｗ）

未だにRubyMotion成分0の進捗（-ω-）

# これまでで分かったこと

* iOS用frameworkはOpenCVの持つごく一部の機能の実装しかない
* ただ省略されているAPIはiOS SDK内に同様な機能があるものも多い
* GPUを使うAPIはまだ移植されていない
* コアはC++で書かれているしAPIもC++
* CのAPIも用意されている

# RubyMotionで使えるようにするためには

C/C++どちらにしてもヘッダファイルにインライン関数やC++のクラスが出現するのでRubyMotionのコンパイラに見つかるとコンパイルエラーになる(のだと思われる)

なのでおそらく内部にopencvのスタティックライブラリを直接持つラッパーFrameworkにする必要がある。

C++のクラスは全てObjective-Cのクラスでラップする必要がある。メインのAPIだけでなくそれらにパラメータとして渡す変数の型もRubyMotionが理解できるObjective-C（やC）の型である必要がある。

＃↑間違ってたら指摘してください

# 今後の予定

* サンプルで使用したクラスのみラップしたFrameworkを実装してみる
* RubyMotionのstaticライブラリとして使ってみる

この辺と、以下を並行でやるつもり。

* OpenCVのiOS Framework用ビルドスクリプト(pythonでCMake,Xcodeをハンドリングしてる)を読む
* JoyBoxが同じような事をしているはずなので読む
