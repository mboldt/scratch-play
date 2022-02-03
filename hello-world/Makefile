.PHONY: run
run: container
	docker run --rm hello-world-scratch

.PHONY: container
container: hello-world
	docker build -t hello-world-scratch .

hello-world: main.go
	GOOS=linux GOARCH=amd64 go build

.PHONY: clean
clean:
	rm -f hello-world
	docker image rm hello-world-scratch || true
