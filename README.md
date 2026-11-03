![Banner](banner.png)

# net-asn-lookup
Looks up ASN (Autonomous System Number) information for a given IP address or hostname using a public database, and prints the ASN and description lines it returns. Focused on Basic network operations.

## Install
```bash
git clone https://github.com/ShadowGuard-AI/net-asn-lookup.git
cd net-asn-lookup
pip install -r requirements.txt
```

Python 3 plus the `requests` package (see `requirements.txt`). The lookup queries `https://api.hackertarget.com/aslookup/`; only the first two lines of its answer are used, the ASN line and the description line.

## Usage
```bash
python3 main.py TARGET
```

## Parameters
- `target`: IP address or hostname to look up. Required. IPv4 only: an IPv6 address fails validation and then fails hostname resolution. A hostname is resolved with `gethostbyname` to a single IPv4 address.
- `-v`, `--verbose`: Enable verbose logging.

## Exit codes
- `0`: the run completed, including a lookup that returns no ASN information (that prints "No ASN information found").
- `1`: the target could neither be validated as an IPv4 address nor resolved as a hostname.
- `2`: missing required argument (argparse).

## License
MIT. See [LICENSE](LICENSE).
