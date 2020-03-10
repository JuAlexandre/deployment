# Configuration for subdomains

Place it in `/etc/nginx/sites-available/<subdomain>.<domain>` file:

```
# Proxy buffer
proxy_buffers 16 64k;
proxy_buffer_size 128k;

location / {
  # Change the port if you want
  proxy_pass http://localhost:8000;
  proxy_http_version 1.1;
  proxy_set_header Upgrade $http_upgrade;
  proxy_set_header Connection 'upgrade';
  proxy_set_header Host $host;
  proxy_set_header X-Real_IP $remote_addr;
  proxy_set_header X-Forwarded_For $proxy_add_x_forwarded_for;
  proxy_cache_bypass $http_upgrade;
  proxy_max_temp_file_size 0;
}
```