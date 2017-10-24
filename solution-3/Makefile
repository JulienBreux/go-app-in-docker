CWD := $(shell dirname $(realpath $(lastword $(MAKEFILE_LIST))))

build :
	docker build --no-cache --rm -t temp/solution:3-builder -f Dockerfile-builder .
	docker run -v ${CWD}:/go/src/github.com/JulienBreux/go-program-in-docker \
			   -v ${CWD}:/output temp/solution:3-builder
	docker build --no-cache --rm -t temp/solution:3 .
