# Google Spanner

# Get All Tables Available

SELECT 
    t.table_name
FROM
    information_schema.tables AS t
WHERE
    t.table_catalog='' and
    t.table_schema=''
