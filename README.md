# Docker内でPythonを使う（初心者向けシンプルな例）

表現を簡易的にするために厳密には間違った表現が多々ありますがご了承ください

gitとDocker for Windowsがインストールされていることが前提です

インストールされていない場合には

- git: https://git-scm.com/downloads

- Docker for Windows: https://www.docker.com/docker-windows

からダウンロードしてインストールしてください

インストール済みだったら以下のコマンドをじゃんじゃん打ってみましょう

```bash
git clone https://github.com/solt9029/DockerPythonTutorial 
```

これでプログラムをダウンロードします

```bash
cd DockerPythonTutorial
```

これで今ダウンロードしたDockerPythonTutorialフォルダに移動します

```bash
docker-compose up -d
```

これでDockerを利用して仮想環境を作ります！簡単ですね

```bash
docker ps
```

このコマンドを打ってみると、今立ち上がっている仮想環境の一覧が出てきます

dockerpythontutorial_python_1とかいう名前のものがあるか確認してみてください

```bash
docker exec -it dockerpythontutorial_python_1 bash
```

これで仮想環境の中に入っちゃいます！

```bash
cd /var/www/html
```

仮想環境の中の/var/www/htmlフォルダに移動します

```bash
ls
```

/var/www/htmlに入ってるファイルのリストが見れます

test.pyなどが入ってると思います

実は、WindowsのDockerPythonTutorialフォルダに入っているファイルがそのまま仮想環境の中の/var/www/htmlフォルダの中にリンクされています

だから、Windows上でDockerPythonTutorialフォルダに何かファイルを追加すれば、仮想環境の/var/www/htmlフォルダにも追加されるわけです！

```bash
python test.py
```

これでHello Worldが出力されればとりあえずOKです！

# 補足説明

今やった手順だと仮想環境の中にはpython3.5がインストールされています

python2.7が欲しいぞい！とかいうときは、このフォルダの中にあるDockerfileを開いてみてください

以下のような記述が見れると思います

```docker
FROM python:3.5
```

この3.5のところを2.7にかえちゃうだけです！簡単！