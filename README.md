# :file_cabinet: Censys CLI has been [merged](https://github.com/censys/censys-python/pull/42) into [`censys-python`](https://github.com/censys/censys-python)

> Please use [`censys/censys-python`](https://github.com/censys/censys-python) as [`censys/censys-command-line`](https://github.com/censys/censys-command-line) has been implemented as of [`censys/censys-python#42`](https://github.com/censys/censys-python/pull/42).

## Censys Command Line

This script allows a user to query the Censys API from the command. The results from the query can be written to CSV, JSON, or simply to the screen.

### Installation

```bash
pip install censys-command-line
```

Or

```bash
pip install git+https://github.com/censys/censys-command-line
```

### Usage

```bash
usage: censys [-h] [--fields FIELDS [FIELDS ...]] --query_type
                              ipv4|certs|websites [--append {true,false}]
                              [--output json|csv|screen]
                              [--start_page START_PAGE]
                              [--max_pages MAX_PAGES]
                              [--censys_api_id XXXXXXXXXX]
                              [--censys_api_secret XXXXXXXXXX]
                              query

Search The Censys Data Set via the command line

positional arguments:
  query

optional arguments:
  -h, --help            show this help message and exit
  --fields FIELDS [FIELDS ...]
  --query_type ipv4|certs|websites
  --append {true,false}
                        Append the given list of fields to the default fields
  --output json|csv|screen
  --start_page START_PAGE
  --max_pages MAX_PAGES
  --censys_api_id XXXXXXXXXX
                        (optional) You must provide your Censys API ID here or
                        as an environmental variable CENSYS_API_ID
  --censys_api_secret XXXXXXXXXX
                        (optional) You must provide your Censys API SECRET
                        here or as an environmental variable CENSYS_API_SECRET

```

#### Searching IPv4

```bash
censys "ip: [ 134.54.0.0 TO 134.54.65.255 ]" --query_type ipv4 --fields ip protocols --output json
```

#### Searching Certificates

```bash
censys "parsed.issuer.organization: Let's Encrypt" --query_type=certs
```
