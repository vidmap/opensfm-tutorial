# opensfm-tutorial
How to set up opensfm on any computer through docker.
First, to download from Docker, run:
`sudo docker pull awkbr549/opensfm`
## Run OpenSfM on localhost

## First time using opensfm within the docker container

Run this command to enter your docker container:

`sudo docker run -it --expose 8000 -p 8000:8000 awkbr549/opensfm`

Save the id after root@ somewhere so when we exit the docker container, we can go back to the exact same version of the container.

Go to the root of the project(OpenSfm) and run

`./bin/run_all data/berlin`

Start the http server

`python -m SimpleHTTPServer`

Go to [this link](http://localhost:8000/viewer/reconstruction.html#file=/data/berlin/reconstruction.meshed.json) to check out the reconstruction

In the future, change the path data/berlin to other paths.


### Reentering opensfm

`sudo docker start BLANK(id goes here)`

After starting that docker image, we want to attach to it:

`sudo docker attach BLANK(same id)`

After running the command above, enter any key to continue(run things on localhost etc.).


### Moving things from outside into docker containers

`sudo docker cp PATH_TO_FILE ID_GOES_HERE: PATH_TO_DESTINATION`


### Save your edits in your docker container

`sudo docker commit IMAGE_ID IMAGE(Ex: awkbr549/opensfm)

## Other commands

To see all your current images and find Image IDs

`sudo docker images`


## Potential Errors

for libdc1394 error: Failed to initialize libdc1394, run:

`sudo ln /dev/null /dev/raw1394`


