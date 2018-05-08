# Private IOTA Network in Kubernetes

## Setting up an environment

1. Change the `deployment.config.yaml` as needed
2. Run the script `sudo ruby kubernetesiota` to generate the `deployment.yaml` file
3. Run the deployment on Kubernetes `kubectl apply -f deployment.yaml`
4. Create a milestone using the coordinator from [private-iota-testnet](https://github.com/schierlm/private-iota-testnet) tools

The deployment runs an [iota-connector](https://github.com/Strydom/iota-connector).
A Python script that runs on the cluster, listening for Kubernetes events, adding the nodes as neighbours
when the Pod IP's and eventually the Ports become available.

This deployment uses a [pre-built docker image](https://hub.docker.com/r/retrolatch/private-iri/)
from the instructions found at the [private-iota-testnet](https://github.com/schierlm/private-iota-testnet) repository.
The [Snapshot.txt](kubernetes-private-iota/Snapshot.txt) used with the preallocated addresses can be found in this directory.

## Tools

- [IOTA Peer Manager](https://github.com/akashgoswami/ipm)