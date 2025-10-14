# Launch NVIDIA NIM

Set you environment variable for the NVIDIA API key

`export NGC_API_KEY=nvapi-XXXXXXXX` (nvapi-XXXXXXXX is just a placehoder)

Login to NCG repo

`echo "$NGC_API_KEY" | docker login nvcr.io --username '$oauthtoken' --password-stdin`

Define and create cache directory to be used by NIM container

`export LOCAL_NIM_CACHE=~/.cache/nim`

`mkdir -p "$LOCAL_NIM_CACHE"`

Run container interactively and verify funtion

```
docker run -it --rm \
    --gpus all \
    --shm-size=16GB \
    -e NGC_API_KEY \
    -e NIM_MAX_MODEL_LEN=16324 \
    -v "$LOCAL_NIM_CACHE:/opt/nim/.cache" \
    -u $(id -u) \
    -p 8000:8000 \
    nvcr.io/nim/microsoft/phi-4-mini-instruct:1.12.0
```

Notes:
* Context length set to 16K (Due to size of A2 & L4)
* Best practice to specify tag (1.12.0) instead of 'latest'

---
## Testing the model

From a separate console, run the following to testL
```
curl -X 'POST' \
'http://0.0.0.0:8000/v1/chat/completions' \
-H 'accept: application/json' \
-H 'Content-Type: application/json' \
-d '{
    "model": "microsoft/phi-4-mini-instruct",
    "messages": [{"role":"user", "content":"Write a limerick about the wonders of GPU computing."}],
    "max_tokens": 64
}'
```
---
## Serving the model

When happy with configuration of container, run it in 'detached' mode

Note: If you launced a new ssh session, you will need to set NIM Cache variable again with:

`export LOCAL_NIM_CACHE=~/.cache/nim`

```
docker run -d \
    --name nim-phi4 \
    --restart unless-stopped \
    --gpus all \
    --shm-size=16GB \
    -e NGC_API_KEY \
    -e NIM_MAX_MODEL_LEN=16324 \
    -v "$LOCAL_NIM_CACHE:/opt/nim/.cache" \
    -u $(id -u) \
    -p 8000:8000 \
    nvcr.io/nim/microsoft/phi-4-mini-instruct:1.12.0
```
* `-d` detached mode
* `--name <container_name>` friendly name
* `--restart unless-stopped` to autostart across reboots




