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

Once you launch them, you should see their status turn to green:

![image](https://user-images.githubusercontent.com/75443246/171029605-0c0f010c-298a-417e-8b15-d27fdcbf3fd2.png)

For MacOS users:

Click Start on the General section and wait until the status turns to green:

![image](https://user-images.githubusercontent.com/75443246/171029810-dd83c232-ed74-4926-a7b0-91fbb6ada956.png)

Then go to Services section and start Apache and MySQL services:

![image](https://user-images.githubusercontent.com/75443246/171029927-5bef1b9b-0836-40d4-b2e3-f4a7282dc7f1.png)

## Step 2: Navigate to your local service
Now you should be able to test that your local server is working by going to http://localhost/ (**Windows** users) in your web browser of choice or click on "Go To Application" in General section (**MacOS** users):

![image](https://user-images.githubusercontent.com/75443246/171030234-83f069d1-7635-4c41-a1a2-8ae333d56e35.png)

## Step 3: Create a database for WordPress

Next, you need to create a MySQL database for your WordPress. To do that, launch PHPMyAdmin from your XAMPP control panel:

**Windows** users:

![image](https://user-images.githubusercontent.com/75443246/171030629-234b94b1-eea2-46f4-bc20-a6f3e58fdf56.png)


**MacOS** users:
Navigate to phpAdmin on your Dashboard page:

![image](https://user-images.githubusercontent.com/75443246/171031002-53cb9915-002e-4d85-91d6-08be40c04834.png)

### If you have PhpMyAdmin Access Forbidden Error 
1. **MacOS** users:
- Click Volumes tab —> Mount button to mount /opt/lampp volume.
- Click Explore button to open /opt/lampp folder in macOS Finder.
    
   **Windows** users: Click Explorer button to open /opt/lampp
2. Open etc/extra folder, edit httpd-xampp.conf file.
3. Comment line which load Perl module.
```
#LoadModule perl_module        modules/mod_perl.so
```
4. Change Directory “/opt/lampp/phpmyadmin” access permission as below.
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

Then click on Databases at the top:

![image](https://user-images.githubusercontent.com/75443246/171031144-f516dbe0-ccde-42f8-b4a6-bd5fd8db8594.png)

And enter a name for your database and click Create. Your name can be anything (like Wordpress) – just remember it because you’ll need it for the next step:

![image](https://user-images.githubusercontent.com/75443246/171031184-c7262d6e-163f-4ab2-a678-bf944914203d.png)

## Step 4: Download and add Wordpress files
First, you need to download Wordpress archive on youe local PC: https://wordpress.org/download/

Now you need to open file directory of your server:
**MacOS** users:
- Click Volumes tab —> Mount button to mount /opt/lampp volume.
- Click Explore button to open /opt/lampp folder in macOS Finder.
    
**Windows** users: Click Explorer button to open /opt/lampp

Then open htdocs directory and create new folder (name it Wordpress). Copy all unarchived Wordpress files to the new folder.
## Step 5: add wordpress files to root directory (htdocs in Xampp)
## Step 6: create database and user using phpMyAdmin
## Step 7: Set up wp-config.php (enter your database name, username, password)
## Step 8: Run install script - localhost/wp-admin/install.php
## Step 9: You can now access Wordpress dashboard
