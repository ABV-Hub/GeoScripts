# How to run
1. Ensure Docker is installed on machine
1. Ensure you can use make files on machine
1. Copy images into current directory with format frame%d05.png (can be changed in run.sh)
1. `make video`

# Container contents 
Based of from alpine 3.7 for the linux kernel for the size (5mb)

Install ffmpeg program

Runs run.sh as entrypoint

# Run script
This script runs FFmpeg in the current directory on files with format `frame%05d.png` and produces an mp4 out called `video.mp4` the framerate is set to 30 fps and resolution to 1920 x 1080
