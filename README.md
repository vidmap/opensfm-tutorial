# opensfm-tutorial
How to set up opensfm on any computer through docker.
First, to download from Docker, run:

`sudo docker pull awkbr549/opensfm`
# Running OpenSfM on localhost
To expose the Docker container's port 8000 to localhost, run:

`sudo docker run -it --expose 8000 -p 8000:8000 awkbr549/opensfm`

This will start an instance of the awkbr549/opensfm container, and this instance number should show up after root@ in the command line. Save the id after root@ somewhere so when we exit the docker container, we can go back to the exact same version of the container.

To run the reconstruction of an example set of images in `data/berlin`, go to the root of the project `/source/OpenSfM` and run:

`./bin/run_all data/berlin`

Then, run the following command to start the python server:

`python -m SimpleHTTPServer`

To see the 3D reconstruction in your browser, copy and paste the following into your browser's address bar:

`http://localhost:8000/viewer/reconstruction.html#file=/data/berlin/reconstruction.meshed.json`

# Important Operations
### Commits
Remember to always commit any changes you've made to the docker container if you don't want to lose information. This can be done with the following command, where `IMAGE` is the title of the image you want to save these commits to:

`sudo docker commit CONTAINER_ID IMAGE(Ex: awkbr549/opensfm)`
### Returning to a Particular Docker Instance
To see all docker instances, including ones that aren't currently running, type:

`sudo docker ps -a`

To see the list of all your docker images, type:

`sudo docker images`

To enter any particular container, use the following command, replacing BLANK for the docker container ID:

`sudo docker start BLANK(id goes here)`

After starting that docker image, we want to attach to it with:

`sudo docker attach BLANK(same id)`

Now you are running this particular docker image. If for some reason, the terminal looks like it is still loading the image, just press any key to continue.

### Moving files from host computer into docker
To move files from your host computer into docker, type the following command, replacing `HOST_FILE_PATH` with the path to your file on your host computer, `CONTAINER_ID` with your docker container ID, and `PATH_TO_DESTINATION` with the path to your destination inside your docker folder.

In our particular instance, we want to move any images into the `data` folder. Therefore `PATH_TO_DESTINATION` should be `/source/OpenSfM/data/`.

`sudo docker cp HOST_FILE_PATH CONTAINER_ID: PATH_TO_DESTINATION`

### Other
# Potential Errors

for libdc1394 error: Failed to initialize libdc1394, run:

`sudo ln /dev/null /dev/raw1394`


