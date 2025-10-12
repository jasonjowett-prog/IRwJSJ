# International Relations with J. S. Jowett - Podcast Player

A beautiful, interactive podcast player for Google Sites featuring your Google NotebookLM podcasts.

## Features

- 🎵 Audio playback with progress bar and volume control
- 🖼️ Custom episode cover images
- 💬 Direct links to Google NotebookLM for interactive chat with AI podcast hosts
- 📄 Additional resource links for each episode
- 📱 Fully responsive design
- ⌨️ Keyboard shortcuts (Space to play/pause)
- ↪️ Auto-play next episode

## Setup Instructions for Google Sites

### Step 1: Prepare Your Files

1. **Add Episode Cover Images** (400x400px PNG recommended)
   - Create or design cover images for each episode
   - Name them: `episode1-cover.png`, `episode2-cover.png`, etc.
   - Upload to a public hosting service (Google Drive, Imgur, or GitHub)

2. **Host Your Audio Files**
   - Your podcast audio files are already in this directory
   - Upload them to Google Drive or another hosting service
   - For Google Drive:
     - Right-click file → Share → Change to "Anyone with the link"
     - Get the shareable link
     - Convert to direct download link format:
       ```
       https://drive.google.com/uc?export=download&id=FILE_ID
       ```
     - Extract FILE_ID from the share link (between `/d/` and `/view`)

3. **Get Your Google NotebookLM Links**
   - Open each podcast in Google NotebookLM
   - Copy the notebook URL from your browser address bar
   - It should look like: `https://notebooklm.google.com/notebook/abc123xyz`

### Step 2: Update the Code

1. **Edit index.html** - Update the episode data (around line 389):

   ```javascript
   const episodes = [
       {
           id: 1,
           title: "Your Episode Title",
           audioUrl: "YOUR_AUDIO_FILE_URL_HERE",  // Direct link to audio
           coverImage: "YOUR_COVER_IMAGE_URL_HERE",  // Direct link to image
           duration: "26:45",
           links: [
               {
                   title: "💬 Chat with this Podcast",
                   url: "YOUR_NOTEBOOKLM_LINK_HERE",
                   description: "Interact with AI hosts - ask questions and explore topics in real-time",
                   type: "notebooklm"
               }
           ]
       }
   ];
   ```

2. **Replace these placeholders:**
   - `YOUR_AUDIO_FILE_URL_HERE` → Direct link to your .m4a file
   - `YOUR_COVER_IMAGE_URL_HERE` → Direct link to your cover image
   - `YOUR_NOTEBOOKLM_LINK_HERE` → Your Google NotebookLM notebook URL

### Step 3: Deploy to Google Sites

#### Option A: Embed from GitHub (Recommended)

1. **Create a GitHub Repository:**
   - Go to https://github.com/new
   - Name it (e.g., `ir-podcast-player`)
   - Make it public
   - Upload your `index.html` file

2. **Use GitHub Pages:**
   - Go to repository Settings → Pages
   - Under "Source", select "main" branch
   - Click Save
   - Your site will be at: `https://YOUR_USERNAME.github.io/ir-podcast-player/`

3. **Embed in Google Sites:**
   - Edit your Google Site
   - Click "Insert" → "Embed"
   - Paste your GitHub Pages URL
   - Adjust the iframe height (recommended: 900px)

#### Option B: Direct Embed

1. **Copy the HTML:**
   - Open `index.html`
   - Copy the entire contents

2. **Embed in Google Sites:**
   - Edit your Google Site
   - Click "Insert" → "Embed"
   - Click "Embed code"
   - Paste your HTML
   - Click "Next" → "Insert"

> **Note:** Google Sites may have limitations on embedded HTML. If you encounter issues, use Option A (GitHub Pages).

### Step 4: Test Your Player

1. Visit your Google Site
2. Click on an episode to play
3. Test the "Chat with this Podcast" button
4. Verify all audio files play correctly

## Customization

### Change Colors

Edit the CSS gradient colors in `index.html`:

```css
/* Main gradient (lines 16, 31, 99, 143) */
background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%);

/* Change to your preferred colors */
background: linear-gradient(135deg, #YOUR_COLOR_1 0%, #YOUR_COLOR_2 100%);
```

### Add More Episodes

Add new episode objects to the `episodes` array:

```javascript
{
    id: 3,
    title: "Your New Episode",
    description: "Episode description here",
    audioUrl: "path/to/audio.m4a",
    coverImage: "path/to/cover.png",
    duration: "30:00",
    links: [
        {
            title: "💬 Chat with this Podcast",
            url: "https://notebooklm.google.com/notebook/...",
            description: "Interact with AI hosts",
            type: "notebooklm"
        },
        {
            title: "📄 Research Paper",
            url: "https://link-to-paper.pdf",
            description: "Original research",
            type: "resource"
        }
    ]
}
```

### Add More Resource Links

Each episode can have multiple links:

```javascript
links: [
    {
        title: "💬 Chat with this Podcast",
        url: "...",
        type: "notebooklm"  // Shows in green with special styling
    },
    {
        title: "📄 Source Materials",
        url: "...",
        type: "resource"  // Shows in gray
    },
    {
        title: "📖 Related Article",
        url: "...",
        type: "resource"
    }
]
```

## What is the "Chat with this Podcast" Feature?

The **"💬 Chat with this Podcast"** button links to your Google NotebookLM notebook, which allows visitors to:

- 🗨️ **Ask questions** to the AI podcast hosts in real-time
- 🔍 **Explore topics** deeper than the podcast covers
- 💡 **Get clarifications** on complex concepts
- 🎯 **Jump to specific sections** they're interested in
- 🤝 **Have a conversation** with the AI about the podcast content

This transforms your podcast from passive listening into an **interactive learning experience**!

## Troubleshooting

### Audio Won't Play
- Ensure your audio files are publicly accessible
- Check that URLs are direct download links, not preview pages
- Test the audio URL directly in your browser

### Images Not Loading
- Verify image URLs are publicly accessible
- Use direct image links (ending in .png, .jpg, etc.)
- Check image file permissions

### Embed Not Working in Google Sites
- Google Sites has restrictions on embedded content
- Use GitHub Pages method instead (Option A)
- Ensure no blocked scripts or iframes

### NotebookLM Link Not Working
- Make sure your notebook is set to "Anyone with the link"
- Copy the full URL from your browser
- Test the link in an incognito window

## Current Episodes

1. **Marx's Paradox: Why the Communist Manifesto's 'Guaranteed Reality' Never Came to Pass**
   - File: `Marx's_Paradox__Why_the_Communist_Manifesto's_'Guaranteed_Reali.m4a`
   - Duration: ~26 minutes

2. **North Korea, Nukes, and Narratives: Why Constructivism Beats Neorealism**
   - File: `North_Korea,_Nukes,_and_Narratives__Why_Constructivism_Beats_Ne.m4a`
   - Duration: ~27 minutes

## Support

For issues or questions about:
- Google Sites: https://support.google.com/sites
- Google NotebookLM: https://support.google.com/notebooklm
- This player: Check the HTML comments in index.html

---

**Enjoy your interactive podcast experience!** 🎙️✨
