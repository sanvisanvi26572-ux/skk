# Network Access Guide

Your restaurant ordering system is now configured to work on your local network, allowing access from phones, tablets, and other devices on the same Wi-Fi network.

## 🌐 Finding Your Network IP Address

### Windows:
1. Open Command Prompt (press `Win + R`, type `cmd`, press Enter)
2. Type: `ipconfig`
3. Look for **IPv4 Address** under your active network adapter (usually "Wireless LAN adapter Wi-Fi" or "Ethernet adapter")
4. Your IP will look like: `192.168.1.5` or `10.212.123.38`

### Mac/Linux:
1. Open Terminal
2. Type: `ifconfig` or `ip addr`
3. Look for `inet` address (usually starts with `192.168` or `10.`)

## 📱 Access URLs

When you run `npm run dev`, you'll see output like:
```
[1]   Local:            http://localhost:3001
[1]   On Your Network:  http://10.212.123.38:3001
```

### Use These URLs:

**Customer App (for phones/tablets):**
- Network: `http://10.212.123.38:3001`
- Local: `http://localhost:3001` (only on your computer)

**Admin Dashboard:**
- Network: `http://10.212.123.38:3002`
- Local: `http://localhost:3002` (only on your computer)

**Backend API:**
- Network: `http://10.212.123.38:5000`
- Local: `http://localhost:5000` (only on your computer)

## 🔧 How It Works

The apps automatically detect:
- **If accessed via localhost** → Connect to `http://localhost:5000`
- **If accessed via network IP** → Connect to `http://<network-ip>:5000`

This means:
- ✅ Access from your phone using the network IP works perfectly
- ✅ Access from your computer using localhost still works
- ✅ All API calls and WebSocket connections use the correct backend URL

## 🧪 Testing

1. **Start the project:**
   ```bash
   npm run dev
   ```

2. **Note the network IP** shown in the terminal output

3. **On your phone (same Wi-Fi):**
   - Open browser
   - Go to: `http://<your-network-ip>:3001`
   - Example: `http://10.212.123.38:3001`
   - The menu should load and work perfectly!

4. **For admin (from another device):**
   - Go to: `http://<your-network-ip>:3002`
   - Login with: `admin` / `admin`

## 🔒 Firewall Settings

If you can't access from other devices:

### Windows:
1. Open Windows Defender Firewall
2. Click "Allow an app or feature through Windows Firewall"
3. Make sure Node.js is checked for both Private and Public networks
4. Or temporarily disable firewall for testing

### Mac:
1. System Preferences → Security & Privacy → Firewall
2. Click "Firewall Options"
3. Allow Node.js

## ⚠️ Important Notes

- **All devices must be on the same Wi-Fi network**
- The IP address may change when you reconnect to Wi-Fi
- Check the terminal output after starting to see the current network IP
- For production, you'll need to deploy to a server with a static IP or domain

## 🎯 Quick Start

1. Start: `npm run dev`
2. Check terminal for: "On Your Network: http://..."
3. Use that URL on your phone!
4. Done! 🎉

---

**Example:**
If your terminal shows:
```
On Your Network:  http://10.212.123.38:3001
```

Use `http://10.212.123.38:3001` on your phone browser!

