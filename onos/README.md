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

## Tags

The tags are differentiated with burst size settings in bandwidth management application.

### latest

Burst size of flow is set to maximum port speed of P4 switches.

### bans5gc

The `bans5gc` tag is customized for BANS-5GC implementation. Burst size of flow is determined with the burst when RANSIM sends uninterrupted ICMP packets, which is around 2 Mbits in 100 ms.
