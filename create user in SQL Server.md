’’’sql

-- Step 1: Create a SQL Server login (if it doesn't already exist)
USE [master];
GO

IF NOT EXISTS (SELECT * FROM sys.server_principals WHERE name = 'your_login')
BEGIN
    CREATE LOGIN your_login 
    WITH PASSWORD = 'your_password'; -- Set your strong password
END
GO

-- Step 2: Switch to the target database
USE your_database; -- Replace with the database where views exist
GO

-- Step 3: Create a user for that login in the database
IF NOT EXISTS (SELECT * FROM sys.database_principals WHERE name = 'your_user')
BEGIN
    CREATE USER your_user FOR LOGIN your_login;
END
GO

-- Step 4: Grant SELECT permission on the specific views
GRANT SELECT ON view1 TO your_user;
GRANT SELECT ON view2 TO your_user;
GO
’’’