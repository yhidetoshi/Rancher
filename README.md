# Rancher
Rancher


- 環境
  - EC2
    - CoreOS
      - CoreOS stable (1353.8.0)
  - Rancher
  
 
- Rancherサーバのコンテナが動いているCore-OSのホストで実行した。
  - `$ docker run --rm -it --privileged -v /var/run/docker.sock:/var/run/docker.sock rancher/agent http://<RancherホストのIP>:8080`
  
