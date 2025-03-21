# example-ansible

ansible の練習 [getting started][getting started]をやる。

[getting started]: https://docs.ansible.com/ansible/latest/getting_started/index.html

## メモ

`ansible myhosts -m ping -i inventory.ini`で、ssh permission denied が出た。つうことは、鍵ファイルは登録しておく必要がある？
登録しといた方が無難ぽい。そうすると、公開鍵を入れるくらいまでの設定はしといたイメージを作っておくのが良さそう。
が、localhost で実行するようにすれば、それも不要か。リモートからやりたいと思ったのは、元のイメージを、なるべくシンプルに保ちたかったから。
と思うと、公開鍵を入れとくだけの方がよりシンプルな感じがする。

元イメージに必要なこと

- /etc/wsl.conf にデフォルトユーザーを追加
- /home/hotoku/.ssh/authorized_keys を配置

その他手動で必要な設定

- terminal の実行コマンドラインの設定で、-u hotoku を追加
