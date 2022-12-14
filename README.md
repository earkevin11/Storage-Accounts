# Storage-Accounts

# What is the purpose of Azure Storage Accounts?
- This service provide storage on the cloud
- Storage account can be used to store many types of data
- There are multiple types of storage accounts: Blob, Table, Queue, and File

# Creating a Storage Account
- When creating a Standard Storage account, you will access to various services.
- Services such as Containers, File Shares, Queues, and Tables


# Azure Blob Service
- Blob service is optimized for storing large amounts of UNSTRUCTURED DATA like images, files, videos, and etc.
- When you start using Azure Storage Account, you create a CONTAINER, which is like a folder that holds your objects (images, files, and videos)


# Different types of blobs
- Block blobs - this is made up of blocks of data that can be managed individually
- Append blobs - these are block blobs that are optimized for append opeartions - good for logging
- Page blobs - used for virtual hard drive files for Azure virtual machines

# Blob service - uploading a blob
- Remember to create a container and then upload the object
- Create folders by navigating to "Advanced" and go to Upload to Folder

# Blob service - Accessing the blob
- Every object gets a unique URL
- Users have to be authorized to access the objects in th storage account
- Navigate to the container > change access level > anonymous access makes the container PUBLIC so anyone can access it (it's not the most secure way)


# Azure Storage Accounts - File Service
- Files are stored as normal files in a file share where multuple users can access them.
- Difference between Blob storage and file storage is that Blobs are stored as objects and blobs have a unique URL where you access them individually
- With file share, users can map a drive onto a file share.

# Azure Storage Accounts - Creating a File share
- File shares > Create a new File share > Upload your files > Add directory (folders)

# Azure Storage Accounts - Mapping a drive
- Connect > Copy the script and paste into powershell in your local system and run it
- That code will map the drive on your local system onto the file share
- You will see the drive that is connecte to the File share and have access to the files that you uploaded 
- Multiple users can map onto the file share using the same script
- If users cannot map to the fileshare, it may be a firewall issue

# Azure Storage Accounts - Mapping a drive alternative way
- Go to my computer > map a network drive > grab the name of the folder on the fileshare > select "connect using credentials" > and use the username and password that is located in the powershell script

# Immutable Blob Storage Lab #261
- Immutable blobs means no one can change the contents of the objects
- Access policy > Under Immutable blob storage > Add a policy 
- Legal Hold - if for legal reasons no one can manipulate the contents
- Time-based retention - no one should be able to modify the blob for a day

# Azure Storage Accounts - Different Authorization techniques
- We can use Access Keys, Shared Access Signatures, and Azure AD.

# Azure Storage Explorer
- You can work with Azure Storage accounts using Storage Explorer instead of the Azure Portal
- You would need to download Azure Storage Explorer and install
- It's just another interface to work with the Storage Accounts


# Authorization via Access Keys
- Say you want to give users access to work with the Storage Accounts, we can provision Access Keys
- Go to the Storage Account < Access Keys 
- We have two keys. If Key 1 gets compromised, we can use Key 2. We can also rotate Key 1 if it is compromised.
- Take the key < Go to "Add an Account" on the Explorer > Select Storage Account > add the selected key > Connect
- Try and access the storage accounts and their containers



# Authorization via Shared Access Signatures  - At the Blob Level
- Navigate to Storage Account and your container
- Change Access Level > Select Private no anonymous access
- Select any object > Generate a SAS (It will use 1 of the access key to generate a SAS)
- Say we want to give access to a specific Blob for only 1 week, we can set a TIME LIMIMT for the SAS
- We can also designate specific IP addresses to certain blobs
- Access is only valid via the SAS.




# Authorization via Shared Access Signatures  - At the Storage Account Level
- We can specify and limit what access/permissions a user has using a SAS.
- There is a time/end time for SAS access 
- We can also specify which IP addresses are allowed
- Connect via SAS


# Azure Storage Accounts - Stored Access Policy
- If a Shared Access Signature gets in the wrong hands, we can use Stored Access Policy where we can disable permissions. 
- The SAS would be invalid and not have any permissions that were previously given. 

# Azure Storage Accounts - Active Directory Authentication
- We can assign access to users within Azure AD by going to Azure Storage Account > Access Control (IAM) > Add Role Assignment > Select "Storage Account Contributor"
- Select the user
- Now the user will be able to access the storage account and their services


# Azure Storage Accounts - Authorization techniques review
- 3 ways to give access are 1. Access Keys, 2. SAS, 3. Azure Active Directory
- Access Keys should be the last resort in giving access.
- Most secure way is defining users in Azure AD, then use SAS, and then using Shared Access Keys
