#### **Host a static website on s3 bucket:-**

* create a bucket
* open the bucket
* upload all the files required for static website
* click close
* go to Properties
* inside properties go to static website hosting 
* click on edit ->enable it 
* inside index document write your html file name with (.html)
* save changes
* go inside permission->block public access->edit
* deselect->block all public access->save changes
* go to permission->object ownership->edit->ACLs enabled
* click on (i acknowledge that acls will be restored) ->save changes.
* go to object select all object->Action button->make public using acl->make public  
* go to object and click html copy the link and paste it in google;
* DONE 
