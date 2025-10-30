# 🚀 Simple Startup Guide - Pulse System

## What is Pulse?
Pulse is a Smart Venue Automation System that monitors your space using sensors for temperature, humidity, people counting, sound levels, and music detection.

---

## 📦 First Time Setup

### Option 1: One-Line Install (Raspberry Pi)
```bash
curl -fsSL https://raw.githubusercontent.com/Opentab1/thefinale2/main/install.sh | sudo bash
```

### Option 2: Manual Install
```bash
git clone https://github.com/Opentab1/thefinale2.git
cd thefinale2
sudo bash install.sh
```

---

## ▶️ Starting the System

### Quick Start (Recommended)
```bash
./START_HERE.sh
```
This will:
- ✅ Start the Pulse Hub
- ✅ Start the Dashboard
- ✅ Open your browser automatically
- ✅ Show debug output in terminal

### Alternative: Dual Terminal Mode
```bash
./start_pulse_dual.sh
```
Opens two separate terminals for Hub and Dashboard.

---

## 🌐 Accessing the Dashboard

Once started, open your browser to:
```
http://localhost:8080
```

You'll see:
- 👥 Live occupancy count
- 🌡️ Temperature & humidity
- 💡 Light levels
- 🔊 Sound levels
- 🎵 Currently playing music

---

## ⏹️ Stopping the System

Press **Ctrl+C** in the terminal, or run:
```bash
pkill -f "python.*hub/main.py"
pkill -f "python.*dashboard/api/server.py"
```

---

## 🔧 Basic Troubleshooting

### Check if sensors are connected:
```bash
# Camera
ls /dev/video*

# I2C sensors (BME280)
i2cdetect -y 1

# Microphone
arecord -l
```

### View logs:
```bash
tail -f /var/log/pulse/hub.log
tail -f /var/log/pulse/hub-error.log
```

### Configuration:
Edit settings in:
```
/workspace/config/config.yaml
```

---

## 📋 System Requirements

**Hardware:**
- Raspberry Pi 4 or 5
- Camera (Pi Camera or USB webcam)
- Microphone (USB)
- BME280 sensor (optional)
- Internet connection

**Software:**
- Raspberry Pi OS (64-bit)
- Python 3.9+
- Node.js 16+

---

## 🆘 Need Help?

1. **Check terminal output** - Shows detailed error messages
2. **Check logs** - Located in `/var/log/pulse/`
3. **Review documentation:**
   - `HOW_TO_START.md` - Detailed startup guide
   - `TROUBLESHOOTING.md` - Common issues and solutions
   - `README.md` - Full project documentation

---

## ⚡ Quick Commands Reference

| Action | Command |
|--------|---------|
| Start system | `./START_HERE.sh` |
| Stop system | Press `Ctrl+C` |
| View logs | `tail -f /var/log/pulse/hub.log` |
| Check status | Look at terminal output |
| Access dashboard | Open `http://localhost:8080` |
| Edit config | `nano /workspace/config/config.yaml` |

---

**That's it!** Start the system with `./START_HERE.sh` and open `http://localhost:8080` in your browser. 🎉
