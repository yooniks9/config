## Create cloud template for proxmox

Ref: https://pve.proxmox.com/wiki/Cloud-Init_Support

### SOP

```
# wget https://cloud-images.ubuntu.com/bionic/current/bionic-server-cloudimg-amd64.img

# qm create 9002 --memory 2048 --net0 virtio,bridge=vmbr0

# qm importdisk 9002 bionic-server-cloudimg-amd64.img ssd0

# qm set 9002 --scsihw virtio-scsi-pci --scsi0 ssd0:9002/vm-9002-disk-0.raw

# qm set 9002 --boot c --bootdisk scsi0

# qm set 9002 --serial0 socket --vga serial0

# qm set 9002 --ide2 ssd0:cloudinit
```

