# mkinitcpio-growrootfs
The package is intended to use for ArchLinux cloud images to detect the size of the underlying block device, resize the root partition to fill it, and then resize the root filesystem.

The mkinitcipio hook and the install files were taken from the GregSutcliffe's repository (https://github.com/GregSutcliffe/aur-projects/tree/master/mkinitcpio-growrootfs) The growpart code is exactly the same as the Ubuntu cloud-guest-utils package but adapted to work with sfdisk 2.26.
sfdisk does not longer provide any functionality for CHS (Cylinder-Head-Sector) addressing. This growpart takes care about the sfdisk 2.26.1 bug: https://bugzilla.redhat.com/show_bug.cgi?id=1211405

# How to use it
Install the package and add growfs to the HOOK list in the ```/etc/mkinitcpio.conf``` file. It must be after the fsck hook. After this create the initial ramdisk environment:
```bash
# mkinitcpio -p linux
```
