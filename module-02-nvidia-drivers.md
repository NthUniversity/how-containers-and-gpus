# Install NVIDIA Drivers #

Add repo for drivers

`sudo add-apt-repository -y ppa:graphics-drivers/ppa`

Update Catalog

`sudo apt update`

List avaialable drivers

`ubuntu-drivers devices`

Install drivers

`sudo apt install -y nvidia-driver-580-server `

Driver Version Reference: https://docs.nvidia.com/datacenter/tesla/drivers/#supported-drivers-and-cuda-toolkit-versions

Reboot

`sudo reboot now`

After logging in again, use NVIDIA's System Management Interface to verify funtionality

`nvidia-smi`

```
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 580.65.06              Driver Version: 580.65.06      CUDA Version: 13.0     |
+-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA A2                      Off |   00000000:07:00.0 Off |                    0 |
|  0%   44C    P0             22W /   60W |       0MiB /  15356MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+

+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI              PID   Type   Process name                        GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|  No running processes found                                                             |
+-----------------------------------------------------------------------------------------+
```
