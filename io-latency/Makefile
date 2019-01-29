.PHONY: run
run:
	docker run --name=app -p 10000:80 -itd 192.168.200.120/perf/word-pop


.PHONY: build
build:
	docker build -t 192.168.200.120/perf/word-pop -f Dockerfile .


.PHONY: push
push:
	docker push 192.168.200.120/perf/word-pop


.PHONY: clean
clean:
	docker rm -f app
