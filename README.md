# Teste-VPS---Locaweb-vs-ServerSP

Vamos comparar planos semelhantes de VPS Locaweb e ServerSP
Iremos usar Ubuntu 16 64bit e tentaremos rodar os testes no mesmo horário.

O plano Locaweb escolhido foi o mais básico

### Locaweb [lw]

- 2 core / 1 GB RAM / 40 GB SSD



A ServerSP não tem plano semelhante, o mais básico é

### ServerSP [sp]

- 1 core / 1 GB RAM / 25 GB SSD

## Desempenho de leitura/gravação

Init:
```sh
mkdir ~/_bench/
cd ~/_bench/
```

### Write

```sh
dd if=/dev/zero of=diskbench bs=1M count=1024 conv=fdatasync
```

- [lw]: `1073741824 bytes (1.1 GB, 1.0 GiB) copied, 53.1643 s, 20.2 MB/s` :snail: SSD mesmo???
- [sp]: `1073741824 bytes (1.1 GB, 1.0 GiB) copied, 1.28125 s, 838 MB/s` ServerSP foi 41 x mais rápido

### Read

Clear cache
```sh
echo 3 | sudo tee /proc/sys/vm/drop_caches
```

```sh
dd if=diskbench of=/dev/null bs=1M count=1024
```
Uncached

- [lw]: `1073741824 bytes (1.1 GB, 1.0 GiB) copied, 19.9907 s, 53.7 MB/s`
- [sp]: `1073741824 bytes (1.1 GB, 1.0 GiB) copied, 1.41795 s, 757 MB/s`

## CPU performance

```sh
dd if=/dev/zero bs=1M count=1024 | md5sum
```

- [lw]: `1073741824 bytes (1.1 GB, 1.0 GiB) copied, 4.41503 s, 243 MB/s`
- [sp]: `1073741824 bytes (1.1 GB, 1.0 GiB) copied, 2.43448 s, 441 MB/s`
