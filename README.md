==========
dockerfile
==========

------------------
Setup Instructions
------------------

1. Installing docker

  * Ubuntu
  ```sh
  sudo apt-get install docker.io
  ```

  * Fedora
  ```sh
  sudo yum install docker-io
  ```

2. Adding the current user to docker group

```sh
sudo gpasswd -a `whoami` docker
```

3. Ensure the docker group can run `sudo docker` without password

```sh
sudo cp docker-io.conf /etc/sudoers.d/docker-io.conf
```

-----------------------
Available Dockerfile(s)
-----------------------

1. rbenv
