# Rancher

![Alt Text](https://github.com/yhidetoshi/Pictures/blob/master/Rancher/rancher.png)

Rancher


- 環境
  - EC2
    - CoreOS
      - CoreOS stable (1353.8.0)
  - Rancher-server
    - $ `docker run -d --restart=always -p 8080:8080 rancher/server`
  
 
- Rancherサーバのコンテナが動いているCore-OSのホストで実行した。
  - `$ docker run --rm -it --privileged -v /var/run/docker.sock:/var/run/docker.sock rancher/agent http://<RancherホストのIP>:8080`
  


` ~ $ docker ps`
```
CONTAINER ID        IMAGE                            COMMAND                  CREATED             STATUS              PORTS                              NAMES
052a1a6fca7d        rancher/net:v0.11.2              "/rancher-entrypoint."   6 minutes ago       Up 6 minutes                                           r-ipsec-ipsec-router-1-c194b13e
d9531896ae16        rancher/net:holder               "/.r/r /rancher-entry"   6 minutes ago       Up 6 minutes                                           r-ipsec-ipsec-1-bfb6fe3e
1ec90606e469        rancher/healthcheck:v0.3.1       "/.r/r /rancher-entry"   6 minutes ago       Up 6 minutes                                           r-healthcheck-healthcheck-1-53a786a1
896e46b5b51e        rancher/dns:v0.15.1              "/rancher-entrypoint."   6 minutes ago       Up 6 minutes                                           r-network-services-metadata-dns-1-cbc65891
b3d55e0f5281        rancher/net:v0.11.2              "/rancher-entrypoint."   6 minutes ago       Up 6 minutes                                           r-ipsec-ipsec-cni-driver-1-2929efee
eb947e80a636        rancher/scheduler:v0.8.0         "/.r/r /rancher-entry"   6 minutes ago       Up 6 minutes                                           r-scheduler-scheduler-1-b8c99ac3
c69f4593ca2c        rancher/network-manager:v0.7.1   "/rancher-entrypoint."   6 minutes ago       Up 6 minutes                                           r-network-services-network-manager-1-6a18283d
07a1b646a825        rancher/metadata:v0.9.1          "/rancher-entrypoint."   6 minutes ago       Up 6 minutes                                           r-network-services-metadata-1-cb2c0eed
5aeeab9f7fd7        rancher/agent:v1.2.2             "/run.sh run"            7 minutes ago       Up 7 minutes                                           rancher-agent
d94c53a7ce58        rancher/server                   "/usr/bin/entry /usr/"   10 minutes ago      Up 10 minutes       3306/tcp, 0.0.0.0:8080->8080/tcp   jolly_murdock
```

