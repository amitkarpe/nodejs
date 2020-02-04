export version=v7

all: build run test

build:
	echo $${version}
	docker build --force-rm=true -t expressjs\:$${version} .

run:
	docker stop  expressjs | true
	@echo ""
	docker run --rm --name expressjs -d -p 8080\:8080 expressjs\:$${version}

test:
	@sleep 2
	@echo ""
	@curl http://0.0.0.0:8080
