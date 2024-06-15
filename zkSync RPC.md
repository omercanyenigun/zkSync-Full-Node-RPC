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

```python
docker --version
```

```python
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```python
sudo chmod +x /usr/local/bin/docker-compose
```

```python
docker-compose --version
```

```python
git clone https://github.com/codeesura/zksync-era.git
```

```python
cd zksync-era/docs/guides/external-node
cd docker-compose-examples
```

```python
docker-compose -f mainnet-external-node-docker-compose.yml up -d
```

```python
docker ps -a
```

Bu kod ile zkSync için olan docker containerlarını görebilirsiniz.

Logları görüntülemek isterseniz

```python
docker logs -f --tail 100 docker-compose-examples_external-node_1
```







