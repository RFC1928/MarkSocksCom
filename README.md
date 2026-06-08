# marksocks.com

Personal landing page for Mark Socks — AI Automation Manager, Henry Ford Health.

Static single-file site (`index.html`), served via GitHub Pages with a custom
domain (`CNAME` → marksocks.com). No build step.

## Editing

Everything lives in `index.html` — markup, styles, and a little JS. Light and
dark themes follow the visitor's system preference.

## Homelab link

A "homelab" link in the footer stays hidden until your homelab responds, so it
only appears when you're on-VLAN. Configure it in the `HOMELAB` block near the
bottom of `index.html`:

```js
var HOMELAB = {
    href: 'https://home.marksocks.lan',          // where the link points
    ping: 'https://home.marksocks.lan/favicon.ico', // small image used to test reachability
    timeout: 2500,                                // ms before giving up
    alwaysShow: false                            // true = skip detection, always show
};
```

Note: this page is served over HTTPS, and browsers block HTTPS→HTTP requests
("mixed content"). For detection to work, make the homelab reachable over HTTPS
too — or set `alwaysShow: true` if you don't mind it always being visible.

## Demo subdomains

The root domain is the public face; demos go on subdomains
(e.g. `yourdemo.marksocks.com`). Dropping the prefix lands on this page.
