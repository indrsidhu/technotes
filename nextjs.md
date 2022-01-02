sudo apt-get install rsync -y
rsync -r out/* /var/www/html/

vim /etc/nginx/sites-available/default
systemctl restart nginx

pm2 list
pm2 delete
pm2 start yarn --name "nextjs" -- start

pm2 restart nextjs
