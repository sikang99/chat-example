
#
# Makefile for building janus-gateway docker image
#
ORG=cojam
NAME=niltalk
VERSION=0.0.0
DIST=alpine-3.10
BASE=$(ORG)/$(NAME)
BUILD=$(VERSION).1
IMAGE=$(BASE):$(BUILD)-$(DIST)
COMPOSE=docker-compose.yml
IPADDR=localhost
.PHONY: usage set bak
# -------------------------------------------------------------------------------
usage:
	@echo "usage: make [docker|compose|open] for [33m$(IMAGE)[0m"
# -------------------------------------------------------------------------------
edit e:
	@echo "> make (edit) [entry|make]"

edit-entry ee:
	vi entrypoint.sh
edit-make em:
	vi dist/alpine/Makefile.root

edit-config ec:
	@echo "> make (edit-config) [redis|niltalk|caddy]"
ecr:
	vi conf/redis/redis.conf
ecn:
	vi conf/niltalk/config.json
ecc:
	vi conf/caddy/Caddyfile

bak:
	cp Dockerfile bak/Dockerfile.$(BUILD)-$(DIST)
	cp $(COMPOSE) bak/compose.$(BUILD)-$(DIST)
recover:
	cp bak/Dockerfile.$(BUILD)-$(DIST) Dockerfile

build b:
	cd src && go build -o $(NAME) *.go
run r:
	cd src && ./$(NAME)
clean:
	rm -f src/$(NAME)

logs l:
	tail -f log/redis/* log/niltalk/* log/caddy/*
# -------------------------------------------------------------------------------
docker d:
	@echo "> make (docker) [edit|build|run|exec:x|ps|kill|push:u|clean]"

docker-edit de:
	vi Dockerfile

docker-build db:
	docker build -t $(IMAGE) .

docker-push du:
	docker push $(IMAGE)

docker-run dr:
	docker run -d \
		-v $(PWD)/cert:/etc/ssl/cert \
		-v $(PWD)/log/$(NAME):/var/log/$(NAME) \
		--name $(NAME) $(IMAGE)

docker-run-base drb:
	docker run -d \
		-v $(PWD)/log/$(NAME):/var/log/$(NAME) \
		--name $(NAME) $(IMAGE)

docker-restart-exec drx:
	-make docker-kill
	-make docker-clean
	-make docker-run
	-make docker-exec

docker-exec dx:
	docker exec -it $(NAME) /bin/bash

docker-kill dk:
	docker stop $(NAME) && docker rm $(NAME)

docker-ps dp:
	docker ps -a

docker-logs dl:
	docker logs $(NAME)

#	docker container rm $(docker container ls -aq)
docker-clean dc:
	rm -rf log/redis/* log/niltalk/* log/caddy/*

docker-clobber clobber:
	docker container prune --force
	docker network prune --force
	docker system prune --force

docker-images di:
	docker images $(BASE)
# -------------------------------------------------------------------------------
compose c:
	@echo "> make (compose) [up|down|ps]"

compose-up cu cr:
	docker-compose -f $(COMPOSE) up -d

compose-down cd ck:
	docker-compose -f $(COMPOSE) down

compose-ps cp:
	docker-compose -f $(COMPOSE) ps

compose-logs cl:
	docker-compose -f $(COMPOSE) logs -f

compose-restart cx:
	docker-compose -f $(COMPOSE) restart

compose-restart-niltalk crn:
	docker-compose -f $(COMPOSE) restart niltalk
# -------------------------------------------------------------------------------
DOMAIN=chat.cojam
cert-copy cc:
	@echo "> make (cert-copy) [local|public]"

cert-install-local cil:
	brew install mkcert

cert-copy-local ccl:
	mkcert -install
	mkcert localhost 127.0.0.1
	mv localhost+1.pem cert/cert.pem
	mv localhost+1-key.pem cert/key.pem
	ls -al cert/

cert-install-public cip:
	sudo apt-get install -y certbot
	sudo certbot --standalone -d ${DOMAIN} certonly

cert-copy-public ccp:
	sudo cp /etc/letsencrypt/live/$(DOMAIN)/cert.pem cert/cert.pem
	sudo cp /etc/letsencrypt/live/$(DOMAIN)/privkey.pem cert/key.pem	

cery-copy-renew ccr:
	sudo certbot renew --dry-run

cert-check:
	openssl s_client -showcerts -connect $(DOMAIN):4439
# -------------------------------------------------------------------------------
tcpproxy:
	tcpproxy -lcert cert/cert.pem  -lkey cert/key.pem -lhost :4009 -rhost :4008

redis-check rc:
	@echo "> make (redis-check) [local|chat]"
redis-check-local rcl:
	redis-cli -u redis://127.0.0.1:6379 ping
redis-check-chat rcc:
	redis-cli -u redis://chat.cojam.shop:6379 ping

open o:
	@echo "> make (open) [web]"

open-web ow:
	open https://$(IPADDR):4009
	open http://$(IPADDR):4008
# -------------------------------------------------------------------------------
git-update gu:
	cd ..; make gu
