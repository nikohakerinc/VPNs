# WireGuard & OpenVPN Linux installer
## Блокировка двухстороннего пинга сайтов для скрытия VPN туннеля
`iptables -A OUTPUT -p icmp --icmp-type echo-request -j DROP` *Блокирует исходящий Ping*

`iptables -A INPUT -p icmp --icmp-type echo-reply -j DROP`  *Блокирует входящий Ping*

Отключение ICMP пакетов на уровне ядра:
`sudo nano /etc/sysctl.conf`

Затем добавьте в файл следующую строку:
`net.ipv4.icmp_echo_ignore_all = 1`

Сохраните и закройте файл.
Затем введите следующую команду в Терминале, чтобы применить эту конфигурацию без перезагрузки:
`sysctl -p`
