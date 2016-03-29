---
layout: post
title: "Expressでバックエンドを作る"
date: 2016-03-30 00:39:31 +0900
comments: true
categories: make_online_judge tech
---

しばらくこのエントリに追記する形で進める。

# express-generator

+ [Node.jsのMVCフレームワーク「Express」の基礎知識とインストール](http://www.atmarkit.co.jp/ait/articles/1503/04/news047.html)

`express-generator` コマンドでプロジェクトの雛形が作れるらしい。
前回の `app.json` の代わりに、上記で置き換えることにした。

```
$ npm install exress-generator
$ express judgesv_app_prototype
$ cd judgesv_app_prototype && npm install
```

実行する場合は、

```
$ npm start
```

これで、`package.json` に書かれている通り、`node ./bin/www` が実行されて起動するようになった。

# まずはともかくユーザ認証
ユーザ認証を実装する。以前調べた [Passport](http://knimon-software.github.io/www.passportjs.org/)を使ってみる。
ためしに、GoogleアカウントでOAuth認証してみる。

```
$ npm install passport-google
```
