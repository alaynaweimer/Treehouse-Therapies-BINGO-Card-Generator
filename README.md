# Team Bingo Card Generator - Setup Guide

## Quick Start

### Step 1: Set Up Your Google Sheet

**Tab 1: Sheet1** (Bingo Items)
Put your bingo items in Column A:

| A |
|---|
| Has a pet at home |
| Drinks coffee every morning |
| Has worked here 5+ years |
| ... (need at least 24 items) |

**Tab 2: Settings** (Theme Control)
Create a new tab called "Settings" with:

| A |
|---|
| Theme |
| Christmas |

**Available Themes:**
- Christmas (green & red)
- Valentine (pink & red)
- Halloween (orange & purple)
- Easter (purple & teal)
- Summer (blue & orange)
- Thanksgiving (brown & orange)
- StPatricks (green & gold)
- Treehouse (teal & orange - default brand colors)

Just change the theme name in cell A2 to switch the entire look!

### Step 2: Share Your Sheet

1. Open your Google Sheet
2. Click **Share** (top right)
3. Change to **"Anyone with the link can view"**
4. Click **Done**

### Step 3: Get Your Sheet ID

Your Sheet ID is in the URL:
```
https://docs.google.com/spreadsheets/d/[THIS-IS-YOUR-SHEET-ID]/edit
```

### Step 4: Configure the HTML File

Open `index.html` and find the CONFIGURATION section at the top of the `<script>`:

```javascript
// Your Google Sheet ID (from the URL)
const SHEET_ID = 'YOUR_SHEET_ID_HERE';

// The name of the sheet/tab containing the bingo items
const SHEET_NAME = 'Sheet1';

// Column that contains the bingo items (A = 0, B = 1, etc.)
const ITEMS_COLUMN = 0;

// Does your sheet have a header row? Set to true to skip row 1
const HAS_HEADER = true;
```

Replace `YOUR_SHEET_ID_HERE` with your actual Sheet ID.

### Step 5: Upload to GitHub

1. Create a new GitHub repository (e.g., `team-bingo`)
2. Set it to **Public**
3. Upload the HTML file as `index.html`
4. Go to **Settings → Pages → Source: main branch**
5. Your tool will be live at: `https://yourusername.github.io/team-bingo/`

---

## How It Works

1. **Team member opens the link** on their phone or computer
2. **Enters their name** - this seeds their unique card
3. **Gets their personalized bingo card** - same name always = same card
4. **Clicks squares** to mark them off during the activity
5. **Prints** if they want a paper version

### Key Features

- ✅ **Unique cards per person** - Each name generates a different arrangement
- ✅ **Consistent cards** - Same name always produces the same card
- ✅ **Interactive** - Click to mark squares on screen
- ✅ **Printable** - Clean print layout for paper play
- ✅ **Mobile-friendly** - Works great on phones
- ✅ **Auto-detects BINGO** - Celebrates when you get 5 in a row!
- ✅ **FREE space** - Center square is always FREE

---

## Google Sheet Tips

### Example Bingo Items

**Team/Work Bingo:**
- Has been here over 5 years
- Works remotely
- Has a standing desk
- Drinks tea instead of coffee
- Has kids
- Born in a different state
- Plays a musical instrument
- etc.

**Event/Holiday Bingo:**
- Wearing red
- Brought homemade food
- Has traveled internationally this year
- Can name all the reindeer
- Has a live Christmas tree
- etc.

### Updating Items

Just edit your Google Sheet - changes appear immediately when someone generates a new card.

---

## Troubleshooting

**"Unable to load bingo items" error:**
- Make sure sheet is shared as "Anyone with link can view"
- Verify Sheet ID is correct
- Check that sheet/tab name matches exactly

**"Need at least 24 items" error:**
- Add more items to your Google Sheet (need 24+)

**Cards look the same:**
- Names are case-sensitive ("John" vs "john" = different cards)
- Make sure each person enters a unique name

---

## Customization

### Change Colors

Edit the CSS variables at the top of the `<style>` section:

```css
:root {
    --teal: #008080;
    --orange: #FF6B35;
    --yellow: #FFD700;
    --red: #E63946;
}
```

### Change Title

Find and edit the header section:

```html
<h1>🎯 Team Bingo</h1>
<p>Enter your name to generate your unique bingo card!</p>
```

---

## Questions?

The tool is self-contained - just one HTML file that connects to your Google Sheet. Share the GitHub Pages link with your team and they're ready to play!
