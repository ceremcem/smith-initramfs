# smith-initramfs
Rescue system right in the initramfs

## Roadmap

- [x] Add SSH support (see [unlock-luks-partition](https://github.com/ceremcem/unlock-luks-partition))
- [ ] Include BTRFS progs for rescue purposes
- [ ] Change cryptroot UUID at initramfs stage either temporarily or permanently 
- [ ] Select another GRUB option temporarily 
    * Place a file to indicate the option 
    * Make GRUB select the option at boot time 
    * Delete this file in order to be able to boot from last good option if anything goes wrong with the new option 
    * Mark that selection permanent if everything goes well.

## How 

Use Slitaz strategy (or even Slitaz itself):

1. Create a minimal initramfs to boot. 
2. Create another initramfs image and open that image on top of current one. (like async dependency). 
