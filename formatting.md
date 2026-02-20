# Formatting

Watch your partitions

    lsbk

Select your Drive ( i.e. sdb )

<img width="815" height="191" alt="image" src="https://github.com/user-attachments/assets/654fc477-1f19-46e7-87cf-6be661d42949" />

Wipe your Drive

    sudo pacman -Sy gdisk
    sudo gdisk /dev/sdb

Press x, z, y, y to wipe everything
