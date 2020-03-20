# ONOS Image

## Build

```
# Build ONOS
cd $ONOS_ROOT && bazel build onos

# Extract ONOS tarball to Docker build directory
cd bans-5gc-images/onos
tar -xf $ONOS_ROOT/bazel-bin/onos.tar.gz --strip-components=1

# Build Docker image
docker build -t onos .
```
