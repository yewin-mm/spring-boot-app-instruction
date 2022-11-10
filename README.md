<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/yewin-mm/spring-boot-app-instruction.svg?style=for-the-badge
[contributors-url]: https://github.com/yewin-mm/spring-boot-app-instruction/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/yewin-mm/spring-boot-app-instruction.svg?style=for-the-badge
[forks-url]: https://github.com/yewin-mm/spring-boot-app-instruction/network/members
[stars-shield]: https://img.shields.io/github/stars/yewin-mm/spring-boot-app-instruction.svg?style=for-the-badge
[stars-url]: https://github.com/yewin-mm/spring-boot-app-instruction/stargazers
[issues-shield]: https://img.shields.io/github/issues/yewin-mm/spring-boot-app-instruction.svg?style=for-the-badge
[issues-url]: https://github.com/yewin-mm/spring-boot-app-instruction/issues
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/ye-win-1a33a292/

# spring-boot-app-instruction
* This is the sample instruction to setting up Java, Spring boot application.

<!-- TABLE OF CONTENTS -->
## Table of Contents
- [About The Project](#about-the-project)
- [Before you begin](#before-you-begin)
- [Prerequisites](#prerequisites)
- [Instruction](#instruction)
    - [Git Clone and Download](#git-clone-and-download)
    - [Import in IDE](#import-in-IDE)
    - [Prepare Database Setting (For RDBMS)](#prepare-database-setting)
        - [For MySQL](#for-mysql)
        - [For Postgresql](#for-postgresql)
        - [For Oracle](#for-oracle)
    - [Run Project](#run-project)
    - [Database GUI](#database-gui)
    - [Testing](#testing)
- [Contact Me](#contact)
- [Contributing](#Contributing)


## About The Project
This is the sample instruction to setting up Java, Spring boot based application. <br>
Here, you can learn which application are needed to develop your application and which tips are needed while developing application. 

## Before you begin
Before you do instruction, you should setting up and download needed application in you machine which are in [Prerequisites](#prerequisites) section.


## Prerequisites
* Install Git in you machine. [Get Git](https://git-scm.com/downloads)
* Install Java in your machine. [Get Java](https://www.oracle.com/au/java/technologies/javase/javase-jdk8-downloads.html) 
* Install Maven in your machine. [Get Maven](https://maven.apache.org/download.cgi) 
    * Please note that maven is no need to install as installer file and just need to set Environment variable in your machine, please see how to install Maven in google.
* Install your favourite java IDE in your machine eg. [IntelliJ](https://www.jetbrains.com/idea/download/) or [Eclipse](https://www.eclipse.org/downloads/packages/release/photon)
* Install MySQL database in your machine [Get MySQL](https://dev.mysql.com/downloads/installer/) (If you want to use Mysql)
* Install Postgresql database in your machine [Get Postgresql](https://www.postgresql.org/download/) (If you want to use PostgreSQL)
    * Here, You can install your favourite database like Oracle, etc.
* If you want to run your database with Docker [Get Docker](https://docs.docker.com/get-docker/) or Homebrew (MacOs) [Get Homebrew](https://brew.sh/), you can find way to run your Database with docker, etc in google. (For that case, you need to install Docker in your machine first)
* Install project lombok in your IDE. (My projects used Lombok and you need to add lombok plugin if you want to test by projects,)
    * if you don't know how to install lombok in your IDE, please reference in google. [install lombok in IntelliJ and Eclipse](https://www.baeldung.com/lombok-ide)
    * Please make sure lombok dependency is added in your `pom.xml` file too.
* Install Postman for testing backend API. [Get Postman](https://www.postman.com/)


## Instruction
### Git Clone and Download
1. Go to your folder with Command Prompt (window) or Terminal (MacOs and Linux) where you want to put your liked git project and type git clone command. (You can either use Git Bash or other command line terminal)
    * Go to GitHub project repository [see my project list](https://github.com/yewin-mm?tab=repositories) which you want to checkout, you need to click `Code` button which located top right corner of Git repository and choose HTTPS instead of GitHub Cli and SSH.
    * Copy the given link in there and type `git clone` in your Command Prompt and then Paste your copy link and press `Enter`. 
    * There, link should start with `https://github.com/{your_name}/{app_name}` and end with `.git`.
    * Another way is you can copy link from `browser address link bar` when your cursor is reached source of git project repository and add `.git` at the end of the link), you can type in your Command Prompt like git clone {paste your browser bar copied link}.git.
    * Please note that your git clone Command should start with `git clone` followed by space and `https://github.com/{your_name}/{app_name}` and after that project repository link will follow and should end with `.git` .
    * After that You can see some text like `Cloning into etc..` and "remote etc.." after that, go to your command prompt located folder and you will see your cloned project is in there.
    * Below git clone command is one of my sample project link. So, there can be change as your desire project link.
    ```sh
   eg. git clone https://github.com/yewin-mm/spring-boot-sample-crud.git
2. If you don't want to clone this project, you can also download as zip file by clicking `Code` button which located top right corner of git repository and choose `Download Zip` and move to your desire folder and unzip that downloaded project.

### Import in IDE
* Import your cloned or downloaded project.
* For Intellij IDE,
  * Under File menu, Click Open and choose your project path directory (which project folder should be parent folder of pom.xml, other folders like src, etc)
  * Another way is Click Open and go to your project path directory and go inside and click `pom.xml` and choose open as  a project. 
* For Eclipse IDE,
  * Under file menu, click Import and under Maven, choose existing maven projects and add your project path directory.

### Prepare Database Setting
* If your application is not use any Database, you can skip this section.
* Below is for demo RDBMS configurations. If you use No-SQL database, you can reference in google.
* You need to setup in your application which is depend on your installed database. eg. if you installed Mysql, please reference [For MySQL](#for-mysql) section.
* Find the `application.properties` file which located under `/src/main/resources` of your project.
* Find the `pom.xml` file which located under project `Root folder` (source directory).


* If you got error with database when you run the application, please see in google as reference. 
* as an example, sometime, you might got no privilege or permission denied error in Postgresql. If so, you need to create new user or new database with name 'postgres' and grant access on that. (please see in google as reference for that)
* If you don't use Postgresql database, please change your database driver in `pom.xml` file and change your database url, username, password and dialect in `application.properties` file. 


#### For MySQL

* Sample MySQL connector dependency which need to add in `pom.xml`.
    ```sh 
     <dependency>
         <groupId>mysql</groupId>
         <artifactId>mysql-connector-java</artifactId>
         <scope>runtime</scope>
     </dependency>
    ```
    
    * Copy above code and paste between `<dependencies> </dependencies>` tag of `pom.xml` file and refresh your pom.xml to make sure your new dependency is imported into your project. 
        * For IntelliJ, right click anywhere insdie `pom.xml` or right click on `pom.xml` and choose `maven` and click `reload project`.
        * For Eclipse, right click on `pom.xml` and choose `maven` and click `update project`.
    * You can check new dependency is added in your project under `External Libraries` of `IntelliJ` and `Maven Dependencies` of `Eclipse`.
    * Sometimes, you need to clean your project.
        * For IntelliJ, click `File` menu in top left corner and choose `Invalidate Caches` and (check mark on clear file system cache and local history in new version) click `Invalidate and Restart`.
        * For Eclipse, click `Project` menu in top left corner and choose `clean` and check mark on your project and click `OK`.
    * You can manually add jar for non Maven Project in both IDE.

* Change your MySQL Database username and password in spring datasource username and password fields in `application.properties` file.
* Sample MySQL properties which need to add in `application.properties`
    ```sh
         #here testdb is database name and you can use your database name or you can create new database with name testdb
     spring.datasource.url=jdbc:mysql://localhost:3306/testdb
         #username is your mysql user name
     spring.datasource.username=your username
         #password is your set password
     spring.datasource.password=your password
         #if you are using mysql 5 version, you need to remove cj and so, it will be com.mysql.jdbc.Driver. below is for MySql version 5.
     spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
         #you need to change your mysql version in dialect, eg. if you install MySQL 8, dialect will be MySQL8Dialect
     spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
     spring.jpa.hibernate.ddl-auto=update
    ```
* Copy above code and paste in `application.properties` to connect MySQL Database.

#### For Postgresql

* Sample Postgresql connector dependency which need to add in `pom.xml`. (My sample projects use postgres and you don't need to add again if that dependency is already existed in `pom.xml`)
       ```sh 
        <dependency>
            <groupId>org.postgresql</groupId>
            <artifactId>postgresql</artifactId>
            <scope>runtime</scope>
        </dependency>
       ```

    * Copy above code and paste between `<dependencies> </dependencies>` tag of `pom.xml` file and refresh your pom.xml to make sure your new dependency is imported into your project. 
        * For IntelliJ, right click anywhere insdie `pom.xml` or right click on `pom.xml` and choose `maven` and click `reload project`.
        * For Eclipse, right click on `pom.xml` and choose `maven` and click `update project`.
    * You can check new dependency is added in your project under `External Libraries` of `IntelliJ` and `Maven Dependencies` of `Eclipse`.
    * Sometimes, you need to clean your project.
        * For IntelliJ, click `File` menu in top left corner and choose `Invalidate Caches` and (check mark on clear file system cache and local history in new version) click `Invalidate and Restart`.
        * For Eclipse, click `Project` menu in top left corner and choose `clean` and check mark on your project and click `OK`.
    * You can manually add jar for non Maven Project in both IDE.

* Change your Postgresql Database username and password in spring datasource username and password fields in `application.properties` file. 
* Postgresql default username is postgres and password is your set password when you installed.
* Sample Postgresql properties which need to add in `application.properties`
   ```sh
    spring.datasource.url=jdbc:postgresql://localhost:5432/postgres
        #username is your postgresql user name and default is postgres
    spring.datasource.username=postgres
        #password is your set password which need to set when you install.
    spring.datasource.password=postgres
    spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
    spring.jpa.hibernate.ddl-auto=update
        # For postgresql database, it's need to set true for hibernate con_contextual creation because default is false  ## update - it's not need to set true after spring version 2.2.x.
    spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
   ```
    * Copy above code and paste in `application.properties` to connect PostgreSQL Database.
     
#### For Oracle
* Please note that Oracle don't have public repository and so need to add jar file as manual in your maven.
* Go to this link [Maven Repository](https://mvnrepository.com/artifact/com.oracle.database.jdbc/ojdbc6/11.2.0.4) and download jar file by clicking Jar (top-middle) of File column.
* Type in you Command Prompt like below
   ```sh 
    mvn install:install-file -Dfile=path/to/your/ojdbc6-11.2.0.4.jar -DgroupId=com.oracle -DartifactId=ojdbc8 -Dversion=11.2.0.4 -Dpackaging=jar
   ```
    * There -Dfile value is path of your downloaded jar file (including jar file name) and the -Dversion= is depends on your database version, here, I tested with Oracle XE 11g.
* Sample Oracle connector dependency which need to add in `pom.xml`.
   ```sh 
    <dependency>
        <groupId>com.oracle.database.jdbc</groupId>
        <artifactId>ojdbc6</artifactId>
        <version>11.2.0.4</version><!-- This is your downloaded oracle jar file version which give in above Maven Repository link -->
    </dependency>
   ```

    * Copy above code and paste between `<dependencies> </dependencies>` tag of `pom.xml` file and refresh your pom.xml to make sure your new dependency is imported into your project. 
        * For IntelliJ, right click anywhere insdie `pom.xml` or right click on `pom.xml` and choose `maven` and click `reload project`.
        * For Eclipse, right click on `pom.xml` and choose `maven` and click `update project`.
    * You can check new dependency is added in your project under `External Libraries` of `IntelliJ` and `Maven Dependencies` of `Eclipse`.
    * Sometimes, you need to clean your project.
        * For IntelliJ, click `File` menu in top left corner and choose `Invalidate Caches` and (check mark on clear file system cache and local history in new version) click `Invalidate and Restart`.
        * For Eclipse, click `Project` menu in top left corner and choose `clean` and check mark on your project and click `OK`.
    * You can manually add jar for non Maven Project in both IDE.

* Change your Oracle Database username and password in spring datasource username and password fields in `application.properties` file. 
* Sample Oracle properties which need to add in `application.properties`
   ```sh
        #here tested with Oracle 11g XE database.
    spring.datasource.url=jdbc:oracle:thin:@localhost:1521:xe
        #username is your oracle user name
    spring.datasource.username=your username
        #password is your set password
    spring.datasource.password=your password
    spring.jpa.hibernate.ddl-auto=update
    spring.datasource.driver-class-name=oracle.jdbc.driver.OracleDriver
   ```
    * Copy above code and paste in `application.properties` to connect Oracle Database.
   
### For more details about database setting and for other databases, please see in google.
   
### Run Project
* Run the project in your IDE (eg. Run in Intellij or Eclipse).
    * Click run button in your IDE or find the class name which name is end with `Application` which has main method and it's under `/src/main/java/{package}/`, right click on that `Application` class and choose Run or Run as java application.
    * You can also click `run` button of your IDE if your IDE default is point to that `Application` main class. With that case, sometimes, you might got `could not found main class` error.
    * See the console log and find below text log in your IDE.
        * eg. Started SpringBootSampleCrudApplication ..etc. log (it's mean application is successfully run) 
        * eg. APPLICATION FAILED TO START ..etc. log. (it's mean application cannot run and got error). For that case, please find the root error and reference to google for that error. 
        * If some error like port is already use, you need to change the port in `application.properties` file or stop (terminate) other process or application which is using the same default port (8080). 

### Database GUI
* Database GUI is easier to use rather than doing by database query operation in Command Prompt.
* You can easily view your data easily in Database GUI tools.
* There are many good GUI tools eg. DataGrip (not free) [Datagrip](https://www.jetbrains.com/datagrip/), DBeaver (free) and SQL developer, etc. 
* Here, you can use free database gui tools like [Dbeaver](https://dbeaver.io/) to connect and view the database.
* If you use that, firstly, you need to connect to your database with DBeaver. Do new Database Connection in DBeaver and choose your installed database (if you don't know, see how to connect database with DBeaver in google).
* DBeaver need to install Jar file as per your connected (installed) database.
* For the usage of GUI tools like Datagrip, DBeaver, you can see more about in google.
* After you run spring boot application which use jpa and use ddl to update to your entity class table, you should see the table which is auto create table by your application by entity class in DBeaver. If you can't see, you can refresh you database in DBeaver and find that table again. 
 
### Testing
* You can test backend microservice application by calling API. In there, you can use Postman (which give in above) or SoupUI tools.
* You can also use Test class (under src/test folder) for unit testing and api calling by code.
* All of my repositories projects will give you sample Postman collection (under project root directory) which make easier to test instead of typing manual in Postman by checking code, endpoint and parameters.
* Import sample postman json file which file name ended with `.json` and located under project Root folder (Source directory) into your installed Postman application.
* You can see that file in my all repositories and normally I gave the name is same with application name and it's ended with `.json`.
* Click in your Postman (top left corner) import -> file -> upload files -> {choose that json file} and open/import.
* After that, you can see the folder which you import from file in your Postman.
* Now, you can 'Test' your cloned application by calling API from Postman. (make sure the application was running)
    * Click 'Send' button for each API request which inside imported folder in your Postman and see the response. 
    * You can check data in database too for the application which use database (here you can check data in table as per Entity class by DBeaver tools or other GUI tools, or you can even manually select query in your database console)
* After testing api, you can see the code and check the code which you don't know. You can learn it, and you can apply in your job or study fields.

***Have Fun and Enjoy in Learning Code***

## Contact
Name - Ye Win <br> LinkedIn profile -  [Ye Win's LinkedIn](https://www.linkedin.com/in/ye-win-1a33a292/)  <br> Email Address - yewin.mmr@gmail.com

My Repository Link: [Java Spring Framework Projects](https://github.com/yewin-mm?tab=repositories)


## Contributing
Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.
<br>If you want to contribute....
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/yourname`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push -u origin feature/yourname`)
5. Open a Pull Request

