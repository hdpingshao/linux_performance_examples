DATA_NUM ?= 5000

.PHONY: run
run: redis
	docker run --name=app --network=container:redis -itd 192.168.200.120/perf/redis-app

.PHONY: redis
redis:
	docker run --name=redis -itd -p 10000:80 192.168.200.120/perf/redis-server


.PHONY: build
build:
	docker build -t 192.168.200.120/perf/redis-app -f Dockerfile .
	docker build -t 192.168.200.120/perf/redis-server -f Dockerfile.redis .


.PHONY: init
init:
	curl http://127.0.0.1:10000/init/$(DATA_NUM)


.PHONY: push
push:
	docker push 192.168.200.120/perf/redis-app
	docker push 192.168.200.120/perf/redis-server

.PHONY: clean
clean:
	docker rm -f app redis
