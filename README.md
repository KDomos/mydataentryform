# NIRA Notice of Birth of a Child — data entry form

A web app for collecting the details for the NIRA *Notice of Birth of a Child* and printing them on one A4 page
that matches the official form. Built for smartphones: it works offline once opened, and can be installed like an app.

## Files
`index.html` (the app), `manifest.webmanifest`, `sw.js` (offline support), `icon-192.png`, `icon-512.png`, `.gitignore`. Upload all of them.

## Publish on GitHub Pages
1. Create a repository on github.com and upload all the files above (Add file → Upload files).
2. **Settings → Pages → Deploy from a branch → main → / (root)** → Save.
3. After a minute the app is live at `https://<your-username>.github.io/<repository-name>/`. Share that link.

## On each phone (do this once)
1. Open the link **while you have internet** and let it load fully.
2. Install it: Android Chrome → ⋮ → *Install app* / *Add to Home screen*. iPhone Safari → Share → *Add to Home Screen*.
3. Open it from the home-screen icon. It now works with no internet.
4. Menu → *Load font* and pick your font file (once per phone).

Use the home-screen app rather than a normal browser tab: iPhone Safari clears website storage after about 7 days of not
visiting, but an installed home-screen app is kept.

## Using it
Fill Steps 1 to 4, then Step 5 shows the exact A4 page. **Print / Save as PDF** saves the client and opens the print screen:
choose *Save as PDF*, paper **A4**. **Next client** gives a new Field Registration No (`…/00A1A`, `…/00A1B`, …).
The app warns before printing if key details are missing or the child's date of birth is invalid.

## Working with colleagues
- Saved clients and the counter live **in each person's own phone**. Nothing is sent to GitHub or any server, so the repository never holds personal data.
- **Give every colleague a different number prefix** (Menu → Numbering), for example `AMU/NIRA/Field-Client-No/JD/` and `…/SK/`, so numbers never clash.
- To collect data: Menu → *Share backup* (sends a file through WhatsApp, email and so on), *Export CSV* (spreadsheet) or *Export backup*. *Import backup* merges a backup file into another phone.
- Back up regularly (the app reminds you every 10 clients). Clearing browser data, or uninstalling the app, erases saved clients and the counter.
- Never commit exported CSV/JSON files to the repository. `.gitignore` blocks them.

## Updating the app
Change `index.html`, then change `nira-form-v1` to a new name (for example `nira-form-v2`) in `sw.js` so phones pick up the update.
