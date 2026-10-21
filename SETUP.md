# Profile README setup

This repository powers the README shown at the top of `github.com/emperor1234`.
GitHub only displays it when the repository name **exactly matches** the
account username and the repository is **public**.

## Repository layout

```
emperor1234/
├── README.md                       # The profile page itself
├── .lycheeignore                   # URLs the link checker skips
├── SETUP.md                        # This file (not shown on the profile)
└── .github/
    └── workflows/
        ├── snake.yml               # Daily contribution-snake animation
        └── link-check.yml          # Weekly broken-link check
```

## One-time setup (about 5 minutes)

1. **Confirm the username.** Every stats card, the view counter and the snake
   use `emperor1234`. If your account name is different, find-and-replace
   `emperor1234` in `README.md` and `.lycheeignore`.
2. **Push the files** to the `main` branch:
   ```bash
   git add .
   git commit -m "feat: premium profile README with stats and automation"
   git push origin main
   ```
3. **Allow workflows to write.** Repository → Settings → Actions → General →
   Workflow permissions → select **Read and write permissions** → Save.
4. **Run the snake once.** Actions tab → *Generate contribution snake* →
   **Run workflow**. After about a minute an `output` branch appears and the
   animation shows on your profile. It then refreshes every day automatically.
5. **Count private work (optional).** Your stats card already passes
   `count_private=true`. To make private contributions count, go to your
   GitHub profile → Contributions settings → enable
   **Include private contributions on my profile**.

## Keeping it current

| When this changes | Edit this section of README.md |
|---|---|
| New project shipped | `Featured Work` cards or the "more projects" table |
| New certificate | `Credentials` table |
| New role or client type | `Experience` dropdowns |
| What you are working on | `Currently` list |
| Upwork rating or badge | Badges under the header and in `Track record` |

## Troubleshooting

- **A stats card shows an error or "rate limited".** The public
  `github-readme-stats` instance is shared and occasionally throttled. It
  recovers on its own; for guaranteed uptime, deploy your own copy to Vercel
  (free) and swap the domain in the two stats URLs.
- **Mermaid diagrams don't render.** GitHub renders Mermaid natively on the
  web. Some mobile apps and third-party viewers show the source instead; that
  is expected.
- **The snake image is broken.** The workflow has not run yet, or workflow
  permissions are still read-only (step 3).
