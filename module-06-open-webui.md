# Open WebUI
Launch Container
```
docker run -d \
  --name open-webui \
  --restart unless-stopped \
  -p 3000:8080 \
  -v open-webui:/app/backend/data \
  ghcr.io/open-webui/open-webui:main
```
Navigate to Open WebUI `http://10.106.6.XXX:3000` and create admin account

![](images/getting-started.PNG)

Navigate to the Admin Portal

![](images/menu-admin-panel.PNG)

Navigate to Connections

![](images/setup-connection.PNG)

Setup connection to NIM container `http://10.106.6.XXX:3000/v1`

![](images/setup-connection-address.PNG)

