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

Select <b>New</b> to create New Partition and press <b>Enter</b> to accept the size

<img width="904" height="162" alt="image" src="https://github.com/user-attachments/assets/86432808-fe9b-4ff3-a7ca-6b0342c727dd" />

Press <b>Write</b> to write the <b>New Partition</b>

<img width="874" height="66" alt="image" src="https://github.com/user-attachments/assets/776e1aeb-67f4-4218-af6b-1d1b8cf8f16b" />

Type <b>yes</b>

<img width="796" height="37" alt="image" src="https://github.com/user-attachments/assets/e12c582c-4f67-4788-acce-e191beeb9513" />

Select <b>Quit</b>

<img width="845" height="61" alt="image" src="https://github.com/user-attachments/assets/c927b28d-13e4-44fe-a098-76e85a2101af" />
