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
