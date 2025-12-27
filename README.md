# 🍽️ QR-Based Restaurant Ordering System

A beautiful, modern restaurant ordering system with real-time updates, featuring a customer-facing menu and admin dashboard.

## Features

### Customer Features
- 📱 **QR Code Entry** - Smooth entry to the menu
- 🍽️ **Menu Browsing** - Browse items by category with beautiful imagery
- 🛒 **Shopping Cart** - Add/remove items with live total calculation
- 📝 **Order Placement** - Enter table number and place orders
- 📊 **Real-Time Tracking** - Track order status with live updates
- 💳 **Modern UI** - Beautiful, food-focused design with smooth animations

### Admin Features
- 🔐 **Secure Login** - Protected admin access
- 📋 **Order Management** - View and manage all orders in real-time
- 🍴 **Menu Management** - Add, edit, and delete menu items
- ⚡ **Live Updates** - See new orders appear instantly
- 🎯 **Status Tracking** - Update order status (pending → preparing → ready → completed)

## Design System

- **Colors**: Warm terracotta (#A0522D), deep burgundy (#8B4513), cream (#FDF5E6), golden accents (#FFD700)
- **Typography**: Modern, readable fonts
- **Animations**: Smooth transitions and hover effects
- **Imagery**: Beautiful food photography from Unsplash

## Tech Stack

### Backend
- Node.js + Express.js
- Socket.io for real-time updates
- JSON file-based storage
- JWT authentication

### Frontend
- React.js
- Socket.io Client
- CSS3 with animations
- Responsive design

## Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn

### Installation

1. **Clone or download the project**

2. **Install dependencies**
   ```bash
   npm run install-all
   ```

3. **Start the development servers**
   ```bash
   npm run dev
   ```

   This will start:
   - Backend server on `http://localhost:5000`
   - Customer app on `http://localhost:3000`
   - Admin dashboard on `http://localhost:3001`

### Manual Start (Alternative)

If you prefer to run services separately:

```bash
# Terminal 1 - Backend
cd backend && npm install && node server.js

# Terminal 2 - Customer
cd customer && npm install && npm start

# Terminal 3 - Admin
cd admin && npm install && npm start
```

### Run locally (Windows PowerShell)

If you're on Windows PowerShell (default for this workspace), run these commands in separate terminals. They use PowerShell syntax to set temporary environment variables for a single command.

```powershell
# Install dependencies (root)
npm install

# Start backend (example: override port if 5000 is in use)
$env:PORT=5000; npx nodemon backend/server.js

# Start customer app (dev)
cd customer; npm install; npm start

# Start admin app (dev)
cd admin; npm install; npm start
```

## Usage

### For Customers

1. Visit `http://localhost:3000`
2. Click "Enter Menu"
3. Browse menu items by category
4. Add items to your cart
5. Enter your table number
6. Place your order
7. Track your order status in real-time

### For Administrators

1. Visit `http://localhost:3001`
2. Login with credentials:
   - Username: `admin`
   - Password: `admin`
3. View and manage orders in the "Orders" tab
4. Update order status as you progress through preparation
5. Manage menu items in the "Menu Management" tab

## Project Structure

```
qr-restaurant-system/
├── backend/
│   ├── server.js           # Express server with Socket.io
│   ├── data/               # JSON storage files
│   └── package.json
├── customer/               # Customer-facing React app
│   ├── src/
│   │   ├── App.js
│   │   └── components/
│   └── package.json
├── admin/                  # Admin dashboard React app
│   ├── src/
│   │   ├── App.js
│   │   └── components/
│   └── package.json
└── package.json            # Root package.json
```

## Default Menu

The system comes with a sample menu featuring:
- Appetizers (Bruschetta, Calamari)
- Main Courses (Salmon, Steak, Pasta)
- Desserts (Chocolate Lava Cake, Tiramisu)
- Beverages (Lemonade, Wine)

## Real-Time Features

The system uses Socket.io for real-time updates:
- New orders appear instantly in admin dashboard
- Order status changes are pushed to customers immediately
- Menu updates sync across all clients

## Customization

### Add Menu Items
1. Login to admin dashboard
2. Select a category
3. Click "Add Item"
4. Fill in the form and submit

### Modify Colors
Edit the CSS files:
- Customer: `customer/src/App.css` and component CSS files
- Admin: `admin/src/components/*.css`

### Change Ports
Edit the respective package.json files to set custom ports.

## Security Notes

⚠️ **For Production Use:**
- Change default admin credentials
- Implement proper authentication
- Use a real database (PostgreSQL, MongoDB)
- Add HTTPS support
- Implement rate limiting
- Add input validation and sanitization

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Troubleshooting

**Port already in use?**
- Change ports in package.json files
- Or stop the process using the port

**Socket.io connection issues?**
- Ensure backend is running
- Check firewall settings
- Verify CORS configuration

**Menu not loading?**
- Check backend server is running
- Verify data directory exists
- Check browser console for errors

## License

MIT License - Feel free to use this project for your restaurant!

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

---

**Enjoy building your restaurant ordering system! 🍽️✨**





