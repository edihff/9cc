# 9cc

## コンテナを作成してその中でコマンドを実行するためには、docker runコマンドの引数としてイメージ名とコマンドを与えてください。以下はls /コマンドをcompilerbookのコンテナの中で実行する例です。
docker run --rm compilerbook ls /

## ホームディレクトリの9ccというサブディレクトリにソースファイルが置いてあるものとしましょう。そのディレクトリに対してコンテナ内からmake testを実行するためには、次のコマンドを実行してください。

docker run --rm -v $(pwd):/9cc -w /9cc compilerbook make test

## コンテナ内でシェルを起動してインタラクティブに使いたい場合は、以下のように-itオプションをつけてdocker runを実行してください。

## コンテナの起動と中に入る
docker run --rm -it -v "$(pwd):/9cc" -w /9cc compilerbook

## test.sh実行（コンテナの中で）
chmod a+x test.sh

./test.sh