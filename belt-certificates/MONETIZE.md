# Monetize this in 30 seconds

The app already paywalls itself. The only thing missing is where the money goes.

---

## The 30-second version

**1. Get a payment link** (~20s)

Pick whichever account you already have. All three give you a hosted checkout page with no
code and no website required:

- **Stripe** → Dashboard → Payment links → New → one-time, set price → Create
- **Gumroad** → New product → digital product, set price → Publish
- **Lemon Squeezy** → New product → set price → Publish

**2. Generate one unlock code** (~5s)

Open `keygen.html`, click **Generate codes**, copy one.

**3. Wire the two together** (~5s)

Paste the payment URL into `index.html`:

```js
const CONFIG = {
  payUrl: "https://buy.stripe.com/your_link_here",
  price: "$19",
  ...
};
```

Then paste the unlock code into your payment provider's **post-payment confirmation
message** — the text a buyer sees the instant they pay:

- Stripe: payment link → *After payment* → *Show confirmation page* → custom message
- Gumroad: product → *Content* → the text shown after purchase
- Lemon Squeezy: product → *Thank-you note*

Done. Buyers pay, see the code on the confirmation page, paste it into the app, and it
unlocks. You are not in the loop at all.

---

## Why one shared code first

It is the only arrangement with **zero** ongoing work. Yes, a buyer could pass the code to a
friend. Weigh that against the alternative: per-buyer codes mean either a manual email after
every sale or a Zapier automation to build — both of which cost you more than the occasional
shared code does.

Ship the shared code. If it sells, upgrade.

### Upgrading to per-buyer codes

Generate a batch in `keygen.html` and feed them to your provider's built-in licence
delivery, which hands each buyer a different one automatically:

- **Gumroad** has licence keys natively — enable *Generate a unique licence key per sale*.
  Note these are Gumroad's own key format, so you'd check them against Gumroad's licence
  verification endpoint instead of `keyIsValid`.
- **Lemon Squeezy** has the same, under *Licence keys*.
- **Stripe** needs a Zapier/Make step: *new payment → send email with the next code from a
  list*.

---

## Hosting, also free

```
GitHub → repo Settings → Pages → Source: Deploy from branch → main → /(root) → Save
```

Live at `https://<your-username>.github.io/belt-certificates/` in about a minute. No server,
no bill, no cold starts. Remember to update `CONFIG.creditLine` to your real URL — that line
is printed on every free certificate and is your only distribution channel.

---

## Where the first customers actually are

The build is the easy part. This is the part that decides whether it earns anything.

**The pitch that works:** "Print promotion certificates for your whole class in one go. Free
to try, $19 once, no subscription." Instructors are allergic to another monthly fee, and
that sentence is the entire product.

**Where to post it, in order of how well it tends to work:**

1. **r/taekwondo, r/martialarts** — post the free tool, not an ad. Say you built it for your
   own school and ask what belt systems to add. Works because it is true.
2. **Facebook groups for school owners** — "Martial Arts Business", "Dojo Owners", ATA/ITF
   regional groups. These are the actual buyers, and they discuss costs constantly.
3. **Direct email to 50 local schools** before their next grading. One short paragraph and
   the link. Gradings are seasonal, so time it.
4. **Your own instructor first.** One real school using it gives you a testimonial, a
   screenshot, and a list of what is missing.

**Realistic expectations:** a tool like this with no audience converts somewhere around
1–3% of people who open it. A good Reddit post is a few hundred visitors, so think a handful
of sales per post, not hundreds. The compounding part is the credit line on free
certificates — every free batch printed is 30 parents holding your URL.

**What would actually raise the price:** per-student progress tracking, attendance, and
grading-sheet printouts. That is when schools pay monthly instead of once. The certificate
generator is the wedge, not the business.
