# Belt Certificate Studio

Print belt promotion certificates for a whole class in one print job.

Type a roster, pick the belts, hit **Print / Save PDF**. One letter-landscape page per
student, ready for the ceremony. No account, no install, no upload — the page runs
entirely in the browser, so a school's student roster never leaves the device.

**Live:** `https://<your-username>.github.io/belt-certificates/`

---

## Why this exists

A dojang promoting 30 students has two bad options: hand-write 30 certificates, or pay a
monthly fee for school-management software whose certificate module they'd use four times
a year. This is the third option — the certificate part, done well, for a one-time price.

## What it does

- **Whole-class mode** — paste `Name, Belt, Date` one per line, straight out of a
  spreadsheet column. Belt and date are optional per line and fall back to the batch default.
- **25 ranks** built in, white through 9th Dan, including Poom ranks, with the belt colour
  printed as an accent on each certificate.
- **Your branding** — school name, location, logo, two signature lines, six accent colours,
  and every line of wording is editable.
- **Optional certificate numbers**, date-prefixed and sequential, for promotion records.
- **Print-exact output** — real letter-landscape pages at 1:1, not a screenshot scaled to fit.
- **Remembers everything** in the browser, so next grading cycle you only type the new roster.

## Pricing model

| | Free | Unlocked |
|---|---|---|
| Certificates per batch | 3 | unlimited |
| Credit line at the foot | yes | removed |
| Everything else | included | included |

The free tier is deliberately useful: three real, printable certificates. The credit line on
free output is also the only marketing this thing has — parents keep these certificates, and
the URL is on them.

## Run it

It is one HTML file with no build step and no dependencies beyond two Google Fonts.

```
# locally
open index.html

# hosted, free, forever
# push to GitHub, then Settings → Pages → Branch: main → /(root)
```

## Files

| | |
|---|---|
| `index.html` | the whole app |
| `keygen.html` | mints unlock codes to sell — run it locally, it needs no server |
| `MONETIZE.md` | the 30-second setup to start taking money |

## Honest note on the unlock codes

Code checking happens in the browser, because there is no server. Anyone who reads the
JavaScript can mint their own code, and a code can be shared. This is a speed bump, not
security — the same one most small paid web tools run on, and it works because the people
buying this are martial arts instructors, not people reading your source.

If it ever sells enough to be worth protecting, move `keyIsValid` behind a server endpoint
and have it check the code against a list of real orders. Until then, this is the version
that costs nothing to run.

## Licence

MIT. See `LICENSE`.
