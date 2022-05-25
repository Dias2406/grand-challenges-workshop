# Workshop
## Step 1: install xamp
https://www.apachefriends.org/index.html
## Step 2: install php on your virtual machine (Xamp provides php)
## Step 3: install MySql on your virtual machine (Xamp already provides phpMyAdmin)
### If you have PhpMyAdmin Access Forbidden Error
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
## Step 4: install Wordpress on virtual machine
`wget https://wordpress.org/latest.tar.gz`
Then extract the package using:
`tar -xzvf latest.tar.gz`
## Step 5: add wordpress files to root directory (htdocs in Xampp)
## Step 6: create database and user using phpMyAdmin
## Step 7: Set up wp-config.php (enter your database name, username, password)
## Step 8: Run install script - localhost/wp-admin/install.php
## Step 9: You can now access Wordpress dashboard
