# MediCare Hub Demo Website

A lightweight static medical website created for an AWS high-availability / reliability architecture portfolio project.

## Files

- `index.html`
- `style.css`
- `images/` — local SVG artwork used by the page

## Important

This is a demo application only. It does **not** use real patients, medical records, or Protected Health Information (PHI).

## Example EC2 UserData

For Amazon Linux 2023:

```bash
#!/bin/bash
dnf update -y
dnf install -y httpd git
systemctl enable httpd
systemctl start httpd

rm -rf /var/www/html/*
git clone https://github.com/YOUR-USERNAME/medicare-hub-demo.git /tmp/medicare-hub-demo
cp -r /tmp/medicare-hub-demo/* /var/www/html/

chown -R apache:apache /var/www/html
systemctl restart httpd
```

Replace `YOUR-USERNAME` with your GitHub username.

## Local preview

Open `index.html` directly in a browser, or run:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.
