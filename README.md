# TryUpWireGuardVPN
Попытка поднять p2p wireguard vpn

`noip2.service` и `wg-quick@wg0.service` - сервисы `systemd` для автоматической отправки своего IP в noip.com для корректировки namespace и для запуска wg0 при запуске системы. Они работают штатно.
На обоих машинах вывод команды `sudo wg` следующий:

Gentoo PC x86_64
```
  public key: PyBRR52RC3kQFZ9SeXLQZub2yy8BjYvbbCQv34T8ml8=
  private key: (hidden)
  listening port: 51820

peer: yBeAehC5smGleXWdZ/JTFZfyjFqUoWZ+6HVcoi20DkM=
  endpoint: 217.71.236.159:51820
  allowed ips: 10.0.0.1/32
  transfer: 0 B received, 25.73 KiB sent
  persistent keepalive: every 25 seconds
```
Raspberry pi arm64 Ubuntu Server 24.04 LTS
```
  public key: yBeAehC5smGleXWdZ/JTFZfyjFqUoWZ+6HVcoi20DkM=
  private key: (hidden)
  listening port: 51820

peer: PyBRR52RC3kQFZ9SeXLQZub2yy8BjYvbbCQv34T8ml8=
  endpoint: 217.71.236.159:51820
  allowed ips: 10.0.0.2/32
  transfer: 0 B received, 19.80 KiB sent
  persistent keepalive: every 25 seconds
```

`ping` `distsmarthomevpn1.ddns.net` и `distsmarthomevpn2.ddns.net` не работает, как не работает и 
`ping 10.0.0.2` с Raspberry и `ping 10.0.0.1` с PC
Все остальное (google.com и пр. а так же себя (например `ping 10.0.0.1` с Raspberry) успешно пингует.
