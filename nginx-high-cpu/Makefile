.PHONY: run
run:
	docker run --name nginx -p 10000:80 -itd 192.168.200.120/perf/nginx:cpu
	docker run --name phpfpm -itd --network container:nginx 192.168.200.120/perf/php-fpm:cpu

.PHONY: build
build:
	docker build -t 192.168.200.120/perf/nginx:cpu -f Dockerfile.nginx .
	docker build -t 192.168.200.120/perf/php-fpm:cpu -f Dockerfile.php-fpm .

.PHONY: push
push:
	docker push 192.168.200.120/perf/nginx:cpu
	docker push 192.168.200.120/perf/php-fpm:cpu

.PHONY: clean
clean:
	docker rm -f nginx phpfpm
