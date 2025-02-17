## Building and Pushing the Docker Image

Run the following to build the `fuzzme/cpp-honggfuzz-gcc` Docker image and push it to a specified Docker registry.

```sh
docker build -t $DOCKER_REGISTRY/fuzzme/cpp-honggfuzz-gcc .
docker push $DOCKER_REGISTRY/fuzzme/cpp-honggfuzz-gcc
```

## Executing the Mayhem Run

Then initiate a Mayhem run using a Mayhemfile similar to the following:

```yaml
version: '1.13'
baseimage: $MAYHEM_DOCKER_REGISTRY/fuzzme/cpp-honggfuzz-gcc:latest
duration: 90
project: fuzzme
target: cpp-honggfuzz-gcc
cmds:
  - cmd: /fuzzme
    honggfuzz: true
```