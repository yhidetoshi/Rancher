# Rancher

![Alt Text](https://github.com/yhidetoshi/Pictures/blob/master/Rancher/rancher.png)

Rancher


- 環境
  - EC2
    - CoreOS
      - CoreOS stable (1353.8.0)
  - Rancher-server
    - `$ `docker run -d --restart=always -p 8080:8080 rancher/server`
  
 
- Rancherサーバのコンテナが動いているCore-OSのホストで実行した。
  - `$ docker run --rm -it --privileged -v /var/run/docker.sock:/var/run/docker.sock rancher/agent http://<RancherホストのIP>:8080`
  
