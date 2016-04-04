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
## Google OAuth2
ためしに、GoogleアカウントのOAuth2で認証してみる。

+ https://github.com/barberboy/passport-google-oauth2-example

```
$ npm install passport-google-oauth --save
```

## GoogleAPIs
+ https://console.developers.google.com/project

新しいプロジェクトを作成して、新しく認証情報を作成する。(OAuthクライアントID)

`承認済みのJavaScript生成元`, `承認済みのリダイレクトURI` は空白のままでOK。

redirect_uri_mismatchで認証できなかったが、GoogleAPIsでリダイレクトURLが設定できてなかったため。 [こちら](http://perl.no-tubo.net/2013/09/27/netgoogleanalyticsoauth2-%E3%81%A7%E3%80%8C%E3%82%A8%E3%83%A9%E3%83%BCredirect_uri_mismatch%E3%80%8D%E3%81%A3%E3%81%A6%E8%A8%80%E3%82%8F%E3%82%8C%E3%81%A6refresh_access_token%E3%81%8C%E5%8F%96/)を参考。

今度はコールバックされた先で`failed to fetch user profile`のエラー。GoogleAPIsで作ったプロジェクトで`Google+ API`を有効にすればよい。[こちら](https://github.com/jaredhanson/passport-google-oauth/issues/46)を参考。


## SemanticUI を導入
これまではCSSに[Bootstrap](http://getbootstrap.com/)ばかり使っていたのですが、今回は[SemanticUI](http://semantic-ui.com/)を使ってみることに。

ビルドするのにgulpが必要なのでインストールする。
```
$ npm install -g gulp
```

```
$ npm install semantic-ui --save
```

途中いろいろ聞かれたが、`Express` を選択し、packageは全て選択した。

```
$ cd semantic/
$ gulp build
```

これで必要なファイルが生成された。読み込むようheadを修正する。

```
doctype html
html
  head
    title= title
    link(rel='stylesheet', type='text/css' href='semantic/dist/semantic.min.css')
    script(src='semantic/dist/semantic.min.js')

  body
    block content
```

![Signup]({{ root_url }}/assets/blog/2016-04-05-express/signup.png)
こんなかんじになった。
