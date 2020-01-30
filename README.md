# migrate-files-to-azure-using-azcopy
copy local files to Blob storage Account using AzCopy Powershell Script to copy local files to Blob storage Account using AzCopy
Introduction
AzCopy is a command-line utility that you can use to copy blobs or files to or from a storage account. 

This article helps you to understand the workings and how to parameterized AzCopy.exe to Export and Import Azure files.  You can find Powershell Script to copy local files to Blob storage Account using AzCopy at my git that uses azCopy to move files from an on-premise directory to azure storage.

https://github.com/mkjmkumar/migrate-files-to-azure-using-azcopy

How to Download AzCopy
To download Azure azcopy windows executable visit Microsoft website https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10

Authenticate your User ID
Open Powershell terminal and locate to the azcopy directory from Above. Now Authenticate yourself using below command and follow instructions

#.\azcopy.exe login --tenant-id xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx

Permission Error and configure script
In case you are getting permission error that means user id do not have permission to Azure Storage account or SAS key expired, to get fresh SAS key. In Case your SAS key expired go to storage account "mystorageaccount" and left hand pane search for "Shared access signature" and replace this key with $SAS variable in powershell script.




Add alt text
No alt text provided for this image


How to execute Powershell script
Once you have made the changes to ps file locate azcopy executable use below command to execute your powershell file:-

. "C:\copytoazure.ps1"

Demo 
PS C:\AzCopy> .\copytoazure.ps1
Please authenticate using .\azcopy login to avoid permission error...
Current Directory..
C:\FMAG\TempAZ\Sombody.txt
1-datasource1
2-datasource2
3-datasource3
4-datasource4
Choose Datasource from Above...: 2
Your Choice is Envestnet
-------------------------------
1-xxxxx/mf_1/
2-xxxxx/mf_2/
3-xxxxx/sma_1/
4-xxxxx/sma_2/
5-xxxxx/manage_1/
-------------------------------
Please Choose entity name...: 3
Your Choice is 3-xxxxx/sma_1/ Folder!
Target Location =
https://wwwwwwwwwwwwww.blob.core.windows.net/wwwwwwww-zone/wwwwwww/www_wwww/?wwwwwwwwwwwwwwwwwwww
Output
Job e726bb1f-fdb0-bc4f-7f02-ea2670aa93f4 has started Log file is located at: C:\xxxxx.azcopy\e726bb1f-fdb0-bc4f-7f02-ea2670aa93f4.log


0.0 %, 0 Done, 0 Failed, 1 Pending, 0 Skipped, 1 Total, 
0.0 %, 0 Done, 0 Failed, 1 Pending, 0 Skipped, 1 Total, 
0.0 %, 0 Done, 0 Failed, 1 Pending, 0 Skipped, 1 Total, 
0.0 %, 0 Done, 0 Failed, 1 Pending, 0 Skipped, 1 Total,


Job e726bb1f-fdb0-bc4f-7f02-ea2670aa93f4 summary Elapsed Time (Minutes): 2.1104 
Total Number Of Transfers: 1 
Number of Transfers Completed: 1 
Number of Transfers Failed: 0 
Number of Transfers Skipped: 0 
TotalBytesTransferred: 19 
Final Job Status: Completed
