
![alt text](https://i.hizliresim.com/9ivrvu6.png)

**Minimum Sistem Gereksinimleri**

- **32 RAM**
- **500GB DISK**

```python
sudo apt update
```

```python
sudo apt install -y unzip logrotate git jq sed wget curl coreutils systemd
```

```python
sudo apt install docker.io
```

```python
sudo systemctl status docker
```
![alt text](https://i.hizliresim.com/op8i2sq.png)

CTRL-C ile çıkabilirsiniz.

```python
docker --version
```

![alt text](https://i.hizliresim.com/1h330hc.png)

```python
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```python
sudo chmod +x /usr/local/bin/docker-compose
```

```python
docker-compose --version
```
![alt text](https://i.hizliresim.com/9zoqkrt.png)

```python
git clone https://github.com/codeesura/zksync-era.git
```

```python
cd zksync-era/docs/guides/external-node/docker-compose-examples
```

```python
docker-compose -f mainnet-external-node-docker-compose.yml up -d
```

```python
docker ps -a
```
- **Bu kod ile zkSync için olan docker containerlarını görebilirsiniz.**

![alt text](https://i.hizliresim.com/arzwcu5.png)

- **Logları görüntülemek isterseniz**

```python
docker logs -f --tail 100 docker-compose-examples_external-node_1
```

- **Loglardan CTRL-C ile çıkabilirsiniz.**

## RPC PORT ve GRAFANA (isteğe bağlı)

- **Metamaska ekleyebilmemiz için port ayarı yapmamız gerekiyor.**

```python
cd
nano zksync-era/docs/guides/external-node/docker-compose-examples/mainnet-external-node-docker-compose.yml
```
- **Çıkan dosyada aşağıya inin external-node altındaki port ayarlarını aşağıdaki gibi yapın.**

![alt text](https://i.hizliresim.com/cpqem5q.png)

- **Grafana üzerinden node durumunu izleyebilmek için yine aynı dosyayada
aşağıdaki görselde olduğu gibi düzenleme yapmanız gerekiyor.**

```python
nano zksync-era/docs/guides/external-node/docker-compose-examples/mainnet-external-node-docker-compose.yml
```

![alt text](https://i.hizliresim.com/pr5frup.png)


- **Bu işlemden/işlemlerden sonra restart atalım.**

```python
cd zksync-era/docs/guides/external-node/docker-compose-examples
docker-compose -f mainnet-external-node-docker-compose.yml down
docker-compose -f mainnet-external-node-docker-compose.yml up
```

- **Metamask'a Ağ Olarak eklemek için**

```python
Ağ adı: istediğiniz bir ad girebilirsiniz.

RPC URL: http://sunucu-ipsi:3060

Zincir Kimliği: 324

Blok Gezgini: https://explorer.zksync.io/blocks/
```

![alt text](https://i.hizliresim.com/4ixy3wa.png)

- **Grafana üzerinden Node durumunu görüntülemek için**

```python
http://sunucu-ipsi:3000/d/0/external-node
```

![alt text](https://i.hizliresim.com/bqbx2uf.png)


### Full Node'unuz 8-10 saate senkronize olur. O zamana kadar blocklar ve grafana monitor ağağıdaki gibi görünür.

![alt text](https://i.hizliresim.com/r29h9y9.png)

![alt text](https://i.hizliresim.com/duzl6k6.png)

- **Senkronize olduktan sonra**

![alt text](https://i.hizliresim.com/lw3tv8j.png)

![alt text](https://i.hizliresim.com/cvmw69q.png)

- **Sistem Kullanımı**

```python
htop
```
![alt text](https://i.hizliresim.com/33qd4ix.png)

- **Disk Kullanımı**

```python
df -h
```

![alt text](https://i.hizliresim.com/8m45bvs.png)















