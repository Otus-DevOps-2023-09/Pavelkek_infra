# Pavelkek_infra
Pavelkek Infra repository
Для подключения в одну строку использовать флаг J
ssh -J appuser@158.160.51.92 appuser@10.128.0.20
Для подключения через алиас изменить .ssh/config
Host bastion
    Hostname 158.160.51.92
    User appuser
Host someinternalhost
    Hostname 10.128.0.20
    User appuser
    ProxyJump bastion

bastion_IP=158.160.51.92
someinternalhost_IP=10.128.0.20
testapp_IP = 51.250.42.48
testapp_port = 9292
Для создания ВМ команда:
yc compute instance create    --name reddit-app-app    --hostname reddit-app-app    --memory=4    --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1604-lts,size=10GB    --network-interface subnet-name=default-ru-central1-c,nat-ip-version=ipv4    --metadata-from-file='user-data=startup.yaml'    --metadata serial-port-enable=1

Параметризирован созданый шаблон, добавлен гит_игнор файл для файла переменных
