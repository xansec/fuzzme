FROM debian:buster-slim as builder
RUN apt-get update && \
    apt-get install -y gcc-powerpc-linux-gnu make libc6-dbg && \
    rm -rf /var/lib/apt/lists/*
COPY src/fuzzme.c .
RUN powerpc-linux-gnu-gcc -o fuzzme -Wno-div-by-zero -fno-stack-protector -zexecstack -no-pie fuzzme.c

# Set to fuzz!
ENTRYPOINT []
CMD /fuzzme @@
