:original_name: en-us_topic_0015667820.html

.. _en-us_topic_0015667820:

Creating a VBS Backup
=====================

You can create backups for your EVS disks to protect the disk data through the VBS console or the EVS console.

Precautions
-----------

-  An EVS disk can be backed up only when its status is **Available** or **In-use**. If you have performed operations such as expanding, attaching, detaching, or deleting an EVS disk, refresh the page first to ensure that the operation is complete and then determine whether to back up the disk.
-  You are advised not to back up an EVS disk larger than 4 TB.

Create a VBS Backup (Method 1)
------------------------------

#. Log in to the management console.

#. Click |image1|. Under **Storage**, click **Volume Backup Service**.

#. Click |image2| in the upper left corner of the management console and select a region and a project.

#. On the VBS page, click **Create Backup**.

#. From the EVS disk list on the left, click |image3| to select the EVS disks you want to back up. Then they appear in the **Selected Disks** list on the right. See :ref:`Figure 1 <en-us_topic_0015667820__fig64893544452>`. You can click |image4| in the **Operation** column to delete EVS disks that do not need to be backed up.

   .. _en-us_topic_0015667820__fig64893544452:

   .. figure:: /_static/images/en-us_image_0152878917.png
      :alt: **Figure 1** Selecting a disk

      **Figure 1** Selecting a disk

   .. note::

      The system will identify whether the selected EVS disk is encrypted. If it is encrypted, its backup data will be stored in encrypted mode.

      In earlier versions, backup data of encrypted EVS disks is stored in non-encrypted mode. In the current version, newly generated backup data is stored in encrypted mode; however, historical non-encrypted backups will remain unchanged.

#. Confirm that the EVS disks selected for backup are correct. Then in the **Configure Backup** area below, set **Auto Backup** or **Immediate Backup** or both. See :ref:`Figure 2 <en-us_topic_0015667820__fig17436105514815>`.

   .. _en-us_topic_0015667820__fig17436105514815:

   .. figure:: /_static/images/en-us_image_0152879159.png
      :alt: **Figure 2** Configuring backup schemes

      **Figure 2** Configuring backup schemes

   .. note::

      **Auto Backup**: The selected EVS disks will be associated with the backup policy. If the policy is enabled, the EVS disks will be automatically backed up according to the backup policy. If the selected EVS disks have been associated with another backup policy, they will be disassociated from that backup policy first and then associated with the new backup policy.

      **Immediate Backup**: backs up the selected EVS disks at once.

   -  Select **Auto Backup**: In the **Backup Policy** drop-down list, select an existing one. You can also click **Create Policy** to create a new one. For details, see :ref:`Data Backup Using a Backup Policy <en-us_topic_0033745918>`.

   -  Select **Immediate Backup**: Enter the backup name and description. :ref:`Table 1 <en-us_topic_0015667820__table11869527309>` describes the parameters.

      .. _en-us_topic_0015667820__table11869527309:

      .. table:: **Table 1** Parameter description

         +-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
         | Parameter   | Description                                                                                                                                                                                                                                                                                                                            | Example Value |
         +=============+========================================================================================================================================================================================================================================================================================================================================+===============+
         | Name        | The name can only contain letters, digits, underscores (_), and hyphens (-). It cannot contain special characters or start with **auto**. If you select only one EVS disk to back up, the backup name ranges from 1 to 64 characters. If you select more than one EVS disk to back up, the backup name ranges from 1 to 59 characters. | disk01_backup |
         +-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
         | Description | The description consists of 0 to 64 characters and cannot contain a greater-than sign (>) or less-than sign (<).                                                                                                                                                                                                                       | for_test      |
         +-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+

#. Determine whether to select **Enable** next to **Full Backup**. If **Full Backup** is enabled, the generated full backup and later generated incremental backups will support instant restoration. When you use Instant Restore for the first time through APIs and the to-be-restored disk has been backed up before the feature is enabled, enable full backup. After doing this, the disk backups generated through APIs will support instant restoration.

#. Add tags to the backup.

   A tag is represented in the form of a key-value pair. Tags are used to identify, classify, and search for cloud resources. Tags are used to filter and manage backup resources only. A backup can have a maximum of 10 tags.

   :ref:`Table 2 <en-us_topic_0015667820__table191162312815>` describes parameters of a tag.

   .. _en-us_topic_0015667820__table191162312815:

   .. table:: **Table 2** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                           | Example Value         |
      +=======================+=======================================================================================================================================================+=======================+
      | Key                   | Each tag of a backup has a unique key. The key of a tag is user-definable or is selected from those of existing tags in Tag Management Service (TMS). | Key_0001              |
      |                       |                                                                                                                                                       |                       |
      |                       | The naming rules for a tag key are as follows:                                                                                                        |                       |
      |                       |                                                                                                                                                       |                       |
      |                       | -  It ranges from 1 to 36 Unicode characters.                                                                                                         |                       |
      |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                                                             |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Value                 | The values of tags can be repetitive and can be blank.                                                                                                | Value_0001            |
      |                       |                                                                                                                                                       |                       |
      |                       | The naming rules for a tag value are as follows:                                                                                                      |                       |
      |                       |                                                                                                                                                       |                       |
      |                       | -  It ranges from 0 to 43 Unicode characters.                                                                                                         |                       |
      |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                                                             |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

