# mkinitcpio-growrootfs
The package is intended to use for ArchLinux cloud images to detect the size of the underlying block device, resize the root partition to fill it, and then resize the root filesystem.

It was taken from the GregSutcliffe's repository (https://github.com/GregSutcliffe/aur-projects/tree/master/mkinitcpio-growrootfs) and modified to work with the last version of sfdisk from util-linux. The growpart code is exactly the same as the Ubuntu cloud-guest-utils package but adapted to the new version and buggy of sfdisk from util-linux 2.26.1 (https://bugzilla.redhat.com/show_bug.cgi?id=1211405)
