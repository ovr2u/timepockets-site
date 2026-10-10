# timepockets.co.uk

The landing page for TimePockets: printable workbooks for brilliant, busy brains, and the TimePockets app (coming soon).

Plain static files, served by GitHub Pages from `main`. No framework, no build step, no cookies, no analytics, and nothing loaded from other sites. The only outside request is the sign-up itself, to MailerLite.

```
index.html            the page (copy, form and the small sign-up script)
styles.css            all styling
images/               logo, workbook cover, app illustration, share image
fonts/                Fredoka and Andika, self-hosted so no visitor data goes to Google
favicon.ico           browser tab icon
apple-touch-icon.png  phone home-screen icon
.nojekyll             tells GitHub Pages to serve the files as they are
CNAME                 the custom domain, written by GitHub
```

## Mailing list (MailerLite)

The sign-up form is in `index.html`, under the `MAILING LIST` comment. It takes two MailerLite embedded form action URLs:

- `data-list-action`: the form that adds people to the **App launch** group.
- `data-list-action-news`: the form that adds people to **App launch** and **TimePockets news**. It is used when the "occasional TimePockets news" box is ticked. The box always starts unticked.

While `data-list-action` is empty, "Keep me posted" opens an email draft to contact@timepockets.co.uk with the subject "Keep me posted", saying whether they ticked the news box. After pasting the URLs, sign up once with and once without the box ticked, and check each address lands in the right groups. The browser cannot read MailerLite's reply, so it always shows the thank-you message.

## Custom domain

Done. GitHub added the `CNAME` file when the custom domain was saved, and `https://ovr2u.github.io/timepockets-site/` now redirects to timepockets.co.uk. For the record:

1. In the 123 Reg DNS (it runs on GoDaddy's systems) for timepockets.co.uk, remove any existing A records for `@` and any CNAME for `www`, then add:

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
