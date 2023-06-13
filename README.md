#!/bin/bash
# Subdomain Enumeration
# Subdomain Enumeration Tool

# Prompt user for the target domain
read -p "Enter the target domain: " target_domain

# Prompt user for the subdomains
read -p "Enter the path to the file containing subdomains: " subdomain_file

# Perform subdomain enumeration
while IFS= read -r subdomain; do
  # Make a DNS lookup for the subdomain
  host "$subdomain.$target_domain" >/dev/null 2>&1
  
  # Check the exit status to determine if the subdomain exists
  if [ $? -eq 0 ]; then
    echo "Subdomain found: $subdomain.$target_domain"
  fi
done < "$subdomain_file"







Save the script to a file (e.g., subdomain_enu.sh) and make it executable using the command chmod +x subdomain_enu.sh.
Run the script using ./subdomain_enu.sh in the terminal.
When prompted, enter the target domain you want to emulate subdomains for (e.g., vishnurai.com).
Enter the path to the file containing the subdomains you want to test (e.g., subdomains.txt). An example list is below:
www
mail
blog
shop
app
api
cdn
dev
admin
test
stage
forum
secure
login
support
info
demo
