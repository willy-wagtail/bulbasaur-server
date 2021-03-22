# Pihole with Unbound DNS


Create file with name ``.env`` in this directory with environment variables referenced in the ``docker-compose.yml`` - i.e.:
```
PIHOLE_PASSWORD=<password Pihole for web UI>
PIHOLE_TIMEZONE=Europe/London
PIHOLE_ServerIP=<local IP Address of host>
```

Build and start pihole-unbound docker container
- ``docker-compose up -d`` 
- ``docker ps -a`` to get container id
- ``docker logs <container_id>`` to check the startup logs

Whitelist (optional)
- ``git clone https://github.com/anudeepND/whitelist.git ~/Documents/pihole-whitelist``
- ``cd ~/Documents/pihole-whitelist/``  
- ``sudo python3 ./scripts/whitelist.py --dir ~/.pihole-unbound/etc-pihole/ --docker``

On your home network's router, change the default DNS server to point to the IP address of the pihole-unbound host.

Verify that advert blocking works using this [ad-blocker test](https://ads-blocker.com/testing/).

Stop pihole-unbound docker container
- ``docker-compose down``
