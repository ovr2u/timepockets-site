# timepockets.co.uk

The landing page for TimePockets: printable workbooks for brilliant, busy brains, and the TimePockets app (coming soon).

Plain static files, served by GitHub Pages from `main`. No framework, no build step, no cookies, no analytics, no third-party requests.

```
index.html            the page (copy, form and the small sign-up script)
styles.css            all styling
images/               logo, workbook cover, app illustration, share image
fonts/                Fredoka and Andika, self-hosted so no visitor data goes to Google
favicon.ico           browser tab icon
apple-touch-icon.png  phone home-screen icon
.nojekyll             tells GitHub Pages to serve the files as they are
```

## Things to swap in later

All in `index.html`, each marked with a `PLACEHOLDER` or `MAILING LIST` comment.

- **Etsy shop link.** Currently `https://www.etsy.com/uk/shop/TimePockets`, used three times. Find and replace it.
- **Facebook link.** Currently `https://www.facebook.com/timepockets`, in the footer.
- **Mailing list.** Paste your Kit or MailerLite form action into `data-list-action=""` on the sign-up form. The script works out which provider it is and sends the email address in the field that provider expects (`email_address` for Kit, `fields[email]` for MailerLite). While it is empty, "Keep me posted" opens an email draft to hello@timepockets.co.uk with the subject "Keep me posted". After pasting, sign up once with your own address and check it arrives in the provider, because the browser cannot read the provider's reply and so always shows the thank-you message.

## Custom domain

The `CNAME` file is added when the domain moves, not before. While it is absent the site can be previewed at `https://ovr2u.github.io/timepockets-site/`. Once it exists, that address redirects to timepockets.co.uk.

1. In GoDaddy DNS for timepockets.co.uk, remove any existing A records for `@` and any CNAME for `www`, then add:

   | Type  | Name | Value             |
   |-------|------|-------------------|
   | A     | @    | 185.199.108.153   |
   | A     | @    | 185.199.109.153   |
   | A     | @    | 185.199.110.153   |
   | A     | @    | 185.199.111.153   |
   | CNAME | www  | ovr2u.github.io   |

2. In this repo, Settings, Pages, Custom domain: enter `timepockets.co.uk` and Save. GitHub writes the `CNAME` file into `main` for you.
3. When the DNS check turns green, tick Enforce HTTPS. `www.timepockets.co.uk` then redirects to `timepockets.co.uk` automatically.

## Fonts

Fredoka and Andika are used under the SIL Open Font License 1.1 (https://openfontlicense.org). Their copyright and licence notices are kept inside each font file.
