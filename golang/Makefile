NAME = mtvb/golang

.PHONY: all build shell

all: build

build:
	docker build --quiet -t $(NAME) --rm .

shell: build
	docker run -it --rm --entrypoint /bin/bash $(NAME) --
