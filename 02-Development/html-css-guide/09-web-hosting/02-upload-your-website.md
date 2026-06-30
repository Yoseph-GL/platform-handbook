# Web Hosting: Upload Your Website to the Internet

## Architecture / Rationale

Uploading a website means moving your files from your computer to a web server. The process depends on your hosting provider.

Common upload methods:
- **Git**: push your code to a repository. The hosting service deploys it automatically.
- **FTP/SFTP**: upload files with a file transfer client.
- **Drag and drop**: some services let you upload a folder through their web interface.

## Query / Code Blocks

```bash
# Deploying with Git (GitHub Pages example)
git init
git add index.html styles.css
git commit -m "First version of my site"
git push origin main
# Site is live at: https://username.github.io/repository/
```

## Performance / Optimization Notes

- After uploading, clear your browser cache to see the latest version.
- Check your site on your phone. Mobile issues are often missed during local development.
- Set up a custom domain if you have one. Free subdomains (`.github.io`, `.netlify.app`) work but look less professional.
