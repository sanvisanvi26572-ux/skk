# Installation Guide

## Quick Start (Recommended)

### Step 1: Install All Dependencies

```bash
npm run install-all
```

This will install dependencies for the root, backend, customer, and admin folders.

### Step 2: Start Everything

Open a single terminal and run:

```bash
npm run dev
```

This starts all three services:
- Backend API server
- Customer frontend (React)
- Admin dashboard (React)

### Step 3: Access the Applications

- **Customer Menu**: http://localhost:3000
- **Admin Dashboard**: http://localhost:3001
- **Backend API**: http://localhost:5000

## Manual Installation (Alternative)

If the above doesn't work, install manually:

### Backend Setup
```bash
cd backend
npm install
```

### Customer App Setup
```bash
cd customer
npm install
```

### Admin Dashboard Setup
```bash
cd admin
npm install
```

### Starting Services Manually

You'll need three terminal windows:

**Terminal 1 - Backend:**
```bash
cd backend
node server.js
```

**Terminal 2 - Customer:**
```bash
cd customer
npm start
```

**Terminal 3 - Admin:**
```bash
cd admin
npm start
```

## Default Login Credentials

**Admin Dashboard:**
- Username: `admin`
- Password: `admin`

⚠️ **Remember to change these in production!**

## Verification

Once everything is running:

1. ✅ Backend should show: "Server running on port 5000"
2. ✅ Customer app opens automatically at http://localhost:3000
3. ✅ Admin dashboard available at http://localhost:3001

## Troubleshooting

### Port Already in Use?

If you see "EADDRINUSE" errors, either:
1. Stop other processes using ports 3000, 3001, or 5000
2. Or modify the ports in the respective package.json files

### Module Not Found?

Make sure you ran `npm install` in each directory:
- Root directory
- backend/
- customer/
- admin/

### Socket.io Connection Failed?

- Ensure backend is running before starting the frontends
- Check that all services are using the same port configuration

## Next Steps

See README.md for usage instructions and features!





