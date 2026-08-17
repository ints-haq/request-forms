# request-forms

Internal request forms. Plain HTML, no build step, no dependencies, no data leaves the browser.

## Live

`https://<your-github-username>.github.io/request-forms/`

Set to `noindex` and blocked in `robots.txt`, so it will not turn up in search. It is still reachable by anyone who has the link, so share the link rather than publishing it.

## What is here

| File | What it is |
|---|---|
| `index.html` | Kismet discount code request form. Fills in, then emails, copies or downloads a markdown request. |
| `robots.txt` | Keeps search engines out. |

## Turning on GitHub Pages

Settings → Pages → Source: **Deploy from a branch** → Branch: **main**, folder: **/ (root)** → Save. Live in about a minute.

## Editing the form

Everything is in `index.html`. Two things you are most likely to change:

**1. Where the email goes.** Near the top of the `<script>` block:

```js
var SEND_TO = "Intshaquani@me.com";
```

**2. The platform numbers.** Just below that:

```js
var FREE_SHIP_THRESHOLD = 50;   // dollars, applied AFTER the discount
var SHIP_COST = 5;              // flat rate below the threshold
var SUB_RECURRING = 40.49;      // 9lb bag recurring price
var SUB_FIRST = 31.49;          // 9lb bag first-order price before any code
```

All four were verified in live Shopify checkout on 15 August 2026. The form uses them to work out the real subscriber discount and the free shipping dead band, and writes both into the request. **If Kismet's pricing or free shipping threshold changes, update these or the form starts giving confident wrong answers.**

To edit: open the file on GitHub, click the pencil, change the line, commit. The live page updates in about a minute.
