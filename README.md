#!/bin/bash
# Subdomain Enumeration
# Subdomain Enumeration Tool

# Set the target domain
target_domain="vishnugit.com"

# Define the wordlist file containing subdomains
wordlist_file="subdomains.txt"

# Perform subdomain emulation
while IFS= read -r subdomain; do
  # Make a DNS lookup for the subdomain
  host "$subdomain.$target_domain" >/dev/null 2>&1
  
  # Check the exit status to determine if the subdomain exists
  if [ $? -eq 0 ]; then
    echo "Subdomain found: $subdomain.$target_domain"
  fi
done < "$wordlist_file"
