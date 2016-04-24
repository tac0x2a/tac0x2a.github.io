---
layout: post
title: "AngularJS導入"
date: 2016-04-24 14:30:27 +0900
comments: true
categories: make_online_judge tech
---
随分間が空きましたがこつこつ進めてますよ！

npm で AngularJS 入れると node_modulesの下に入ってしまい面倒なのでBowerを使ってみることに。

+ [ここ数年前から2015/5までのモダンフロントエンドを総まとめしてみた](http://qiita.com/okmttdhr/items/1caff5a36c8468779a64)

> Angular.js 2.0やReact.jsなど、ES6の流れをくんでいるスクリプトは、Node.jsの世界で完結させることができるので、今後Bowerは使いドコロが減ってゆきそうです。


ぐぬぬ。初心者なのでちょっと枯れてるくらいが丁度いいんですよ！

## Bower 入れる

![Bower](http://bower.io/img/bower-logo.svg)

アイコンかわいい！

Bowerはフロントエンドで使われるパッケージマネージャ。npmはバックエンド(Node.js)用と考えておけばOKっぽい。

+ [Bower - A package manager for the web](http://bower.io/)
+ [npm とか bower とか一体何なんだよ！Javascript 界隈の文脈を理解しよう](http://qiita.com/megane42/items/2ab6ffd866c3f2fda066)

```sh
$ npm install -g bower
```

以下の内容で`.bowerrc`を作る。
```json
{
  "directory": "public/components",
  "json": "bower.json"
}
```

```sh
$ bower init
```


## 余計な静的ファイルを見えないようにする

bowerのパッケージをpublicの下にしたので、`app.js`の静的ファイルのルーティングを修正して、余計なファイル(Bowerde入れたパッケージのREADME.mdとか)を見えないように、必要な物だけ見せるように設定する。
```diff
-app.use(express.static(path.join(__dirname, 'public')));
+app.use('/images', express.static(path.join(__dirname, 'public','images')));
+app.use('/javascripts',express.static(path.join(__dirname, 'public','javascripts')));
+app.use('/stylesheets',express.static(path.join(__dirname, 'public','stylesheets')));
+app.use('/semantic',express.static(path.join(__dirname, 'public','semantic')));
+app.use('/angular',express.static(path.join(__dirname, 'public','components','angular')));
```

## AngularJSを入れる

```sh
$ bower install --save angular
```

あとは以下を参考に。

+ [MongoDB+Express+AngularJS+Node.jsでシンプルなCRUDアプリ作成](http://qiita.com/naga3/items/e63144e17cb1ab9e03e9)


# 小ネタ

## ファイル変更で自動サーバ再起動

```
$ npm install -g nodemon
```

以下のコマンドで起動する。
```
$ nodemon ./bin/www
```
