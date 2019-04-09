# MYACEPORTRAIT

This is a cloud based first-time-hire profile advertisement application to allow for still active or recently graduated students to showcase their non-workplace verified skill sets to potential employers. It is meant to include an anonymous base of profiling from the potential hiree, or prospect's, perspective. In this way, prospects cannot see the interaction base of their cohort potentials, and can only see the interest of hunters should the hunter attempt contacting them through the asynchronous contact functionality provided within. 

The app currently exists actively within a DigitalOcean Ubuntu 16.04 droplet interactable upon call to the http://myaceportrait.tk domain. DigitalOcean IaaS was chosen for it's potential as an elastic and scalable service upon increasing user demand. The application itself is a Python based implementation taking advantage of the toolset offered to the Python programming language through the Django webframework. Django was selected as the basis for implementation due to it's feasible inclusion of Python control between front end and back end interaction, and due to the fluidity involved in allowing for feature expansion upon necessity due to the wide spread library inclusion within. 

myACEportrait is a valid means of functionality for usage described above, and leaves enough editablility to include expansion potential for whatever functionality may come to be required upon usage implications.   

## Getting Started

In order to run in a cloud VM, as is done currently @ http://myaceportrait.tk, it is necessary to install and configure apache2 as described here. Redis and uwsgi are implemented through the Django web framework concurrently, as provided through the internal Django configuration of a stock project, in order to allow for differentiating synchronous HTTP calls for application usage, and asynchronous wsgi calls for smtp interaction of hunters to huntees upon request. The ServerConfig of the Apache2 server running the initial HTTP interaction of users to the Django maintained interactions are kept within the /server directory of the root of this repository. All of the files included in /ServerConfig should be in your Ubuntu VM before starting of the server. It is also necessary that the cloud VM run is an Ubuntu VM running version 16.04.

1) Follow the instructions provided @ https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-18-04-quickstart in order to configure apache2 within your DigitalOcean droplet.

2) Edit your apache2 deault at /etc/apache2/sites-available/000-default.conf to that mimic that in /server/000-default.conf

3) Clone this repository into the directory located at /webapps/myaceportrait/ in your droplet
  
4) Run "$ sudo ln -s /etc/apache2/sites-available/ /etc/apache2/sites-enabled" in order to symlink your apache2 sites-available to the sites-enabled for appropriate interaction upon starting the server. 

5) Run "$sudo service apache2 start" in order to begin distribution of the applications from your droplet 

Should local running of the app be required, simpley clone this repository to your local device and run "$ python manage.py runserver 0.0.0.0:8000" from within the same directory as that including the manage.py script of the app within your device. Port 8000 can be altered to whatever preference you have should you require an alternative port.

## Location of Corresponding Content Within this Repo



## Built With

* [Django](https://www.djangoproject.com/) - The web framework used, including functionality of synch to asych control server uwsgi and redis queueing mechanism for differentiating the different types of HTTP calls
* [Apache2](https://help.ubuntu.com/lts/serverguide/httpd.html) - The overarching URL request server
* [DigitalOcean](https://www.digitalocean.com/) - Used to allow for cloud distribution through an IaaS Ubuntu 16.04 droplet VM

## Authors

* **Brady Ibanez** 
* **Navjot Aulakh**
* **Nicolas Zarfino**
