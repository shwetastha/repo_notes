# Art of Prostgres

Part IV: SQL Toolbox

Loading Dump:
- Installing the dump was pain.
- mysql 8 did not owrk
- installed mysql 5.7 
- then issue with the authentication
- solved with changes in my.cnf
- finally pgloader worked.

## Queries
- DML- Data Manipulation Language
- DDL- Data Definition Language
- TCL- Transaction Control Language
	- commit, rollback, savepoint
- DCL- Data control Language
	- grant and revoke
- Postgres maintanence commands
	- vaccum, analyze, cluster 

SELECT
- projection
- select * from races limit 1;
	- select * from races fetch first 1 rows only;

JOIN
- also can use subquery

WHERE
- where not exists
- using select 1 to just check if the filter exists or not.

Ordering
- kNN Ordering and GiST indexes:
	- select name, location, country from circuits
	order by point(lng,lat) <-> point(2.349014, 48.864716) limit 10;
	- <-> gives the distance
	- order by nulls last
	- Order by case statemetn to assign priority
	- point data type:

Group By:
- Grouping sets

Not Null:
- is distinct
- is not distinct
- not null constraint
- 
