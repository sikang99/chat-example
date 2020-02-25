#
# Makefile for chat
#
PROG=websockets
usage:
	@echo "usage: make [edit|buil|run]"

edit e:
	vi $(PROG).go

build b:
	go build -o $(PROG)

run r:
	go run --race $(PROG).go

clean:
	rm -f $(PROG)


git-update gu:
	cd ..; make gu

