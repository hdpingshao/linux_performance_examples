.PHONY: build
build:
	gcc -o app app.c
	docker build -t 192.168.200.120/perf/app:short-process -f Dockerfile .

.PHONY: push
push:
	docker push 192.168.200.120/perf/app:short-process

.PHONY: run
run:
	docker run --name=app -itd 192.168.200.120/perf/app:short-process

.PHONY: clean
clean:
	rm -f app
	docker rm -f app
