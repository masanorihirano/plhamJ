---
title: Install
author: Masanori HIRANO
math: false
---

# Getting started

## Install Java

Java を使用するため，Java をインストールし，環境変数 `JAVA_HOME` を設定しておく必要がある．
また，コマンドで実行するためには ant が必要となる．
IntelliJでも実行することが可能であるので，その場合は，IntelliJをダウンロードする

## Download from GitHub

ターミナルを起動し，以下の手順でソースコードを入手する．

```
$ git clone git@github.com:plham/plhamJ.git
$ git clone https://github.com/plham/plhamJ.git    # HTTPS を使う場合
```

正しく完了すれば，`plham` というフォルダができている．

[githubページ](https://github.com/plham/plhamJ)からダウンロードして，解凍するのでも構わない．


## Run sample programs from command line

本ソフトウェアは人工市場シミュレーションの研究例をサンプルコードをして含む．
ここでは一例として，Chiarella & Iori (2002) のシミュレーション（変更あり）を実行する．

先ほど `git clone` を実行したフォルダから，

```
$ cd plhamJ
$ ant
$ javac samples/CI2002/CI2002Main.java                                     # C++ 経由でコンパイル
$ java samples/CI2002/CI2002Main samples/CI2002/config.json > output.dat   # 実行出力を output.dat に保存
$ Rscript samples/CI2002/plot.R output.dat output.png                      # 価格時系列をプロット
```

