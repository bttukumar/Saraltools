# Saral

Small tools for money, files and everyday work. One static page, no build step, no backend. Everything runs in the browser, so files and numbers never leave the user's device.

## Tools

- **Money:** EMI calculator, SIP calculator, income tax (new vs old regime, FY 2026-27), retirement planner
- **Files:** PDF toolkit (merge, extract or remove pages, split to zip, images to PDF), image toolkit (resize, compress, convert, fit under a KB limit)
- **Everyday:** unit and currency converter, planner (tasks, habits, journal), password generator
- **Make:** resume builder, GST invoice generator, QR code (link, UPI, Wi-Fi) and barcode generator

## Run it

Open `index.html` in a browser, or serve the folder with any static server:

```
python3 -m http.server 8000
```

## Publish on GitHub Pages

1. Create a repository and add `index.html` (and this README) to the root.
2. Go to **Settings > Pages**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
3. Your site goes live at `https://<your-username>.github.io/<repo-name>/`.

## Notes

- Helper libraries load on demand from cdnjs, with jsDelivr as a fallback: pdf-lib, JSZip, qrcodejs, JsBarcode. The typeface loads from Google Fonts.
- Currency rates are an offline snapshot (20 Sep 2026) and can be edited in the tool. Update `RATE_DATE` and `RATE_DEFAULTS` in `index.html` to refresh them.
- Tax slabs live in `NEW_SLABS` and `oldSlabs()` near the top of the first `<script>` block. Update them each Budget.
- Tax figures are a guide only. Check them with the Income Tax Department or a chartered accountant before filing.
- PDF exports use standard fonts, so the rupee sign is written as "Rs." and characters outside basic Latin become "?".
- User data (planner, resume, invoice, theme, edited rates) is stored in `localStorage` in the visitor's own browser.
