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

### Sample Output
You can list iSCSI LUN inside the pod. But it seems devicePath(/dev/xvda) on pod configuration is ignored.
```
root@pod-with-block-volume:/# lsblk -S
NAME
    HCTL       TYPE VENDOR   MODEL             REV SERIAL TRAN
sda 0:0:0:0    disk VMware   Virtual disk     2.0
sdb 33:0:0:0   disk NETAPP   LUN C-Mode       9141        iscsi
sdc 34:0:0:0   disk NETAPP   LUN C-Mode       9141        iscsi
sr0 3:0:0:0    rom  NECVMWar VMware SATA CD00 1.00        sata
```

