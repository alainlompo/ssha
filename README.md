# ssha
ssha (super simple hello api)

## Release Milestones

### V0 (1 day)
- [ ] Onboarding Documentation
- [ ] Simple API
- [ ] Unit tests
- [ ] Running on server

### V1 (? days)
- [ ] Replace existing service

## Dependencies

- Go version 1.17

## Setup

Development expects to run in a Unix-like system. If you are running Windows please consider following these [directions](https://ubuntu.com/tutorials/ubuntu-on-windows#1-overview).

### Install Go

NOTE: MacOS is not supported by this Makefile yet.

`sudo make install-go && make init-go`

### Upgrade Go

NOTE: MacOS is not supported by this Makefile yet.

`sudo make install-go`

GO_VERSION :=1.17

.PHONY: install-go init-go

setup: install-go init-go

#TODO add MacOS support
install-go:
	wget "https://golang.org/dl/go$(GO_VERSION).linux-amd64.tar.gz"
	sudo tar -C /usr/local -xzf go$(GO_VERSION).linux-amd64.tar.gz
	rm go$(GO_VERSION).linux-amd64.tar.gz

init-go:
	echo 'export PATH=$$PATH:/usr/local/go/bin' >> $${HOME}/.bashrc
	echo 'export PATH=$$PATH:$${HOME}/go/bin' >> $${HOME}/.bashrc

