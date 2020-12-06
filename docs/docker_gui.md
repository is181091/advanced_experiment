# Docker（GUI編）
- DockerはCUIの利用を想定している。
- X Window System（X11）を用いてホストOS上でGUIを表示できる。

## Ubuntu
### 権限
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

### X11
- 接続が許可されているホストにLOCALがあることを確認する。
  ```
  $ xhost
  ```
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

## Windows

