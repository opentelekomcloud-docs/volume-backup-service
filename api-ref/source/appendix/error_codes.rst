:original_name: en-us_topic_0022472083.html

.. _en-us_topic_0022472083:

Error Codes
===========

+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
| Module                          | Error Code        | Description                                                                          |
+=================================+===================+======================================================================================+
| Shared                          | common.0011       | Failed to query the task.                                                            |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0014 | Failed to submit the task.                                                           |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0041 | Failed to check user rights.                                                         |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0042 | The user does not have the rights to perform operations.                             |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0044 | User rights are invalid.                                                             |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
| Creating a Backup               | VolumeBackup.0002 | The request format is incorrect.                                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0003 | Parameter **name** in the request is too long.                                       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0004 | Parameter **name** in the request contains invalid characters.                       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0005 | Parameter **name** in the request starts with **auto**.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0006 | Parameter **description** in the request is too long or contains invalid characters. |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0007 | Parameter **name** in the request is empty.                                          |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0008 | Failed to obtain the permission.                                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0009 | Failed to obtain the key.                                                            |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0010 | Parameter **volume_id** in the request is empty.                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0011 | The format of parameter **volume_id** in the request is incorrect.                   |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0012 | The disk status is not **available** or **in_use**.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0013 | The previous backup creation task is not complete.                                   |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0017 | Failed to create the snapshot.                                                       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0018 | The snapshot creation result is empty.                                               |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0019 | Failed to query the snapshot during backup creation.                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0020 | The snapshot query result is empty.                                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0021 | The EVS disk does not exist or has been deleted.                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0022 | Failed to create the temporary disk.                                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0023 | The result of creating the temporary disk is empty.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0024 | Failed to query the temporary disk.                                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0025 | The result of querying the temporary disk is empty.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0026 | Parameter **name** in the request is too short.                                      |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0027 | Failed to create the backup.                                                         |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0028 | The backup creation result is empty.                                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0029 | Failed to query the backup result.                                                   |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0030 | The backup query result is empty.                                                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0035 | Failed to query all disks of a user.                                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0036 | Failed to query all backups of a user.                                               |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0037 | Failed to query the snapshot status.                                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0038 | Failed to query the status of the temporary disk.                                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0039 | Failed to query the backup status.                                                   |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0040 | The number of backups for the disk has reached the upper limit (20).                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0043 | Failed to query the disk or backup.                                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0049 | The tag parameter is invalid.                                                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0050 | The number of tags has reached the upper limit.                                      |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0053 | DESS disks do not support backup.                                                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0062 | The snapshot status is **error**.                                                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0063 | The status of the temporary disk is **error**.                                       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0064 | The backup status is **error**.                                                      |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0070 | Failed to query the quota information.                                               |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0071 | The quota for the number of SAS disks has been used up.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0072 | The quota for the capacity of SAS disks has been used up.                            |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0073 | The quota for the number of SATA disks has been used up.                             |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0074 | The quota for the capacity of SATA disks has been used up.                           |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0075 | The quota for the number of SSD disks has been used up.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0076 | The quota for the capacity of SSD disks has been used up.                            |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0077 | The quota for the number of SAS disk snapshots has been used up.                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0078 | The quota for the number of SATA disk snapshots has been used up.                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0079 | The quota for the number of SSD disk snapshots has been used up.                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0080 | The quota for the number of backups has been used up.                                |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0081 | The quota for the capacity of backups has been used up.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0082 | The quota for the number of disks has been used up.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0083 | The quota for the capacity of disks has been used up.                                |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0084 | The quota for the number of snapshots has been used up.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
| Deleting a Backup               | VolumeBackup.0100 | Failed to submit the subtask.                                                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0101 | Failed to delete the snapshot.                                                       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0102 | Failed to delete the backup.                                                         |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0103 | Failed to query the backup details.                                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0104 | Failed to obtain the image information.                                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0105 | The format of the backup deletion request is incorrect.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0109 | Failed to query the snapshot during backup deletion.                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0110 | Failed to query the backup.                                                          |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0113 | The backup has already been used to create an image and cannot be deleted.           |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0123 | Failed to query all backups.                                                         |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0125 | Failed to perform the backup deletion operation.                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0900 | The service is unavailable.                                                          |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
| Restoring a Disk Using a Backup | VolumeBackup.0111 | The disk to be restored or the backup used to restore the disk does not exist.       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0200 | Failed to restore data.                                                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0201 | The data restoration result is empty.                                                |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0202 | The disk status is **error**.                                                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0203 | Parameter **backup_id** in the request is empty.                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0204 | The format of parameter **backup_id** in the request is incorrect.                   |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0205 | The disk status is **unavailable**.                                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0206 | A backup is being created for the disk.                                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0207 | The disk to be queried does not exist.                                               |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0208 | Parameter **volume_id** in the request is incorrect.                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0209 | The capacity of the disk must be greater than or equal to that of the backup.        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0210 | The format of the disk restoration request is incorrect.                             |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0211 | Cloud disks at the disaster recovery site cannot be restored.                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | VolumeBackup.0089 | The disk backup status is **unavailable**.                                           |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
| Backup Policy                   | AutoBackup.0000   | The request is empty.                                                                |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0001   | The object contained in the request is empty.                                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0002   | The token contained in the request header is empty.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0003   | The token contained in the request header has expired.                               |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0005   | Failed to obtain the domain ID from the token contained in the request header.       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0006   | The policy ID contained in the request is empty.                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0008   | Failed to convert the request into a JSON object.                                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0009   | An exception occurred in internal system processing.                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0100   | The tenant cannot modify the default backup policy.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0101   | The length of the backup policy name is invalid.                                     |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0102   | The parameter of the backup policy name is invalid.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0103   | The parameter of the backup job start time is invalid.                               |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0104   | The parameter of the backup policy status is invalid.                                |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0105   | The parameter of whether to retain the first backup in the current month is invalid. |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0106   | The parameter of the backup job interval is invalid.                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0107   | The parameter of the number of retained backups is invalid.                          |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0203   | The number of existing backup policies has reached the upper limit.                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0204   | The number of associated volumes has reached the upper limit.                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0205   | The policy does not exist.                                                           |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.1100   | The queried policy does not exist.                                                   |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.1300   | Failed to delete the policy.                                                         |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.1400   | The resource to be associated is invalid.                                            |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.1700   | Failed to execute the backup policy.                                                 |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0206   | The status of the disk to be associated is invalid.                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0207   | The resource to be associated is empty.                                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0208   | An exception occurred when you were obtaining details about the associated resource. |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0209   | The resource ID or name is empty.                                                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0210   | HANA disks cannot be associated with the backup policy.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0211   | The resource type is invalid.                                                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0213   | The request is not authorized.                                                       |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0214   | The tag parameter is invalid.                                                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0215   | The number of tags has reached the upper limit.                                      |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0216   | The tag does not exist.                                                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0217   | The snapshot quota is insufficient.                                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0218   | The backup quota is insufficient.                                                    |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0220   | DESS disks cannot be associated with the backup policy.                              |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0221   | The request cannot contain less-than signs (<) or greater-than signs (>).            |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0222   | Only specified actions are supported.                                                |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0225   | The policy is being executed.                                                        |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.0226   | The time zone parameter is invalid.                                                  |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
|                                 | AutoBackup.9002   | An internal exception occurred in system authentication.                             |
+---------------------------------+-------------------+--------------------------------------------------------------------------------------+
