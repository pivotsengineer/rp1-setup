# rp1-setup
Raspberry PI 1 services and sensors

1. ADD docker compose to your rc.local

#!/bin/sh -e
#
# rc.local
#
# This script is executed at the end of each multiuser runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.

docker-compose -f /home/ssergienko/setup/services/pihole/docker-compose.yml up -d
docker-compose -f /home/ssergienko/setup/services/homeassistant/docker-compose.yml up -d

# Print the IP address
_IP=$(hostname -I) || true
if [ "$_IP" ]; then
  printf "My IP address is %s\n" "$_IP"
fi

exit 0
