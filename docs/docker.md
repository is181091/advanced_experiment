# Docker
## Ubuntu
### 準備
- Dockerをインストールする。
  ```
  % sudo apt update
  % sudo apt install docker
  ```
- dockerが実行できることを確認する。
  ```
  $ docker version
  ```
- Ubuntu 18.04のイメージをダウンロードする。
  ```
  $ docker pull ubuntu:18.04
  ```
- イメージが存在するかを確認する。
  ```
  $ docker images
  ```

### 起動
- コンテナーを立ち上げる。
  ```
  $ docker run -itd --name コンテナー名 ubuntu:18.04 /bin/bash
  ```
- コンテナーが存在するかを確認する。
  ```
  $ docker ps
  ```
- コンテナーに入る。
  ```
  $ docker exec -it コンテナー名 /bin/bash
  ```

### 停止
- コンテナーを抜ける。
  ```
  $ exit
  ```

## Mac（Catalina）
### 準備
- Dockerのアカウントを作成し、Docker Hubにアクセスする。
  - https://hub.docker.com/
- Docker Desktop for Macをインストールする。
  - https://docs.docker.com/get-docker/
- Docker.appを起動し、IDとPasswordを入力する。
- ターミナルでDockerが実行できることを確認する。
  ```
  $ docker version
  ```
- Ubuntu 18.04のイメージをダウンロードする。
  ```
  $ docker pull ubuntu:18.04
  ```
- イメージが存在するかを確認する。
  ```
  $ docker images
  ```

### 起動
- コンテナーを立ち上げる。オプションnameでコンテナーに対して名前を付ける。例えば「ubuntu」と名付ける。
  ```
  $ docker run -it -d --name コンテナー名 ubuntu:18.04
  ```
- コンテナーが存在するかを確認する。
  ```
  $ docker ps
  ```
- コンテナーに入る。
  ```
  $ docker exec -it ubuntu /bin/bash
  ```

### 停止
- コンテナーを抜ける。
  ```
  $ exit
  ```
- コンテナーを止める。
  ```
  $ docker stop ubuntu
  ```    

## Windows（10）
### 準備
- 「タスクマネージャー」を起動し、［パフォーマンス］→［CPU］から「仮想化：有効」となっていることを確認する。
  - 有効にする方法はメーカーや機種によって異なるので、自分で調べてください。
- 「コントロールパネル」を起動し、［プログラム］→「Windowsの機能の有効化または無効化」から「Hyper-V」にチェックが入っていることを確認する。
- Dockerのアカウントを作成し、Docker Hubにアクセスする。
  - https://hub.docker.com/
- Docker Desktop for Windowsをインストールする。
  - https://docs.docker.com/get-docker/
- Docker.appを起動し、IDとPasswordを入力する。
- コマンドプロンプトでDockerが実行できることを確認する。
  ```
  $ docker version
  ```
- Ubuntu 18.04のイメージをダウンロードする。
  ```
  $ docker pull ubuntu:18.04
  ```
- イメージが存在するかを確認する。
  ```
  $ docker images
  ```

### 起動
- コンテナーを立ち上げる。コンテナー名は「ubuntu」などと名付ける。
  ```
  $ docker run -it --name コンテナー名 ubuntu:18.04 /bin/bash 
  ```
- コンテナーを抜けるときはexitコマンドを使用する。
  ```
  $ exit
  ```
- コンテナーの一覧を確認する。
  ```
  $ docker ps -a
  ```

### 停止
- stopコマンドを使用する。
  ```
  $ docker stop コンテナーID
  または
  $ docker stop コンテナー名
  ```

## 共通
- 必要に応じて、sudoパッケージをインストールする。
  ```
  $ su（※rootでないとき）
  $ apt update
  $ apt install sudo
  ```
- ユーザーを作成する。ユーザー名は「suzuki」などとする。
  ```
  $ adduser ユーザー名
  $ gpasswd -a ユーザー名 sudo
  $ su - ユーザー名
  ```
- コンテナーを作り直す場合は、psコマンドでコンテナーIDを確認し、rmコマンドで削除する。基本的に、コンテナーを停止してから行う。
  ```
  $ docker ps -a
  $ docker rm コンテナーID
  ```
