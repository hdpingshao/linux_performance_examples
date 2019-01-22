.PHONY: build
build:
	gcc -o app app.c
	docker build -t 192.168.200.120/perf/app:iowait -f Dockerfile .
	gcc -o app app-fix1.c
	docker build -t 192.168.200.120/perf/app:iowait-fix1 -f Dockerfile .
	gcc -o app app-fix2.c
	docker build -t 192.168.200.120/perf/app:iowait-fix2 -f Dockerfile .

.PHONY: push
push:
	docker push 192.168.200.120/perf/app:iowait
	docker push 192.168.200.120/perf/app:iowait-fix1
	docker push 192.168.200.120/perf/app:iowait-fix2

.PHONY: run
run:
	docker run --privileged --name=app -itd 192.168.200.120/perf/app:iowait

.PHONY: run-fix1
run-fix1:
	docker run --privileged --name=app -itd 192.168.200.120/perf/app:iowait-fix1

.PHONY: run-fix2
run-fix2:
	docker run --privileged --name=app -itd 192.168.200.120/perf/app:iowait-fix2

.PHONY: clean
clean:
	rm -f app
	docker rm -f app
