---
layout: post
title: "オンラインジャッジを作ろう vol.5(Atom設定)"
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
+ [minimap](https://atom.io/packages/minimap) - スクロールバーの位置にソースコードの全体像を表示する
+ atom-typescript - TypeScript用のplugin. 機能多すぎてよくわからんけど凄い


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

# テーマ
## `robin-hood-syntax`
![](https://i.github-camo.com/ab5bd775f86c75113818f712d96c55ba934e1cf8/68747470733a2f2f6769746875622e636f6d2f617a61742d696f2f61746f6d2d726f62696e2d686f6f642d73796e7461782f626c6f622f6d61737465722f696d616765732f68746d6c2e706e673f7261773d74727565)
![](https://i.github-camo.com/e16edf8a04d83900fd3cb9d6907fe8b677e051e7/68747470733a2f2f6769746875622e636f6d2f617a61742d696f2f61746f6d2d726f62696e2d686f6f642d73796e7461782f626c6f622f6d61737465722f696d616765732f6373732e706e673f7261773d74727565)

# その他
Markdownプレビューのフォントを変更する。
+ AP[AtomでカッコよくMarkdown PreviewするためのCSS](http://tanksuzuki.com/post/atom-markdown-style/)


ここまで。気が向いたら追記する。
