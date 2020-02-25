#
# Makefile for chat
#
PROG=websockets
usage:
	@echo "usage: make [edit|buil|run|open]"

edit e:
	vi $(PROG).go

build b:
	go build -o $(PROG)

run r:
	go run --race $(PROG).go

clean:
	rm -f $(PROG)

open o:
	open http://localhost:4000/

git-update gu:
	cd ../..; make gu

