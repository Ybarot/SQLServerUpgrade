This script can help you create Custom SSM document. 

Here are the input parameters for the custom document. 

InstanceId: Target EC2 instance on which SQL Server edition upgrade is required. We can select this using an interactive instance picker from all the instances managed by Systems Manager.
Sqlversion: New version to which SQL Server needs to be upgraded. Permitted values are sql2016, sql2017, sql2019 and sql2022
Backuprequired: Specify whether backup to be taken as part of this automation. Permitted values are Backuprequired and Nobackup
BackupLocation: If you opt in for backup to be taken as part of this automation, specify the location to store backups of databases e.g. D:\MSSQL\Backup.
S3BucketName: It’s the S3 bucket name where we kept new SQL Server version media
AdminUserSecret: AWS Secrets Manager Secret name that stores Windows AD user and password that has administrator permissions on the EC2 instance and system administrator role for SQL Server. It should be stored as key value pair of username and password
As shown in Figure 4, Windows AD User password and SA password are stored in the AWS Secrets Manager. Read AWS Secrets Manager to create secrets for detailed instructions.
Figure 4 Windows user credentials in secret manager
In the S3 bucket, new SQL Server binaries need to be stored in the mounted state to a folder in the format “sqlxxxx” where xxxx can be 2016, 2017,2019 or 2022.

