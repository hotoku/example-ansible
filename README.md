# example-ansible

ansibleでwslの環境を管理するために必要になりそうな諸々を実験してメモするレポジトリ。まずは、ansible の練習 [getting started][getting started]をやる。

[getting started]: https://docs.ansible.com/ansible/latest/getting_started/index.html

## メモ

`ansible myhosts -m ping -i inventory.ini`で、ssh permission denied が出た。つうことは、鍵ファイルは登録しておく必要がある？
登録しといた方が無難ぽい。そうすると、公開鍵を入れるくらいまでの設定はしといたイメージを作っておくのが良さそう。
が、localhost で実行するようにすれば、それも不要か。リモートからやりたいと思ったのは、元のイメージを、なるべくシンプルに保ちたかったから。
と思うと、公開鍵を入れとくだけの方がよりシンプルな感じがする。

元イメージに必要なこと

- /home/hotoku/.ssh/authorized_keys を配置
- hotoku のパスワードを消しておく

その他手動で必要な設定

- terminal の実行コマンドラインの設定で、-u hotoku を追加

## 作業用のディストリに必要なこと

- /etc/wsl.conf にデフォルトユーザーを追加
- python-gce と同じようなこと
- vscode のインストールと設定
- 作業用ディレクトリを掘って、windows 側にデータが残るようにする

## 作業用ディレクトリ

win 側に /home/horik/OneDrive/lifebook を作っておく

wsl 側で、~/projects を /mnt/c/.../lifebook/projects にシンボリックリンク。
これを、projects 以外にも必要なやつら全部にやっておく。

- projects
- .zsh_history
- junk
- myps
