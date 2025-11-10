---
title: Welcome to Quartz
---

This is a blank Quartz installation.
See the [documentation](https://quartz.jzhao.xyz) for how to get started.

Hosting options a) Immedaite, b). xamp c). Docker  d). hubpages

Works yyy
a). Immediate

if running other ports

 npx quartz build --serve --port 3000


Works yyy
b). xamp   ---- quite the same for hostinger

1) copy   project --- public    to xamp\htdocs\quartzpublic

2) add .htaccess

--- code ---
RewriteEngine On
 
ErrorDocument 404 /404.html
 
# Rewrite rule for .html extension removal (with directory check)
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{DOCUMENT_ROOT}/%{REQUEST_URI}.html -f
RewriteRule ^(.*)$ $1.html [L]
 
# Handle directory requests explicitly
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^(.*)/$ $1/index.html [L]

--- code ---

3).   http://localhost:8012/quartzpublic/


Works
c).  to Docker  see -- https://quartz.jzhao.xyz/features/Docker-Support

docker run --rm -itp 8080:8080 -p 3001:3001 -v ./content:/usr/src/app/content $(docker build -q .)



Works yyy
d). hubpages

deploy.yml  in .github  and workflows/deploy.yml

https://youtu.be/6s6DT1yN4dw?t=944

Then:

Head to “Settings” tab of your forked repository and in the sidebar, click “Pages”. Under “Source”, select “GitHub Actions”.
Commit these changes by doing npx quartz sync. This should deploy your site to <github-username>.github.io/<repository-name>.
Hint

https://ashboro.github.io/quartz/