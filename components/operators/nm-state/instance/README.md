# OpenShift NM State Operator

Installs a NM State Operator Config instance.

## Prerequisites

First, install the [OpenShift NM State Operator](../operator) in your cluster.

Do not use the `base` directory directly, as you will need to patch the `channel` based on the version of OpenShift you are using, or the version of the operator you want to use.

## Overlays

The options for this operator are the following *overlays*:
* [default](overlays/default)

### Default

[default](overlays/default) configures a basic default configuration for the nm state instance.  For more details on customizing the NM State configs, refer to the [docs](https://docs.redhat.com/en/documentation/openshift_container_platform/4.17/html/networking/kubernetes-nmstate.)

## Usage

If you have cloned the `gitops-catalog` repository, you can install the operator by running from the root `gitops-catalog` directory

```
oc apply -k nm-state/instance/overlays/default
```

Or, without cloning:

```
oc apply -k https://github.com/redhat-cop/gitops-catalog/tree/main/nmstate/overlays/default
```

As part of a different overlay in your own GitOps repo:

```
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
  - github.com/redhat-cop/gitops-catalog/tree/main/nmstate/overlays/default?ref=main
```
