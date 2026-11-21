# lastbackend

Containerized applications need a consistent way to move from an image to a running service, then manage nodes, networking, and scaling from one place. lastbackend provides the platform components needed to deploy and operate those workloads across a cluster.

## Features

- Expose a REST API for cluster, node, service, and volume management.
- Schedule container workloads across available nodes.
- Discover services and balance pod traffic with IPVS-based internal endpoints.
- Connect containers across nodes with a VXLAN overlay network.
- Route incoming traffic through an HAProxy-based ingress server.

## Installation

Build lastbackend from source with Go:

```sh
git clone https://github.com/lastbackend/lastbackend.git
cd lastbackend
go build -o lastbackend .
```

The resulting `lastbackend` binary is created in the repository root. The project also includes runtime interfaces for container, image, storage, network, and proxy implementations.

## Usage

Run the command with `--help` to view the options supported by the build:

```sh
./lastbackend --help
```

The REST API is the main interface for managing a cluster. It can be used directly with `curl`, from a client application, or through a compatible Last.Backend CLI.

## License

lastbackend is licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).

This project is based on [lastbackend/lastbackend](https://github.com/lastbackend/lastbackend), which is also distributed under Apache-2.0. See the repository's license and attribution files when redistributing or modifying the code.
