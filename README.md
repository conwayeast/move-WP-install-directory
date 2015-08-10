# move-WP-install-directory
directions on how to move the WordPress install to a different directory


Sometimes you want to put your WordPress install into its own folder. This will help avoid clutter in your web hosting environment by removing all those WordPress files and folders from the root of your domain, and it will make it easier to manage various web endeavors. Suppose you want to add other web software installs; you may have a hard time finding the files you need if they're all mixed in together (although it helps that everything WordPress at this level is named wp-something). It gets messy if you want to do anything other than just use WordPress.

Installing to a subfolder is the same as installing to the root of a domain. The idea is to have the WordPress install in a subfolder but have the blog being displayed as if it were in the root folder, while keeping the root folder on the server clean. You can either install WordPress to a subfolder directly or install it to the root folder and then move the files to a subfolder. How you decide to tackle it is up to you; both ways are easy.

The following instructions assume that you already installed WordPress in your root folder and now want to move it to a subfolder. For this example, suppose that you have WordPress installed in the root folder (domain.com) and want it to be in a subfolder called wpsystem instead, while keeping the actual site in root. This means that when people visit http://domain.com, they'll see your WordPress site, but when you log in and manage it, you'll be working in the wpsystem folder (or domain.com/wpsystem/wp-admin/, to be precise).

You should set up permalinks before doing this because you'll want them to work regardless of whether you use a subfolder.

To move your WordPress install to the new directory, first create the wpsystem folder. Then go to the General Settings page and change the WordPress address URL field to http://domain.com/wpsystem to reflect your new folder, and the Blog address URL field to http://domain.com, where you want your site to be. Next, click the Update button and move all the WordPress files to thier new directory at http://domain.com/wpsystem, except for the index.php and .htaccess files, which should be where you want your site to be (http://domain.com).

When the files have been moved, open index.php and locate this code snippet:

  require('./wp-blog-header.php');
  
Replace it with this code snippet

  require('./wpsystem/wp-blog-header.php');
  
As you can see, the code now points to the wpsystem folder instead and to the wo-blog-header.php file.

Log in to the WordPress admin interface (which is now on http://domain.com/wpsystem/wp-admin/) and update the permalinks, and there you have it.


More info at: https://codex.wordpress.org/Giving_WordPress_Its_Own_Directory

