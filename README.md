Simple-Wordpress-Multisite
==========================

Run multiple Wordpress sites on separate databases using 1 Wordpress installation

Installation Instructions
=====================

1.Create define your private string
----------
> - this string will be prepended to your db name
> - since your dbname and passwords are usually different. Your private string will be set as your password for all sites
> **NOTE: Wordpress Multi-site normally uses the same method. One db username with one db password **

2.Setup Databases and Define Domains
---------

> - remember the database name should make should have the private string prepended to the name.
> - example: gh8YG5O1Ppmy_db_name
> - point all Wordpress domains to the single wordpress directory on your server.

3. Begin Wordpress Setup
---------

> - Go to your first domain and initalize wordpress installer.


4. COMPLETED!!
---------
>- if you encounter any errors like db connection error, check to make sure your private password matches the one used during the database creation.
>- you can now log into each domain using a single Wordpress Installation

Caveates
--------
***Specify upload path per site using this code in your themes function.php***
***This will keep the upload path for every site nice and organized***

    add_filter( 'pre_option_upload_path', 'upload_path_files' );
        function upload_path_files(){
         return 'sites/'.array_shift(explode(".",$_SERVER['HTTP_HOST'])).'/uploads';  
        }

