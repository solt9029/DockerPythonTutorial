# Docker内でPythonを使う（初心者向けシンプルな例）

表現を簡易的にするために厳密には間違った表現が多々ありますがご了承ください

gitとDocker for Windowsがインストールされていることが前提です

インストールされていない場合には

- git: https://git-scm.com/downloads

- Docker for Windows: https://www.docker.com/docker-windows

からダウンロードしてインストールしてください

インストール済みだったら以下のコマンドをじゃんじゃん打ってみましょう

```
git clone https://github.com/solt9029/DockerPythonTutorial 
```

これでプログラムをダウンロードします

```
cd DockerPythonTutorial
```

これで今ダウンロードしたDockerPythonTutorialフォルダに移動します

```
docker-compose up -d
```

これでDockerを利用して仮想環境を作ります！簡単ですね

```
docker ps
```

このコマンドを打ってみると、今立ち上がっている仮想環境の一覧が出てきます

dockerpythontutorial_python_1とかいう名前のものがあるか確認してみてください

```
docker exec -it dockerpythontutorial_python_1 bash
```

これで仮想環境の中に入っちゃいます！

```
cd /var/www/html
```

仮想環境の中の/var/www/htmlフォルダに移動します

```
ls
```

/var/www/htmlに入ってるファイルのリストが見れます

test.pyなどが入ってると思います

実は、WindowsのDockerPythonTutorialフォルダに入っているファイルがそのまま仮想環境の中の/var/www/htmlフォルダの中にリンクされています

だから、Windows上でDockerPythonTutorialフォルダに何かファイルを追加すれば、仮想環境の/var/www/htmlフォルダにも追加されるわけです！

```
python test.py
```

これでHello Worldが出力されればとりあえずOKです！