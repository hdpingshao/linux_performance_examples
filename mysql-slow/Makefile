DATA_NUM ?= 10000

.PHONY: run
run: mysql dataservice
	docker run --name=app --network=container:mysql -itd 192.168.200.120/perf/mysql-slow

.PHONY: dataservice
dataservice:
	docker run --name=dataservice -itd --privileged 192.168.200.120/perf/mysql-dataservice


.PHONY: mysql
mysql:
	docker run --name=mysql -itd -p 10000:80 -m 800m 192.168.200.120/perf/mysql:5.6


.PHONY: init
init:
	docker exec -i mysql mysql -uroot -P3306 < tables.sql
	curl http://127.0.0.1:10000/db/insert/products/$(DATA_NUM)


.PHONY: build
build:
	docker build -t 192.168.200.120/perf/mysql-slow -f Dockerfile .
	docker build -t 192.168.200.120/perf/mysql:5.6 -f Dockerfile.mysql .
	docker build -t 192.168.200.120/perf/mysql-dataservice -f Dockerfile.dataservice .


.PHONY: test
test:
	curl http://127.0.0.1:10000/products/geektime


.PHONY: push
push:
	docker push 192.168.200.120/perf/mysql-slow
	docker push 192.168.200.120/perf/mysql:5.6
	docker push 192.168.200.120/perf/mysql-dataservice


.PHONY: clean
clean:
	docker rm -f app mysql dataservice
