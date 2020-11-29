# Git
## 準備
- gitをインストールする。
  ```
  $ sudo apt install git
  ```
- gitがインストールされたことを確認する。
  ```
  $ git version
  ```
- ユーザーの名前とメールアドレスを登録する。
  ```
  《記法》
  $ git config --global user.name "名前"
  $ git config --global user.email "メールアドレス"
  ```
  ```
  《実例》
  $ git config --global user.name "Takuo Suzuki"
  $ git config --global user.email "takuo.suzuki@ist.aichi-pu.ac.jp"
  ```

## 使い方
- ROSでは、プログラムをワークスペースのソースに置くので、ディレクトリーを移動する。
  ```
  $ cd ~/catkin_ws/src
  ```
- cloneコマンドでプログラムをコピーする。
  ```
  $ git clone https://github.com/stl-apu/advanced_experiment.git
  ```
- lsコマンドでadvanced_experimentがあるを確認する。
  ```
  $ ls
  ```
- ディレクトリーadvanced_experimentに移動する。
  ```
  $ cd advanced_experiment
  ```
- ブランチの一覧を確認する。
  ```
  $ git branch
  ```
- ブランチ「develop」に移動する。
  ```
  $ git checkout develop
  ```
- 自分用のブランチを作成する。
  ```
  《記法》
  $ git branch feature/名_性
  ```
  ```
  《実例》
  $ git branch feature/takuo_suzuki
  ```
- 自分用のブランチを移動する。
  ```
  $ git branch feature/名_性
  ```
- 
