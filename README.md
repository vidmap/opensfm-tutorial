# opensfm-tutorial
how to set up opensfm

## Download from docker

Click [here](https://hub.docker.com/r/awkbr549/opensfm/) and run command

` sudo docker pull awkbr549/opensfm


## Run OpenSfM on localhost(using the example dataset called berlin)

### First time using opensfm within the docker container

Run this command to enter your docker container

` sudo docker run -it --expose 8000 -p 8000:8000 awkbr549/opensfm

Save the id after root@ somewhere so when we exit the docker container, we can go back to the exact same version of the container.

Go to the root of the project(OpenSfm) and run

` bin/run_all data/berlin

Start the http server

` python -m SimpleHTTPServer

Go to [this link](http://localhost:8000/viewer/reconstruction.html#file=/data/DATASET_NAME/reconstruction.meshed.json) to check out the reconstruction


### Reentering opensfm

` sudo docker start BLANK(id goes here)

After starting that docker image, we want to attach to it:

` sudo docker attach BLANK(same id)

After running the command above, enter any key to continue(run things on localhost etc.).


### Moving things from outside into docker containers

` sudo docker cp PATH_TO_FILE ID_GOES_HERE: PATH_TO_DESTINATION


### Other commands

To see all your current images and find Image IDs

` sudo docker images



