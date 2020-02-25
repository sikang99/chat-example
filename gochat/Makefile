#
# Makefile for chat in go
#
##--------------------------------------------------------------
usage:
	@echo "usage: make [edit|build|run|clean]"
##--------------------------------------------------------------
edit e:
	@echo "> make (edit) [client|server]"

edit-client ec:
	vi client/main.go

edit-server es:
	vi server/main.go
##--------------------------------------------------------------
build b:
	@echo "> make (build) [client|server|all]"

build-all ba:
	@make build-client
	@make build-server

build-client bc:
	cd client; go build -o client

build-server bs:
	cd server; go build -o server
##--------------------------------------------------------------
run r:
	@echo "> make (run) [client|server]"

run-client rc:
	client/client

run-server rs:
	server/server
##--------------------------------------------------------------
clean:
	rm -f client server

open-web ow:
	open https://localhost:9200
##--------------------------------------------------------------
DOMAIN=cojam.tv
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

cert-copy-public ccp:
	sudo cp /etc/letsencrypt/live/$(DOMAIN)/cert.pem cert/cert.pem
	sudo cp /etc/letsencrypt/live/$(DOMAIN)/privkey.pem cert/key.pem
	sudo certbot renew --dry-run

cert-check:
	openssl s_client -showcerts -connect $(DOMAIN):4439
##--------------------------------------------------------------
src-search ss:
	hub-search --lang=go "chat"

git update gu:
	cd ..; make gu
##--------------------------------------------------------------