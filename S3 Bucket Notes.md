#### **Host a static website on s3 bucket:-**

* Create a S3 Bucket
* Ppen the Bucket
* Upload all the files required for static website
* Click "Close"
* go to Properties
* inside properties go to Static Website Hosting 
* Click on Edit ->Enable it 
* Inside Index Document write your html file name with (.html)
* Save Changes
* Go Inside Permission -> Block Public Access -> Edit
* Deselect -> Block all Public Access -> Save Changes
* go to permission->object ownership->edit->ACLs enabled
* Click on (i acknowledge that acls will be restored) -> Save Changes.
* Go to object select all object -> Action button -> make public using acl -> make public  
* Go to object and Click html copy the link and paste it in google;
* DONE 



Questions related S3 Bucket:-

1. What is Amazon S3?
-> Amazon S3 (Simple Storage Service) is an object storage service that allows you to store and retrieve any amount of data at any time.

2. What type of storage does S3 provide?
-> S3 provides Object Storage, not block or file storage.

3. Are bucket names global or regional?
->Bucket names must be globally unique across all AWS accounts.

4. What is S3 Versioning?
-> Versioning allows you to keep multiple versions of an object in the same bucket to protect against accidental deletes or overwrites.

5. What is S3 Static Website Hosting?
->S3 can host static websites (HTML, CSS, JS files) by enabling Static Website Hosting in bucket properties.

6. What is S3 Storage Class?
-> Storage classes define the cost and availability of stored data.

7. What are S3 Access Policies?
->1. Policies that control access:
, 2. Bucket Policy
, 3. IAM Policy
, 4. ACL (Access Control List)

8. Can we make an S3 bucket public?
-> Yes — by modifying the bucket policy and disabling Block Public Access.

9. What is S3 Glacier?
-> A low-cost storage class for archival data that is accessed rarely.

10. How do you secure an S3 bucket?
-> 1. Enable encryption
, 2. Disable public access
, 3. Use IAM roles
, 4. Enable bucket policy restrictions
, 5. Use VPC endpoints