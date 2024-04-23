# Google Spanner

# Get All Tables Available

SELECT 
    t.table_name
FROM
    information_schema.tables AS t
WHERE
    t.table_catalog='' and
    t.table_schema=''

# Rename a database in spanner
- Cannot be rename.

# How to copy a database from one database.



