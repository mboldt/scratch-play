.PHONY: run
run: container
	docker run -it --rm bash-scratch

.PHONY: container
container: bash-static
	docker build -t bash-scratch .

bash-static:
	curl ftp://ftp.us.debian.org/debian/pool/main/b/bash/bash-static_5.1-2+b3_amd64.deb | tar -xzO data.tar.xz | tar -xz --strip-components 2 ./bin/bash-static

.PHONY: clean
clean:
	rm -f bash-static
	docker image rm bash-scratch || true
