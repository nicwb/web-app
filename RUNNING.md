## Running the Project Backend

1. Start PostgreSQL 10 docker image `pgsql-db-faculty`
    ```bash
    docker run -d -p 5432:5432 pgsql-db-faculty
    ```
2. Compile and Package `spring-cloud-config`: run the following in the _spring-cloud-config_ directory
    ```bash
    mvn compile
    mvn package
    docker run -d -p 8888:8888 spring-cloud-config:1.0
    ```
3. Compile and Package `eureka`: run the following in the _eureka_ directory (**failing**)
    ```bash
    mvn compile
    mvn package
    docker run -d -p 8761:8761 eureka:1.0
    ```
4. Compile and Package `faculty`: run the following in the _faculty_ directory
    ```bash
    mvn compile
    mvn package
    docker run -d -p 9100:9100 faculty:1.0
    ```
5. Compile and Package `report`: run the following in the _report_ directory
    ```bash
    mvn compile
    mvn package
    docker run -d -p 9200:9200 report:1.0
    ```
6. Compile and Package `zuul`: run the following in the _zuul_ directory
    ```bash
    mvn compile
    mvn package
    docker run -d -p 8765:8765 zuul:1.0
    ```