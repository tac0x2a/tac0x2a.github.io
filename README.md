# TACの雑記
https://tac0x2a.github.io/

## セットアップ
```
$ git clone git@github.com:tac0x2a/tac0x2a.github.io.git
$ cd tac0x2a.github.io
$ git checkout -b source
$ rbenv exec bundle install
```

## 記事を書く
```
$ rbenv exec rake new['EntryTitle'] # source/_posts 以下にファイルが出来る
$ emacs source/_posts/<yyyy-mm-dd->'EntryTitle'.markdown
```

## 記事を確認する
```
$ rbenv exec rake preview
$ open http://localhost:4000
```

## 記事を公開する
```
$ rbenv exec rake gen_deploy #masterブランチに_deploy以下がpushされる
```
