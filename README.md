# Suresh Bhupala — Personal Portfolio

A responsive static portfolio website built with HTML, CSS and vanilla JavaScript.

## Files
- `index.html` — page content and metadata
- `styles.css` — responsive visual design and animations
- `script.js` — mobile navigation, reveal animations and scroll progress

## Before publishing
1. Open `index.html`.
2. Replace `YOUR_EMAIL@example.com` with the email address you want to publish.
3. Replace `https://www.linkedin.com/in/YOUR-LINKEDIN/` with your LinkedIn profile URL.
4. Review all project descriptions and confirm they accurately reflect your individual responsibilities.
5. Optionally add a downloadable resume PDF link and your preferred contact details.

## Publish on a personal subdomain
Example: `suresh.yourdomain.com`

### Nginx (Ubuntu/Linux)
1. Upload the contents of this folder to `/var/www/suresh-portfolio`.
2. Create an Nginx server block:

```nginx
server {
    listen 80;
    server_name suresh.yourdomain.com;
    root /var/www/suresh-portfolio;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

3. Enable the site, test and reload Nginx:

```bash
sudo ln -s /etc/nginx/sites-available/suresh-portfolio /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx
```

4. Point the subdomain DNS A record to your server's public IP.
5. Configure HTTPS with your existing certificate workflow or Certbot.

### IIS (Windows Server)
1. Create a website in IIS and set its physical path to this folder.
2. Add an HTTPS binding for your subdomain and install the appropriate certificate.
3. Point the subdomain DNS record to the Windows server.

This is a static site; no Node.js runtime, database or build process is required.
