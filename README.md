# opensfm-tutorial
How to set up opensfm on any computer through docker.
First, to download from Docker, run:

`sudo docker pull awkbr549/opensfm`
## Running OpenSfM on localhost
To expose the Docker container's port 8000 to localhost, run:

`sudo docker run -it --expose 8000 -p 8000:8000 awkbr549/opensfm`

This will start an instance of the awkbr549/opensfm container, and this instance number should show up after root@. Save the id after root@ somewhere so when we exit the docker container, we can go back to the exact same version of the container.

To run the reconstruction of an example set of images in `data/berlin`, go to the root of the project `/source/OpenSfM` and run:

`./bin/run_all data/berlin`

Then, run the following command to start the python server:

`python -m SimpleHTTPServer`

To see the 3D reconstruction in your browser, copy and paste the following into your browser's address bar:

`http://localhost:8000/viewer/reconstruction.html#file=/data/berlin/reconstruction.meshed.json`

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


