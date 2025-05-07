# OpenShift SR-IOV Operator

Installs a SR Operator Config instance.

## Prerequisites

First, install the [OpenShift SR-IOV Operator](../operator) in your cluster.

Do not use the `base` directory directly, as you will need to patch the `channel` based on the version of OpenShift you are using, or the version of the operator you want to use.

## Overlays

The options for this operator are the following *overlays*:
* [default](overlays/default)

### Default

[default](overlays/default) configures a basic default configuration for the sr-iov instance.  For more details on customizing the SR-IOV workers, refer to the [docs](https://docs.redhat.com/en/documentation/openshift_container_platform/4.17/html/networking/hardware-networks#about-sriov).

## Usage

If you have cloned the `gitops-catalog` repository, you can install the operator by running from the root `gitops-catalog` directory

```
oc apply -k sr-iov/instance/overlays/default
```

Or, without cloning:

```
oc apply -k https://github.com/redhat-cop/gitops-catalog/tree/main/openshift-sriov-network-operator/overlays/default
```

As part of a different overlay in your own GitOps repo:

```
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
  - github.com/redhat-cop/gitops-catalog/tree/main/openshift-sriov-network-operator/overlays/default?ref=main
```
