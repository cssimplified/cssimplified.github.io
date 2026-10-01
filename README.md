# CS Simplified launch site

A beginner-editable, dependency-free static website for **CS Simplified — IB & IGCSE Computer Science resources**. It is designed for GitHub Pages and includes no third-party libraries, trackers, or build process.

## Local preview

Open `index.html` directly in a browser, or run a small local web server from the repository root:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>. Stop the server with `Ctrl+C`.

## Deployment

The public site is available at <https://cssimplified.github.io>.

This repository includes `.github/workflows/deploy-pages.yml`. Every push to `main` deploys the root static site through GitHub Pages using the official Pages actions.

1. On GitHub, open **Settings** → **Pages**.
2. Under **Build and deployment**, select **GitHub Actions** as the source.
3. Push changes to the repository's `main` branch.
4. Open the **Actions** tab and wait for the **Deploy static content to Pages** workflow to finish.
5. Confirm the deployment URL is <https://cssimplified.github.io>.

The workflow is configured for a root user site: it publishes the repository root, requires no build step, and has the required `pages: write` and `id-token: write` permissions.

## Customize before launch

Search for `REPLACE_WITH` in `index.html` and replace every placeholder:

| Placeholder | What to replace it with |
| --- | --- |
| `https://www.youtube.com/@REPLACE_WITH_CHANNEL_URL` | The public URL for the CS Simplified YouTube channel. It is used in the resource card and footer. |
| `https://example.com/REPLACE_WITH_FLASHCARD_DOWNLOAD_URL.pptx` | The public direct download URL for the free Flashcard PowerPoint. Host the `.pptx` on a service that permits public downloads. |
| `https://example.com/REPLACE_WITH_STORE_URL` | The public checkout/store URL for paid matching worksheets. |
| `mailto:hello@example.com` | A public business email address for tutoring and enquiries, or remove the contact button until one is ready. |
| Instagram and LinkedIn example URLs | The relevant public CS Simplified social profile URLs, or remove those links if they are not used. |

The educational copy, sections, colors, and layout are all in `index.html` and `styles.css`. `script.js` only provides the mobile navigation and automatic footer year. Keep the public files privacy-safe: use the CS Simplified brand and generic contact/social accounts instead of personal names, personal handles, school names, or private email addresses.

## File structure

```text
.
├── .github/workflows/deploy-pages.yml  # GitHub Pages deployment
├── index.html                          # Page content and links
├── styles.css                          # Responsive visual design
├── script.js                           # Small accessible navigation enhancement
└── README.md                           # Setup and customization guide
```

## Adding the flashcard file to this repository

If the PowerPoint is small enough to store in Git, add it to a folder such as `downloads/flashcards.pptx`, then update the flashcard link in `index.html` to:

```html
<a href="downloads/flashcards.pptx">Download the flashcards</a>
```

For large files, host the download externally and use its public direct-download link instead.
