---
layout: post
title: "オンラインジャッジを作ろう vol.5 (Atom設定)"
date: 2016-03-26 01:19:06 +0900
comments: true
categories:
---

# パッケージ
+ sync-settings - [Atomの設定を同期する](http://qiita.com/T_M/items/0fb0804eb1fd256aac4e)。
+ atomic-emacs - Emacsのキーバインド
+ emacs-plus   - Emacsのキーバインド
+ disable-keybindings - Emacsのキーバインドとぶつかっているキーを無効にする。
+ ruby-block - Rubyのblockをハイライトしてくれる
+ file-icons - ファイルツリーのアイコンを見やすく
+ project-manager - 複数プロジェクトを記憶して切り替える

コマンドでインストールするには

```
apm install sync-settings
apm install atomic-emacs
apm install emacs-plus
apm install disable-keybindings
apm install ruby-block
apm install file-icons
apm install project-manager
```

## sync-settings
+ GistのIDとGitHubのAccessTokenをそれぞれ設定する。
+ コマンドパレットを開いて(`Cmd+Shift+p`) `Sync Settings:Restore` でgistから設定をリストアする。

## disable-keybindings
+ All Community Packages にチェック入れる。
+ Except Community Packages に `atomic-emacs, emacs-plus` を設定する。
+ Prefix Keys に `ctrl-k` を設定する。


ここまで。気が向いたら追記する。