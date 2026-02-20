# Formatting

Watch your partitions

    lsbk

Select your Drive ( i.e. sdb )
<img width="815" height="191" alt="image" src="https://github.com/user-attachments/assets/654fc477-1f19-46e7-87cf-6be661d42949" />

Wipe your Drive

    sudo pacman -Sy gdisk
    sudo gdisk /dev/sdb

Press x, z, y, y to wipe everything

Create new GPT Partition Table

    sudo pacman -Sy --no-confirm util-linux
    sudo cfdisk /dev/sdb

Select <b>gpt</b> Partition Table
<img width="349" height="186" alt="image" src="https://github.com/user-attachments/assets/2c936e71-1e01-4423-a079-c557228d5cfe" />

Select <b>New</b> Partition Table
<img width="929" height="883" alt="image" src="https://github.com/user-attachments/assets/d3b250e4-62b6-4acb-9964-651ff488252e" />
