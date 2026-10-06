# 🐢 CodingTurtle

A cute-game style interview-practice site. Players sign up, pick a course, type answers (75% word match to pass), earn points, finish modules and climb the leaderboard.

It is a plain static site – **no build step, no dependencies**.

## Files
| File | What it is |
|---|---|
| `index.html` | Page shell |
| `styles.css` | All styling |
| `app.js` | App logic (login, modules, buying, leaderboard) |
| `data.js` | Questions & answers (DevOps: Linux, Bash, Networking, Docker) |
| `vercel.json` | Vercel config |

## Upload to GitHub
1. Create an empty repo on github.com (e.g. `codingturtle`) – no README/licence.
2. In this folder run:
```bash
git init
git add .
git commit -m "CodingTurtle first version"
git branch -M main
git remote add origin https://github.com/<your-username>/codingturtle.git
git push -u origin main
```

## Deploy on Vercel
1. Go to vercel.com → **Add New… → Project** and import the GitHub repo.
2. Framework Preset: **Other**. Leave Build Command and Output Directory empty. Root Directory: `./`.
3. Click **Deploy**. Every `git push` to `main` redeploys automatically.

## Change prices
Edit the top of `app.js`: `const FEE_TOPIC=49,FEE_COURSE=499;` (₹ – a topic is Linux / Bash / Networking / Docker).

## Add more questions or courses
`data.js` holds the DevOps question bank. Courses marked "coming soon" live in the `COURSES` list in `app.js`.

## Important: what is a demo
- **Accounts** are saved in each visitor's own browser (`localStorage`); there is no server, no password reset, and a new device means a new account.
- **Payments** are a demo checkout – no money is taken, and anyone can bypass the locks from the browser tools.
- **Leaderboard** shows players on the same device only.

For real accounts, real payments and one shared leaderboard you need a backend, for example Supabase or Firebase for login and the database, plus Razorpay or Stripe with a Vercel serverless function that verifies each payment before unlocking modules.
