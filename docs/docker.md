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


## 共通
- ユーザーを作成する。
  ```
  $ adduser ユーザー名
  $ gpasswd -a user_name sudo
  $ su - ユーザー名
  ```
  - sudoコマンドをインストールする必要がある？
    ```
    $ apt update
    $ apt install sudo
    ```
