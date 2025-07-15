Nmap Scanning Lab — Network Reconnaissance Project
A hands-on project demonstrating the use of Nmap, a powerful network scanning and enumeration tool used by cybersecurity professionals to identify active hosts, open ports, and running services in a network.

🚀 What It Does
This project focuses on performing network discovery and service enumeration using Nmap from a Kali Linux machine in a lab setup.

Key Actions:

🎯 Scanned a local subnet to identify live hosts.

🔎 Identified open ports and services on a target machine.

⚙️ Used Nmap options to perform stealth, aggressive, and version detection scans.

📄 Analyzed scan results for further security assessments.

🧪 Commands Used
  sudo nmap -sn 192.168.1.0/24
 

Purpose: Ping scan to find active IPs in the subnet.
Result: Identified all live hosts (e.g., 192.168.1.150).

 sudo nmap -sS -sV -T4 192.168.1.150
 
 
-sS: TCP SYN scan (stealthy and fast)

-sV: Service version detection

-T4: Faster timing template

Output:
Port	State	Service	Version
80/tcp	open	http	Apache httpd 2.4.41
3306/tcp	open	mysql	MySQL 5.7.31
80/tcp open http Apache httpd 2.4.4
Port 80/tcp: Standard port for HTTP (web traffic).

open: The port is accessible and actively accepting connections.

http: Indicates a web server is running here.

Apache httpd 2.4.41: The exact web server software and version. Apache is one of the most popular web servers used for hosting websites.

🔐 Security Note: Outdated versions of Apache (like 2.4.41) may contain known vulnerabilities. Always check CVEs for this version.

3306/tcp open mysql MySQL 5.7.31
Port 3306/tcp: Default port used by MySQL (a database server).

open: The MySQL service is accepting connections.

mysql: Indicates a MySQL database is running here.

MySQL 5.7.31: The version of the MySQL server.

🔐 Security Note: Exposing MySQL to the network can be risky. It should usually only accept connections from localhost unless securely configured.

🚨 Why This Is Important: Apache HTTP on port 80: If it's not running HTTPS (port 443), traffic can be intercepted or tampered with (man-in-the-middle attacks).

MySQL on port 3306: If not firewalled properly, an attacker might try brute-force or exploit known MySQL vulnerabilities.

✅ Recommendations: Consider upgrading Apache and MySQL to the latest stable versions.

Ensure Apache uses HTTPS (TLS/SSL).

Restrict MySQL access using firewall rules or bind it to localhost if external access isn't needed.

Regularly apply security patches and monitor logs.
