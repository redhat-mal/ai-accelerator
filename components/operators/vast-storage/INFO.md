# VAST CSI Driver Overview
VAST CSI Driver allows container orchestration frameworks such as Kubernetes to dynamically provision storage volumes on a VAST cluster.
VAST provides scalable, reliable, and fast persistent storage that can be accessed remotely by any Kubernetes application container.
With dynamic provisioning, you do not need to create container-specific persistent volumes. Instead, you deploy the following elements that
allow for dynamic volume provisioning:
• A storage class, which is a YAML class definition that specifies a dynamic provisioner and volume-related options.
• A dynamic provisioner.
When an application makes a Persistent Volume Claim (PVC), the Kubernetes framework employs the dynamic provisioner to dynamically
create a persistent volume. Later, when a container (via its YAML) references a PVC, Kubernetes provides the volume to the container. For
more information about VAST and Kubernetes interaction, see A Deeper Dive into VAST CSI (page 8).