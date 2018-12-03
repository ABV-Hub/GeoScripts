APP=ffmpeg

.PHONY: py-clean build video

py-clean:
	find . | grep -E "(__pycache__|\.pyc|\.pyo|.egg-info)" | xargs rm -rf

build:
	docker build -t $(APP):latest -f Dockerfile .

video: build
	docker run --mount source=`pwd`,target=/tmp,type=bind -it --rm --name ffmpeg $(APP):latest
