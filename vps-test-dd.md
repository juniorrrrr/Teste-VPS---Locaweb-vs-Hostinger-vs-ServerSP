# Using `dd`

### RunAbove Sandbox [ra]
- 1 core / 2 GB RAM / 20 GB SSD

### EC2 Micro [ec]
- 1 core / 1 GB RAM / 8 GB

### Digital Ocean [do]
- 1 core / 512 MB RAM / 20 GB SSD

### Digital Ocean [do2]
- 2 core / 2048 MB RAM / 40 GB SSD

### Vultr [vt]
- 2 core / 2048 MB RAM / 45 GB SSD

### Scaleway [sw]
- 4 core (ARM) / 2048 MB RAM / 50 GB LSSD

## Disk read/write performance

Init:
```sh
mkdir ~/_bench/
cd ~/_bench/
```

### Write

```sh
dd if=/dev/zero of=diskbench bs=1M count=1024 conv=fdatasync
```

- [ra]: `1073741824 bytes (1.1 GB) copied, 7.35618 s, 146 MB/s`
- [ec]: `1073741824 bytes (1.1 GB) copied, 16.9822 s, 63.2 MB/s`
- [do]: `1073741824 bytes (1.1 GB) copied, 2.12969 s, 504 MB/s`
- [vt]: `1073741824 bytes (1.1 GB) copied, 2.51819 s, 426 MB/s`
- [sw]: `1073741824 bytes (1.1 GB) copied, 11.288 s, 95.1 MB/s`
- [do2 1st run]: `1073741824 bytes (1.1 GB) copied, 37.8891 s, 28.3 MB/s` :neutral_face:
- [do2 2nd run]: `1073741824 bytes (1.1 GB) copied, 32.7894 s, 32.7 MB/s` :snail:

Clearly, something wasn't right with this Digital Ocean instance.

### Read

Clear cache
```sh
echo 3 | sudo tee /proc/sys/vm/drop_caches
```

```sh
dd if=diskbench of=/dev/null bs=1M count=1024
```
Uncached
- [ra]: `1073741824 bytes (1.1 GB) copied, 5.71051 s, 188 MB/s`
- [ec]: `1073741824 bytes (1.1 GB) copied, 16.5122 s, 65.0 MB/s`
- [do]: `1073741824 bytes (1.1 GB) copied, 1.06747 s, 1.0 GB/s`
- [vt]: `1073741824 bytes (1.1 GB) copied, 3.18181 s, 337 MB/s`
- [sw]: `1073741824 bytes (1.1 GB) copied, 12.1583 s, 88.3 MB/s`
- [do2]: `1073741824 bytes (1.1 GB) copied, 1.88625 s, 569 MB/s`

Cached
- [ra]: `1073741824 bytes (1.1 GB) copied, 0.780069 s, 1.4 GB/s`
- [ec]: `1073741824 bytes (1.1 GB) copied, 16.3098 s, 65.8 MB/s`
- [do]: `1073741824 bytes (1.1 GB) copied, 0.957031 s, 1.1 GB/s`
- [vt]: `1073741824 bytes (1.1 GB) copied, 0.125819 s, 8.5 GB/s`
- [sw]: `1073741824 bytes (1.1 GB) copied, 1.20416 s, 892 MB/s`
- [do]: `1073741824 bytes (1.1 GB) copied, 0.215533 s, 5.0 GB/s`

## CPU performance

```sh
dd if=/dev/zero bs=1M count=1024 | md5sum
```

- [ra]: `1073741824 bytes (1.1 GB) copied, 2.36411 s, 454 MB/s`
- [ec]: `1073741824 bytes (1.1 GB) copied, 2.46927 s, 435 MB/s`
- [do]: `1073741824 bytes (1.1 GB) copied, 2.95077 s, 364 MB/s`
- [vt]: `1073741824 bytes (1.1 GB) copied, 1.80603 s, 595 MB/s`
- [sw]: `1073741824 bytes (1.1 GB) copied, 6.57509 s, 163 MB/s`
- [do2]: `1073741824 bytes (1.1 GB) copied, 3.80824 s, 282 MB/s`
