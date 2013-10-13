# Build template with Packer

This is an example to build templates in Virtualbox for sysbuilder with Packer.

Run the following to get going:

    packer build packer.json

The image should be converted to qcow:

    tar -xvf ubuntu1204.ova # Extract .ova
    qemu-img convert -O qcow ubuntu1204-disk1.vmdk template.qcow # Convert to .qcow

## The image

The image is an Ubuntu 12.04 with some specifics in `/etc/rc.local`. As sysbuilder removes
the SSH keys, the script in rc.local will create them again.
