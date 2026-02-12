# JABA References

A collaborative visual reference board for collecting and organizing creative inspiration from across the web. **Now with real-time Firebase sync!**

## ✨ Features

- 📸 Save references from Instagram, YouTube, TikTok, Vimeo, Behance, and more
- 🎨 Organize by customizable categories (Color, Motion Graphics, 3D, Creativity, etc.)
- 🔍 Fast search by title, tags, platform, or notes
- 📁 Upload images or paste from clipboard
- 🔄 **Real-time sync** - Everyone sees the same references instantly
- 👥 **Collaborative** - Multiple people can add and edit references

## 🚀 Deploy to Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/YOUR_USERNAME/jaba-references)

## 🔥 Firebase Setup (Already Done!)

The app is already configured with Firebase! The database is set to **test mode** for easy collaboration.

### ⚠️ Important: Secure Your Database

After deploying, you should update the Firestore security rules:

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Select your project: `jaba-references`
3. Go to **Firestore Database** → **Rules**
4. Replace the test rules with production rules (see below)

**Recommended Production Rules:**
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Allow read access to everyone
    match /references/{reference} {
      allow read: if true;
      allow write: if request.auth != null; // Only authenticated users can write
    }
    
    match /categories/{category} {
      allow read: if true;
      allow write: if request.auth != null;
    }
  }
}
```

**For now (Test Mode):**
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

**Note:** Test mode expires after 30 days. Update to production rules before then!

## 📦 What's Different from localStorage Version?

| Feature | localStorage | Firebase |
|---------|-------------|----------|
| **Data persistence** | Per browser only | Cloud database |
| **Collaboration** | ❌ No sharing | ✅ Real-time sync |
| **Cross-device** | ❌ No sync | ✅ Works everywhere |
| **Multiple users** | ❌ Separate data | ✅ Shared collection |

## 🛠️ Local Development

Simply open `index.html` in your browser. No build process needed!

## 📖 Usage

1. Click **+ New Reference** to add a visual reference
2. Fill in the details (title, platform, category, URL, image, tags, notes)
3. Use categories to filter your references
4. Click on any card to view full details
5. Click **+ Add Category** to create custom categories
6. **Everyone who visits sees the same references in real-time!**

## 🔐 Privacy Note

- All references are **publicly visible** to anyone with the link
- There's currently **no authentication** (test mode)
- Anyone can add, edit, or delete references
- For production use, enable Firebase Authentication

## 📝 License

MIT
