# htaccess-redirect-301
Redirect 301 /oldfile.htm /newfile.htm

Redirect 301 /oldfile.htm http://example.net/newfile.htm

RewriteEngine on
RewriteCond %{HTTP_HOST} ^example.com [NC,OR]
RewriteCond %{HTTP_HOST} ^www.example.com [NC]
RewriteRule ^(.*)$ http://example.net/$1 [L,R=301,NC]

RewriteEngine on
RewriteCond %{HTTP_HOST} ^example.com [NC]
RewriteRule ^(.*)$ http://www.example.com/$1 [L,R=301,NC]

RewriteEngine on
RewriteCond %{HTTP_HOST} ^www.example.com [NC]
RewriteRule ^(.*)$ http://example.com/$1 [L,R=301,NC]

RewriteEngine On
RewriteCond %{REQUEST_URI} .php$
RewriteRule ^(.*).php$ /$1.htm [R=301,L]

