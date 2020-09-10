# EN Coda Sandbox Centos 8 Installation

Update packages

```
sudo dnf -y update
```

Install docker
```
sudo dnf -y config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf -y install https://download.docker.com/linux/centos/7/x86_64/stable/Packages/containerd.io-1.2.6-3.3.el7.x86_64.rpm
sudo dnf install docker-ce docker-ce-cli
```

Start docker
```
sudo systemctl enable --now docker
```

Run sandbox container. (Set your number of cpus limit)
```
sudo docker run --cpus=4 --publish 3085:3085 -d --name coda codaprotocol/coda-demo:pickles-sandbox
```

Logs watching
```
sudo docker logs --follow coda
```

# RU Установка песочницы Coda на Centos 8
Обновление пакетов

```
sudo dnf -y update
```

Установка docker
```
sudo dnf -y config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf -y install https://download.docker.com/linux/centos/7/x86_64/stable/Packages/containerd.io-1.2.6-3.3.el7.x86_64.rpm
sudo dnf install docker-ce docker-ce-cli
```

Запуск docker
```
sudo systemctl enable --now docker
```

Запуск контейнера песочницы (Установите свое ограничение кол-ва процессоров)
```
sudo docker run --cpus=4 --publish 3085:3085 -d --name coda codaprotocol/coda-demo:pickles-sandbox
```

Просмотр логов
```
sudo docker logs --follow coda
```
