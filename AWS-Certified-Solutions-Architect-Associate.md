### IAM

Exam Tips

* IAM is universal. It doesn't apply to regions at this time
* The "rot account" is simply the account created when first setup your AWS account. It has complete Admin access.
* New users have no permission when first created.
* New users are assigned access key id & secret access key when first created
* These are not the same as a password. yoou cann't use the access key ID & secret access ke to lgon in to the console. You can use this to access AWS via the APIS and command line.
* You only get to view these once. If you lose them, you have to regenerate them. So, save them in a secure location.
* Always setup Multicactor Authentication on your root account.
* You can create and customise your own password rotation policies.

### S3

#### Data consistency for S3
* Read after write consistency for PUTS of new objects
* Eventual Consistency for overwrite PUTS and DELETES (can take some time propagate)

#### Exam tips
* S3 is object-based
* Files can be from 0 bytes to 5 TB
* There is unlimited storage
* Files are stored in buckets
* S3 is a universal namespace.
* Not suitable to install an OS on
* Successful uploads will generate a HTTP 200 status code
* You can turn on MFA Delete
* Key Fundamentals
  * Key (name)
  * Value (data)
  * Version ID
  * Metadata
  * Subresources
    * Access control lists
    * Torrent
* Read after write consistency for PUTS of new objects
* Eventual Consistency for overwrite PUTS and DELETES (can take some time propagate)
* Storage class
  * S3 standard
  * S3 - IA
  * S3 one zone - IA
  * S3 - Intelligent Tiering
  * S3 Glacier
  * S3 Glacier Deep Archive
