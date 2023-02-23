# Install-Docker-Docker-Compose-and-Helm-on-Oracle-Linux-8


# dnf install -y dnf-utils zip unzip


Last metadata expiration check: 0:16:23 ago on Thu 08 Sep 2022 04:20:41 PM GMT.
Package yum-utils-4.0.21-11.0.1.el8.noarch is already installed.
Package zip-3.0-23.el8.x86_64 is already installed.
Package unzip-6.0-46.el8.x86_64 is already installed.
Dependencies resolved.
========================================================================================================
 Package           Architecture        Version                     Repository                    Size
========================================================================================================
Upgrading:
 unzip             x86_64              6.0-46.0.1.el8              ol8_baseos_latest            196 k

Transaction Summary
========================================================================================================
Upgrade  1 Package

Total download size: 196 k
Downloading Packages:
unzip-6.0-46.0.1.el8.x86_64.rpm                                                        2.7 MB/s | 196 kB    
--------------------------------------------------------------------------------------------------------
Total                                                                                  2.6 MB/s | 196 kB       
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                1/1 
  Upgrading        : unzip-6.0-46.0.1.el8.x86_64                                                    1/2 
  Cleanup          : unzip-6.0-46.el8.x86_64                                                        2/2 
  Running scriptlet: unzip-6.0-46.el8.x86_64                                                        2/2 
  Verifying        : unzip-6.0-46.0.1.el8.x86_64                                                    1/2 
  Verifying        : unzip-6.0-46.el8.x86_64                                                        2/2 

Upgraded:
  unzip-6.0-46.0.1.el8.x86_64                                                                                          

Complete!


# dnf config-manager –add-repo=https://download.docker.com/linux/centos/docker-ce.repo

Adding repo from: https://download.docker.com/linux/centos/docker-ce.repo

# dnf remove -y runc

No match for argument: runc
No packages marked for removal.
Dependencies resolved.
Nothing to do.
Complete!

# dnf install -y docker-ce –nobest

Docker CE Stable - x86_64                                                              691 kB/s |  26 kB     00:00    
Dependencies resolved.
========================================================================================================
 Package                    Arch       Version                                   Repository       Size
========================================================================================================
Installing:
 docker-ce                  x86_64     3:20.10.17-3.el8                            docker-ce-stable  
Installing dependencies:
 container-selinux          noarch     2:2.188.0-1.module+el8.6.0+20721+d8d917a9   ol8_appstream     
 containerd.io              x86_64     1.6.8-3.1.el8                               docker-ce-stable   
 docker-ce-cli              x86_64     1:20.10.17-3.el8                            docker-ce-stable   
 docker-ce-rootless-extras  x86_64     20.10.17-3.el8                              docker-ce-stable  
 fuse-common                x86_64     3.3.0-15.0.2.el8                            ol8_baseos_latest  
 fuse-overlayfs             x86_64     1.9-1.module+el8.6.0+20721+d8d917a9         ol8_appstream     
 fuse3                      x86_64     3.3.0-15.0.2.el8                            ol8_baseos_latest 
 fuse3-libs                 x86_64     3.3.0-15.0.2.el8                            ol8_baseos_latest 
 libcgroup                  x86_64     0.41-19.el8                                 ol8_baseos_latest 
 libslirp                   x86_64     4.4.0-1.module+el8.6.0+20721+d8d917a9       ol8_appstream  
 slirp4netns                x86_64     1.2.0-2.module+el8.6.0+20721+d8d917a9       ol8_appstream  
Installing weak dependencies:
 docker-scan-plugin         x86_64     0.17.0-3.el8                                docker-ce-stable 
Enabling module streams:
 container-tools                          ol8                                                                         

Transaction Summary
========================================================================================================
Install  13 Packages

Total download size: 93 M
Installed size: 389 M
Downloading Packages:
(1/13): docker-ce-20.10.17-3.el8.x86_64.rpm                                            109 MB/s |  22 MB     00:00    
(2/13): docker-ce-rootless-extras-20.10.17-3.el8.x86_64.rpm                            101 MB/s | 4.7 MB     00:00    
(3/13): docker-scan-plugin-0.17.0-3.el8.x86_64.rpm                                     101 MB/s | 3.8 MB     00:00    
(4/13): containerd.io-1.6.8-3.1.el8.x86_64.rpm                                          85 MB/s |  33 MB     00:00    
(5/13): docker-ce-cli-20.10.17-3.el8.x86_64.rpm                                         60 MB/s |  29 MB     00:00    
(6/13): fuse-common-3.3.0-15.0.2.el8.x86_64.rpm                                        106 kB/s |  22 kB     00:00    
(7/13): fuse3-3.3.0-15.0.2.el8.x86_64.rpm                                              510 kB/s |  55 kB     00:00    
(8/13): fuse3-libs-3.3.0-15.0.2.el8.x86_64.rpm                                         1.3 MB/s |  95 kB     00:00    
(9/13): libcgroup-0.41-19.el8.x86_64.rpm                                               507 kB/s |  70 kB     00:00    
(10/13): container-selinux-2.188.0-1.module+el8.6.0+20721+d8d917a9.noarch.rpm          427 kB/s |  59 kB     00:00    
(11/13): fuse-overlayfs-1.9-1.module+el8.6.0+20721+d8d917a9.x86_64.rpm                 568 kB/s |  73 kB     00:00    
(12/13): slirp4netns-1.2.0-2.module+el8.6.0+20721+d8d917a9.x86_64.rpm                  721 kB/s |  54 kB     00:00    
(13/13): libslirp-4.4.0-1.module+el8.6.0+20721+d8d917a9.x86_64.rpm                     839 kB/s |  70 kB     00:00    
-----------------------------------------------------------------------------------------------------------------------
Total                                                                                  128 MB/s |  93 MB     00:00     
Docker CE Stable - x86_64                                                              133 kB/s | 1.6 kB     00:00    
Importing GPG key 0x621E9F35:
 Userid     : "Docker Release (CE rpm) "
 Fingerprint: 060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35
 From       : https://download.docker.com/linux/centos/gpg
