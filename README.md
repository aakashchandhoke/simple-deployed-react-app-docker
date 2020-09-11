Reference from Medium page https://medium.com/greedygame-engineering/so-you-want-to-dockerize-your-react-app-64fbbb74c217

Build Docker - `docker build . -t react-docker`

Run Docker - `docker run -p 8000:80 react-docker`

export Docker to Tar file - `docker save react-docker > react-docker-example.tar`

import from tar - `docker load < react-docker-example.tar` then use run docker command with the name allocated to the docker image as `docker_image:latest` (here as `react-docker:latest`)

For configuring in nginx follow this page :- 

https://medium.com/@timmykko/deploying-create-react-app-with-nginx-and-ubuntu-e6fe83c5e9e7

`sudo mkdir /var/www`

`cd /var/www/`

`sudo gpasswd -a "$USER" www-data`

`sudo chown -R "$USER":www-data /var/www`

`find /var/www -type f -exec chmod 0660 {} \;`

`sudo find /var/www -type d -exec chmod 2770 {} \;`

`git clone [Your repository URL]`

`cd [Your Repository Name]`

`sudo npm install`

`sudo npm run build`

`sudo apt-get install nginx`

Configure default file in /etc/nginx/sites-available

server {

   listen 80 default_server;

   root /var/www/[Your repo name]/build;

   server_name [your.domain.com] [your other domain if you want to];

   index index.html index.htm;

}

`sudo service nginx start`

`sudo service nginx restart`

`sudo service nginx stop`
