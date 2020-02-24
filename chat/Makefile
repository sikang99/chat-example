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
	vi client/client.go

edit-server es:
	vi server/server.go
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
	cd client; ./client

run-server rs:
	cd server; ./server
##--------------------------------------------------------------
clean:
	rm -f client server
##--------------------------------------------------------------
git update gu:
	cd ..; make gu
