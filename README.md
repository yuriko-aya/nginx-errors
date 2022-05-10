# Minimalist Nginx error pages

A set of custom minimalist 4xx and 5xx error pages for Nginx.

## Preview
![404 error page](https://i.imgur.com/UhkO7uP.pngg)

## Installation

1. Navigate into Nginx's default document directory:
	```
    cd /usr/share/nginx/html
    ```
2. Clone the repository:
	```
    git clone https://github.com/yuriko-aya/nginx-errors.git
    ```

3. Add the custom error pages to the server's default configuration in `/etc/nginx/sites-enabled/default` file:
	```
    server {
    ...
    include /usr/share/nginx/html/nginx-errors/nginx-errors.conf;
    }
    ```
4. add additional configuration if nginx acting as reverse proxy
	```
    server {
    ...
    proxy_intercept_errors on;
    }
    ```
5. Verify the configuration and reload Nginx:
	```
    sudo nginx -t
    sudo service nginx reload
    ```