Key imported successfully
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                               1/1 
  Installing       : docker-scan-plugin-0.17.0-3.el8.x86_64                                                       1/13 
  Running scriptlet: docker-scan-plugin-0.17.0-3.el8.x86_64                                                       1/13 
  Installing       : docker-ce-cli-1:20.10.17-3.el8.x86_64                                                        2/13 
  Running scriptlet: docker-ce-cli-1:20.10.17-3.el8.x86_64                                                        2/13 
  Running scriptlet: container-selinux-2:2.188.0-1.module+el8.6.0+20721+d8d917a9.noarch                           3/13 
  Installing       : container-selinux-2:2.188.0-1.module+el8.6.0+20721+d8d917a9.noarch                           3/13 
  Running scriptlet: container-selinux-2:2.188.0-1.module+el8.6.0+20721+d8d917a9.noarch                           3/13 
  Installing       : fuse3-libs-3.3.0-15.0.2.el8.x86_64                                                           4/13 
  Running scriptlet: fuse3-libs-3.3.0-15.0.2.el8.x86_64                                                           4/13 
  Installing       : containerd.io-1.6.8-3.1.el8.x86_64                                                           5/13 
  Running scriptlet: containerd.io-1.6.8-3.1.el8.x86_64                                                           5/13 
  Installing       : libslirp-4.4.0-1.module+el8.6.0+20721+d8d917a9.x86_64                                        6/13 
  Installing       : slirp4netns-1.2.0-2.module+el8.6.0+20721+d8d917a9.x86_64                                     7/13 
  Running scriptlet: libcgroup-0.41-19.el8.x86_64                                                                 8/13 
  Installing       : libcgroup-0.41-19.el8.x86_64                                                                 8/13 
  Running scriptlet: libcgroup-0.41-19.el8.x86_64                                                                 8/13 
  Installing       : fuse-common-3.3.0-15.0.2.el8.x86_64                                                          9/13 
  Installing       : fuse3-3.3.0-15.0.2.el8.x86_64                                                               10/13 
  Installing       : fuse-overlayfs-1.9-1.module+el8.6.0+20721+d8d917a9.x86_64                                   11/13 
  Running scriptlet: fuse-overlayfs-1.9-1.module+el8.6.0+20721+d8d917a9.x86_64                                   11/13 
  Installing       : docker-ce-rootless-extras-20.10.17-3.el8.x86_64                                             12/13 
  Running scriptlet: docker-ce-rootless-extras-20.10.17-3.el8.x86_64                                             12/13 
  Installing       : docker-ce-3:20.10.17-3.el8.x86_64                                                           13/13 
  Running scriptlet: docker-ce-3:20.10.17-3.el8.x86_64                                                           13/13 
  Running scriptlet: container-selinux-2:2.188.0-1.module+el8.6.0+20721+d8d917a9.noarch                          13/13 
  Running scriptlet: docker-ce-3:20.10.17-3.el8.x86_64                                                           13/13 
  Verifying        : containerd.io-1.6.8-3.1.el8.x86_64                                                           1/13 
  Verifying        : docker-ce-3:20.10.17-3.el8.x86_64                                                            2/13 
  Verifying        : docker-ce-cli-1:20.10.17-3.el8.x86_64                                                        3/13 
  Verifying        : docker-ce-rootless-extras-20.10.17-3.el8.x86_64                                              4/13 
  Verifying        : docker-scan-plugin-0.17.0-3.el8.x86_64                                                       5/13 
  Verifying        : fuse-common-3.3.0-15.0.2.el8.x86_64                                                          6/13 
  Verifying        : fuse3-3.3.0-15.0.2.el8.x86_64                                                                7/13 
  Verifying        : fuse3-libs-3.3.0-15.0.2.el8.x86_64                                                           8/13 
  Verifying        : libcgroup-0.41-19.el8.x86_64                                                                 9/13 
  Verifying        : container-selinux-2:2.188.0-1.module+el8.6.0+20721+d8d917a9.noarch                          10/13 
  Verifying        : fuse-overlayfs-1.9-1.module+el8.6.0+20721+d8d917a9.x86_64                                   11/13 
  Verifying        : libslirp-4.4.0-1.module+el8.6.0+20721+d8d917a9.x86_64                                       12/13 
  Verifying        : slirp4netns-1.2.0-2.module+el8.6.0+20721+d8d917a9.x86_64                                    13/13 

