# lego_creator_challenge
A SQL Portfolio challenge to create a schema
See https://github.com/wjsutton/lego_analysis_challenge/tree/main for full challenge

Part 1: Schema Setup 📥

We're going to build and populate a series of tables that make up a LEGO database. You will need to create tables, insert data, set primary and foreign keys, and then create an ER (Entity-Relationship) diagram.

Key Steps
1. Create Your Schema:
We'll be working in a database called lego and a schema called staging contains all our initial data. You should create a new schema within the lego database. This will be the container for all your tables.

Hint: Use the CREATE SCHEMA command to create a schema.

CREATE SCHEMA schema_name;
2. Create Tables:
Based on the existing data, create the following tables in your schema:

COLORS
INVENTORIES
INVENTORY_PARTS
INVENTORY_SETS
PARTS
PART_CATEGORIES
SETS
THEMES
Ensure you define the correct data types for each column in these tables.

Hint: Use the CREATE TABLE command. Look at the data in the staging schema for guidance on the data types and column names you'll need.

CREATE TABLE schema.table (
	column_1 integer,
	column_2 VARCHAR(44)
);

-- Check column character length, for varchar() length
SELECT MAX(LENGTH(part_num))
FROM staging.lego_parts;
3. Insert Data:
Once the tables have been created, you'll need to populate them with data from the corresponding tables in the STAGING schema.

Hint: Use the INSERT INTO command combined with a SELECT * FROM query to pull in the data from the STAGING tables.

INSERT INTO schema.destination_table (
SELECT *
FROM  schema.source_table
);
4. Set Primary and Foreign Keys:
After populating your tables, you'll need to define primary and foreign keys for each of them.

Use the diagram below for guidance, not all tables will have a primary key.



--Set a primary key:
ALTER TABLE table_name ADD PRIMARY KEY (column_name);

--Set a foreign key:
ALTER TABLE table_name ADD FOREIGN KEY (column_name) REFERENCES another_table(another_tables_primary_key_column);
5. Create ER Diagram:
Once your tables are built, populated, and linked right click on your schema to create an ER diagram to visualize the relationships between your tables.

Alternatively you can create a ER diagram using DBeaver and the following steps

Download DBeaver
Create connection > SQL > PostgresSQL
Host: localhost
Database: lego
Schema: the schema you created earlier
Enter username and password
Navigate to your schema: right click > View Schema

Deliverable
At the end of this section, you should have:

a schema in the LEGO database filled with tables populated with LEGO data.
a SQL script creating your schema, tables, inserting data and creating primary and foreign keys
an ER diagram showing the relationships between your tables
