APP=ffmpeg

.PHONY: py-clean build video jupyter

py-clean:
	find . | grep -E "(__pycache__|\.pyc|\.pyo|.egg-info)" | xargs rm -rf

build:
	docker build -t $(APP):latest -f Dockerfile .

build-jupyter:
	docker build -t $(APP)-jupyter:latest -f Dockerfile_jupyter_ui .

video: build
	docker run --mount source=`pwd`,target=/tmp,type=bind -it --rm --name $(APP) $(APP):latest

jupyter: build-jupyter
	docker run -it --rm \
		-p 8889:5555 \
		--name $(APP)-jupyter \
		$(APP)-jupyter:latest \
	jupyter notebook --ip=0.0.0.0 --port=5555 \
         --allow-root \
         --NotebookApp.password='' --NotebookApp.token='' \
         --NotebookApp.open_browser=False

	


