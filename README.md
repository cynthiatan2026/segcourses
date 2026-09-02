# NYP School of Engineering — Course Discovery Site

A static, self-contained site helping prospective students explore the 8 SEG
diplomas and 2 common programmes.

## Pages

| File | What it does |
|---|---|
| `index.html` | Landing page — four entry points |
| `personalityquiz.html` | Interests matcher and the Start the Sort quiz |
| `eligibility.html` | JAE Score check, Subject Grades finder, Compare Points |
| `courses.html` | All courses in three clusters + common programmes |
| `games.html` | 10 mini-games, one per course |
| `university.html` | University Pathway Programme explorer |

## Deploying to GitHub Pages

1. Create a repository (e.g. `seg-course-finder`).
2. Upload **the contents of this zip** — not a containing folder — to the
   repository root. `index.html` must sit at the top level.
3. Go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch**; pick `main` and `/ (root)`.
5. Save. The site appears at
   `https://<username>.github.io/<repository>/` within a minute or two.

### Deploying elsewhere

Vercel, Netlify, and Cloudflare Pages all work the same way — drop the files in
and point the host at `index.html`. Those hosts also honour `_headers`, which
GitHub Pages ignores.

### Supporting files

- `.nojekyll` — stops GitHub processing the site with Jekyll. Keep it.
- `_headers` — security headers for Netlify / Cloudflare Pages. Ignored by
  GitHub Pages but harmless to leave in place.

## Notes

- Links between pages are **relative**, so all files must stay in one directory.
- The only external request is to Google Fonts; everything else is embedded.
- **No data is collected, stored, or transmitted.** No database, no cookies, no
  analytics. Anything a student types exists only in their browser until the
  tab closes.
- Every page carries a Content-Security-Policy meta tag, since GitHub Pages
  cannot serve custom headers.

## Updating course data

Course details, cut-off points, and university pathways are hardcoded as
JavaScript objects inside each page (`diplomaDetails`, `eligibilityData`,
`tracks`). The same figure can appear in more than one file, so check each page
when a cut-off point changes.

Cut-off points reflect the 2026 JAE intake and should be reviewed annually.
