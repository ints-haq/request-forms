# request-forms

Internal Kismet request forms. Plain HTML, no build step, no dependencies. Nothing is submitted anywhere — everything runs in the browser until the person presses a button.

## Live

**https://ints-haq.github.io/request-forms/**

| Path | Form |
|---|---|
| `/` | Hub. Lists the forms. Share this link, not the individual ones. |
| `/discount/` | Discount code request |
| `/monoku/` | Monoku initiative / ticket form |

Every page is `noindex` and the whole site is blocked in `robots.txt`, so none of it turns up in search. It is still reachable by anyone with the link, so share the link rather than publishing it.

## Adding another form

Drop `yourform/index.html` in, then add a card to the root `index.html` copying one of the two already there. Nothing else to wire up.

## Editing

Open the file on GitHub, click the pencil, commit. The live page updates in about a minute.

### Discount form: the two things you are most likely to change

Near the top of the `<script>` block in `discount/index.html`:

```js
var SEND_TO = "Intshaquani@me.com";     // where the email button addresses to
```

```js
var FREE_SHIP_THRESHOLD = 50;   // dollars, applied AFTER the discount
var SHIP_COST = 5;              // flat rate below the threshold
var SUB_RECURRING = 40.49;      // 9lb bag recurring price
var SUB_FIRST = 31.49;          // 9lb bag first-order price before any code
```

All four verified in live Shopify checkout on 15 August 2026. The form uses them to work out the real subscriber discount and the free shipping dead band, and writes both into the request. **If Kismet's pricing or free shipping threshold changes, update these or the form starts giving confident wrong answers.**
