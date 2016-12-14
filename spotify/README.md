==============
spotify-client
==============

1. Running instructions

    * Linux
    ```sh
    docker run --rm --interactive --tty --env="DISPLAY" --volume="${HOME}:${HOME}" --volume="/etc/passwd:/etc/passwd:ro" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" --volume="/dev/snd:/dev/snd:ro" --privileged spotify su - ${USER} -s /bin/bash -c spotify
    ```
