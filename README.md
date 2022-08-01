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


# Using Access Keys
- Say you want to give users access to work with the Storage Accounts, we can provision Access Keys
- Go to the Storage Account < Access Keys 
- We have two keys. If Key 1 gets compromised, we can use Key 2. We can also rotate Key 1 if it is compromised.
- Take the key < Go to "Add an Account" on the Explorer > Select Storage Account > add the selected key > Connect
- Try and access the storage accounts and their containers



# Shared Access Signatures  - At the Blob Level
