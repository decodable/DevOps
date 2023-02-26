FROM ubuntu:22.04
RUN apt-get update && apt-get install -q -y \
      build-essential cmake \
      gdb strace \
      valgrind cppcheck \
      git \
      && rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -q -y \
      libgtest-dev \
      libboost-all-dev \
      python-is-python3 \
      && rm -rf /var/lib/apt/lists/*

ARG GTEST_DIR=/usr/src/googletest

WORKDIR $GTEST_DIR
WORKDIR build
RUN cmake -DBUILD_SHARED_LIBS=ON $GTEST_DIR && make && make install \
      && rm -rf * && apt-get remove -y libgtest-dev

CMD ["bash"]
