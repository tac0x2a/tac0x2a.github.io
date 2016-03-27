---
layout: post
title: "オンラインジャッジを作ろう vol.6(Node.jsとExpress)"
date: 2016-03-26 15:49:39 +0900
comments: true
categories:
---
前回はフロントエンドとしてAngular2のチュートリアルを軽く触ってみました。
今回はNode.js + Expressでバックエンドの環境を触ってみようと思います！

# Node.js
どちらもちょっと古め。WebアプリのフレームワークとしてExpressを紹介している。
+ [基礎から学ぶNode.js](http://gihyo.jp/dev/serial/01/nodejs/0001)
+ [ビギナーのための Node.jsプログラミング入門](http://libro.tuyano.com/index2?id=1115003)

# Express

+ [express実践入門](https://gist.github.com/mitsuruog/fc48397a8e80f051a145) - めちゃわかりやすい！

> expressを理解する上での最小構成要素。
> + routing -
>   外部からのHTTP(S)リクエストに対して、内部のロジックをマッピングすること。

> + middleware -
>   routingの過程で何らかの処理を差し込む仕組み。
>   共通処理(認証、エラーハンドリング、リクエストデータの加工、etc)を本来のロジッ> クから分離して、コードベースを健全に保つ。

## Expressのキーワード
+ Jade - デファクトなテンプレートエンジン
+ Mongoose - MongoDBなORM
+ Sequelize - PostgreSQL, MySQL, SQLite, MSSQL なORM
+ Passport - node.jsの認証モジュールでデファクト

# まとめ
なんか作れそうな気がしてきた！
当面の方針として、Expressで作ってみて、フロントエンドをリッチにしたくなってきたらAngular2なりReactなりでViewを強化するようにしてみよう。
まずは、Node.js(Express)とDockerで

+ ユーザ登録/認証
+ 問題の登録
  + テストの登録
+ 回答の登録
  + ユーザごとの回答の履歴
+ 送信された回答とテストの実行

このあたりを作りたいと思います。
