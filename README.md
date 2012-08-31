fluxui
======

to run:
* Make sure you're running at least Java 1.6 ($> javac -version)
* ensure phantomjs 1.6+ is installed
* download and unzip [maven 3](http://maven.apache.org/download.html) and add "maven3-dir"/bin to your path

## install mysql 5.5
* create a new database and add user
** mysql -u root
** CREATE database fluxui;
** CREATE USER 'fluxui'@'localhost' IDENTIFIED BY 'fluxui123';
** GRANT ALL PRIVILEGES ON fluxui.* TO 'fluxui'@'localhost' WITH GRANT OPTION;

## run the app server
* unzip jboss-as-7.1.1.Final-fluxui.zip to the filesystem root in /www/ (should be /www/jboss-as-7.1.1.Final-fluxui/)
* run the server with...
** ./bin/standalone.sh --server-config=standalone-full.xml -b 0.0.0.0

## build and copy the application to the appserver for deployment
* from the root of this project run...
* mvn clean package;cp -rf target/fluxui.war ~/wherever-you-unzipped-to/jboss-as-7.1.1.Final-fluxui/standalone/deployments/

## Notes
* the loadreport.js git repository is already cloned into the appserver directory. if you need to make changes to the phantomjs script, make 'em there.