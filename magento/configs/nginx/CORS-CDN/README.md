## CORS issue fixing

Installing the **Edgeport - Premium CDN Add-On** on Magento 2 application, you will be experiencing the [**Cross-Origin Resource Sharing (CORS)**](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) issue which is invoked when a web application executes a cross-origin HTTP request when it requests a resource that has a different origin (domain, protocol, and port) than its own origin.
 
There are several ways how to overcome this issue. One of them we describe here for **NGINX** application server:
   
1. Open [**Jelastic Configuration Manager**](https://docs.jelastic.com/configuration-file-manager) and create new **/etc/nginx/conf.d/cors** directory. 

2. Upload [**cors.conf**](https://raw.githubusercontent.com/sych74/magento/master/CORS-CDN/cors.conf) file from repository directory [**CORS-CDN**](https://github.com/sych74/magento/tree/master/CORS-CDN) to **/etc/nginx/conf.d/cors** directory.
   
3. Edit **/etc/nginx/conf.d/site-default.conf** according to provided example [**site-default.conf**](https://raw.githubusercontent.com/sych74/magento/master/CORS-CDN/site-default.conf) in repository directory [**CORS-CDN**](https://github.com/sych74/magento/tree/master/CORS-CDN).
The changes should be added as the lines **76, 96, 108** and **119** to **/etc/nginx/conf.d/site-default.conf** and look as follows:

***include /etc/nginx/conf.d/cors/cors.conf;***  

4. Change the URLs in magento admin panel like as on the example picture below in case **SITE_DOMAIN** is **magento.jelastic.cloud** and generated by Add-On **CDN_DOMAIN** is **magento-demo.cdn.edgeport.net**:

<p align="left"> 
<img src="../images/urls-example.png" width="600">
</p>

5. Clear Magento cache. 

<p align="left"> 
<img src="../images/cache-clearance.png" width="600">
</p>
  
6. Restart application server to apply changes.
 
<p align="left"> 
<img src="../images/appserver-restart.png" width="600">
</p>

7. Clear CDN cache with Add-On's built-in feature **Purge All**
  
<p align="left"> 
<img src="../images/purgeall.png" width="400">
</p>
  
8. Wait up to 1 hour for static assets to be propagated across **CDN Points-of-Presence**.


