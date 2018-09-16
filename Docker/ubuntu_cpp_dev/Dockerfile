FROM ubuntu:18.04
RUN apt-get update && apt-get install -q -y \
      build-essential cmake \
      gdb strace \
      libgtest-dev valgrind cppcheck \
      git \
      && rm -rf /var/lib/apt/lists/*

ENV GTEST_DIR=/usr/src/googletest
ENV GTEST_BUILD_DIR=$GTEST_DIR/build
RUN mkdir -p $GTEST_BUILD_DIR \
      && cd $GTEST_BUILD_DIR \
      && cmake -DBUILD_SHARED_LIBS=ON $GTEST_DIR && make && make install \
      && cd / && rm -rf $GTEST_BUILD_DIR && apt-get remove -y libgtest-dev

CMD ["bash"]
