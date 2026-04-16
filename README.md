# ADOS

Quick reference for connecting to and using a brev.nvidia.com GPU instance.

## Key Paths

| Path | Description |
|------|-------------|
| `/models` | Model checkpoints |
| `/ComfyUI` | ComfyUI installation |
| `/LTX-2` | LTX-2 installation |
| `/mnt/gcs` | GCS bucket mount |
| `/scripts/sync_models.sh` | Manual model sync script |

---

## Access

### Web Terminal (ttyd)

Port: `7681`

```
https://web-ssh0-<instance-id>.brevlab.com
```

### ComfyUI

Port: `8188`

```
https://comfyui0-<instance-id>.brevlab.com
```

To start manually:

```bash
cd /ComfyUI
source .venv/bin/activate
python main.py --port 8188 --disable-cuda-malloc --listen 0.0.0.0
```

### JupyterLab

Use for uploading/downloading files or running notebooks.

Port: `8888`

```
https://jupyter0-<instance-id>.brevlab.com
```

---

## GCS Bucket

The bucket is auto-mounted at `/mnt/gcs` on container startup

To sync models manually:

```bash
/scripts/sync_models.sh
```
