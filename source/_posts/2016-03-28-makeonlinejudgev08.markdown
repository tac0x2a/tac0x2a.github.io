---
layout: post
title: "プロトタイプを作ろう"
date: 2016-03-28 22:22:25 +0900
comments: true
categories: make_online_judge tech
---
# まずはプロトタイプ

前回なんとかDockerで実行環境兼開発環境を構築できました。
とにかく早く作ってみたいので、プロトタイプという体で手を動かしてみます。
どうせ作り直したくなってくるので、最初は適当にやってみようというかんじ。死にゲー。

## Expressの環境構築
```
$ nvm use v5.9.0
$ npm init
$ npm install --save-dev express
```
`--save-dev` オプションを付けておくと、インストールしたパッケージを`package.js`へ自動で追記してくれます。便利！

## アプリを書いてみる
`app.js` という名前で以下のファイルを作った。

```js
var express = require('express');
var app = express();

// receive http request
app.get('/', function (req, res) {
  res.send("Hello, World");
});

// launch server
var server = app.listen(3000, function () {
  var host = server.address().address;
  var port = server.address().port;
  console.log("Judge server is started at http://%s:%s", host, port);
});
```

で、できあがったのがこれ。

+ [tac0x2a/judgesv_app_prototype](https://github.com/tac0x2a/judgesv_app_prototype)

## 実行してみる
```
$ node app.js
$ curl http://:::3000
Hello, World
```

おおお、動いてる！


# Dockerで動かす
これまでは直接Macで動かしていましたが、前回作ったDockerの実行環境で動かしてみます。

+ [tac0x2a/judgesv_devenv](https://github.com/tac0x2a/judgesv_devenv)

```
$ git clone git@github.com:tac0x2a/judgesv_devenv.git
$ cd judgesv_devenv/
$ git clone git@github.com:tac0x2a/judgesv_app_prototype.git data/work
$ docker-compose build
$ docker-compose pull
$ docker-compose up -d
```

`data/work` が DataVolumeになっており、コンテナの `/home/devenv/work` にマウントされて、`node app.js` で実行されます。

エントリポイントが`app.js` 固定になってて気持ち悪いですが、何か設定ファイル等で指定する方法があるんだと思います。そのうち調べます。

はい、今回はここまで〜
