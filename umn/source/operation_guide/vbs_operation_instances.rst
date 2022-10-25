:original_name: en-us_topic_0033871603.html

.. _en-us_topic_0033871603:

VBS Operation Instances
=======================

This section explains how to use VBS to ensure data security in different scenarios, its limitations, and its typical operations.

Scenarios
---------

VBS applies to the following scenarios:

-  Hardware faults

   Production storage devices on the cloud platform have faults.

-  Software faults

   System faults cause data losses (for example, the system malfunctions and the system incorrectly delivers resource deletion commands) and application system faults on a user's guest OSs.

-  User misoperations

   User misoperations cause data loss and system bootup failures.

Requirements and Limitations
----------------------------

-  EVS disks cannot be restored in a batch.
-  If you use data backups to create an EVS disk, the new EVS disk cannot be used as a system disk.

EVS Disk Data Backup
--------------------

VBS works only on EVS disks. For details, see :ref:`Creating a VBS Backup <en-us_topic_0015667820>`.

EVS Disk Data Restoration
-------------------------

You can use a VBS backup to restore an EVS disk to the time when the backup was created.

Before restoring the disk data, stop the server to which the EVS disk is attached and detach the EVS disk from the server. After the restoration is complete, re-attach the EVS disk and start the server. For details, see :ref:`Data Restoration Using a VBS Backup <en-us_topic_0015667886>`.

Creating an EVS Disk Using a VBS Backup
---------------------------------------

After an EVS disk is created using a data backup, the initial data of the new EVS disk is the same as the initial backup data. For details, see :ref:`Creating an EVS Disk Using a VBS Backup <en-us_topic_0015667886__section44845024152024>`.
