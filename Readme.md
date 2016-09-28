Example taken from:
http://www.benchresources.net/apache-cxf-jax-rs-restful-web-service-integrating-with-spring-hibernate/

+jetty runner added

-----------------------------

CREATE DATABASE BENCHRESOURCES;

CREATE TABLE `PLAYER` (
  `PLAYER_ID` INT(6) NOT NULL AUTO_INCREMENT,
  `NAME` VARCHAR(50) NOT NULL,
  `AGE` INT(3) NOT NULL,
  `MATCHES` INT(3) NOT NULL,
  PRIMARY KEY (`PLAYER_ID`)
);

INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Sachin Tendulkar",41,200);
INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Shane Warne",44,145);
INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Kevin Pietersen",34,104);
INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Shahid Afridi",35,27);
INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Brian Lara",45,131);
INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Graeme Smith",34,117);
INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Mahela Jayawardene",37,145);
INSERT INTO `PLAYER`(`NAME`, `AGE`, `MATCHES`) VALUES ("Steve Waugh",49,168);

mvn clean install
mvn package
java -jar target/dependency/jetty-runner.jar target/*.war

http://localhost:8080/services/playerservice/getplayer/1
http://localhost:8080/services/playerservice/getallplayer
