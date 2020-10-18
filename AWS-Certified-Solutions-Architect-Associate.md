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

#### S3 security & encryption

#### S3 versioning

Exam Tips

* stored all version of an object(including all writes and even if you delete an object)
* Great backup tool
* Once enabled, can not be disabled, only suspended.
* Integrates with lifecycle rules
* Versioning's MFA delete capability can be used to provide an additional layer of security

#### S3 Lifecycle management and Glaicer

* Automates moving your objects between the different storage tiers.
* Can be used in conjunction with versioning
* Can be applied to current versions and previous versions

#### S3 object Lock & Glacier Vault Lock

S3 object lock - With S3 Object Lock, you can store objects using a write-once-read-many (WORM) model. You can use it to prevent an object from being deleted or overwritten for a fixed amount of time or indefinitely. Object Lock helps you meet regulatory requirements that require WORM storage, or simply add another layer of protection against object changes and deletion.

Object locks can be on individual objects or applied across the bucket as a whole.

S3 Object Lock provides two retention modes:
* Governance mode - In governance mode, users can't overwrite or delete an object version or alter its lock settings unless they have special permissions. With governance mode, you protect objects against being deleted by most users, but you can still grant some users permission to alter the retention settings or delete the object if necessary. 
* Compliance mode - a protected object version can't be overwritten or deleted by any user, including the root user in your AWS account. When an object is locked in compliance mode, its retention mode can't be changed, and its retention period can't be shortened.Compliance mode ensures that an object version can't be overwritten or deleted for the duration of the retention period.

A retention period protects an object version for a fixed amount of time. When you place a retention period on an object version, Amazon S3 stores a timestamp in the object version's metadata to indicate when the retention period expires. After the retention period expires, the object version can be overwritten or deleted unless you also placed a legal hold on the object version.

Legal holds - Object Lock also enables you to place a legal hold on an object version. Like a retention period, a legal hold prevents an object version from being overwritten or deleted. However, a legal hold doesn't have an associated retention period and remains in effect until removed. Legal holds can be freely placed and removed by any user who has the s3:PutObjectLegalHold permission. 

Vault Locking - S3 Glacier Vault Lock allows you to easily deploy and enforce compliance controls for individual S3 Glacier vaults with a vault lock policy. You can specify controls such as “write once read many” (WORM) in a vault lock policy and lock the policy from future edits. Once locked, the policy can no longer be changed.