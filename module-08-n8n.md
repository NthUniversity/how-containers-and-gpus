# n8n Deployment

Another bonus module if time permits

```
docker run -d \
  --name n8n \
  --restart unless-stopped \
  -p 5678:5678 \
  -e GENERIC_TIMEZONE="America/Los_Angeles" \
  -e TZ="America/Los_Angeles" \
  -e N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS=true \
  -e N8N_RUNNERS_ENABLED=true \
  -e N8N_SECURE_COOKIE=false \
  -e N8N_EXTERNAL_URL="http://10.106.6.1XX:5678/" \
  -e WEBHOOK_URL="http://10.106.6.1XX:5678/" \
  -v n8n_data:/home/node/.n8n \
  -v /home/labadmin/n8nfiles:/n8nfiles \
  docker.n8n.io/n8nio/n8n
```

Make sure to adjust the address in `N8N_EXTERNAL_URL` & `WEBHOOK_URL`
