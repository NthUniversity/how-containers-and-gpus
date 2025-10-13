# Open Web-UI

```
docker run -d \
  --name open-webui \
  --restart unless-stopped \
  -p 3000:8080 \
  -v open-webui:/app/backend/data \
  ghcr.io/open-webui/open-webui:main
```

  

![](images/getting-started.PNG)
![](images/menu-admin-panel.PNG)
![](images/setup-connection-address.PNG)
![](images/setup-connection.PNG)

