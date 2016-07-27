# FireFox in Docker

A docker image that contains the current FireFox browser.

You can use it to browse the net whilst keeping all config contained separately from everything else.

Alternatively you can use it on a remote server (which I do) when the local machine is low on resources.

## To use:

docker run -it --rm \
   -e DISPLAY \
   --net=host \
   -v /tmp/.X11-unix:/tmp/.X11-unix \
   -v $HOME/.Xauthority:/home/user/.Xauthority \
   area51/firefox

You can also mount /home/user as an additional mount if you want to persist settings between sessions.

Also, you can also run it in the background by replacing -it --rm with -d if you so wish.

## Running on OSX

I've only tested this with running the image on a remote Linux server but presuming you have X11 installed on the mac:

 ssh -Y user@linux.box

Then run the docker command above.

