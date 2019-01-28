.PHONY: build
build:
	gcc -o app app.c
	docker build -t 192.168.200.120/perf/app:io-direct -f Dockerfile .
	gcc -o app app-cached.c
	docker build -t 192.168.200.120/perf/app:io-cached -f Dockerfile .

.PHONY: push
push:
	docker push 192.168.200.120/perf/app:io-direct
	docker push 192.168.200.120/perf/app:io-cached

.PHONY: run
run:
	docker run --privileged --name=app -itd 192.168.200.120/perf/app:io-direct

.PHONY: clean
clean:
	rm -f app
	docker rm -f app
