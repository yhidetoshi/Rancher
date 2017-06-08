# Rancher

![Alt Text](https://github.com/yhidetoshi/Pictures/blob/master/Rancher/rancher.png)

Rancher

- 環境(Mac)
  - Vagrant
    - CoreOS
      - `"Container Linux by CoreOS 1430.0.0 (Ladybug)"`
    - Docker
      - `Docker version 17.05.0-ce, build 89658be`

- core1
```
core@core-01 ~ $ docker ps
CONTAINER ID        IMAGE                            COMMAND                  CREATED             STATUS              PORTS                              NAMES
bf4e18345a3e        rancher/net:v0.11.2              "/rancher-entrypoi..."   About an hour ago   Up About an hour                                       r-ipsec-ipsec-router-1-6dd0583e
f80bc029081a        rancher/healthcheck:v0.3.1       "/.r/r /rancher-en..."   About an hour ago   Up About an hour                                       r-healthcheck-healthcheck-2-eb3a0b16
9fdc33c78b81        rancher/dns:v0.15.1              "/rancher-entrypoi..."   About an hour ago   Up About an hour                                       r-network-services-metadata-dns-2-a9ce26a6
a6c10fe4e3c0        rancher/net:holder               "/.r/r /rancher-en..."   About an hour ago   Up About an hour                                       r-ipsec-ipsec-1-efb96a14
80969174f028        rancher/metadata:v0.9.1          "/rancher-entrypoi..."   About an hour ago   Up About an hour                                       r-network-services-metadata-2-59cc09ba
ac28852c51ae        rancher/net:v0.11.2              "/rancher-entrypoi..."   About an hour ago   Up About an hour                                       r-ipsec-ipsec-cni-driver-1-cec72bd9
800e768bc553        rancher/scheduler:v0.8.0         "/.r/r /rancher-en..."   About an hour ago   Up About an hour                                       r-scheduler-scheduler-1-41985006
65310f3c3d97        rancher/network-manager:v0.7.1   "/rancher-entrypoi..."   About an hour ago   Up About an hour                                       r-network-services-network-manager-2-f4a33261
3f39c6645511        rancher/agent:v1.2.2             "/run.sh run"            About an hour ago   Up About an hour                                       rancher-agent
7638a2e20fcf        rancher/server                   "/usr/bin/entry /u..."   About an hour ago   Up About an hour    3306/tcp, 0.0.0.0:8080->8080/tcp   stupefied_bass
```

- core2
```
core@core-02 ~ $ docker ps
CONTAINER ID        IMAGE                            COMMAND                  CREATED             STATUS              PORTS               NAMES
b8b9ea61cc2d        ubuntu:14.04.3                   "/.r/r /bin/bash"        25 minutes ago      Up 25 minutes                           r-test-create-stack-create-ubunt-1-b37397ab
3038dd4619b1        rancher/net:v0.11.2              "/rancher-entrypoi..."   37 minutes ago      Up 37 minutes                           r-ipsec-ipsec-router-2-32e2b3a7
9988e6624cb4        rancher/net:holder               "/.r/r /rancher-en..."   37 minutes ago      Up 37 minutes                           r-ipsec-ipsec-2-6ab50af8
c301dd348e3a        rancher/healthcheck:v0.3.1       "/.r/r /rancher-en..."   37 minutes ago      Up 37 minutes                           r-healthcheck-healthcheck-3-40febde0
5115d5f2c7ee        rancher/dns:v0.15.1              "/rancher-entrypoi..."   38 minutes ago      Up 38 minutes                           r-network-services-metadata-dns-3-9ce8e30b
7c6abdf82a09        rancher/net:v0.11.2              "/rancher-entrypoi..."   38 minutes ago      Up 38 minutes                           r-ipsec-ipsec-cni-driver-2-34d64403
8cb3dd7b1662        rancher/metadata:v0.9.1          "/rancher-entrypoi..."   38 minutes ago      Up 38 minutes                           r-network-services-metadata-3-31818ead
7b92eab74e2c        rancher/network-manager:v0.7.1   "/rancher-entrypoi..."   39 minutes ago      Up 39 minutes                           r-network-services-network-manager-3-a21d23bc
9b08a0e44a7a        rancher/agent:v1.2.2             "/run.sh run"            40 minutes ago      Up 40 minutes                           rancher-agen
```




- 環境(AWS)
  - EC2
    - CoreOS
      - CoreOS stable (1353.8.0)
  - Rancher-server
    - $ `docker run -d --restart=always -p 8080:8080 rancher/server`
  
- Agentを追加するホストで下記のコマンドを実行する
`$ docker run --rm -it --privileged -v /var/run/docker.sock:/var/run/docker.sock rancher/agent <Registry-URL>:8080`

※ `<Registry-URL>の値は、Admin --> Setting  --> Host Registration URLで設定する`
  


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


#### Rancherサーバコンテナが入ない（ホストを追加下側）
```
core@ip-172-31-50-195 ~ $ docker ps
CONTAINER ID        IMAGE                            COMMAND                  CREATED             STATUS              PORTS               NAMES
25d8b235d129        rancher/net:v0.11.2              "/rancher-entrypoint."   2 minutes ago       Up 2 minutes                            r-ipsec-ipsec-router-2-d59ff008
62fcdb40dc85        rancher/net:holder               "/.r/r /rancher-entry"   2 minutes ago       Up 2 minutes                            r-ipsec-ipsec-2-fa39d828
a3a3189e289e        rancher/healthcheck:v0.3.1       "/.r/r /rancher-entry"   2 minutes ago       Up 2 minutes                            r-healthcheck-healthcheck-2-4daaccf7
1d57bd4d606b        rancher/dns:v0.15.1              "/rancher-entrypoint."   2 minutes ago       Up 2 minutes                            r-network-services-metadata-dns-2-6fff76b4
c2f3e5fd8e59        rancher/net:v0.11.2              "/rancher-entrypoint."   2 minutes ago       Up 2 minutes                            r-ipsec-ipsec-cni-driver-2-ab286bcf
c1e21caed044        rancher/network-manager:v0.7.1   "/rancher-entrypoint."   2 minutes ago       Up 2 minutes                            r-network-services-network-manager-2-562e487a
237c10348c74        rancher/metadata:v0.9.1          "/rancher-entrypoint."   2 minutes ago       Up 2 minutes                            r-network-services-metadata-2-b9d5bfce
9b07be62ea11        rancher/agent:v1.2.2             "/run.sh run"            3 minutes ago       Up 3 minutes                            rancher-agent
```
