# Kyle Vance Photography

A dark, cinematic photography portfolio site with three gallery sections and a contact page. Built as a static site — no build tools required. Runs directly on GitHub Pages.

---

## File Structure

```
kyle-vance-photography/
├── index.html          ← Cover page (three-panel homepage)
├── gallery.css         ← Shared styles for gallery pages
├── contact.html        ← Contact page
├── travel/
│   └── index.html      ← Travel gallery
├── portraits/
│   └── index.html      ← Portraits gallery
└── dailys/
    └── index.html      ← Dailys gallery
```

---

## Adding Your Photos

Each gallery page has 8 placeholder slots. To add images:

1. **Put your images** inside the relevant folder:
   - Travel photos → `travel/`
   - Portrait photos → `portraits/`
   - Daily photos → `dailys/`

2. **Uncomment the `<img>` tags** in each gallery page and update the `src`:
   ```html
   <!-- Before -->
   <!-- <img src="img-1.jpg" alt="Travel 01"> -->

   <!-- After -->
   <img src="img-1.jpg" alt="Travel 01">
   ```

3. To add **more than 8 images**, copy and paste an existing `<div class="gallery-item">` block.

4. To use a photo as the **panel background** on the homepage, replace the CSS gradient in `index.html`:
   ```css
   /* Before */
   #panel-travel .panel-bg {
     background-image: linear-gradient(...);
   }

   /* After */
   #panel-travel .panel-bg {
     background-image: url('travel/your-cover-photo.jpg');
   }
   ```

---

## Customization

### Contact page
- Update your location in `contact.html` (marked with `— Add your location`)
- Update social media links (Instagram, VSCO, 500px) with your real profile URLs

### Gallery descriptions
- Each gallery page has a short intro paragraph — update to fit your style

---

## Deploying to GitHub Pages

### First time setup

1. **Create a new GitHub repository** at [github.com/new](https://github.com/new)
   - Name it something like `photography` or `kyle-vance-photography`
   - Set it to **Public**
   - Do NOT initialize with a README (you already have one)

2. **Push this folder** to your new repo:
   ```bash
   cd kyle-vance-photography
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to your repo on GitHub
   - Click **Settings** → **Pages** (left sidebar)
   - Under "Source", select **Deploy from a branch**
   - Branch: `main`, Folder: `/ (root)`
   - Click **Save**

4. Your site will be live in ~1 minute at:
   `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

### Updating your site

After making changes locally:
```bash
git add .
git commit -m "Add new travel photos"
git push
```
GitHub Pages will automatically redeploy within ~1 minute.

### Custom domain (optional)

If you own a domain like `kylevance.com`:
1. In your repo, go to **Settings → Pages**
2. Enter your domain under "Custom domain" and click Save
3. Add a `CNAME` record with your DNS provider pointing to `YOUR_USERNAME.github.io`

---

## Lightbox

Clicking any photo opens a fullscreen lightbox. Press `Escape` or click anywhere outside the image to close. (Only works once you've added real `<img>` tags — placeholder tiles won't open a lightbox.)
