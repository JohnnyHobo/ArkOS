These are floppy disk and CD-ROM images containing ArkOS and accompanying
programs.

You can use 'dd' on Linux or RAWRITE on Windows to write the floppy disk
image to a real floppy. Alternatively, you can burn the .iso to a CD-R and
boot from it in your CD burning utility.

Note that the CD image is generated automatically from the build scripts,
and uses the floppy image as a boot block (a virtual floppy disk).

In Linux/Unix, you can create a new floppy image with this command:

  mkdosfs -C arkos.flp 1440

In Linux/Unix you can mount your floppy image using these commands:
  sudo mkdir /mnt/floppy
  sudo mount -t vfat -o loop arkos.flp /mnt/floppy

From here you will be able to add/remove your own files to the disk.

To unmount use the following command:
  sudo umount /mnt/floppy

To add a new bootloader use the following command:
  dd status=noxfer conv=notrunc if=bootload.bin of=arkos.flp
