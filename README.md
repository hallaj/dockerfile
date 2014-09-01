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
  * TODO
1. rails
  * Extends the ubuntu:latest
  * Includes the following items:
    * Installed rbenv
    * Installed rails
    * Created user account
    * Default change changed to user's home
    * Installed editor (vim) and vcs (git)
    * Default ```docker run``` state return's bash.
  * Use case
  ```sh
  docker run -v /home/hallaj:/home/hallaj -i -t rails/hallaj
  ```
  * Ensure you comment out 'therubyracer' after creating a new application
