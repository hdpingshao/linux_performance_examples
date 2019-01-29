.PHONY: run
run:
	docker run -v /tmp:/tmp --name=app -itd 192.168.200.120/perf/logapp


.PHONY: build
build:
	docker build -t 192.168.200.120/perf/logapp -f Dockerfile .


.PHONY: push
push:
	docker push 192.168.200.120/perf/logapp


.PHONY: clean
clean:
	docker rm -f app
