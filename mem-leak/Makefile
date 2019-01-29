.PHONY: build
build:
	gcc -o app app.c -pthread
	docker build -t 192.168.200.120/perf/app:mem-leak -f Dockerfile .
	gcc -o app app-fix.c -pthread
	docker build -t 192.168.200.120/perf/app:mem-leak-fix -f Dockerfile .

.PHONY: push
push:
	docker push 192.168.200.120/perf/app:mem-leak
	docker push 192.168.200.120/perf/app:mem-leak-fix

.PHONY: run
run:
	docker run --name=app -itd 192.168.200.120/perf/app:mem-leak

.PHONY: clean
clean:
	rm -f app
	docker rm -f app
