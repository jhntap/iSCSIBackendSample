# Kubernetes iSCSI LUN Mounting Samples with NetApp ONTAP
contains a collection of sample configuration files for Kubernetes, which demonstrate how to mount an iSCSI LUN from NetApp ONTAP as **a block device** in a pod. 

### Repository Contents
This repository includes the following sample Kubernetes configuration files:

* sc-iscsi.yaml: A sample StorageClass resource configured to provision storage from a NetApp ONTAP system using the iSCSI protocol.
* iscsi-pvc.yaml: A sample PersistentVolumeClaim (PVC) that requests storage from the defined StorageClass.
* pod-iscsi-block-ubuntu.yaml: A sample pod definition that mounts the provisioned iSCSI LUN as a block device.

### Testing Environment
All samples have been tested with the following environment:

* Trident with Kubernetes Advanced v6.0 (Trident 24.02.0 & Kubernetes 1.29.4) <https://labondemand.netapp.com/node/878>

Please note that while these samples have been tested in a specific environment, they may need to be adjusted for use in other setups.


