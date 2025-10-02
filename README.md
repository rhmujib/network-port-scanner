# Network Port Scanner ( WOLF )

A Python-based network port scanner for reconnaissance and network analysis. This tool allows you to scan ports on a target host or range of hosts, identify open ports, and optionally generate a PDF/csv/json report of the results.

---
  ╔════════════════════════════════════════════════════════════════════════╗
    ║                        Network Port Scanner v1.0                       ║
    ║                      For authorized testing only!                      ║
    ╚════════════════════════════════════════════════════════════════════════╝

                        ██     ██   ██████    ██       ███████ 
                        ██     ██  ██    ██   ██       ██      
                        ██  █  ██  ██    ██   ██       █████   
                        ██ ███ ██  ██    ██   ██       ██      
                        ███   ███   ██████    ███████  ██  
                    

                     --- Developed by:  >>>  CYBERMJ-MUJIB  <<< ---
    """

## Features
- Scan single ports, ranges of ports, or comma-separated lists of ports.
- Supports scanning multiple targets (IP addresses, hostnames, or CIDR ranges).
- Multithreaded scanning for faster results.
- Configurable timeout for socket connections.
- Common port-to-service mapping for easy identification.
- Optional PDF report generation (requires `reportlab`).

---

## Requirements
- Python 3.7 or higher
- Optional: `reportlab` library for PDF generation

---

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/network-port-scanner.git
   cd network-port-scanner
   
2. Install the required dependencies:

        pip install -r requirements.txt

3. (Optional) Install reportlab for PDF generation:

        pip install reportlab

## Usage
Command-Line Arguments
The tool accepts the following arguments:

    --target: Specify the target(s) to scan (IP, hostname, or CIDR range).
    --ports: Specify the ports to scan (single port, range, or comma-separated list).
    --timeout: Set the socket connection timeout (default: 1.0 seconds).
    --threads: Set the maximum number of concurrent threads (default: 50).

    Now, when you run the tool with -o followed by a filename with a specific extension, it will generate the report in the specified format. For example:

        wolf -t 192.168.1.1 -p 80 -o report.json → Exports to JSON.
        wolf -t 192.168.1.1 -p 80 -o report.csv → Exports to CSV.
        wolf -t 192.168.1.1 -p 80 -o report.pdf →
            
## Example Commands:

    Scan a single target on a specific port:
    python wolf --target 192.168.1.1 --ports 80

    Scan a range of ports on a target:
    python wolf --target 192.168.1.1 --ports 20-100

    Scan multiple target with a comma-separated list of ports:
    python wolf --target 192.168.1.1,192.168.1.2 --ports 22,80,443

    Generate a PDF report:
    python wolf --target 192.168.1.1 --ports 80 report.pdf

## Project Structure:

How It Works
Port Parsing: 

The tool parses the port argument to handle single ports, ranges, or comma-separated lists.
Target Parsing: 
The tool supports IP addresses, hostnames, and CIDR ranges.
Multithreading: 
Uses ThreadPoolExecutor to scan multiple ports/targets concurrently.
PDF Generation: 
If reportlab is installed, the tool can generate a PDF report of the scan results.

## Limitations:

The tool requires Python 3.7 or higher.
PDF generation is optional and requires the reportlab library.
Scanning large ranges of ports or targets may take time depending on network conditions.
Contributing
Contributions are welcome! Feel free to open issues or submit pull requests.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgments
ReportLab for PDF generation.
Python's socket and concurrent.futures libraries for networking and multithreading.
