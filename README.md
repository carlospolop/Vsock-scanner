# Vsock-scanner

Scan local and accessible vsock CIDs and ports via brute-forcing (trying to connect to them).

It's possible to configure the CIDs range, the port range to scan, the number of threads to use and the timeput to wait for a successful connection.

By default, it will scan CIDs from 0 to 100, nmap top 1000 ports, with 100 threads and a timeout of 0.05s.

## Help

```bash
python3 vsock-scanner.py -h
usage: vsock-scanner.py [-h] [--cids CIDS] [--ports PORTS] [--threads THREADS]
                        [--timeout TIMEOUT]

vSock Port Enumerator

optional arguments:
  -h, --help         show this help message and exit
  --cids CIDS        Range of CIDs to scan in format <start>-<end>
  --ports PORTS      Range of ports to scan in format <start>-<end>
  --threads THREADS  Number of threads to use
  --timeout TIMEOUT  Timeout for connection attempts in seconds
```

## Scan

```bash
# Use default values
python3 vsock-scanner.py

# Configure new values
python3 vsock-scanner.py --cids 0-100 --ports 0-10000 --threads 100 --timeout 0.05
```