# Workshop
In this step-by-step tutorial, I’ll show you exactly how to install XAMPP and set up a local WordPress development site. I’ll also share some common XAMPP errors and troubleshooting tips so that you can fix any problems you encounter
## Step 1: Install Xampp
First step in the way is to download XAMPP on your computer: https://www.apachefriends.org/index.html
You will need to download a version of XAMPP according to your OS.
Once the download finishes, run the file to launch the XAMPP installer.
**MacOS** users may encounter a problem with installing XAMPP. You may see this error:
![image](https://user-images.githubusercontent.com/75443246/171028198-37fdb8f0-d44e-4bd3-b193-7092b321f34e.png)
Apple does not trust this application, because it was downloaded from the internet. To solve this problem navigate to Settings -> Security and Privacy -> General. There you can grant access to open XAMPP installer:
![image](https://user-images.githubusercontent.com/75443246/171028583-4fe785a7-1bf9-4365-aedc-7bc5a1d224ae.png)

## Step 2: Start the modules and test your server
To install XAMPP and WordPress properly, you’ll need to run two modules:
- Apache
- MySQL

For **Windows** users:
![image](https://user-images.githubusercontent.com/75443246/171029459-b08b8e36-3047-447a-8595-39f269b958d7.png)

## Step 2: Start the modules and test your server
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
