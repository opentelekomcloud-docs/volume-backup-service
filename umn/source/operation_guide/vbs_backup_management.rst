:original_name: en-us_topic_0015667849.html

.. _en-us_topic_0015667849:

VBS Backup Management
=====================

You can set filtering criteria to query wanted backups, add tags to backups for grouped management, and share your backups with other projects.

CSBS backups of ECSs are also displayed on the VBS backup page and can be distinguished from VBS backups by **Source** in the backup details.

After Instant Restore is enabled, each backup will be marked with a letter **C** or **E** at the right of its name to show whether it supports instant restoration. A backup marked with letter **C** is a common backup and does not support instant restoration. A backup marked with letter **E** is an enhanced backup and supports instant restoration. For details, see :ref:`Instant Restore <en-us_topic_0071076576__section1713119814918>`.

.. _en-us_topic_0015667849__section3521024785717:

Searching for a VBS Backup
--------------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region and a project.
#. Click |image2|. Under **Storage**, click **Volume Backup Service**.
#. Search for backups.

   -  On the top of the list, select **My backups** and **Backups shared with me** in the drop-down list.

      -  On the **My backups** page, search for backups by backup name, backup ID, KMS key ID, or disk ID, and then click |image3| to search. See :ref:`Figure 1 <en-us_topic_0015667849__fig144211243155512>`.

         .. _en-us_topic_0015667849__fig144211243155512:

         .. figure:: /_static/images/en-us_image_0075595478.png
            :alt: **Figure 1** My backups


            **Figure 1** My backups

      -  On the **Backups shared with me** page, you can see the time when the backup is shared in the **Shared** column. You can search for backups by backup name, backup ID, disk ID, or owner project ID, as shown in :ref:`Figure 2 <en-us_topic_0015667849__fig1252813127211>`. Click |image4| to search.

         .. _en-us_topic_0015667849__fig1252813127211:

         .. figure:: /_static/images/en-us_image_0075595645.png
            :alt: **Figure 2** Backups shared with me


            **Figure 2** Backups shared with me

   -  Above the page, select a state to search for backups.
   -  In the upper right corner of the page, you can click the **Search by Tag** tab to search for backups.

      -  On the **Search by Tag** tab page that is displayed, enter a tag key and a tag value (must be among existing keys and values), click |image5|, and then click **Search**.
      -  You can use more than one tag for a combination search. Each time after a key and a value are entered, click |image6|. The added tag search criteria are displayed under the text boxes. When more than one tag is added, they will be applied together for a combination search. A maximum of 10 tags can be added at the same time.
      -  You can click **Reset** under the search criteria to reset the search criteria.

#. Click |image7| in the row of a VBS backup to view its details.

   .. note::

      The **Created** column in the backup list indicates the time when the backup was created.

View the Status of a Backup Job
-------------------------------

After creating backup jobs, you can view backup job status in **Job Status** above the backup list.

The backup job status can be:

-  **Processing**: a backup job is being executed
-  **Failed**: a backup job failed to be executed

   .. note::

      -  You can click the number next to **Job Status** to view details about the backup job creation. The **Created** column indicates the time when the backup job was started.
      -  If no backup jobs in either of the two states are displayed, **Job Status** is left blank.

Delete a VBS Backup
-------------------

To delete unwanted VBS backups, ensure the backups' statuses are **Available** or **Error** and **Source** is **VBS**.

Backups whose **Source** is **CSBS** can be deleted only on the CSBS management console.

#. Log in to the management console.

#. Click |image8| in the upper left corner of the management console and select a region and a project.

#. Click |image9|. Under **Storage**, click **Volume Backup Service**.

#. Locate the row that contains the target VBS backup in the backup list.

#. Click **Delete** in the **Operation** column.

#. In the dialog box displayed, confirm the information and click **OK**. See :ref:`Figure 3 <en-us_topic_0015667849__fig10847162913589>`.

   .. _en-us_topic_0015667849__fig10847162913589:

   .. figure:: /_static/images/en-us_image_0086680618.png
      :alt: **Figure 3** Deleting a backup


      **Figure 3** Deleting a backup

#. Optional: To delete multiple backups in a batch, click |image10| to select them, and then click the **Delete** button above the list. In the dialog box that is displayed, confirm the deletion information and click **OK**.

Manage Tags of a VBS Backup
---------------------------

You can add tags to a backup as well as edit and delete these tags. Tags are used to filter and manage backup resources only.

#. Log in to the management console.

#. Click |image11| in the upper left corner of the management console and select a region and a project.

#. Click |image12|. Under **Storage**, click **Volume Backup Service**.

#. Click |image13| in the row of a VBS backup to view its details.

