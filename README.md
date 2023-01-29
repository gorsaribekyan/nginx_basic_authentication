# Nginx with Basic Authentication

- Install  NGINX.

```
sudo apt install nginx
```

- Install Apache2 Utils.

```
sudo apt install apache2-utils
```

- Setup user credential into **.htpasswd** file.

```
htpasswd -c /etc/nginx/.htpasswd <user>
```

- Open default config file with nano.

```
nano /etc/nginx/sites-available/default
```

- Add this.

```
location /admin {
    try_files $uri $uri/ =404;
    auth_basic "Admin page.";
    auth_basic_user_file /etc/nginx/.htpasswd
}
```

- Restart NGINX server.

```
systemctl status nginx
```

All done.
