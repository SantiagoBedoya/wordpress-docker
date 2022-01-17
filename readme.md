# WordPress
## Generate Backup

1. Install `All-in-One WP Migration` plugin
2. `Export` backup with Export to `File`
3. Save a `.wpress` file

## Run & start empty WordPress
Run basic WordPress implementation with 
```
    docker-compose up -d 
```

### Increase maximum upload file

1. Install `All-in-One WP Migration` plugin
2. All permissions to the project folder to avoid compatibility problems `sudo chmod -R 777 wordpress`, only do it for local execution 
3. Update and add de follow code in `wp-project/.htaccess` 
```
    php_value upload_max_filesize 999M
    php_value post_max_size 999M
    php_value memory_limit 999M
    php_value max_execution_time 999
    php_value max_input_time 999
```
3. Update and add de follow code in `wp-project/wp-configuration.php`
```
    @ini_set( 'upload_max_filesize' , '999M' );
    @ini_set( 'post_max_size', '999M');
    @ini_set( 'memory_limit', '999M' );
    @ini_set( 'max_execution_time', '999' );
    @ini_set( 'max_input_time', '999' );
```

> Resource: https://help.servmask.com/2018/10/27/how-to-increase-maximum-upload-file-size-in-wordpress/

## Commands
* `docker-compose down` removes the containers and default network, but preserves your WordPress database
* `docker-compose down --volumes` removes the containers, default network, and the WordPress database