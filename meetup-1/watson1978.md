# RubyMotionTokyo Meetup#1

## Project Management の翻訳
RubyMotion 2.1 をリリースする際に、新たに追加した設定項目 (OSX 用の　Embedded Frameworks) について英語のドキュメントが増えたので、それを訳していました。

- [Project Management](http://rubymotion.jp/RubyMotionDocumentation/guides/project-management/index.html)

## 質疑
いくつか質問を受けたのでそれに回答してました。

- Q : Objective-C のコード内で用意されている定数が REPL で使えない。
- A : 定数は　gen_bridge_metadata というツールを用いて、`xxxx.bridgesupprt` というファイルにメタデータとして抽出しています。ただ、現時点では Ruby のコードをコンパイルした時点で使用している定数などのみが、アプリ内に埋め込まれます。REPL からはアプリが保持している情報しか参照できないので、注意してください。

- Q : Foo.new で呼び出されるメソッドが異なる？
- A : Objective-C では Foo.new は [[Foo alloc] init] とメッセージが送られますが、Ruby では Foo.allocate.initialize とメソッドが呼び出されます。RubyMotion は Objective-C のコード内で用意されたクラス (またはそれを継承したもの) に対して、Foo.new は Foo.alloc.init と呼び出し、Ruby のコード内だけで用意したクラスには Foo.allocate.initialize と呼び出します。また、Objective-C のコード内で用意されたクラスであっても、Foo.new(42) とデータを与える場合には、Foo.allocate.initialize(42) が呼ばれます (Objective-C の init メソッドは引数をとらないので、ユーザが initialize メソッドを別途用意していることを期待しています)