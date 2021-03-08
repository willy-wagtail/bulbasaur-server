# Pihole with Unbound DNS

Build and start pihole-unbound docker container
- ``docker-compose up -d`` 
- ``docker ps -a`` to get container id
- ``docker logs <container_id>`` to check the startup logs

Whitelist (optional)
- ``git clone https://github.com/anudeepND/whitelist.git ~/Documents/pihole-whitelist``
- ``cd ~/Documents/pihole-whitelist/``  
- ``sudo python3 ./scripts/whitelist.py --dir ~/.pihole-unbound/etc-pihole/ --docker``

Stop pihole-unbound docker container
- ``docker-compose down``
