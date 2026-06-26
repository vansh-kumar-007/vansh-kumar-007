# GitHub Profile Setup Guide

Complete step-by-step to get everything working.

---

## Step 1 — Create the special profile repository

GitHub shows a special README on your profile page when you create a repo
whose name **exactly matches your username**.

1. Go to github.com/new
2. Repository name: `vansh-kumar-007`  ← must match your username exactly
3. Set to **Public** (required for profile README to show)
4. Check "Add a README file"
5. Click Create repository

---

## Step 2 — Add the files

Copy these files into that repo:
```
vansh-kumar-007/
├── README.md                        ← the main profile file
└── .github/
    └── workflows/
        └── snake.yml                ← auto-generates snake animation daily
```

---

## Step 3 — Set up Spotify Now Playing

This uses the `spotify-github-profile` service. Takes ~2 minutes:

1. Go to: **https://spotify-github-profile.kittinanx.com**
2. Click "Login with Spotify" and authorize
3. After login, you'll see your Spotify User ID — copy it
4. In `README.md`, find this line (appears twice):
   ```
   uid=3i35o6ztjhve08y6cj9zfo8av
   ```
5. Replace `YOUR_SPOTIFY_USER_ID` with your actual Spotify ID (e.g. `31abc...xyz`)

That's it — the card updates live whenever you play something.

---

## Step 4 — Enable the snake workflow

The snake animation needs write permission to commit the SVG output.

1. In your `vansh-kumar-007` repo, go to **Settings → Actions → General**
2. Under "Workflow permissions", select **Read and write permissions**
3. Click Save
4. Go to **Actions tab → Generate Snake Animation → Run workflow**

After it runs (~30 seconds), the snake SVG will appear at:
`https://raw.githubusercontent.com/vansh-kumar-007/vansh-kumar-007/output/github-contribution-grid-snake-dark.svg`

And the README will automatically display it.

---

## Step 5 — Fix the email badge

In `README.md`, find:
```
mailto:your.email@gmail.com
```
Replace with your actual email.

---

## Step 6 — Update project repo names (if needed)

The pinned project cards use these repo names:
- `vansh-kumar-007/cuda-alife-engine`
- `vansh-kumar-007/CyberArena-RL`

If your actual repo names are different, update the `repo=` values in the
`github-readme-stats` URLs in the README.

---

## What each service is & why it's trustworthy

| Service | What it does | Privacy |
|---|---|---|
| `komarev.com/ghpvc` | Visitor counter badge | Counts visits, no personal data |
| `readme-typing-svg.demolab.com` | Animated typing SVG | Stateless, generates SVG from URL params |
| `github-readme-stats.vercel.app` | Stats + language cards | Reads public GitHub API only |
| `github-readme-streak-stats.herokuapp.com` | Streak card | Reads public GitHub API only |
| `spotify-github-profile.kittinanx.com` | Now Playing card | Needs Spotify OAuth, reads playback state |
| `github-readme-activity-graph.vercel.app` | Activity graph | Reads public GitHub API only |
| `Platane/snk` | Snake SVG generator | GitHub Action, runs in your repo |
| `capsule-render.vercel.app` | Decorative header/footer waves | Stateless SVG generator |

---

## Troubleshooting

**Snake not showing?**
- Check the `output` branch exists in your repo after the workflow runs
- Make sure workflow permissions are set to Read and Write (Step 4)

**Stats cards showing "not found"?**
- Your repo must be public
- Stats services cache for ~30 minutes; wait and hard-refresh

**Spotify showing "Not Playing"?**
- Normal when nothing is playing — it shows your last played track
- Make sure you used the correct Spotify User ID (not your display name)

**Typing animation not animating?**
- It's an SVG served from demolab.com; GitHub renders it correctly
- If previewing locally in VS Code, it may appear static — check on github.com
