export tag=v1.0
root:
	export ROOT=github.com/uucads

build:
	echo "building httpserver binary"
	mkdir -p bin/amd64
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o bin/amd64 .

release: build
	echo "building httpserver container"
	docker build -t uucad/httpserver:${tag} .

push: release
	echo "pushing uucad/httpserver"
	docker push uucad/httpserver:${tag}
pull:
	sudo docker pull uucad/httpserver:${tag}
run:
	sudo docker run uucad/httpserver:${tag}
