# Velvet Nails

A responsive, single-page salon website. All styling, JavaScript, the logo and photos are included in `index.html`. No build, packages, external fonts or paid hosting are required.

## Publish for free with GitHub Pages

1. Create a **public** GitHub repository and upload `index.html` to its root.
2. In the repository, open **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose your branch (usually `main`), the **/ (root)** folder, and **Save**.
5. Once deployment finishes, GitHub shows the live address on that page, normally `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

The site works under a repository subpath and can also be opened locally by double-clicking `index.html`.

## Add online booking

Near the bottom of `index.html`, replace the empty value:

```js
const BOOKING_URL = "";
```

with the salon's full HTTPS Setmore URL. All booking links and the booking section update automatically. Before configuration, links go to an honest "coming soon" section, not another salon's booking page. An invalid configured URL reports an error in the browser console and displays an unavailable notice.

## Update gallery photos

The five supplied photos are optimized and embedded as data URLs, so `index.html` remains the only file needed for the website. To replace or add a photo, find the `.gallery-card` figures and use a resized JPEG or PNG as a `data:image/...;base64,...` URL in the image's `src`. Update the image's descriptive `alt` text, dimensions and caption to match. The hero uses a separately embedded copy of one gallery photo; update the `.hero-image` separately when changing it.

For example, on Windows PowerShell, copy a JPEG data URL to the clipboard:

```powershell
$bytes = [System.IO.File]::ReadAllBytes('C:\path\to\photo.jpg')
Set-Clipboard -Value ("data:image/jpeg;base64," + [Convert]::ToBase64String($bytes))
```

Resize photos before embedding (around 900 pixels wide is sufficient) to keep the page download manageable. The logo is also embedded in the header and footer.

## Content

- Address: 100 Moseley Avenue, Coundon, Coventry CV6 1HQ.
- Contact: 07309 356789 and velvetnailsstudio01@gmail.com.
- Prices were transcribed from the supplied menu. The third extensions column is a **new set including removal**, pedicure with gel is **£38**, and the crossed-out nail repair entry is omitted, as confirmed.
- Opening hours, social profiles and customer reviews are intentionally omitted until supplied.
- The visit section includes an embedded Google Map. **Get directions** opens Google Maps with the full address, including if the embed cannot load.
- The embedded map loads from Google when visitors reach the visit section. Google may collect visitor data or use cookies; all other site assets are self-contained.
