ORG=seequent
APP=ffmpeg

.PHONY: build-baseimage build-notebook build-codegen build-slate build-dev \
	build-tests build \
	run deploy notebook codegen tests dev-tests functions \
	docs-resources docs-json docs-slate docs watch-codegen \
	lint-functions lint-cors lint-codebase-yapf lint-codebase-pylint \
	lint-codebase lint

py-clean:
	find . | grep -E "(__pycache__|\.pyc|\.pyo|.egg-info)" | xargs rm -rf

build:
	docker build -t $(ORG)/$(APP):latest -f Dockerfile .

notebook: build
	docker run -it --rm \
		--name=$(APP)-notebook \
		-p 127.0.0.1:8888:8888 \
		-h $(shell hostname) \
		$(ORG)/$(APP):notebook

video: build
	docker run --mount source=`pwd`,target=/tmp,type=bind -it --rm --name ffmpeg $(ORG)/$(APP):latest
