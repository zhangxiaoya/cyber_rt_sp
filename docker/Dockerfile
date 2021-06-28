FROM nvidia/cuda:10.0-devel-ubuntu18.04

# Tsinghua sources
RUN sed -i 's/archive.ubuntu.com/mirrors.tuna.tsinghua.edu.cn/g' /etc/apt/sources.list \
    && apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654 \
    && rm /etc/apt/sources.list.d/cuda.list \
    && apt-get update
ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Shanghai

# apt-get install
RUN apt-get update \
    && apt-get install -y wget \
    && apt-get install -y cmake \
    && apt-get install -y apt-utils \
    && apt-get install -y libglib2.0-0 \
    && apt-get install -y vim \
    && apt-get install -y autoconf automake libtool curl make g++ unzip \
    && apt-get install -y python-dev python3-dev \
    && apt-get install -y uuid-dev \
    && apt-get install -y pkg-config \
    && apt-get install -y libpoco-dev \
    && apt-get install -y libpocofoundation50 \
    && apt-get install -y libasio-dev libtinyxml2-dev libncurses5-dev libgflags-dev locate libatomic1 libboost-atomic-dev libboost-atomic1.65-dev libboost-atomic1.65.1 libgflags-dev
