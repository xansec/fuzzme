FROM debian:buster-slim as builder
RUN apt-get update && \
    apt-get install -y ocaml
COPY src/fuzzme.ml .
RUN ocamlopt fuzzme.ml -o /fuzzme 

# Set to fuzz!
ENTRYPOINT []
CMD /fuzzme @@
