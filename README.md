# HomeKart – WhatsApp Catalogue Website

A free, static website (HTML + CSS + JavaScript). No backend, no database, no paid services.
Customers browse, fill a cart, and tap **Send order on WhatsApp**. WhatsApp opens with the order typed in;
**the customer must press Send**. You receive the order in WhatsApp (+91 90512 47072) and confirm it manually.
Products and prices are updated by you, by editing one file.

## Files
```
index.html          the page
css/styles.css      the design
js/products.js      ★ YOUR PRODUCTS, PRICES, CATEGORIES, SHOP DETAILS (edit this)
js/app.js           cart + WhatsApp logic (no need to edit)
assets/logo.png     your logo
images/products/    put your product photos here
robots.txt, sitemap.xml   for search engines (edit after publishing)
```

## 1. Preview on your computer (₹0)
1. Unzip/download the folder.
2. Double-click `index.html`. It opens in your browser. Everything works offline except WhatsApp opening.

## 2. Add or change products
Open `js/products.js` in Notepad (or any text editor). Each product is one block:
```js
{ id: "p015", name: "Plastic Tiffin Box", category: "kitchen", price: 129, stock: "in",
  image: "images/products/tiffin-box.jpg", variant: "Blue, 3 compartments",
  description: "Leak-resistant tiffin box for school and office." },
```
- `id`: must be unique (p015, p016, …).
- `category`: one of `kitchen, plastic, storage, baskets, cleaning, bathroom, other`.
- `price`: real selling price in rupees, a number only (no ₹).
- `mrp`: add ONLY if the original price is genuine, e.g. `mrp: 159,`. Otherwise leave it out.
- `stock`: `"in"`, `"low"`, `"out"` or `"ask"`.
- Delete the `sample: true` part for real products. **Remove all demo products** before launch.
- When all sample items are gone, set `showSampleNotice: false` at the top of the file.

To change a price: find the product and change the number. To remove a product: delete its block.
Rename categories at the top (`HOMEKART_CATEGORIES`). Keep each `id` matching the products.

## 3. Product photos
- Photograph on a plain white or light background, in daylight, square-ish.
- Resize to about 800×800 px and under 150 KB (free tools: squoosh.app, or phone gallery "resize").
- Save into `images/products/` and use lowercase names without spaces, e.g. `tiffin-box.jpg`.
- Point to it with `image: "images/products/tiffin-box.jpg"`.

## 4. Publish for free (GitHub Pages)
1. Create a free account at github.com.
2. Click **New repository**, name it `homekart`, set **Public**, create.
3. Click **uploading an existing file**, drag in everything inside the project folder (keep the folders), then **Commit changes**.
4. Go to **Settings → Pages**. Under *Branch* choose `main` and `/ (root)`, press **Save**.
5. After a minute your site is live at `https://YOUR-USERNAME.github.io/homekart/`.

Alternative: Cloudflare Pages (free): *Workers & Pages → Create → Pages → Upload assets*, upload the folder.

### After publishing
- In `index.html`, uncomment the canonical line and replace `YOUR-SITE-URL`.
- Do the same in `robots.txt` and `sitemap.xml`.
- Add your website link in Google Business Profile (Contact → Website).
- Optional: submit the sitemap in Google Search Console. Rankings are never guaranteed.

## 5. Updating later
Edit `js/products.js` on GitHub (click the file → pencil icon → Commit). The site updates in about a minute.
Customers may see the old version briefly because of browser caching.

## 6. Important notes
- There is no server: orders exist only as WhatsApp messages. Keep stock and prices current yourself.
- The cart is saved only on each customer's own phone.
- No payment details are collected. Payment (cash or Google Pay) is agreed on WhatsApp after you confirm.
- Hours, payments and service options match the shop's Google Business Profile. If those change, update both.
- Your Google profile showed the new phone number as "pending review". Make sure +91 90512 47072 is the number on WhatsApp.

## Final testing checklist
**WhatsApp**
- [ ] Floating green button opens a chat with +91 90512 47072.
- [ ] Add 2–3 products, open cart, tap Send order: WhatsApp shows names, quantities, line totals, subtotal.
- [ ] Message shows chosen Pickup/Delivery, name, area, notes. Nothing is sent until you press Send.
- [ ] Test on Android, iPhone, and desktop (WhatsApp Web/app).
- [ ] "Ask on WhatsApp" on a product card mentions that product only.

**Cart**
- [ ] + / − change quantity; Remove works; subtotal is correct (check by hand).
- [ ] Empty cart shows the empty message. Refresh keeps the cart.
- [ ] Out-of-stock products cannot be added.

**Catalogue**
- [ ] Search, category chips, category cards and sort all work.
- [ ] Every product name, price, stock status and photo is real and correct.
- [ ] No "Sample item" labels remain; demo notice is off.

**Links and info**
- [ ] Phone link calls the right number. Get Directions opens Google Maps at the right place.
- [ ] Address, hours (9 AM–5 PM daily), payments (cash, Google Pay) are correct everywhere.
- [ ] FAQ wording matches reality (nearby delivery, no same-day delivery, pickup options).

**Mobile / quality**
- [ ] Looks good on a small Android phone: no sideways scrolling, buttons easy to tap.
- [ ] Photos load fast; pages feel quick on mobile data.
