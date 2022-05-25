# Workshop
## Step 1: install xamp
### PhpMyAdmin Access Forbidden Error
1. Open XAMPP by click the XAMPP app icon in macOS Finder —> Applications folder.
2. Click Volumes tab —> Mount button to mount /opt/lampp volume.
3. Click Explore button to open /opt/lampp folder in macOS Finder.
4. Open etc / extra folder, edit httpd-xampp.conf file.
5. 
```
# since XAMPP 1.4.3
<Directory "/opt/lampp/phpmyadmin">
    AllowOverride AuthConfig Limit
    # Require local
    Order allow,deny
    Allow from all
    Require all granted
    ErrorDocument 403 /error/XAMPP_FORBIDDEN.html.var
</Directory>
```
## Step 2: install Wordpress
https://wordpress.org/support/article/how-to-install-wordpress/
