# Teste VPS ServerSP vs Locaweb vs Hostinger

Vamos comparar planos semelhantes de VPS ServerSP, Locaweb e Hostinger

Na primeira rodada de teste, usamos Ubuntu 16 64bit e na segunda usamos CentOS 7.


Procuramos escolher planos **semelhantes** em configuração de valores, veja aqui os [planos](vps-planos.md)

### ServerSP [sp] (https://serversp.com/vps-ssd-nvme/)

- 1 core / 1 GB RAM / 25 GB SSD R$29.90


### Locaweb [lw] (https://www.locaweb.com.br/cloud/vps-locaweb/)

- 2 core / 1 GB RAM / 40 GB SSD R$29.90 



### Hostinger [ht] (https://www.hostinger.com.br/servidor-vps)

- 1 core / 1 GB RAM / 20 GB SSD  R$35.00



**Obs*** O VPS Hostinger foi contratado com 1 core, porém com o `# cat /proc/cpuinfo` informa 2 cores (https://i.imgur.com/N7AamIz.png)

Esse teste foi executado em 27/09/2019


## Resultados


[vps-test-dd](vps-test-dd.md)

[vps-test-disk-latency.md](vps-test-disk-latency.md)

[vps-test-network.md](vps-test-network.md)

[vps-test-unixbench.md](vps-test-unixbench.md)





# Segunda batalha de testes

Para não sobra dúvidas sobre a manipução dos resultados, também testamos através do https://serverscope.io, o resultado de cada teste esta abaixo.

[Resultado ServerScope.io](vps-teste-serverscope.md)