#. Click **Tags** in the details area to expand the tag management panel.

   The panel displays all tags of the VBS backup.

   -  Adding tags

      a. Click **Add Tag** in the upper left corner.

      b. In the dialog box that is displayed, set the key and value of the new tag. For details, see :ref:`Figure 4 <en-us_topic_0015667849__fig0106181012912>`.

         A tag is represented in the form of a key-value pair. Tags are used to identify, classify, and search for cloud resources. A backup can have a maximum of 10 tags.

         :ref:`Table 1 <en-us_topic_0015667849__table870151884719>` describes parameters of a tag.

         .. _en-us_topic_0015667849__table870151884719:

         .. table:: **Table 1** Parameter description

            +-----------------------+------------------------------------------------------------------------------------------------------------------------------+-----------------------+
            | Parameter             | Description                                                                                                                  | Example Value         |
            +=======================+==============================================================================================================================+=======================+
            | Key                   | Each tag of a backup has a unique key. The key of a tag is user-definable or is selected from those of existing tags in TMS. | Key_0001              |
            |                       |                                                                                                                              |                       |
            |                       | The naming rules for a tag key are as follows:                                                                               |                       |
            |                       |                                                                                                                              |                       |
            |                       | -  It ranges from 1 to 36 Unicode characters.                                                                                |                       |
            |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                                    |                       |
            +-----------------------+------------------------------------------------------------------------------------------------------------------------------+-----------------------+
            | Value                 | The values of tags can be repetitive and can be blank.                                                                       | Value_0001            |
            |                       |                                                                                                                              |                       |
            |                       | The naming rules for a tag value are as follows:                                                                             |                       |
            |                       |                                                                                                                              |                       |
            |                       | -  It ranges from 0 to 43 Unicode characters.                                                                                |                       |
            |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                                    |                       |
            +-----------------------+------------------------------------------------------------------------------------------------------------------------------+-----------------------+

         .. _en-us_topic_0015667849__fig0106181012912:

         .. figure:: /_static/images/en-us_image_0152879176.png
            :alt: **Figure 4** Adding tags


            **Figure 4** Adding tags

      c. Click **OK**.

   -  Editing a tag

      a. In the **Operation** column of the tag that you want to edit, click **Edit**.

      b. In the **Edit Tag** dialog box that is displayed, modify the tag value. :ref:`Table 1 <en-us_topic_0015667849__table870151884719>` describes the parameters.

         If the updated tag is identical to an existing one, only one is retained.

      c. Click **OK**.

   -  Deleting a tag

      a. In the **Operation** column of the tag that you want to delete, click **Delete**.
      b. In the dialog box that is displayed, confirm the deletion information.
      c. Click **OK**.

   -  Searching for backups by tag

      For details, see :ref:`Searching for a VBS Backup <en-us_topic_0015667849__section3521024785717>`.

Manage Shared VBS Backups
-------------------------

A tenant can share a backup with other tenants.

Encrypted backups cannot be shared. Backups of common I/O (performance optimized I) and ultra-high I/O (latency optimized) disks cannot be shared.

Backups cannot be shared across regions. This indicates that projects sharing a backup must be in the same region as the backup.

#. Log in to the management console.

#. Click |image14| in the upper left corner of the management console and select a region and a project.

#. Click |image15|. Under **Storage**, click **Volume Backup Service**.

#. Click |image16| in the row of a backup.

#. Click **Shares** in the backup details area to expand the share management panel.

   The panel displays the ID list of projects with which the backup is shared.

   -  Adding a share

   a. In the upper left corner, click **Share Backup**, and then the **Share Backup** dialog box is displayed. For details, see :ref:`Figure 5 <en-us_topic_0015667849__fig6681214115510>`.

      .. _en-us_topic_0015667849__fig6681214115510:

      .. figure:: /_static/images/en-us_image_0152879212.png
         :alt: **Figure 5** Adding a share


         **Figure 5** Adding a share

   b. Enter the project ID of the target tenant.

      .. note::

         A project ID is a string of 32 characters that can contain letters and digits but cannot be digits only.

   c. Click **Add** in the dialog box to add another project ID. A tenant can share a backup with another 10 tenants.

   d. Click **OK**.

   -  Deleting a share

   a. Select a share that you want to delete, and click **Unshare** in the **Operation** column.
   b. In the dialog box that is displayed, confirm the deletion information.
   c. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0148548673.png
.. |image2| image:: /_static/images/en-us_image_0128947790.png
.. |image3| image:: /_static/images/en-us_image_0148561644.png
.. |image4| image:: /_static/images/en-us_image_0148561644.png
.. |image5| image:: /_static/images/en-us_image_0148562574.png
.. |image6| image:: /_static/images/en-us_image_0148562574.png
.. |image7| image:: /_static/images/en-us_image_0148563132.png
.. |image8| image:: /_static/images/en-us_image_0148548673.png
.. |image9| image:: /_static/images/en-us_image_0128947790.png
.. |image10| image:: /_static/images/en-us_image_0148405304.png
.. |image11| image:: /_static/images/en-us_image_0148548673.png
.. |image12| image:: /_static/images/en-us_image_0128947790.png
.. |image13| image:: /_static/images/en-us_image_0148563132.png
.. |image14| image:: /_static/images/en-us_image_0148548673.png
.. |image15| image:: /_static/images/en-us_image_0128947790.png
.. |image16| image:: /_static/images/en-us_image_0148563132.png
