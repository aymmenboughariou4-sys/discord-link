# LazY Discord Server Landing Page

A single-file landing page for the LazY Discord server. Hero section with server icon, banner, name and a join button, plus a gallery of wallpaper previews that link straight to the invite.

## Files

- `index.html` — the whole site (HTML, CSS and JS in one file, no build step, no dependencies to install)

## Running it locally

Just open `index.html` in a browser. No server needed.

## Customizing

All the editable bits live near the top of the `<script>` block at the bottom of `index.html`.

### Invite link

```js
const INVITE_LINK = "https://discord.gg/PbRxFFSqCM";
```

Every "Join the server" button and every wallpaper tile links here.

### Banner

```js
const BANNER_URL = "";
```

Paste an image or gif URL, or a Google Drive share link (auto-converted). Leave it as `""` to hide the banner and show just the icon.

### Wallpapers

```js
const wallpapers = [
  { src: null, alt: "Wallpaper 1", hue: 1 },
  ...
];
```

- `src`: a direct image URL, or a Google Drive share link (auto-converted). Leave as `null` to show a placeholder tile instead.
- `alt`: description for accessibility/SEO.
- `hue`: 1, 2 or 3 — only used for placeholder tile coloring, ignored once `src` is set.

Add or remove entries from the array to change how many tiles show up.

### Google Drive links

If you use a Drive link for the banner or a wallpaper:

1. Right-click the file in Drive → **Share**
2. Set **General access** to **Anyone with the link**, role **Viewer**
3. Paste the regular share link (`https://drive.google.com/file/d/FILE_ID/view?usp=...`) straight into `BANNER_URL` or a wallpaper's `src` — the code converts it automatically

Drive hotlinking can be unreliable long-term (Google may throttle or change behavior without notice). If images stop loading or gifs won't animate, move that file to a host built for hotlinking (Imgur, Cloudinary, or your own domain once this site is live) instead of troubleshooting Drive further.

### Server name and icon

Both are set directly in the HTML, in the `.hero-media` block:

```html
<img class="server-icon" src="ICON_URL" alt="...">
...
<h1 class="server-name">LazY︱Wallpapers・Icons・Gifs・Banners・EN</h1>
```

## Before launch

- [ ] Connect a custom domain
- [ ] Add a favicon
- [ ] Remove any "made with AI" badge if one gets added by a hosting platform
- [ ] Add real content to `privacy.html` and `terms.html` (currently just linked from the footer, not created)
- [ ] Swap remaining placeholder wallpaper tiles for real images
- [ ] Double-check the Discord icon/banner images aren't violating anyone's copyright before going public
