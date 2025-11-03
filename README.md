# 🏟 Stadium Design Showcase — Digital Book

This is a digital “book-style” microsite for the **Macquarie Point Stadium Design Showcase**.  
It presents all display boards, videos, and supporting links from the physical event held **31 Oct – 5 Nov at the Goods Shed, Hobart**.

---

## 📁 Folder Structure

/
├── index.html ← main interactive microsite
├── assets/
│ ├── boards/ ← images of display boards (JPG/PNG)
│ ├── videos/ ← optional thumbnails or MP4s (not required if using YouTube)
│ └── plans/ ← architectural plan images
│
└── README.md ← this file

yaml
Copy code

---

## 🧱 How it Works

The microsite works like a **digital flipbook**:
- Each **display board** and **video** is a separate “page”.
- Users can navigate using **Next / Prev buttons**, keyboard arrows, or **touch-swipe**.
- The **Table of Contents (Contents ▾)** lets users jump directly to any board or video.

---

## 🖼 Adding or Updating Boards

All board images live in:
assets/boards/

css
Copy code

To display them in the book, update the `DEFAULT_BOARD_FILES` array near the top of `index.html`:

```js
const DEFAULT_BOARD_FILES = [
  "assets/boards/boards1_01.jpg",
  "assets/boards/boards1_02.jpg",
  "assets/boards/boards1_03.jpg"
];
👉 Tips

Keep filenames exactly as uploaded.

The order listed here is the order shown in the book.

JPG or PNG both work fine.

🎥 Adding or Changing Videos (YouTube)
Videos are embedded from YouTube using the embed URL format:

arduino
Copy code
https://www.youtube.com/embed/XXXXXXXXXXX
Edit the YOUTUBE_VIDEOS section in index.html:

js
Copy code
const YOUTUBE_VIDEOS = [
  { title: "Player Facilities (Brendon Gale)", url: "https://www.youtube.com/embed/XHOmBV4js_E" },
  { title: "Design Overview", url: "https://www.youtube.com/embed/eX2qFMC8cFo" },
  { title: "Site Preparation", url: "https://www.youtube.com/embed/zpOULjyy-n8" }
];
To get the embed URL:

Open your video on YouTube.

Click Share → Embed → Copy URL (it looks like https://www.youtube.com/embed/...).

Paste that in the url: value above.

If you prefer, you can host MP4s locally instead — just upload them into assets/videos/ and replace the YouTube entries with your own structure. But YouTube is recommended for file size reasons.

🗺 Adding Architectural Plans
Plans can be displayed later in the dedicated section.
For now, drop them into:

bash
Copy code
assets/plans/
You can later add a small gallery or preview function using the existing placeholder text.

🌐 Publishing to Netlify
Option 1 — Connect GitHub (Recommended)
Go to https://app.netlify.com → New site from Git.

Connect your GitHub account.

Select your repository.

Leave build command blank.

Set publish directory to:

Copy code
.
Click Deploy site.

Netlify will instantly publish your book and give you a live URL (e.g. https://stadium-showcase.netlify.app).

Option 2 — Manual Upload
If you prefer, drag and drop the entire folder (including index.html and assets) into https://app.netlify.com/drop.

🧭 Navigation Controls
Action	What it Does
Next / Prev buttons	Move between pages
Left / Right arrow keys	Keyboard navigation
Swipe left / right	Mobile touch navigation
Contents ▾ button	Jump to any page instantly

🪶 Branding
All styles follow Macquarie Point Development Corporation brand colours and tone.
If you wish to change these, edit the colour variables near the top of index.html:

css
Copy code
:root {
  --bg:#0a2433;
  --accent:#c8a86b;
}
🧰 Support & Maintenance
If editing online via GitHub:

Click the pencil icon ✏️ on any file to edit.

Commit your changes (GitHub will automatically save a version).

Netlify redeploys automatically when changes are committed.

If editing locally:

bash
Copy code
git clone https://github.com/yourusername/stadium-design-showcase.git
cd stadium-design-showcase
# make edits
git add .
git commit -m "Update boards and videos"
git push
🪙 Credits
Built and maintained by Macquarie Point Development Corporation (MPDC)
Design and structure adapted from internal MPDC digital projects.
© 2025 MPDC. All rights reserved.
