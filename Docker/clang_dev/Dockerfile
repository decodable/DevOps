FROM codible/ubuntu_cpp_dev:1.0

ARG LLVM_SRC_ROOT=/usr/src/clang-llvm

# get llvm
WORKDIR $LLVM_SRC_ROOT
RUN git clone http://llvm.org/git/llvm.git

# get clang
WORKDIR $LLVM_SRC_ROOT
WORKDIR llvm/tools
RUN git clone http://llvm.org/git/clang.git \
      && cd clang/tools \
      && git clone http://llvm.org/git/clang-tools-extra.git extra

# get ninja
WORKDIR $LLVM_SRC_ROOT
RUN git clone https://github.com/martine/ninja.git \
      && cd ninja \
      && git checkout release \
      && ./bootstrap.py \
      && cp ninja /usr/bin/

# build clang
WORKDIR $LLVM_SRC_ROOT
WORKDIR build
RUN cmake -G Ninja -DLLVM_USE_LINKER=gold -DCMAKE_BUILD_TYPE=Release ../llvm \ 
      && ninja \
      && ninja install

CMD ["bash"]
