# LF
Learning how to source control with new tools 

Johnny's commands for setting up posgres .db:

Last login: Tue Aug 25 10:19:04 on ttys001
blake:~ blakebutterworth$ '/Applications/Postgres.app/Contents/Versions/9.4/bin'/psql -p5432
psql (9.4.4)
Type "help" for help.

blakebutterworth=# \d
No relations found.
blakebutterworth=# \dt
No relations found.
blakebutterworth=# CREATE database test;
CREATE DATABASE
blakebutterworth=# \connect test
You are now connected to database "test" as user "blakebutterworth".
test=# \d
No relations found.
test=# CREATE TABLE test_table(
test(# "row_id" SERIAL PRIMARY KEY,
test(# "data" JSONB NOT NULL);
CREATE TABLE
test=# \d
                      List of relations
 Schema |         Name          |   Type   |      Owner       
--------+-----------------------+----------+------------------
 public | test_table            | table    | blakebutterworth
 public | test_table_row_id_seq | sequence | blakebutterworth
(2 rows)

test=# \dt test_table
               List of relations
 Schema |    Name    | Type  |      Owner       
--------+------------+-------+------------------
 public | test_table | table | blakebutterworth
(1 row)

test=# \d test_table
                           Table "public.test_table"
 Column |  Type   |                          Modifiers                          
--------+---------+-------------------------------------------------------------
 row_id | integer | not null default nextval('test_table_row_id_seq'::regclass)
 data   | jsonb   | not null
Indexes:
    "test_table_pkey" PRIMARY KEY, btree (row_id)

test=# 
