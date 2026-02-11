# 💰 Savings Group Number Picker (Ajo Picker)

An interactive web-based tool for fairly selecting the order in which savings group members receive their contributions each month.

## 🎯 What is this?

This is a digital solution for traditional savings groups (also known as "Ajo", "Esusu", or "Contributory Savings"). Each month, members contribute a fixed amount, and one person receives the total pool. This tool randomly determines the order.

### Example:
- **4 members** contribute **₦150,000 each** = **₦600,000 total**
- Each member picks a card to reveal their position (1-4)
- Position 1 receives the money this month
- Position 4 receives the money last

## 🌐 Live Demo

Visit the live page here: `https://YOUR-USERNAME.github.io/savings-picker/`

## ✨ Features

- 🎴 **Interactive card flip animation** - Click to reveal your number
- 🔢 **Adjustable participants** - Add or remove members from the UI (2-20 people)
- 🔀 **Random shuffle** - Numbers are randomly placed each time
- 🔒 **Real-time sync** - Picked cards are locked for everyone (requires Firebase)
- 🚫 **No duplicate picks** - Once a card is picked, no one else can pick it
- 🎊 **Celebration effects** - Confetti when all cards are revealed
- 📱 **Mobile responsive** - Works on all devices
- 🔄 **Easy reset** - Shuffle and start again
- 🌍 **Web-based** - No app installation needed
- 🆓 **100% Free** - Firebase free tier is more than enough for small groups

## 🚀 How to Use

### **Important: Firebase Setup Required for Real-Time Sync**

To prevent multiple people from picking the same card, you need to set up Firebase (it's free!):

1. **Open the page** - Share the link with all participants
2. **Set up Firebase** - Follow the setup guide below (one-time setup)
3. **Set number of participants** - Use the +/- buttons to match your group size
4. **Each person picks a card** - Click a card to flip and reveal your number
5. **Cards sync in real-time** - Once picked, the card is locked for everyone
6. **Reset for next month** - Click "Reset & Shuffle" button

---

## 🔧 Firebase Setup (5 minutes)

### Step 1: Create Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Click **"Add project"** or select existing project
3. Give it a name (e.g., "Savings Picker")
4. Continue through the setup (disable Google Analytics if you want)

### Step 2: Create Realtime Database

1. In your Firebase project, click **"Realtime Database"** in left menu
2. Click **"Create Database"**
3. Choose your location (e.g., United States, Europe)
4. Start in **"Test mode"** (you can secure it later)
5. Click **"Enable"**

### Step 3: Get Your Configuration

1. Click the ⚙️ (Settings) icon → **"Project settings"**
2. Scroll down to **"Your apps"** section
3. Click the **Web icon** (</>)
4. Register your app with any nickname (e.g., "Savings Picker")
5. Copy the `firebaseConfig` object

### Step 4: Add Config to Your HTML

1. Open your `index.html` file
2. Find the `firebaseConfig` section (around line 285)
3. Replace the placeholder config with your actual config:

```javascript
const firebaseConfig = {
    apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
    authDomain: "your-project.firebaseapp.com",
    databaseURL: "https://your-project-default-rtdb.firebaseio.com",
    projectId: "your-project",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "123456789",
    appId: "1:123456789:web:xxxxxxxxxxxxx"
};
```

4. Save the file and commit to GitHub

### Step 5: Secure Your Database (Optional but Recommended)

1. Go back to **Realtime Database** → **Rules** tab
2. Replace the rules with:

```json
{
  "rules": {
    ".read": true,
    ".write": true,
    "savings-session-*": {
      ".read": true,
      ".write": true
    }
  }
}
```

3. Click **"Publish"**

### ✅ You're Done!

Now when anyone opens the page:
- They see the same shuffled cards
- When someone picks a card, it's locked for everyone
- Real-time synchronization across all devices
- No duplicate picks possible!

---

## 🎯 Without Firebase

If you don't set up Firebase, the page still works but:
- ❌ No real-time sync across browsers
- ❌ People can pick the same number
- ✅ Still works for single-device use (passing one phone around)

---

## 📋 Usage Tips

---

## 🌐 Hosting on GitHub Pages

### Option 1: GitHub Pages (Recommended)

1. **Fork or Clone this repository**
2. **Go to Settings** → **Pages**
3. **Select "main" branch** and "/ (root)" folder
4. **Save** and wait 1-2 minutes
5. **Share the generated URL** with your group

### Option 2: Download and Open Locally

1. Download `index.html`
2. Open it in any web browser
3. Works offline!

## 💡 Usage Tips

- 📸 **Screenshot the results** before resetting
- 📅 **Keep a record** of each month's order  
- 🔗 **Bookmark the page** for easy access
- 👥 **Pick simultaneously** - Everyone opens their own device and picks their card
- ⏰ **Set a date** - Pick the same day each month (e.g., last Friday)
- 🔄 **Daily sessions** - Cards automatically reset at midnight (new day = new session)
- 📱 **Any device works** - Mobile, tablet, or desktop
- 🌐 **No app needed** - Just share the web link

## 🛠️ Customization

You can easily customize:
- Monthly contribution amount (edit line 82 in HTML)
- Color scheme (edit CSS gradient colors)
- Card designs (modify `.card-front` and `.card-back` styles)

## 📱 Mobile Support

Fully optimized for:
- ✅ Android phones
- ✅ iPhones
- ✅ Tablets
- ✅ Desktop browsers

## 🔒 Privacy

- No data is collected or stored
- No login required
- Works completely in your browser
- Your picks are not recorded anywhere

## 🤝 Contributing

Feel free to:
- Report bugs
- Suggest features
- Submit pull requests
- Share with other savings groups

## 📄 License

Free to use and modify for your savings group needs.

## 💬 Support

If you encounter any issues:
1. Check that JavaScript is enabled in your browser
2. Try refreshing the page
3. Clear your browser cache
4. Try a different browser

## 🌟 Star This Project

If this tool helps your savings group, please ⭐ star this repository!

---

**Made with ❤️ for savings groups everywhere**

### Popular Names for This System:
- 🇳🇬 Nigeria: Ajo, Esusu
- 🇬🇭 Ghana: Susu
- 🇰🇪 Kenya: Chama
- 🇿🇦 South Africa: Stokvel
- 🇨🇲 Cameroon: Njangi
- 🇪🇹 Ethiopia: Equb
# ajo-picker
# ajo-picker
