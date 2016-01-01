---
layout: post
title: "Octopressで記事を書くには"
date: 2016-01-02 02:27:30 +0900
comments: true
categories: other
---

備忘録です．Octopressに乗り換えたものの，環境構築忘れるとあれなので．

# TACの雑記
https://tac0x2a.github.io/

## セットアップ
```
$ git clone git@github.com:tac0x2a/tac0x2a.github.io.git
$ cd tac0x2a.github.io
$ git checkout source
$ rbenv exec bundle install
$ git clone git@github.com:tac0x2a/tac0x2a.github.io.git _deploy
```

## 記事を書く
```
$ rbenv exec rake new_post\['Entry Title'\] # source/_posts 以下にファイルが出来る
$ emacs source/_posts/<yyyy-mm-dd->'EntryTitle'.markdown
```

## 記事を確認する
```
$ rbenv exec rake preview
$ open http://localhost:4000
```

## Sourceにコミット
```
$ git add source/_posts/<yyyy-mm-dd->'EntryTitle'.markdown
$ git commit -m "Add new post."
$ git push origin source:source
```

## 記事を公開する
```
$ rbenv exec rake gen_deploy #masterブランチに_deploy以下がpushされる
```

たぶんあってる．