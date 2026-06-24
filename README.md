# Solar Installation Quote Calculator

A simple, no-install web tool that turns your pricing guide spreadsheet into a fill-in-the-blanks quote calculator. No database, no server, no monthly cost — it's a single web page that runs in any browser.

**[Open the live demo once it's set up →]** (link goes here after you finish Step 2 below)

---

## What it does

- Pick a system size (5kW / 8kW / 12kW / 16kW) and it auto-fills all the fixed-price line items from your pricing guide
- For Inverter, Batteries, and Modules — type in the supplier quote and your markup %, it calculates the sell price automatically
- Mounting Structure — choose Tile / Alu / Ballast, enter panel count, it works out the cost
- DC Switchgear — choose 2 / 3 / 4 strings, auto-fills the price
- Travel — enter kilometres, it calculates at R4.80/km
- Running total at the side, including VAT
- "Print / Save as PDF" button to generate a clean quote to send to a customer
- A bulk markup box if you want to apply one % to all the manual items at once

Nothing is saved anywhere — it's meant to be filled in and either printed/exported per quote, or just used to get a number quickly. (If you later want quotes saved and searchable, that's a bigger step — see **Optional Next Steps** at the end.)

---

## How your colleagues will use it day-to-day

Once it's hosted (Step 2), using it is just:

1. Open the link (bookmark it on your phone/laptop)
2. Click the system size
3. Fill in customer name/address (optional, just shows on the printed quote)
4. Type in the inverter/battery/panel supplier costs and markup
5. Pick mounting type + panel count, string count, and travel distance
6. Read the total off the right-hand panel, or click **Print / Save as PDF** to generate a quote document

No login, no app to install — works on phone, tablet, or PC.

---

## Step 1 — Get a free GitHub account (skip if you already have one)

1. Go to [github.com](https://github.com) and click **Sign up**
2. Use your work email, pick a username, set a password
3. Confirm your email when GitHub sends the verification link

---

## Step 2 — Put the file online with GitHub Pages (free hosting)

This makes the calculator available at a permanent web link, free, forever, with no server to maintain.

1. Once logged into GitHub, click the **+** icon top-right → **New repository**
2. Name it something like `solar-quote-tool`
3. Set it to **Public** (Pages needs Public on a free account)
4. Tick **Add a README file**, then click **Create repository**
5. In your new repository, click **Add file → Upload files**
6. Drag in the `index.html` file from this folder, then click **Commit changes**
7. Go to the repository's **Settings** tab (top menu)
8. In the left sidebar, click **Pages**
9. Under "Build and deployment" → "Branch", choose **main** and folder **/ (root)**, click **Save**
10. Wait about a minute, then refresh — GitHub will show you a link like:

   ```
   https://yourusername.github.io/solar-quote-tool/
   ```

11. That's it — open that link, bookmark it, and share it with your colleagues

Any time you want to update pricing later (see Step 3), just upload the new `index.html` over the old one the same way (Add file → Upload files → it'll ask to replace it).

---

## Step 3 — Updating prices later

All your pricing lives near the top of the `index.html` file, clearly labelled. You don't need to know how to code — just open the file in any text editor (Notepad, TextEdit, or GitHub's own editor) and change the numbers.

For example, to update the flat-rate items:

```js
const FLAT_ITEMS = [
  { code:"GEN",   name:"AC & DC Cabling, Fuses and Parts", prices:{ "5kW":5250, "8kW":6895, "12kW":8550, "16kW":13990 } },
  ...
```

Just change the numbers after each size, save, and re-upload to GitHub (Step 2.6 again). The live link updates automatically within a minute or two.

To edit directly on GitHub without downloading anything:
1. Open your repository
2. Click on `index.html`
3. Click the pencil (✏️) icon top-right to edit
4. Make your changes
5. Scroll down, click **Commit changes**

---

## Step 4 (optional) — Use your own domain or company branding

If you'd like this at a link like `quote.yourcompany.co.za` instead of the github.io address, that requires pointing a DNS record at GitHub Pages — happy to walk through that separately if you get a domain.

---

## Optional Next Steps (if you outgrow the basic version)

The current version is intentionally simple — open it, fill it in, print it, done. If down the line you want any of the below, these are bigger builds (a real backend/database) and worth a separate conversation:

- Saving every quote so you can look them up later
- Emailing the PDF straight to the customer from the tool
- Multiple users editing the same pricing guide centrally instead of each updating their own copy
- Customer-facing version where the customer fills in their own details

For now, the spreadsheet-replacement goal — fill in numbers, get an instant accurate total — is fully covered by `index.html`.

---

## Files in this folder

| File | Purpose |
|---|---|
| `index.html` | The whole tool — pricing data, calculator logic, and printable layout, in one file |
| `README.md` | This guide |
