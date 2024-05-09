
FROM debian:bookworm-slim

RUN apt-get update
RUN dpkg --add-architecture arm64
RUN apt-get update
RUN apt-get install -y qemu-user-static
RUN apt-get install -y build-essential subversion \
	cmake git python3-dev libncurses5-dev libxml2-dev \
	libedit-dev swig doxygen graphviz xz-utils ninja-build ssh
RUN apt-get install -y crossbuild-essential-arm64 libpython3-dev:arm64 \
	libncurses5-dev:arm64 libxml2-dev:arm64 libedit-dev:arm64

COPY ./inside-docker /entryscript

ENTRYPOINT ["/entryscript"]

# note that I haven't yet accounted for the syncing of shared libraries over from the host machine to this intermediate machine