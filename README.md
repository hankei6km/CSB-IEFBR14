# CSB-IEFBR14

何もしない Container Sandbox.

## 背景

現時点では、CodeSandbox 上で Container Sandbox を作るには
Container を利用している template を選択する必要がある(たぶん).
公式の Node HTTP Server template は比較的何もしないが、
それでも `creaet-????-app` 等のコマンドで `/sandbox` の中身を入れ替えるのは手間がかかる
(試した限りでは、いきなりファイル・ディレクトリを削除・作成しても
terminal と Files ペインで同期が取れていないなど)

よって、目的とするプロジェクトに入れ替えしやすいように、極力何もしない
tempalate を作成した.

## 利用方法

1. fork する.
1. Explorer で `package.json` 以外を削除する(`yarn.lock` は再作成されることがあるので注意).
1. terminal を開き、`/sandbox` の `package.json` と `node_modules` を削除する.
   このとき、上記で削除したファイルが残っていたら、改めて terminal 内からも削除する.
1. `$ create-????-app` などで `/sandbox` がルートになるように目的のプロジェクトを作成する(`/sandbox/new-proj` 等にならないように注意:).
1. `package.json` を開き、`yarn start` で実行されるスクリプトを書き換える(または`sandbox.config.json` の方を
   ).
1. Server Control Panel を開き server を restart する.

## ライセンス

CC0 1.0](http://creativecommons.org/publicdomain/zero/1.0/deed.ja)
