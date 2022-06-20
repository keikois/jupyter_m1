# jupyter_m1
m1Macでもintel Macでも起動するjupyterを起動するためのdocker-composeです。(pandas入り)


```
jupyterlab_mysql
├── work => （jupyterlabのコードを保存する場所)
│           
└── docker-compose.yml
```
(workは自動で生成されます)
※事前にDocker desktopのインストールが必要です。
## ディレクトリのクローンのやり方
ターミナルで下記を実行してください。
- SSH設定無しでクローンしたい方はこちら
```
git clone https://github.com/keikois/jupyter_m1.git
```
- SSHキーをGitHubで設定している方はこちら
```
git clone git@github.com:keikois/jupyter_m1.git
```

クローンした後
```
cd jupyter_m1
```
```
docker-compose up -d
```
上記コマンドを打つと、jupyterlabが起動します。

localhost:8888をブラウザで開くとjupyterlabが開きます。（pyhton言語が使えます）

- localhost:8888で起動後、workディレクトリを選択し、notebook => python3 (ipykernel)をクリック
- ここにpythonコードを書いた後、shift＋Enterでセルを実行できます。

コンテナ終了コマンドは
```
docker-compose down
```
## git cloneが終ったら
git cloneが終ったら、リモートリポジトリを削除するコマンドを使ってください。

Git のリモートリポジトリを削除するコマンド
```
git remote rm origin 
```
Gitのリモートリポジトリを確認するコマンド
- 何も書かれていないことを確認してください。
```
git remote -v 
```

## CPUアーキテクチャの確認方法
```
uname -m 
```
実行結果の例）x86_64 => (IntelのCPU)

#### コンテナの中に入ってCPUアーキテクチャを確認する方法
コンテナ起動後、下記でコンテナに入る
```
docker exec -it datascience-notebook-container bash
```
```
uname -m
```
これで、コンテナの中のCPUアーキテクチャを確認できます。