#. Confirm the VBS backup information and click **Submit**.

#. Switch back to the VBS backup list.

   You can refresh the page after 10 seconds to view the backup creation status. When the **Status** of the backup changes to **Available**, the VBS backup has been successfully created.

Create a VBS Backup (Method 2)
------------------------------

#. Log in to the management console.

#. Click |image5|. Under **Storage**, click **Elastic Volume Service**.

#. Click |image6| in the upper left corner of the management console and select a region and a project.

#. Locate the row that contains the target EVS disk. Click **More** in the **Operation** column and select **Create Backup**.

#. From the EVS disk list on the left, click |image7| to select the EVS disks you want to back up. Then they appear in the **Selected Disks** list on the right. See :ref:`Figure 3 <en-us_topic_0015667820__fig19341916182310>`. You can click |image8| in the **Operation** column to delete EVS disks that do not need to be backed up.

   .. _en-us_topic_0015667820__fig19341916182310:

   .. figure:: /_static/images/en-us_image_0152878946.png
      :alt: **Figure 3** Selecting a disk

      **Figure 3** Selecting a disk

   .. note::

      The system will identify whether the selected EVS disk is encrypted. If it is encrypted, its backup data will be stored in encrypted mode.

      In earlier versions, backup data of encrypted EVS disks is stored in non-encrypted mode. In the current version, newly generated backup data is stored in encrypted mode; however, historical non-encrypted backups will remain unchanged.

#. Confirm that the EVS disks selected for backup are correct. Then in the **Configure Backup** area below, set **Auto Backup** or **Immediate Backup** or both. See :ref:`Figure 4 <en-us_topic_0015667820__fig22827152142>`.

   .. _en-us_topic_0015667820__fig22827152142:

   .. figure:: /_static/images/en-us_image_0152879164.png
      :alt: **Figure 4** Configuring backup schemes

      **Figure 4** Configuring backup schemes

   .. note::

      **Auto Backup**: The selected EVS disks will be associated with the backup policy and will be automatically backed up according to the backup policy. If the selected EVS disks have been associated with another backup policy, they will be disassociated from that backup policy first and then associated with the new backup policy.

      **Immediate Backup**: backs up the selected EVS disks at once.

   -  Select **Auto Backup**: In the **Backup Policy** drop-down list, select an existing one. You can also click **Create Policy** to create a new one. For details, see :ref:`Data Backup Using a Backup Policy <en-us_topic_0033745918>`.
   -  Select **Immediate Backup**: Enter the backup name and description. :ref:`Table 1 <en-us_topic_0015667820__table11869527309>` describes the parameters.

#. Determine whether to select **Enable** next to **Full Backup**. If **Full Backup** is enabled, the generated full backup and later generated incremental backups will support instant restoration. When you use Instant Restore for the first time through APIs and the to-be-restored disk has been backed up before the feature is enabled, enable full backup. After doing this, the disk backups generated through APIs will support instant restoration.

#. Add tags to the VBS backup. :ref:`Table 2 <en-us_topic_0015667820__table191162312815>` describes the parameters.

   A tag is represented in the form of a key-value pair. Tags are used to identify, classify, and search for cloud resources. Tags are used to filter and manage backup resources only. A backup can have a maximum of 10 tags.

#. Click **Create Now**.

#. Confirm the VBS backup information and click **Submit**.

#. Switch back to the VBS backup list.

   You can refresh the page after 10 seconds to view the backup creation status. When the **Status** of the backup changes to **Available**, the VBS backup has been successfully created.

.. |image1| image:: /_static/images/en-us_image_0128947790.png
.. |image2| image:: /_static/images/en-us_image_0148548673.png
.. |image3| image:: /_static/images/en-us_image_0148405304.png
.. |image4| image:: /_static/images/en-us_image_0148405236.png
.. |image5| image:: /_static/images/en-us_image_0123883658.png
.. |image6| image:: /_static/images/en-us_image_0148548842.png
.. |image7| image:: /_static/images/en-us_image_0148405304.png
.. |image8| image:: /_static/images/en-us_image_0148405236.png
