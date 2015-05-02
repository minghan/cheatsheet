T-SQL
=====

Fetch list of stored procedures

    USE [<TableName>]
    GO

    SELECT 
        name,
        create_date,
        modify_date
    FROM sys.procedures
    WITH (nolock)
    ;
