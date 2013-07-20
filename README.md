fluxui
======
Web interface for [loadreport.js](https://github.com/wesleyhales/loadreport). Live application can be viewed at [http://loadreport.wesleyhales.com/](http://loadreport.wesleyhales.com/)

## Dependencies:

  * Java 1.6          `javac -version`
  * Phantomjs 1.6     `phantomjs -v`
  * MySQL Server 5.5
  * Apache Maven 3

Download [Maven 3](http://maven.apache.org/download.html) and unzip. Add `maven3-dir/bin` to your path.

## Setup
Create a new database and add user:

        mysql -u root
        CREATE database fluxui;
        CREATE USER 'fluxui'@'localhost' IDENTIFIED BY 'fluxui123';
        GRANT ALL PRIVILEGES ON fluxui.* TO 'fluxui'@'localhost' WITH GRANT OPTION;

## Start JBoss Application Server
Unzip jboss-as-7.1.1.Final-fluxui.zip to the filesystem root in /www/ (should be /www/jboss-as-7.1.1.Final-fluxui/)

        ./bin/standalone.sh --server-config=standalone-full.xml -b 0.0.0.0

Visit 0.0.0.0:8080 or localhost:8080 (if your hosts file permits) in your browser to see the app in action.

## Deployment
Build and copy the application to the appserver from project root:

        mvn clean package;cp -rf target/fluxui.war /www/jboss-as-7.1.1.Final-fluxui/standalone/deployments/

## Notes
The [loadreport.js repo](https://github.com/wesleyhales/loadreport) is already cloned into the appserver directory. If you need to make changes to the phantomjs script, make 'em there.

## Contributing

1. Fork it
2. Commit your changes (`git commit -am 'Add some feature'`)
3. Push to the branch (`git push origin master`)
4. [Create new Pull Request](https://github.com/fluxui/FluxServer-Java/pulls)