.PHONY: run
run:
	docker run --name nginx -p 10000:80 -itd 192.168.200.120/perf/nginx:sp
	docker run --name phpfpm -itd --network container:nginx 192.168.200.120/perf/php-fpm:sp

.PHONY: build
build:
	docker build -t 192.168.200.120/perf/nginx:sp -f Dockerfile.nginx .
	docker build -t 192.168.200.120/perf/php-fpm:sp -f Dockerfile.php-fpm .

.PHONY: push
push:
	docker push 192.168.200.120/perf/nginx:sp
	docker push 192.168.200.120/perf/php-fpm:sp

.PHONY: clean
clean:
	docker rm -f nginx phpfpm
