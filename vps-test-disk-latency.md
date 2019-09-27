Quanto menor o tempo de resposta, melhor o desempenho.

# Testing VPS disk latency with `ioping`

Init:
```sh
ioping . -c 10
```

### Locaweb
- 2 core / 1 GB RAM / 40 GB SSD
```
4 KiB from . (ext4 /dev/xvda3): request=1 time=8.74 ms
4 KiB from . (ext4 /dev/xvda3): request=2 time=849 us
4 KiB from . (ext4 /dev/xvda3): request=3 time=728 us
4 KiB from . (ext4 /dev/xvda3): request=4 time=793 us
4 KiB from . (ext4 /dev/xvda3): request=5 time=1.00 ms
4 KiB from . (ext4 /dev/xvda3): request=6 time=2.17 ms
4 KiB from . (ext4 /dev/xvda3): request=7 time=1.11 ms
4 KiB from . (ext4 /dev/xvda3): request=8 time=4.88 ms
4 KiB from . (ext4 /dev/xvda3): request=9 time=1.41 ms
4 KiB from . (ext4 /dev/xvda3): request=10 time=562 us

--- . (ext4 /dev/xvda3) ioping statistics ---
10 requests completed in 9.03 s, 449 iops, 1.76 MiB/s
min/avg/max/mdev = 562 us / 2.22 ms / 8.74 ms / 2.49 ms
```

### ServerSP
- 1 core / 1 GB RAM / 25 GB SSD
```

4 KiB from . (ext4 /dev/vda1): request=1 time=226 us
4 KiB from . (ext4 /dev/vda1): request=2 time=335 us
4 KiB from . (ext4 /dev/vda1): request=3 time=477 us
4 KiB from . (ext4 /dev/vda1): request=4 time=392 us
4 KiB from . (ext4 /dev/vda1): request=5 time=384 us
4 KiB from . (ext4 /dev/vda1): request=6 time=391 us
4 KiB from . (ext4 /dev/vda1): request=7 time=386 us
4 KiB from . (ext4 /dev/vda1): request=8 time=464 us
4 KiB from . (ext4 /dev/vda1): request=9 time=415 us
4 KiB from . (ext4 /dev/vda1): request=10 time=404 us

--- . (ext4 /dev/vda1) ioping statistics ---
10 requests completed in 9.01 s, 2.58 k iops, 10.1 MiB/s
min/avg/max/mdev = 226 us / 387 us / 477 us / 66 us

```
