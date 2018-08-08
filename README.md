# smith-initramfs
Rescue system right in the initramfs, intended to use on servers.

## Target System 

Debian +9

## Roadmap

- [x] Add SSH support (see [unlock-luks-partition](https://github.com/ceremcem/unlock-luks-partition))
- [ ] Include BTRFS progs for rescue purposes
- [ ] Change cryptroot UUID at initramfs stage either temporarily or permanently 
- [ ] Select another GRUB option safely: 
    * Place a file to indicate the desired GRUB option number. 
    * Make GRUB select the option at boot time 
    * Delete this file within GRUB in order to be able to boot from last good option with a simple reboot if anything goes wrong with the new option 
    * Mark that selection permanent if everything goes well.
- [ ] Create a hook to make updates with `update-initramfs -u`

## How 

Use Slitaz strategy (or even Slitaz itself):

1. Create a minimal initramfs to boot. 
2. Create another initramfs image and open that image on top of current one. (like async dependency). 
