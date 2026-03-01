# Networking Commands Cheat Sheet

This document provides short, readable notes on a variety of networking commands commonly used in Linux environments. Each command includes a brief description and usage examples where appropriate. Markdown formatting is used to make the content easy to scan and understand.

## Frequently Used Commands

### `curl` vs `wget`
- **curl**: Transfers data from or to a server using various protocols (HTTP, FTP, etc.). Ideal for scripts and supports more features.
  ```bash
  curl -O http://example.com/file
  curl -I http://example.com
  ```
- **wget**: Non-interactive network downloader. Good for recursively fetching content and can resume downloads.
  ```bash
  wget http://example.com/file
  wget -r http://example.com/dir/
  ```

### `jq`
A lightweight and flexible command-line JSON processor. Use it to parse, filter, and transform JSON data.
```bash
curl -s http://api.example.com/data | jq '.items[] | {name, value}'
```

### `route`
Displays or manipulates the IP routing table.
```bash
route -n       # view routes without resolving names
route add default gw 192.168.1.1
```

### `nmap`
Network scanner for discovering hosts and services on a network. Useful for security auditing and inventory.
```bash
nmap -sP 192.168.1.0/24  # ping scan network
nmap -A example.com      # aggressive scan with service detection
```

### `watch`
Executes a program periodically, showing the output fullscreen. Useful for monitoring changes.
```bash
watch -n 5 netstat -tuln
```

### `iptables`
User-space utility for configuring the Linux kernel firewall (Netfilter).
```bash
iptables -L        # list rules
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

### `traceroute`
Prints the route packets take to a network host, showing each hop's IP and delay.
```bash
traceroute example.com
```

## Additional Networking Utilities

### `ping`
Sends ICMP echo requests to test reachability of a host and measure round-trip time.
```bash
ping -c 4 8.8.8.8
```

### `netstat`
Displays network connections, routing tables, interface statistics, etc. (deprecated in favor of `ss`).
```bash
netstat -tuln
```

### `ifconfig`
Configures or displays network interface parameters (largely replaced by `ip`).
```bash
ifconfig eth0 up
ifconfig
```

### `Tracepath` vs `Traceroute`
- **traceroute**: uses UDP/ICMP probes; shows each hop.
- **tracepath**: similar but doesn't require root privileges and automatically adjusts MTU.

### `nslookup` vs `dig`
- **nslookup**: older DNS query tool, interactive mode available.
- **dig**: more powerful and flexible DNS lookup tool; preferred by network engineers.
  ```bash
  dig example.com A
  dig +short example.com
  ```

### `telnet`
Connects to remote hosts using the TELNET protocol; also used for simple TCP debugging.
```bash
telnet example.com 80
```

### `mtr`
Combines the functionality of `traceroute` and `ping` in a real-time, interactive tool.
```bash
mtr example.com
```

### `hostname`
Displays or sets the system's host name.
```bash
hostname
hostnamectl set-hostname myhost
```

### `ip`
Versatile command for network configuration (interfaces, routes, addresses).
```bash
ip addr show
ip route add default via 192.168.1.1
```

### `iwconfig`
Configures wireless network interfaces (similar to `ifconfig` but for Wi-Fi).
```bash
iwconfig wlan0 essid MyNetwork
```

### `ss`
Utility to investigate sockets. More modern replacement for `netstat`.
```bash
ss -tuln
```

### `arp`
Displays or modifies the system's ARP cache.
```bash
arp -a
arp -d 192.168.1.10
```

### `whois`
Queries databases that store the registered users of an Internet resource, such as domain names.
```bash
whois example.com
```

### `ifplugstatus`
Checks whether a network interface has a cable plugged in (useful for diagnosing Ethernet port issues).
```bash
ifplugstatus eth0
```

### Duplicate Checks
The following commands were listed earlier but are covered above: `route`, `nmap`, `wget`.

---

Keep this cheat sheet handy for quick reference when working with networking in Linux!
