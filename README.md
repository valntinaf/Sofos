# Sofos

[![Watch the video](https://i.ibb.co/NyLnxj4/Untitled-design.png)](https://www.youtube.com/watch?v=qmxDSp5-WMk)

## Running database

> Once cockroach is installed.

Running cockroack
```bash
cockroach start --insecure  
```

Now cockroach is running on port 8080.

Running sql shell
```bash
cockroach sql --insecure
```

## Setting Database

> Execute in the shell


```sql
CREATE DATABASE sofos;
```

```sql
SET DATABASE = sofos;
```


```sql
CREATE TABLE DomainInformation (
    SSLGrade VARCHAR(5),
    Title VARCHAR(100),
    IsDown BOOLEAN,
    Domain VARCHAR(50)
  );
```

```sql
CREATE TABLE HistoryQueries (
    Domain VARCHAR(50),
    LatestQuery TIMESTAMP
  );
```

```sql
CREATE TABLE RelatedServers (
    Domain VARCHAR(50),
    Server VARCHAR(50)
  );
```

```sql
CREATE USER IF NOT EXISTS sofos_u;
ALTER USER sofos_u WITH PASSWORD 'g7D239Asn1';
```


```sql
GRANT ALL ON historyQueries TO sofos_u;
GRANT ALL ON DomainInformation TO sofos_u;
GRANT ALL ON RelatedServers TO sofos_u;
```

## Running Go Server

>  Once go is installed

```bash

cd go_chi

./main

```
Now go is running on port 3000.


> In order to rebuild the executable.

```bash

go get -u github.com/go-chi/chi

go get -u github.com/lib/pq

```


## Running Web Server

>  Once Node and npm are installed


```bash

npm install -g @vue/cli

cd vue_app

npm install

npm run serve
```

Now go is running on port 8081.


> The web application will be available at localhost:8081 if the port is not being used.
