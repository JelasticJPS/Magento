[![Magento](images/magento.png)](../../../magento)
## Magento

The JPS package deploys Magento that initially contains 1 application server and 1 database container.

### Highlights
This package is designed to deploy Magento environment which represents an open-source e-commerce platform written in PHP.<br />Magento employs the MySQL relational database management system, the PHP programming language, and elements of the Zend Framework. It applies the conventions of object-oriented programming and model–view–controller architecture. Magento also uses the entity–attribute–value model to store data.

### Environment Topology

![Magento Topology](images/magento-apache.png)

### Specifics

Layer                |     Server    | Number of CTs <br/> by default | Cloudlets per CT <br/> (reserved/dynamic) | Options
-------------------- | --------------| :----------------------------: | :---------------------------------------: | :-----:
AS                   | Apache 2 (MOD_PHP) |       1                        |           1 / 16                          | -
DB                   |    MySQL      |       1                        |           1 / 16                           | -

* AS - Application server 
* DB - Database 
* CT - Container

**Magento Version**: 2.1.6<br/>
**PHP Engine**: PHP 5.6.x<br/>
**MySQL Database**: 5.7.12

### Deployment

In order to get this solution instantly deployed, click the "Get It Hosted Now" button, specify your email address within the widget, choose one of the [Jelastic Public Cloud providers](https://jelastic.cloud) and press Install.

[![GET IT HOSTED](https://raw.githubusercontent.com/jelastic-jps/jpswiki/master/images/getithosted.png)](https://jelastic.com/install-application/?manifest=https://raw.githubusercontent.com/jelastic-jps/magento/master/magento21-apache-php56-mysql/manifest.jps)

To deploy this package to Jelastic Private Cloud, import [this JPS manifest](https://raw.githubusercontent.com/jelastic-jps/magento/master/magento21-apache-php56-mysql/manifest.jps) within your dashboard ([detailed instruction](https://docs.jelastic.com/environment-export-import#import)).

More information about Jelastic JPS package and about installation widget for your website can be found in the [Jelastic JPS Application Package](https://github.com/jelastic-jps/jpswiki/wiki/Jelastic-JPS-Application-Package) reference.
