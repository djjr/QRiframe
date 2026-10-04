# QRiframe

A static page that shows a QR code for a link. It's for embedding in a slides.com / reveal.js slide as an iframe, so the audience can open the deck on their phones.

```
https://djjr.github.io/QRiframe/?url=https://slides.com/<you>/<deck>
```

| Parameter | Effect |
|---|---|
| `url` | The address to encode (required; http or https). An iframe can't read its parent page's address, so it must be given. |
| `label` | Caption under the code. Defaults to the address. With a custom label, the address still appears in small type beneath it. `&label=` hides the large caption but not the address. |
| `theme=dark` | Light caption text for dark slides. The QR always sits on white, so it stays scannable. |

The QR fills the iframe, so size the iframe to size the code.

**The destination is always shown,** so a misleading label can't disguise where the code goes. The address is parsed by the browser, and the code encodes exactly the address displayed, with the domain in bold. Tricks like `https://slides.com@evil.com` therefore display as **evil.com**, and lookalike Unicode domains display in their `xn--…` form. Only http(s) addresses are accepted. Everything runs in the browser; there's no server.

Hosted on GitHub Pages: the `main` branch, root folder.

QR generation: [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) 1.5.2 by Kazuhiko Arase, MIT license, vendored in `vendor/qrcode.js`.
