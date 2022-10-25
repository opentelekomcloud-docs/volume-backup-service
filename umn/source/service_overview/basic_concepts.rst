:original_name: en-us_topic_0071076576.html

.. _en-us_topic_0071076576:

Basic Concepts
==============

Backup Policies
---------------

A backup policy, including the backup period and retention rules, can automate data backup of EVS disks. Backup policies are user specific.

.. _en-us_topic_0071076576__section1713119814918:

Instant Restore
---------------

Instant Restore is a feature that provides the instant restoration function for restoring disk data and creating disks using backups, which is much faster than the normal restoration function.

Backups generated before the Instant Restore feature is enabled do not support instant restoration. To use the feature, perform a full backup operation and select **Enable** next to **Full Backup** when creating the backup. For details, see :ref:`Creating a VBS Backup <en-us_topic_0015667820>`. After Instant Restore is enabled, manual backups for EVS disks that have not been backed up automatically support instant restoration, without requiring the selection of **Enable** next to **Full Backup**.

No matter whether an EVS disk has been backup or not, its automatic backups generated after Instant Restore is enabled do not support instant restoration, unless you manually perform a full backup on it.

When you use Instant Restore for the first time through APIs and the to-be-restored disk has been backed up before the feature is enabled, you need to perform a full backup on the disk on the console or directly call the API for creating a full backup (**POST /v2/{tenant_id}/cloudbackups**). After doing this, the disk backups generated through APIs will support instant restoration.

Enhanced Backup
---------------

After Instant Restore is enabled, each backup will be marked with a letter **C** or **E** at the right of its name to show whether it supports instant restoration. A backup marked with letter **C** is a common backup and does not support instant restoration. A backup marked with letter **E** is an enhanced backup and supports instant restoration.

Project
-------

Projects are used to group and isolate OpenStack resources (computing, storage, and network resources). A project can be a department or a project team. Multiple projects can be created for one account.
