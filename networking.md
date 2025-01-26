## Network Administration Cheat Sheet

This cheat sheet provides an overview of common Linux commands for network administration.

### 1. ip Command

The `ip` command is a powerful tool for network configuration, replacing older commands like `ifconfig` and `route`.

* **ip addr (or ip a or ip address):** Shows information about network interfaces and their IP addresses.
    * `ip addr show`: Displays all interfaces.
    * `ip addr show <interface>`: Shows details for a specific interface (e.g., `ip addr show ens33`).
    * `ip addr add <address>/<prefix> dev <interface>`: Adds an IP address to an interface (e.g., `ip addr add 192.168.10.10/24 dev ens33`).
    * `ip addr del <address>/<prefix> dev <interface>`: Removes an IP address from an interface.
* **ip link:** Manages network interface links.
    * `ip link show`: Shows all interfaces and their link layer addresses.
    * `ip link set <interface> up`: Enables a network interface.
    * `ip link set <interface> down`: Disables a network interface.
* **ip route:** Manages the routing table.
    * `ip route show`: Displays the current routing table.
    * `ip route add default via <gateway>`: Adds a default gateway.

### 2. ifconfig Command (Legacy)

`ifconfig` is an older network configuration command, though less preferred than `ip`.

* `ifconfig`: Displays information about network interfaces.
    * `<interface>`: Shows information for a specific interface.
    * `<interface> <address>`: Assigns an IP address to an interface.
    * `<interface> up`: Activates an interface.
    * `<interface> down`: Deactivates an interface.

### 3. netstat and ss Commands

These commands display network connections and routing information. `ss` is a newer and more versatile alternative to `netstat`.

* **netstat:** Displays network connections and statistics.
    * `-a`: Shows all sockets.
    * `-t`: Shows TCP connections.
    * `-u`: Shows UDP connections.
    * `-l`: Shows listening sockets.
    * `-r`: Displays the routing table.
* **ss:** Provides detailed socket statistics.
    * `-a`: Shows all sockets.
    * `-t`: Shows TCP sockets.
    * `-u`: Shows UDP sockets.
    * `-l`: Shows listening sockets.
    * `-lt`: Shows all listening TCP sockets.
    * `-lu`: Shows all listening UDP sockets.
    * `-s`: Displays a summary of all sockets.
    * `-u state established`: Displays all established UDP sockets.

### 4. host and dig Commands

These commands perform DNS lookups to translate domain names to IP addresses.

* **host:** Provides a condensed DNS lookup output.
    * `<domain>`: Looks up the IP address for a domain (e.g., `host example.com`).
* **dig:** Offers a more verbose DNS lookup with detailed information.
    * `<domain>`: Shows detailed information about DNS queries and responses (e.g., `dig example.com`).
    * `<domain> <type>`: Queries a specific type of DNS record (e.g., `dig example.com MX`).

### 5. ping Command

* **ping:** Tests network connectivity to a host by sending ICMP echo requests.
    * `<IP address or domain>`: Sends ICMP echo requests to the specified host (e.g., `ping 192.168.0.1`).
    * `-c <count> <IP address or domain>`: Sends a specified number of ICMP requests (e.g., `ping -c 3 192.168.0.1`).

### Key Concepts

* **Interface:** A network connection point on a device.
* **IP Address:** A unique identifier assigned to each device on a network using the Internet Protocol.
* **Routing Table:** A table containing information about routes to different networks.
* **Socket:** An endpoint for communication between processes.
* **DNS:** The Domain Name System, a service that translates domain names to IP addresses.
* **Link Layer:** The physical or logical connection between two devices on a network.
