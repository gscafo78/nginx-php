.PHONY: help
help:
	@echo ""
	@echo "Usage: make COMMAND"
	@echo ""
	@echo "Docker Nginx image makefile"
	@echo ""
	@echo "Commands:"
	@echo "  build        Build and tag image"
	@echo "  push         Push tagged image to registry"
	@echo "  run          Start container in the background with locally mounted volume"
	@echo "  stop         Stop and remove container running in the background"
	@echo "  delete       Delete all built image versions"
	@echo ""

IMAGE=nginx-php
TAG=latest
REGISTRY=4ss078

.PHONY: build
build:
	@docker build -t ${REGISTRY}/${IMAGE}:${TAG} .

.PHONY: push
push:
	@docker push ${REGISTRY}/${IMAGE}:${TAG}

.PHONY: run
run: build
	docker run -it \
	           --name ${IMAGE} \
	           --rm \
	           -p 80:80 \
	           ${REGISTRY}/${IMAGE}:${TAG}

.PHONY: stop
stop:
	@docker stop ${IMAGE}

.PHONY: delete
delete:
	@docker image ls | grep ${IMAGE} | awk '{print $$3}' | xargs -I + docker rmi +
