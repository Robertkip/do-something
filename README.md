# Portfolio with a working contact form

One dynamic feature: a contact form that emails you, using the Web3Forms free tier.

## 1. Get your access key (2 minutes)

1. Go to https://web3forms.com and enter the email address where you want messages to arrive.
2. They email you an access key (a long ID like `a1b2c3d4-...`).
3. In `index.html`, replace `YOUR_WEB3FORMS_ACCESS_KEY` with that key.

## 2. Test locally

```bash
cd ~/do-something
python3 -m http.server 8000
```

Open http://localhost:8000, send yourself a test message, and check your inbox and spam folder.

## 3. Put it live (free)

Pick one:

- **Netlify Drop:** go to https://app.netlify.com/drop and drag this folder onto the page. You get a live URL straight away.
- **GitHub Pages:** push this folder to a public repo, then go to Settings → Pages → Deploy from branch → `main` / root.

## 4. Collect your evidence

- Send a real test message from the **live** URL.
- Screenshot the email that arrives in your inbox, and the green "Thanks!" message on the page.
- Hand in the live URL, the screenshots, and `explainer.md`, rewritten in your own words.

## Personalise

Replace the three "Project one/two/three" placeholders in `index.html` with your real work.
