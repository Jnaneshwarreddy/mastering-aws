




######### DONT FORGET TO CHANGE THE DOMAIN NAME WITH YOUR NAME #########

-    DEPLOY AN EC2 ISNTANCE IN AWS USE UBUNTU 20

-    apt update && apt install -y nginx

-    sudo apt update && sudo apt install certbot python3-certbot-nginx

-    sudo mkdir -p /var/www/testing24.xyz/html

-    sudo chown -R $USER:$USER /var/www/testing24.xyz/html

-    sudo chmod -R 755 /var/www/testing24.xyz
-    nano /var/www/testing24.xyz/html/index.html

<html>
    <head>
        <title>Welcome to testing24.xyz!</title>
    </head>
    <body>
        <h1>Success! The testing24.xyz server block is working!</h1>
    </body>
</html>


-    sudo nano /etc/nginx/sites-available/testing24.xyz

server {
        listen 80;
        listen [::]:80;

        root /var/www/testing24.xyz/html;
        index index.html index.htm index.nginx-debian.html;

        server_name testing24.xyz www.testing24.xyz;

        location / {
                try_files $uri $uri/ =404;
        }
}


-    sudo ln -s /etc/nginx/sites-available/pinapathrunisaikiran.co.in /etc/nginx/sites-enabled/

-    sudo nginx -t

-    sudo systemctl restart nginx

sudo certbot certonly \
  --agree-tos \
  --email jnanibalu58@gmail.com \
  --manual \
  --preferred-challenges=dns \
  -d *.testing24.xyz \
  --server https://acme-v02.api.letsencrypt.org/directory
  
 
 
FOR HTTP TO HTTPS FORWARDING RUN THE BELOW COMMAND.
 
 certbot --nginx
