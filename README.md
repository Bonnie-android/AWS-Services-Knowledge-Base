# AWS-Services-Knowledge-Base
AWS Services Training, On-Job Experience Knowledge Base


EBS Elastic Block Storage

Amazon Elastic Block Store(EBS) offers persistent storage for EC2 instances.
EBS network attached and persist independently from the life of an EC2 instance.
Highly available, highly reliable volumes. 
May be used as EC2 instance boot partition
May be attached to a running EC2 instance as a standard block device.
If used as a boot partition EC2 instances can be stopped and restarted.
Pay only for storage resources used while maintaining the EC2 instance state.
EBS instances are replicated o the backend in the same AZ.
This is better than using an EC2 instance store which is not backed up.
EBS allows creation of Point-In-Time snapshots that are then stored on S3.
EBS snapshots are stored on S3. Replicated across multiple AZ.
Can be used as starting point for new EBS volumnes and protect data for long term durability.
They can be shared.

EBS lifetime is independent of an EC2 instance.
Raw unformatted block device that can be used for OS, Servers
Better than EC2 drives.
Built-In Redundancy within an AZ.
Annual Failure Rate(AFR) is between 0.1% and 1%.
Size 1GB to 16TB

LIFECYCLE
Easily created, attached, backed up, restored and deleted.
Create 1GB to 16TB
Attach to an instance - viewed as a logical drive
The EC2 OS can now format and set up a file system on the EBS volume.
Snapshots can be created while EBS is running, while volume-in-use.
Snapshots stored on S3.
Detach - When the OS no longer uses the volumne it can be detatched. Data is persistent.
Delete

When EBS is used as a boot sector it needs an OS installed on it.
This is called an Amazon Machine Image (AMI).
EC2 instances are created by referencing the EBS snapshot containing the initial OS image.
When you create such an instance a new root file system is created from a volume snapshot containing the OS image.
When an EC2 instance is terminated, the default behavior is to delete the EBS since it can be recreated by an AMI.
To RETAIN the EBS volume's contents after terminating an EC2 instance specify the DeleteOnTermination = False.
DeleteOnTermination = False this must be specified.
In this case the EBS is only detatched from the instance.

