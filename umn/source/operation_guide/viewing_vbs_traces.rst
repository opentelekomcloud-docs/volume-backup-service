:original_name: en-us_topic_0115393304.html

.. _en-us_topic_0115393304:

Viewing VBS Traces
==================

Scenarios
---------

CTS records operations of VBS resources, facilitating query, audit, and backtracking.

Prerequisites
-------------

You have enabled CTS and the tracker is running properly. For details about how to enable CTS, see section "Enabling CTS" in the *Cloud Trace Service User Guide*.

Key Operations Recorded by CTS
------------------------------

.. table:: **Table 1** VBS operations that can be recorded by CTS

   +--------------------------------------------------------------+---------------+----------------------+
   | Operation                                                    | Resource Type | Trace                |
   +==============================================================+===============+======================+
   | Creating a backup                                            | vbs           | bksCreateBackup      |
   +--------------------------------------------------------------+---------------+----------------------+
   | Deleting a backup                                            | vbs           | bksDeleteBackup      |
   +--------------------------------------------------------------+---------------+----------------------+
   | Restoring a backup                                           | vbs           | bksRestoreBackup     |
   +--------------------------------------------------------------+---------------+----------------------+
   | Associating a backup policy                                  | autobackup    | addPolicyResource    |
   +--------------------------------------------------------------+---------------+----------------------+
   | Disassociating a backup policy                               | autobackup    | deletePolicyResource |
   +--------------------------------------------------------------+---------------+----------------------+
   | Executing a backup policy                                    | autobackup    | actionPolicy         |
   +--------------------------------------------------------------+---------------+----------------------+
   | Creating a backup policy                                     | autobackup    | createPolicy         |
   +--------------------------------------------------------------+---------------+----------------------+
   | Deleting a backup policy                                     | autobackup    | deletePolicy         |
   +--------------------------------------------------------------+---------------+----------------------+
   | Modifying a backup policy                                    | autobackup    | modifyPolicy         |
   +--------------------------------------------------------------+---------------+----------------------+
   | Creating a backup scheduled by a backup policy               | autobackup    | scheduleCreateBackup |
   +--------------------------------------------------------------+---------------+----------------------+
   | Automatically deleting a backup scheduled by a backup policy | autobackup    | scheduleDeleteBackup |
   +--------------------------------------------------------------+---------------+----------------------+
   | Batch adding or modifying tags of a backup policy            | autobackup    | batchAddPolicyTag    |
   +--------------------------------------------------------------+---------------+----------------------+
   | Batch deleting tags of a backup policy                       | autobackup    | batchDeletePolicyTag |
   +--------------------------------------------------------------+---------------+----------------------+
   | Adding or modifying a backup policy tag                      | autobackup    | addPolicyTag         |
   +--------------------------------------------------------------+---------------+----------------------+
   | Deleting a backup policy tag                                 | autobackup    | deletePolicyTag      |
   +--------------------------------------------------------------+---------------+----------------------+

Viewing CTS Traces
------------------

#. Log in to the management console.

#. In the upper left corner of the page, click |image1| and select the desired region and project.

#. Click **Service List**. Under **Management & Deployment**, click **Cloud Trace Service**.

#. In the navigation pane on the left, choose **Trace List**.

#. On the trace list page, click **Filter**. In the displayed box, specify **Trace Source**, **Resource Type**, and **Search By**, and click **Query** to query the specified traces.

   For details about other operations, see section "Querying Real-Time Traces" in the *Cloud Trace Service User Guide*.

Disabling or Enabling a Tracker
-------------------------------

This section describes how to disable an existing tracker on the CTS console. After the tracker is disabled, the system will stop recording operations, but you can still view existing operation records.

#. Log in to the management console.
#. In the upper left corner of the page, click |image2| and select the desired region and project.
#. Click **Service List**. Under **Management & Deployment**, click **Cloud Trace Service**.
#. Click **Tracker** in the left pane.
#. Click **Disable** on the right of the tracker information.
#. Click **OK**.
#. After the tracker is disabled, its status changes from **Disable** to **Enable**. To enable the tracker again, click **Enable** and then click **OK**. The system will start recording operations again.

.. |image1| image:: /_static/images/en-us_image_0148411635.png
.. |image2| image:: /_static/images/en-us_image_0148411635.png
