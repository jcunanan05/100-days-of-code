# Wordpress Notes

## Setup

### Requirements:

* Apache Mysql PHP stack setup. You can achieve this easily by installing XAMPP.

* Zip folder of wordpress.

> Tip: Restart computer after installing XAMPP. Might save you hours from debugging. 

### Setup How-to

res: https://torquemag.io/2015/11/install-wordpress-locally-xampp-windows-mac/

1. Start XAMPP.

2. Unzip wordpress. Copy the wordpress folder to htdocs of xampp.

3. Access phpmyadmin dashboard and make a database for wordpress. Name it whatever you want. Usually you can access it by `localhost:$port/phpmyadmin`

4. Go to wordpress setup and fill out the details. Usually it's in `localhost:$port/wordpress` (_if your folder name is wordpress_)

> Tip: I experienced permission errors on mac while going through the setup so remember to set your `htdocs/wordpress` folder permisions to read and write.
