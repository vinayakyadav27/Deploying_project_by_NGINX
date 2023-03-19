NGINX:
Web server that serve files
other eg. 
Apache, Django, httpd

Reverse Proxy
Load balancing
URL Redirection
Indexing??
Caching

sudo apt-get update
sudo apt install nginx
public ip gives nginx page

vim commands

Esc + :w – Save the file but do not exit.
Esc + :q! – To quit from the file without first saving that you were working on.
Esc + :wq – To save the file and exit from vim.


basic html file after nginx installtion in
/var/www/html

nginx files in 
/etc/nginx

git clone project 
https://github.com/LondheShubham153/django-notes-app.git

install docker
give permission to docker
sudo usermod -aG docker $USER 
(gives permission to current user to access docker)

docker build -t notes-app .
docker run -d -p 8000:8000 notes-app:latest

website running on http://localhost:8000

Reverse proxy using nginx
go to /etc/nginx/sites-enabled
vim default
add
proxy_pass http://127.0.0.1:8000; 

in location / i.e home page
restart the nginx service
sudo systemctl restart nginx
now public ip should give a blank page

copy the django-notes-app/mynotes/build files to /var/www/html
sudo cp -r * /var/www/html/

Copies the static file of react app to nginx root folder

add backend location if required in 
/etc/nginx/sites-enabled/default

in under location /whatever
then add proxy_pass




