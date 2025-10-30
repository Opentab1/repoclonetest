# TheFinale2 — Simple Startup Guide

This repo includes a packaged release (`thefinale2-main.zip`). Use one of the options below.

## Option A — Raspberry Pi (one‑line install)
Run on a Raspberry Pi (64‑bit OS) to install, configure services, and reboot:

```bash
oùrl -fsSL https://raw.githubusercontent.com/Opentab1/thefinale2/main/install.sh | sudo bash
```

After reboot, the setup wizard opens at `http://localhost:9090`, and the dashboard runs at `http://localhost:8080`.

## Option B — Local run from this repo (Linux/macOS)
Run the system directly from the included ZIP without modifying any files beyond your machine’s environment.

1) Unpack the app
```bash
unzip thefinale2-main.zip
cd thefinale2-main
```

2) Python backend
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

3) Build the dashboard UI (Vite + React)
```bash
cd dashboard/ui
npm install
npm run build
cd ../../
```

4) Start the integrated runner (Hub + API + serve built UI)
```bash
python run_pulse_system.py
```
- Open `http://localhost:8080` for the dashboard.
- Press Ctrl+C to stop.

Notes:
- If you prefer, you can try the helper script after installing deps: `./START_HERE.sh`.
- Configuration lives in `config/config.yaml` inside the unpacked folder.
- If you skip the UI build, the API will still start, but the root URL returns a small JSON (`{"ui":"not-built"}`).

## Troubleshooting
Inside the unpacked folder (`thefinale2-main/`):
- `TROUBLESHOOTING.md` and `TROUBLESHOOTING_SENSORS.md` for common issues
- `HOW_TO_START.md`, `QUICKSTART.md`, `QUICK_START_GUIDE.md` for detailed guidance

## Requirements
- Raspberry Pi path (Option A): Raspberry Pi OS 64‑bit, sudo
- Local path (Option B): Python 3.10+, Node.js 18+, npm, unzip
