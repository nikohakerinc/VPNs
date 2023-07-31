# WireGuard & OpenVPN Linux installer
## Блокировка двухстороннего пинга сайтов для скрытия VPN туннеля
`iptables -A OUTPUT -p icmp --icmp-type echo-request -j DROP` *Блокирует исходящий Ping*
`iptables -A INPUT -p icmp --icmp-type echo-reply -j DROP`  *Блокирует вхолдящий Ping*
