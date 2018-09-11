FROM ubuntu:18.04
RUN apt-get update && apt-get install -y build-essential gdb strace cmake libgtest-dev

ENV GTEST_DIR=/usr/src/gtest
ENV GTEST_BUILD_DIR=$GTEST_DIR/build
RUN mkdir -p $GTEST_BUILD_DIR \
      && cd $GTEST_BUILD_DIR \
      && cmake $GTEST_DIR && make && make install \
      && cd / && rm -rf $GTEST_BUILD_DIR && apt-get remove -y libgtest-dev

CMD ["bash"]
