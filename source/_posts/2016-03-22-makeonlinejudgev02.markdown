---
layout: post
title: "オンラインジャッジを作ろうvol.2"
date: 2016-03-22 19:43:37 +0900
comments: true
categories:
---

# フレームワークを選ぶ
Webアプリを書くためのフレームワーク(言語)を選ぶ。

## Javascript

+ [人気上昇中のJavaScriptライブラリを調べてみた【2016年版】](http://www.buildinsider.net/web/popularjslib/2016)

### AngularJS

+ [AngularJS入門](http://www.tohoho-web.com/ex/angularjs.html)

> これまでのWebサービスでは、サーバ側で画面(HTML/DOM)を生成していたのに対し、最近のWebサービスでは、サーバ側はDB操作のみを処理し、クライアント－サーバ間をAjaxでJSON交換し、画面(HTML/DOM)はクライアント側で生成する方式が増えてきました。AngularJSは、クライアント側 JavaScript のコントローラでデータモデルを管理し、画面(ビュー)とリアルタイムにデータを交換するのに適したフレームワークです。

なるほど、MVCのVに相当する部分を全部クライアントでやっちゃおうという感じですね。
PHPやJSPみたいに、htmlに埋め込んで記述するみたいです。

サーバ側ではJSONをやりとりするバックエンドの実装が必要になります。

このバックエンドとしてRails(の特にActiveRecord)が挙げられていましたが、
Node.js上で動く[Express](http://expressjs.com/)というフレームワークと、MongoDBと組み合わせた、MEAN(MongoDB+Express+AngularJS+Node.js)という構成が有名みたいです。

MEANを構築するには、Yeomanというワークフロー構築ツールを使うのが一般的みたいです。

+ [あなたのWeb開発人生を変えるYeoman、Bower、Yoのインストールと使い方](http://www.atmarkit.co.jp/ait/articles/1407/02/news040.html)

YoemanはWebフロントエンドでよくある構成を、Railsでいうscaffoldのようにコマンドで生成するツールです。
Grunt(make的なビルドツール), Bower(パッケージマネージャ), Yo(プロジェクトの雛形生成ツール)で構成されています。

+ [Node.jsのMVCフレームワーク「Express」の基礎知識とインストール](http://www.atmarkit.co.jp/ait/articles/1503/04/news047.html)

npmで `generator-angular-fullstack` とか叩くと、Expressやらhttp://blog.mah-lab.com/2014/02/01/angular-fullstack/

[Firebase](https://html5experts.jp/technohippy/18040/) というBaaS(Backend as a Service)もあるみたいですが、今回は一式配布したいのでBaaSは使えませんね。


### Angular2

+ [Angular2は「使える」フレームワークか？](https://developers.eure.jp/tech/angular2_evaluation/)

AngularJSと比較して、劇的にスピードアップし、実装がJavascriptからTypeScriptベースになったそうです。
今始めるならこちらかも。

+ [[初心者向け] Angular2からみるJSフレームワーク入門](http://rdlabo.jp/angular2-373.php)


### React

+ [5分で理解する React.js](http://qiita.com/tomzoh/items/7fabe7cb57dd96425867)

AngularJSと比較されることの多いフレームワーク。こちらもMVCのVに相当する。違いとしては・・・

> ReactではすべてをJSで書き切ることができるのに対して、AngularはHTMLを拡張した独自の記法を使う必要があります。

というかんじらしい。


# まとめ

MEAN(MongoDB, Express, Angular2, Node.js)が良さそう。

今回はここまで。次回は別の言語のフレームワークを調べようかな。
