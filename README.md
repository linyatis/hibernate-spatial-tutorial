Working project for Hibernate Spatial 4 Tutorial 
================================================

This project is based on [Hibernate Spatial 4 Tutorial][1], working with PostgreSQL + PostGIS (but you can also use with others databases, just change the [dialect][2] in persistence.xml.

Follow these instructions to run this project:

###Preparing database
1. Create database hstutorial
Note: if needed, change url, username and password for you database connection, into persistence.xml.

2. In hstutorial database, run psql `CREATE EXTENSION postgis;`

###Preparing application
1. Clone and compile this project: 
```
git clone https://github.com/linyatis/hibernate-spatial-tutorial.git
cd hibernate-spatial-tutorial
mvn compile
```

###Running application
1. Save some data:  
    ```
    mvn exec:java -Dexec.mainClass="event.EventManager" -Dexec.args="store POINT(10 5)"
    ```
2. Select points inside a polygon:  
    ```
    mvn exec:java -Dexec.mainClass="event.EventManager" -Dexec.args="find POLYGON((1\ 1,20\ 1,20\ 20,1\ 20,1\ 1))"
    ```
3. Be happy =)

[1]: http://www.hibernatespatial.org/documentation/02-Tutorial/01-tutorial4/
[2]: http://www.hibernatespatial.org/documentation/03-dialects/01-overview/
