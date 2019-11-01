FROM ubuntu:latest

ENV BOOST_VERSION=1.70.0
ENV BOOST_VERSION_=1_70_0
ENV BOOST_LIB=/usr/local/lib/boost

RUN apt-get -y update \
    && apt-get install -y --reinstall -y make \
    && apt-get -qq update && apt-get install -q -y software-properties-common \
    && add-apt-repository ppa:ubuntu-toolchain-r/test -y \
    && apt-get -qq update && apt-get install -qy g++ gcc git wget emacs

RUN wget --max-redirect 3 https://dl.bintray.com/boostorg/release/${BOOST_VERSION}/source/boost_${BOOST_VERSION_}.tar.gz

RUN mkdir -p ${BOOST_LIB} \
    && tar zxf boost_${BOOST_VERSION_}.tar.gz -C ${BOOST_LIB} --strip-components=1 \
    && cd ${BOOST_LIB} \
    && ./bootstrap.sh --prefix=/usr/local --with-libraries=program_options \
    && ./b2 install

ENTRYPOINT /bin/bash