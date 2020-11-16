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


## [Option1] Run sample programs from command line

本ソフトウェアは人工市場シミュレーションの研究例をサンプルコードをして含む．
ここでは一例として，Chiarella & Iori (2002) のシミュレーション（変更あり）を実行する．

先ほど `git clone` を実行したフォルダから，

```
$ cd plhamJ
$ javac samples/CI2002/CI2002Main.java                                     # C++ 経由でコンパイル
$ java samples/CI2002/CI2002Main samples/CI2002/config.json > output.dat   # 実行出力を output.dat に保存
$ Rscript samples/CI2002/plot.R output.dat output.png                      # 価格時系列をプロット
```

## [Option2] Run sample programs from IntelliJ

 1. IntelliJで落としてきたplhamJのディレクトリーを開く
 2. File > Project Structure を開く
 3. Project タブで Project SDK を指定する
 4. plhamJ 直下に out フォルダーを作成し， Project タブで Project compiler output でそのフォルダ０を指定する
 5. Modules タブの source を開き， プロジェクトディレクトリ(plhamJ)を sourceに指定する
 6. Project Structure の画面を OK で終了する
 7. samples/CI2002/CI2002Main.java (動かしたいプログラムで良い) を開く
 8. `public class CI2002Main extends Main {` の左の緑の▶︎を開き，Runする
 9. Buildが走り，エラーが発生するのをみる．
 10. 右上の緑の▶︎(Run)の左の所に"CI2002Main"と出ているはずなので，それをクリックし， Edit configurationsを押す
 11. Program arguments に `samples/CI2002/config.json` を入れて，OKを押す
 12. もう一度右上の緑の▶︎(Run)から実行
 13. 下のコンソールに結果が表示されるのを確認できます
