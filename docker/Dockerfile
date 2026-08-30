FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update \
    && apt install -y \
	build-essential \
	cmake \
	gcc-arm-none-eabi \
	libnewlib-arm-none-eabi \
	libstdc++-arm-none-eabi-newlib \
	git \
	python3 \
	&& rm -rf /var/lib/apt/lists/*

WORKDIR /workspace
