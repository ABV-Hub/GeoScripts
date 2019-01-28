# Install
1. Ensure Docker is installed on machine
1. Ensure you can use make files on machine

# How to run

## Jupyter
1. `make notebook` This will launch a notebook server on port `localhost:8889` which can be accessed through a web browser
1. Navigate to the frames folder and upload images
1. run convert.ipynb

## Command Line Interfaces

### Run script
This script runs FFmpeg in the current directory on files with format `frame%05d.png` and produces an mp4 out called `video.mp4` the framerate is set to 30 fps and resolution to 1920 x 1080

### How to run
1. Copy images into current directory with format frame%d05.png (can be changed in run.sh)
1. `make video`

# Container contents 
Based of from alpine 3.7 for the linux kernel for the size (5mb)

Install ffmpeg program

Runs run.sh as entrypoint
