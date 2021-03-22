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

## 2 Teardown

Stop syncthing docker container
- ``docker-compose down``

