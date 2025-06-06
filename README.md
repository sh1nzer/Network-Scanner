# Network Scanner

A command-line tool built by **Shaurya Singh** as a personal project for analyzing hosts on a network using various scanning techniques such as ICMP echo requests, TCP port scanning, and ARP scanning. This tool is created with the intention to help network administrators, cybersecurity students, and IT professionals assess network configurations and discover potential vulnerabilities.

---

## 🚀 Features

- 🔍 **ICMP Echo Request (Ping) Scanning**: Check host availability.
- 🔐 **TCP Port Scanning**: Detect open ports and discover running services.
- 🌐 **ARP Network Scanning**: Identify live hosts on a local subnet.
- ⚙️ **Configurable Scan Options**: Choose scan type, timeout, and ports.
- 🎯 **Support for Port Ranges**: Specify exact ports or scan entire ranges.
- 📋 **Detailed Output**: Get clean, informative scan results in your terminal.

---

## 📦 Requirements

- **Python 3.6+**
- **Scapy 2.5.0+**
- **Administrator/Root Privileges** (required for raw socket operations)

---

## 🛠️ Installation

1. **Clone the Repository**:

```bash
git clone https://github.com/yourusername/network-scanner.git
cd network-scanner


2. **Install Dependencies**:

```bash
pip install -r requirements.txt
```

## Usage

Basic usage:

```bash
python src/main.py <target> [options]
```

### Examples

1. **Scan a Single Host with All Scan Types**:

```bash
python src/main.py 192.168.1.1
```

2. **Perform Only ICMP Scan**:

```bash
python src/main.py 192.168.1.1 -t icmp
```

3. **Scan Specific Ports**:

```bash
python src/main.py 192.168.1.1 -p 80,443,8080
```

4. **Scan a Port Range**:

```bash
python src/main.py 192.168.1.1 -p 1-1000
```

5. **Scan a Network Subnet**:

```bash
python src/main.py 192.168.1.0/24 -t arp
```

### Command Line Options

-   `target`: Target IP address or network (required)
-   `-t, --type`: Type of scan to perform (choices: all, icmp, tcp, arp; default: all)
-   `-p, --ports`: Ports to scan (e.g., 80,443 or 1-1000)
-   `-T, --timeout`: Timeout in seconds for each scan (default: 2)

## Project Structure

```
network-scanner/
├── src/
│   ├── main.py         # Command-line interface
│   └── scanner.py      # Core scanning functionality
├── tests/              # Test files
├── docs/               # Documentation
├── requirements.txt    # Project dependencies
└── README.md           # Project documentation
```

## Security Considerations

-   **Intrusive Nature**: This tool performs network scanning which may be considered intrusive.
-   **Permission**: Use only on networks you have permission to scan.
-   **Network Restrictions**: Some networks may block ICMP or ARP requests.
-   **Privileges**: Running the tool requires elevated privileges.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