Installed:
  container-selinux-2:2.188.0-1.module+el8.6.0+20721+d8d917a9.noarch                                                   
  containerd.io-1.6.8-3.1.el8.x86_64                                                                                   
  docker-ce-3:20.10.17-3.el8.x86_64                                                                                    
  docker-ce-cli-1:20.10.17-3.el8.x86_64                                                                                
  docker-ce-rootless-extras-20.10.17-3.el8.x86_64                                                                      
  docker-scan-plugin-0.17.0-3.el8.x86_64                                                                               
  fuse-common-3.3.0-15.0.2.el8.x86_64                                                                                  
  fuse-overlayfs-1.9-1.module+el8.6.0+20721+d8d917a9.x86_64                                                            
  fuse3-3.3.0-15.0.2.el8.x86_64                                                                                        
  fuse3-libs-3.3.0-15.0.2.el8.x86_64                                                                                   
  libcgroup-0.41-19.el8.x86_64                                                                                         
  libslirp-4.4.0-1.module+el8.6.0+20721+d8d917a9.x86_64                                                                
  slirp4netns-1.2.0-2.module+el8.6.0+20721+d8d917a9.x86_64                                                             

Complete!


# systemctl enable docker.service

Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /usr/lib/systemd/system/docker.service.

# systemctl start docker.service

# systemctl status docker.service

● docker.service - Docker Application Container Engine
   Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; vendor preset: disabled)
   Active: active (running) since Thu 2022-09-08 16:38:47 GMT; 4s ago
     Docs: https://docs.docker.com
 Main PID: 36897 (dockerd)
    Tasks: 19
   Memory: 45.8M
   CGroup: /system.slice/docker.service
           └─36897 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Sep 08 16:38:46 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:46.446215726Z" level=warning msg="Your kernel does >
Sep 08 16:38:46 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:46.446326475Z" level=info msg="Loading containers: >
Sep 08 16:38:46 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:46.819311860Z" level=info msg="Default bridge (dock>
Sep 08 16:38:46 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:46.905012618Z" level=info msg="Firewalld: interface>
Sep 08 16:38:46 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:46.991293494Z" level=info msg="Loading containers: >
Sep 08 16:38:47 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:47.001743245Z" level=warning msg="Not using native >
Sep 08 16:38:47 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:47.001974683Z" level=info msg="Docker daemon" commi>
Sep 08 16:38:47 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:47.002142962Z" level=info msg="Daemon has completed>
Sep 08 16:38:47 iam-k8s-002 systemd[1]: Started Docker Application Container Engine.
Sep 08 16:38:47 iam-k8s-002 dockerd[36897]: time="2022-09-08T16:38:47.032423571Z" level=info msg="API listen on /var/r>



Install Docker-Compose


# sudo curl -L “https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)” -o /usr/local/bin/docker-compose

% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 11.6M  100 11.6M    0     0  31.4M      0 --:--:-- --:--:-- --:--:-- 31.4M


# sudo chmod +x /usr/local/bin/docker-compose

# sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

# docker-compose -version

docker-compose version 1.27.4, build 40524192


Install Helm

# wget https://get.helm.sh/helm-v3.9.4-linux-amd64.tar.gz


--2022-09-08 16:39:11--  https://get.helm.sh/helm-v3.9.4-linux-amd64.tar.gz
Resolving get.helm.sh (get.helm.sh)... 152.199.21.175, 2606:2800:233:1cb7:261b:1f9c:2074:3c
Connecting to get.helm.sh (get.helm.sh)|152.199.21.175|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14026634 (13M) [application/x-tar]
Saving to: 'helm-v3.9.4-linux-amd64.tar.gz'

helm-v3.9.4-linux-amd64.tar.g 100%[================================================>]  13.38M  --.-KB/s    in 0.05s   

2022-09-08 16:39:11 (292 MB/s) - 'helm-v3.9.4-linux-amd64.tar.gz' saved [14026634/14026634]

# tar -xvf helm-v3.9.4-linux-amd64.tar.gz

linux-amd64/
linux-amd64/helm
linux-amd64/LICENSE
linux-amd64/README.md

# mv linux-amd64/helm /usr/bin/helm

# helm version


version.BuildInfo{Version:"v3.9.4", GitCommit:"dbc6d8e20fe1d58d50e6ed30f09a04a77e4c68db", GitTreeState:"clean", GoVersion:"go1.17.13"}






