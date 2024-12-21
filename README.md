# Namecheap DNS Manager Role

An Ansible role to manage DNS records for domains hosted on Namecheap. This role retrieves existing DNS records, updates them with new records, and applies the changes back to Namecheap via their API.

## Features

- Retrieve current DNS records.
- Parse and extract DNS record data.
- Combine new and existing records for updates.
- Push updates to Namecheap's API.

## Requirements

- Namecheap API credentials.
- Whitelisted IP for API access.

## Role Variables

These variables should be defined in your playbook or inventory:

```yaml
api_user: "your_api_user"          # Your Namecheap API user
api_key: "your_api_key"            # Your Namecheap API key
username: "your_namecheap_username"  # Your Namecheap username
client_ip: "your_client_ip"        # Your whitelisted client IP

domain_sld: "example"              # SLD of the domain (e.g., 'example' for example.com)
domain_tld: "com"                  # TLD of the domain (e.g., 'com' for example.com)

new_dns_records:                   # New DNS records to add
  - Name: "test1"
    Type: "A"
    Address: "192.0.2.1"
    TTL: 300
  - Name: "test2"
    Type: "CNAME"
    Address: "example.com"
    TTL: 600
  - Name: "test3"
    Type: "TXT"
    Address: "verification_code"
    TTL: 3600
```


## License

This project is licensed under the MIT License