DOCKER_CMD := docker
IMG_NAME := ipfs/kubo:latest 
CONTAINER_NAME := ipfs_host
CURRENT_PATH := $(PWD)
PROJECT_PATH := $(CURRENT_PATH)/..

IPFS_STAGING_PATH := $(PROJECT_PATH)/stage
IPFS_DATA_PATH := $(PROJECT_PATH)/data

all: build run

build:
	$(DOCKER_CMD) build -t $(IMG_NAME) .

run:
	$(DOCKER_CMD) run --name $(CONTAINER_NAME) -v $(IPFS_STAGING_PATH):/export -v $(IPFS_DATA_PATH):/data/ipfs -p 4001:4001 -p 4001:4001/udp -p 127.0.0.1:8080:8080 -p 127.0.0.1:5001:5001 $(IMG_NAME)

attach:
	$(DOCKER_CMD) exec -it $(CONTAINER_NAME) /bin/bash

start:
	$(DOCKER_CMD) start $(CONTAINER_NAME)

stop:
	$(DOCKER_CMD) stop $(CONTAINER_NAME)

monitor:
	$(DOCKER_CMD) logs -f $(CONTAINER_NAME)

.PHONY: clean

clean: stop clear

clear:
	$(DOCKER_CMD) rm $(CONTAINER_NAME)
	$(DOCKER_CMD) rmi $(IMG_NAME)