:original_name: en-us_topic_0015667851.html

.. _en-us_topic_0015667851:

Do I Need to Stop the Server Before Backing Up EVS Disks on a Server Using VBS?
===============================================================================

VBS can back up EVS disks that are is use. When a server is running, data is written into the EVS disks on the server, and some newly generated data is cached in the server memory. During a backup task, data in the memory will not be automatically written into disks, so the disk data and their backups may be inconsistent.

To ensure data integrity, you are advised to back up disks during off-peak hours when no data is written into the disks, or stop all data write operations on the disks before the backup. If you have high requirements on backup data integrity, you can stop the server (cached data is written to disks) and then back up the disks.
