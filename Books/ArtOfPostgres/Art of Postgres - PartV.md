
Part V: Data Types

Serialization and Deserialization:

????
- marshalling ans unmarshalling
- serialisation is subprocess of marchalling


Some relational theory
Consistency: ACID

Attribute Values, Data Domains and Data Types

- Decorated literal: select date '2010-02-28'
- ?? allballs?? :
	- select date 'today' + time 'allballs' as midnight;		- allballs army slang


Consistenct and Data Type Behavior

- opeartor polymorphism.
- pg_operator -> list of functions tobe called with operator and the expected left and right operator.


PostgresSql Data Types:

- bernoulli is probabilistic distribution

- boolean: 3 valued logic
	- bool_and() 
	- count(*) as ran,
	- count(*) filter(where position = 1) as won,
	- count(*) filter(where position is not null) as finished,
- character and text
	- overlay(), substring(),position(),trim()
	- string_agg()
	- regexp_split_to_table()
	- tigram extension: indexing for regular expressions
	- ETL vs ELT >> SIDE NOTE: We are using both the methods.
	- ?? group by rollup(category, subcategory):
		- grouping sets: roll up, cube
		- roll up creates permutation for each 
		- Page 120.  
	- full text search support
- Server Encoding and Client Encoding
	- do not use SQL_ASCII
	- ?? what is the difference between SQL_ASCII and UTF-8
- Numbers
	- integer, bigint, smallint, numeric, real, double precision
- Floating Point Numbers:
	- numeric, integer, money
- Sequences and Serial Pseudo Data Type:
	- use bigserial 
- UUID: Universally Unique Identifier:
	- 128 bit number
	- globally unique identifier
		- ?? what does this mean? is it unique throughout the db?
		- yup unique universally with mac addr + timestamp+bunch of stuff
	- ?? extension: uuid-ossp?
	- yup we use extension
- Bytea and Bitstring:
- Date/Time and Time Zones: #TODO Read Again
	- with or without time zones
	- now() gices transaction time and not each time
- Time Intervals:
	- intervals '1 month'
	- 2 * intervals '1 week' >>> 14 days
	- intervalstyle:
		- set intervalstyle to postgres_verbose
- Date/Time Processing and Querying:
- Network Address Types:
	- cidr, inet, macaddr
- Ranges:
	- daterange data type
	- #TODO need to understand: daterange(date,lead(date) over(partition by currency order by date),'[)')
	- #TODO read Again[skipped over it]

DEnormalized Data Types:

- Arrays: 
	- integrate with sql
	- @> thing #TODO 
- Composite Types:
- XML: 
	- xml stored
- JSON 
- Enum: recommends not to use it.
- 
  
  
  
  
  
  
  
