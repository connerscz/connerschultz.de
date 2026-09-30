# connerschultz.de

My personal landing page: **[connerschultz.de](https://connerschultz.de)**

A small, hand-written static site, no frameworks and no build step.

## Tech

- Plain HTML and CSS
- Self-hosted font (Roboto Mono), so no requests to Google Fonts or other CDNs
- No cookies, no tracking, no analytics
- Imprint and privacy policy according to German law (DDG, DSGVO)

## Deployment

Every push to `main` deploys automatically:

1. A GitHub Actions workflow ([`deploy.yml`](.github/workflows/deploy.yml)) connects to my VPS via SSH.
2. On the server, `git pull` updates the files.
3. nginx serves the site behind Traefik (managed by Coolify), which handles HTTPS with Let's Encrypt certificates.
4. Hidden files and folders such as `.git` are blocked by nginx.

The server is a Hetzner Cloud VPS in the EU (Helsinki).

## Structure

```
index.html / index.css      landing page
imprint/                    imprint (Impressum)
privacy-policy/             privacy policy (Datenschutzerklärung)
fonts/                      self-hosted Roboto Mono
.github/workflows/          auto-deploy
```

## Use of AI

I built this site myself, but I used AI (Claude) as a helper along the way:

- **Debugging and problem solving**, e.g. finding out why CSS wasn't applied or why the typing animation stuttered
- **Some CSS changes**, e.g. the layout and formatting of the privacy policy page
- **Server and security checks** for the setup behind the site
- **Drafting texts**, such as the privacy policy and this README, which I reviewed and adjusted

## License

The **code** (HTML, CSS, workflow) is licensed under the [MIT License](LICENSE).

**Not included:** my name, the texts about me, the imprint and the privacy policy. They are personal content, and all rights are reserved.

The font **Roboto Mono** by Google is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
