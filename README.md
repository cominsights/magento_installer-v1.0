# About Commerce Insights #
Scalend Commerce Insights platform for merchants is a DIY solution that blends your Payment data ( PayPal, Stripe, ..), clickstream data ( Google Analytics,..), & store data (Magento) into a single dashboard and provides actionable insights to increase sales.

## Supported Channels ##
1. Shopping cart
   * Magento
   * Shopify

2. Clickstream data
   * Google Analytics
   
3. Payment Gateway
   * Paypal
   * Stripe
   
# Magento Installation #

The Scalend Magento Extension has to be manually installed using FTP client into the server which holds the magento installation

1. Download scalend.zip and extract contents into a local folder
2. Use FTP clients like Filezilla or WinScp to upload scalend_magentoAPI into the home directory of the magento server.
   Eg. /home/ubuntu
3. Open putty for SSH connection to the magento server.
   1. Browse to /var/www/html/app/code
   2. Create a directory named - Scalend
   3. Command : sudo mkdir var/www/html/app/code/Scalend
   4. Move scalend_magentoAPI (from Step 2.) to var/www/html/app/code/Scalend
   5. Command - sudo cp -avr /home/ubuntu/MagentoApi /var/www/html/app/code/Scalend/
   6. Run the following commands from the /var/www/html folder  
          php bin/magento setup:di:compile;  
          php bin/magento cache:flush;  
          
# Setting up Scalend Commerce Insights #

1. Register with https://insights.scalend.com/login.html
2. From the configuration page, click Magento Connect
3. Choose Magento installer

*A token will be generated from Scalend system. This token is to be entered in Magento Admin Panel*

## Magento Admin panel Configuration ##

1. Login to Magento 2 Admin panel
2. Click Stores -> Configuration -> ‘Scalend’ extension will be visible in the sidebar.
3. Enter the token that was generated in Step 4 of setting up Commerce insights -> Save Config

# Troubleshooting #
In case of access / permission issues with Magento admin after installation of extension,

Login to putty and run the following commands:  
      php bin/magento setup:upgrade;  
      chmod -R 0777 pub/;  
      chmod -R 0777 var/;  
