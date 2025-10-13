# Install NVIDIA Drivers #

Add repo for drivers

`sudo add-apt-repository -y ppa:graphics-drivers/ppa`

Update Catalog

`sudo apt update`

List avaialable drivers

`ubuntu-drivers devices`

Install drivers

`sudo apt install -y nvidia-driver-580-server `

Reboot

`sudo reboot now`
