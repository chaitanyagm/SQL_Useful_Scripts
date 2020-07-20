# SQL_Useful_Scripts
Frequently used / useful SQL Scripts

## Users & Roles
#### To return members of all database roles
```
SELECT isnull (DP2.name, 'No members') AS DatabaseUserName, DP1.name AS DatabaseRoleName
 FROM sys.database_role_members AS DRM  
 RIGHT OUTER JOIN sys.database_principals AS DP1  
   ON DRM.role_principal_id = DP1.principal_id  
 LEFT OUTER JOIN sys.database_principals AS DP2  
   ON DRM.member_principal_id = DP2.principal_id  
WHERE DP1.type = 'R'
ORDER BY DP2.name;
```
