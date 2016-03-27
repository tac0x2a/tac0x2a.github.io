---
layout: post
title: "オンラインジャッジを作ろう vol.7(Dockerによる開発環境)"
date: 2016-03-27 23:23:06 +0900
comments: true
categories:
---

# 開発環境を作る
とりあえず、Node.js, Express, MongoDBが動作する環境を作る。
他環境へ持って行ったり、どこかで自動テストできるように、
以下を参考にしながら開発/実行環境をDockerで作る。

+ [docker-composeを使って最高の開発環境を手に入れた](http://blog.muuny-blue.info/7d128c1d4a33165a8676d1650d8ff828.html)

上記を参考に作ったらこんなかんじになった。

+ [tac0x2a/judgesv_devenv](https://github.com/tac0x2a/judgesv_devenv)

# ところが・・・
MongoDBのVolumeマウントでハマった。

```
2016-03-27T16:58:37.013+0000 I CONTROL  [initandlisten] options: {}
2016-03-27T16:58:37.069+0000 I STORAGE  [initandlisten] exception in initAndListen: 98 Unable to create/open lock file: /data/db/mongod.lock errno:13 Permission denied Is a mongod instance already running?, terminating
2016-03-27T16:58:37.069+0000 I CONTROL  [initandlisten] dbexit:  rc: 100
```

+ [MacのDocker上で動くMongoDBのデータを永続化するの大変そう](http://qiita.com/ota42y/items/af90ada86fd671dc5122)

> MongoDBはVirtualBoxの共有フォルダはサポートしていないようです。

どうしよ。。。次回へ続く！
