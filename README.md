# Rancher
Rancher



### Rancherで追加するホストにログインして下記のコマンドを実行する
- Rancherサーバのコンテナが動いているCore-OSのホストで実行した。
$ `docker run --rm -it --privileged -v /var/run/docker.sock:/var/run/docker.sock rancher/agent http://52.68.30.250:8080`
