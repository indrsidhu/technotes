```
sudo apt-get install rsync -y
rsync -r out/* /var/www/html/

vim /etc/nginx/sites-available/default
systemctl restart nginx

pm2 list
pm2 delete
pm2 start yarn --name "nextjs" -- start:production

pm2 restart nextjs
```

## Set nginx Proxy for nextjs server ##

```
vim /etc/nginx/nginx.conf
```
```
location /api {
   proxy_pass http://127.0.0.1:3001;
}
```
```
systemctl restart nginx
```
