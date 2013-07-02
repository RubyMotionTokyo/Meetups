# RubyMotionTokyo Meetup#2


## RubyMotionのインストール

1. http://www.rubymotion.com/ でライセンスを購入。
2. 購入後の画面からインストーラーをダウンロード。
3. インストーラーを起動し、途中の画面でライセンスキーを入力。

## vimのプラグイン

https://github.com/rcyrus/snipmate-snippets-rubymotion

## チュートリアル

* http://tutorial.rubymotion.jp/

### HelloMotion

#### 1. プロジェクトの作成<br />

```
motion create HelloMotion
```

#### 2. プロジェクトの実行

```
rake
```

tmux上でやったためか、下記のwarningが出てシュミレーターが起動しない。。


```
WARNING! 
It appears you are using tmux without 'reattach-to-user-namespace', the simulator might not work properly. You can either disable tmux or run the following commands:

$ brew install reattach-to-user-namespace
$ echo 'set-option -g default-command "reattach-to-user-namespace -l $SHELL"' >> ~/.tmux.conf
```

tmux を使用しているとシミュレータでアプリが起動しない
http://qiita.com/watson1978/items/558c07f0bd82f64cda73	

解決!!

#### 3. プロジェクトの設定情報確認

```
rake config
```

## 次回

* RubyMotionでAPIのたたきかたとか調べる
* PocketのAPI調べる
