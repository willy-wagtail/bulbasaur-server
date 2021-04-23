# Syncthing

## 1 Setup

Create environment variables referenced in the ``docker-compose.yml`` file:
- ``sudo nano .env`` in same directory as ``docker-compose.yml``
- add env vars to file
    ```
    ST_HOST_FOLDERS_PATH=<path to sync location on host>
    ```

Start syncthing docker container:
- ``docker-compose up -d`` 
- ``docker ps -a`` to get container id
- ``docker logs <container_id>`` to check the startup logs

Setup a password on the web UI
- go to  ``<IP of host>:8384`` on another device on the local network
- follow prompts to setup username and password

From here, you can then configure Syncthing using the GUI or using the configuration file in ``~/.syncthing/config/config.xml``

## 2 Teardown

Stop syncthing docker container
- ``docker-compose down``

## 3 Update 

Stop syncthing docker container
- ``docker-compose down``

Update images
- ``docker-compose pull``

Prune old images
- ``docker image prune``

Start syncthing docker container
- ``docker-compose up -d``
