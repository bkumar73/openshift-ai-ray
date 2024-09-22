# This repository is deprecated and merged to [AI on OpenShift](https://ai-on-openshift.io) site. 

# Introduction

This repository contains examples for using [Kueue](https://kueue.sigs.k8s.io/) and [Kube Ray](https://docs.ray.io/en/latest/cluster/kubernetes/index.html) on OpenShift AI.

## Important Disclaimer

> IMPORTANT DISCLAIMER: Read before proceed!
> 1. These examples are to showcase the capabilities of OpenShift AI.
> 1. Certain components may not be supported if they are using upstream projects.
> 1. Always check with Red Hat or your account team for supportability. 

## Prerequisite

Ensure there is at least 1 worker node that has a GPU. On AWS, this can be a p3.8xlarge instance, otherwise you can run the makefile target to add a `machineset` for a single replica of p3.8xlarge.

```bash
make add-gpu-machineset
```

Taint the GPU node
```bash
oc adm taint nodes <gpu-node> nvidia.com/gpu=Exists:NoSchedule
```

## Setup
Install OpenShift AI using the OpenShift AI Operator. This install the latest version from the fast channel.

```bash
make install-openshift-ai
```

## Examples

1. [Preemption using priority with quota](yaml/preemption/)
1. [Distributed training with Ray for Stable Diffusion](yaml/distributed/)


