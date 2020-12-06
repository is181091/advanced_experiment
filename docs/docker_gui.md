# Docker（GUI編）
- DockerはCUIの利用を想定している。
- X Window System（X11）を用いてホストOS上でGUIを表示できる。

## Ubuntu
### 準備
- dockerグループにユーザーを追加する。
  ```
  $ sudo gpasswd -a $USER docker
  ```
- ソケット通信に関するファイルの所有者を変更する。
  ```
  $ sudo chgrp docker /var/run/docker.sock
  ```
- dockerサービスを再起動する。
  ```
  $ sudo service docker restart
  ```
- コンピューターを再起動する。
  ```
  $ sudo reboot
  ```
- 接続が許可されているホストにLOCALがあることを確認する。
  ```
  $ xhost
  ```

## 実行
- イメージをダウンロードする。
  ```
  $ docker pull ros:melodic-robot-bionic
  ```
- コンテナーを作成する。
  ```
  $ docker run -itd --env="DISPLAY" --env="QT_X11_NO_MITSHM=1" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" --name ros ros:melodic-robot-bionic
  ```
- コンテナーに入る。
  ```
  $ docker exec -it ros bash
  ```

## Mac
### 準備
- XQuartzをインストールする。
  - https://www.xquartz.org/
- XQuartzを起動し、［環境設定］→［セキュリティ］から「ネットワーク・クライアントからの接続を許可」にチェックを入れる。
- コンピューターを再起動する。
- XQuartzを起動する。

### 実行
- イメージをダウンロードする。
  ```
  $ docker pull ros:melodic-robot-bionic
  ```
- コンテナーを作成する。
  ```
  $ docker run -itd -e DISPLAY=$(hostname):0 -v ~/.Xauthority:/root/.Xauthority --name ros ros:melodic-robot-bionic
  ```
- コンテナーに入る。
  ```
  $ docker exec -it ros bash
  ```

## Windows
### 準備
- Xmingをインストールする。
  - https://itcweb.cc.affrc.go.jp/affrit/documents/guide/x-window/x-win-xming
- Xmingを起動し、設定を変更する。
  - Public Domain ReleasesのXming 6.9.0.31を選択する。
- コンテナーのIPアドレスを確認する。
  ```
  $ hostname -i
  ```
- Xmingのインストール先（Program Files/Xming）のX0.hostsファイルで、X Windowの転送を許可するサーバ（X Windowを転送するサーバ）のIPアドレスを記入する。
- PCを再起動する。

## 実行
- Xmingを起動する。
- イメージをダウンロードする。
  ```
  $ docker pull ros:melodic-robot-bionic
  ```
- コンテナーを作成する。
  ```
  $ docker run -itd -e DISPLAY=$(hostname):0.0 -v ~/.Xauthority:/root/.Xauthority --name ros ros:melodic-robot-bionic
  ```
- コンテナーに入る。
  ```
  $ docker exec -it ros bash
  ```
- 
  ```
  $ export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0.0
  ```
