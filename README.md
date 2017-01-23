

# Usage

* Create the `vbase` data volume container:

    ```bash
    docker create -v ~/mnt-sdb2/www:/var/www -v ~/mnt-sdb2/git-repo:/git-repo --name vbase alpine /bin/true
    docker inspect vbase
    ```
        
* Up the compose

    ```bash
    cd compose/dev-env
    docker-compose up -d web
    ```
    
* Up the compose

    ```bash
    docker-compose down --volumes
    ```
    
    
    