# openstack-clients-pyenv

Python libs tarball for openstack clients. Especially for pyenv

## How to make tarball

```console
$ docker-compose build 2.7.11
$ docker-compose up 2.7.11

## Then
$ ls -l pkg/  
total 40884
drwxr-xr-x  4 udzura staff      136 12  9 15:29 .
drwxr-xr-x 11 udzura staff      374 12  9 15:29 ..
-rw-r--r--  1 udzura staff        0 12  9 15:29 .keep
-rw-r--r--  1 udzura staff 41865130 12  9 15:29 python-2.7.11-with-openstack-clients.tar.gz
```
