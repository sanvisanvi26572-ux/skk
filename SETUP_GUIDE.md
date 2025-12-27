# 🛠️ Complete Setup Guide

Welcome to your QR-Based Restaurant Ordering System! This guide will help you get everything running.

## 📦 What's Included

Your system consists of three main components:

1. **Backend Server** - Node.js/Express with Socket.io for real-time updates
2. **Customer App** - React frontend for diners to browse and order
3. **Admin Dashboard** - React admin panel for order and menu management

## ⚙️ Installation Steps

### Step 1: Install Dependencies

From the project root directory:

```bash
npm run install-all
```

This command installs all required packages for:
- Backend
- Customer frontend
- Admin dashboard

**Expected output:**
```
✅ Installing backend dependencies...
✅ Installing customer dependencies...
✅ Installing admin dependencies...
```

### Step 2: Start the Application

Run this single command to start everything:

```bash
npm run dev
```

This starts three processes simultaneously:
- Backend server on port 5000
- Customer app on port 3000 (auto-opens browser)
- Admin dashboard on port 3001

**Alternative:** Use separate terminals

```bash
# Terminal 1
cd backend && node server.js

# Terminal 2
cd customer && npm start

# Terminal 3
cd admin && npm start
```

## 🎯 Quick Test

### Test Customer Flow:
1. Go to http://localhost:3000
2. Click "Enter Menu"
3. Browse categories
4. Add items to cart
5. Enter table number "5"
6. Click "Place Order"
7. Watch your order appear!

### Test Admin Flow:
1. Open new tab: http://localhost:3001
2. Login with username: `admin`, password: `admin`
3. See your order appear instantly!
4. Click "Start Preparing"
5. Click "Mark Ready"
6. Click "Mark Completed"

## 🔍 Verification Checklist

- [ ] Backend server running (check terminal for "Server running on port 5000")
- [ ] Customer app opens at http://localhost:3000
- [ ] Admin dashboard accessible at http://localhost:3001
- [ ] Can browse menu in customer app
- [ ] Can place orders
- [ ] Orders appear in admin dashboard
- [ ] Status updates work in real-time

## 📱 Usage Guide

### For Restaurant Staff

**Viewing Orders:**
1. Login to admin dashboard
2. Navigate to "Orders" tab
3. See all orders with status badges
4. Filter by status if needed

**Updating Order Status:**
1. Find the order in the list
2. Click appropriate button:
   - "Start Preparing" - Order is being worked on
   - "Mark Ready" - Order ready for pickup
   - "Mark Completed" - Order delivered/picked up

**Managing Menu:**
1. Go to "Menu Management" tab
2. Select a category
3. Click "Add Item" to create new items
4. Click "Edit" to modify existing items
5. Click "Delete" to remove items

### For Customers

**Placing an Order:**
1. Scan QR code (or click "Enter Menu" button)
2. Browse menu by category
3. Add items to cart
4. Review cart and enter table number
5. Click "Place Order"
6. Track order status in real-time

**Tracking Order:**
- Status updates automatically
- Icons show current stage
- Order details always visible

## 🎨 Customization

### Adding Menu Items

1. Login to admin (admin/admin)
2. Click "Menu Management"
3. Select category
4. Click "+ Add Item"
5. Fill in:
   - Name
   - Description
   - Price
   - Image URL
6. Click "Add Item"

### Changing Colors

Edit color values in CSS files:
- **Primary color**: Search for `#A0522D` in CSS files
- **Secondary**: Search for `#8B4513`
- **Accent**: Search for `#FFD700`

### Modifying Categories

Categories are defined in `backend/data/menu.json`:
```json
{
  "id": "category-id",
  "name": "Category Name",
  "items": [...]
}
```

## 🐛 Troubleshooting

### Problem: Port Already in Use

**Error:** `EADDRINUSE :::5000`

**Solution:**
```bash
# Find process using port 5000
lsof -i :5000

# Kill the process
kill -9 [PID]
```

Or change the port in the code.

### Problem: Can't Connect to Server

**Error:** `Network error` or `Failed to fetch`

**Solution:**
- Check backend is running
- Verify port 5000 is accessible
- Check firewall settings
- Look for CORS errors in console

### Problem: Socket.io Connection Failed

**Error:** `Socket.io connection failed`

**Solution:**
- Ensure backend is running first
- Check Socket.io is installed
- Verify no proxy blocking WebSocket connections

### Problem: Menu Not Loading

**Error:** Menu is empty or shows "Loading..."

**Solution:**
- Check `backend/data/menu.json` exists
- Verify backend started successfully
- Check browser console for errors
- Restart backend server

### Problem: Order Status Not Updating

**Error:** Status doesn't change in real-time

**Solution:**
- Check Socket.io is working
- Refresh both customer and admin pages
- Verify WebSocket connections in browser dev tools
- Check backend terminal for errors

## 📊 Monitoring

### Check if Services are Running

**Backend:**
```bash
curl http://localhost:5000/api/menu
```

Should return menu JSON data.

**Customer:**
Open http://localhost:3000 in browser

**Admin:**
Open http://localhost:3001 in browser

### View Logs

All services log to their respective terminals. Watch for:
- ✅ "Server running on port 5000"
- ✅ "Compiled successfully" (React apps)
- ❌ Any error messages

## 🔒 Security Notes

**Current Setup (Development):**
- Default credentials: admin/admin
- JSON file storage
- No encryption
- CORS enabled for all origins

**Before Production:**
- [ ] Change admin credentials
- [ ] Use environment variables
- [ ] Implement HTTPS
- [ ] Add rate limiting
- [ ] Use real database
- [ ] Add input validation
- [ ] Implement CSRF protection

## 📚 Next Steps

1. ✅ System is running
2. ✅ Test all features
3. 📖 Read PROJECT_OVERVIEW.md for architecture
4. 🔧 Customize for your restaurant
5. 🚀 Deploy to production when ready

## 💡 Tips

- **Best Practice**: Test in incognito/private browsing mode
- **Order Flow**: Use different browsers for customer and admin
- **Real-time Testing**: Place order as customer, update in admin immediately
- **Menu Testing**: Add new items in admin, refresh customer to see them

## 🎉 You're All Set!

Your restaurant ordering system is ready to use. Start serving customers!

For detailed documentation, see:
- README.md - Main documentation
- QUICKSTART.md - Quick start guide
- PROJECT_OVERVIEW.md - Architecture details
- INSTALL.md - Installation options

---

**Happy Ordering! 🍽️**





