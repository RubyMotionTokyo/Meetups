# 事前準備

事前にopencv2.frameworkを直接使ったり、それを利用するラッパーを作って試したのが失敗したので、opencv2.framework内にRubyMotion向けラッパーを組み込む必要があると認識。

_ただし本当にそうなのかという確固とした自信はない（-ω-）_

## OpenCVのビルド

現状の最新ソースでは一部ワークアラウンドで回避する必要がありましたが、特に難しいことはなかったです。

[OpenCV for iOSのビルド](http://www.iwazer.com/~iwazawa/diary/2013/07/build-opencv-for-ios.html)

## 組み込み方

ソースツリーをひと通り眺めて、ビルドに一緒に組み込むには`modules`ディレクトリ内にソースコードを用意するっぽい事を発見。

https://github.com/Itseez/opencv/tree/master/modules

`motion`モジュールという名前にします。

他のモジュールのディレクトリ構成を参考にソースコードとCMakeLists.txtを作成。詳しいことは近いうちにブログに書きますｗ

そしてビルドするもbridgeSupportファイルに現れない…

opencv2.framework/Headersの中を見るとヘッダファイルが公開されておらず…というところまででRubyMotionTokyo meetup#3に突入。

# meetupでの作業

moduleのビルド設定は`https://github.com/Itseez/opencv/blob/master/cmake/OpenCVModule.cmake`このcmakeファイルに書かれている。

* コンパイルされるソースは[ここに](https://github.com/Itseez/opencv/blob/master/cmake/OpenCVModule.cmake#L430)`src/*.cpp`と指定されているので`src/*.mm`を追加。
* 公開されるヘッダファイルは[ここに](https://github.com/Itseez/opencv/blob/master/cmake/OpenCVModule.cmake#L432)`include/opencv2/${name}/...`とディレクトリ指定されていたのでソースコードの階層を合わせる。

この辺りを対応してopencv2.frameworkをビルドし、とりあえず呼び出すだけやってみる。

```ruby
class AppDelegate
  def application(application, didFinishLaunchingWithOptions:launchOptions)
    mat = MotionMat.new
    puts mat
    puts mat.empty
  end
end
```

`MotionMat`はOpenCVの`cv::Mat`C++クラスをラップしたObjective-Cのクラスで、インスタンス変数に`cv::Mat`インスタンスを保有しています。

`MotionMat#empty`は`cv::Mat#empty`へデリゲートしているだけです。

```
$ be rake
 :
  Simulate ./build/iPhoneSimulator-6.1-Development/opencv-test.app
#<MotionMat:0x9d54d40>
true
```

呼べたっぽい！ヽ(´ー｀)ノ

# 次回の予定

次はRubyMotionもくもく会があるので、そこまでに実際に動くプログラムに必要なクラスとメソッドだけをラップした`modules/motion`を書いて動かすトライ。次回meetupでの予定はその続きからとなります。
