:original_name: en-us_topic_0015667849.html

.. _en-us_topic_0015667849:

VBS Backup Management
=====================

You can set filtering criteria to query wanted backups, add tags to backups for grouped management, and share your backups with other projects.

CSBS backups of ECSs are also displayed on the VBS backup page and can be distinguished from VBS backups by **Source** in the backup details.

After Instant Restore is enabled, each backup will be marked with a letter **C** or **E** at the right of its name to show whether it supports instant restoration. A backup marked with letter **C** is a common backup and does not support instant restoration. A backup marked with letter **E** is an enhanced backup and supports instant restoration. For details, see :ref:`Instant Restore <en-us_topic_0071076576__section1713119814918>`.

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

   -  Above the page, select a state to search for backups.
   -  In the upper right corner of the page, you can click the **Search by Tag** tab to search for backups.

      -  On the **Search by Tag** tab page that is displayed, enter a tag key and a tag value (must be among existing keys and values), click |image4|, and then click **Search**.
      -  You can use more than one tag for a combination search. Each time after a key and a value are entered, click |image5|. The added tag search criteria are displayed under the text boxes. When more than one tag is added, they will be applied together for a combination search. A maximum of 10 tags can be added at the same time.
      -  You can click **Reset** under the search criteria to reset the search criteria.

#. Click |image6| in the row of a VBS backup to view its details.

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

#. Click |image7| in the upper left corner of the management console and select a region and a project.

#. Click |image8|. Under **Storage**, click **Volume Backup Service**.

#. Locate the row that contains the target VBS backup in the backup list.

#. Click **Delete** in the **Operation** column.

#. In the dialog box displayed, confirm the information and click **OK**. See :ref:`Figure 2 <en-us_topic_0015667849__fig10847162913589>`.

   .. _en-us_topic_0015667849__fig10847162913589:

   .. figure:: /_static/images/en-us_image_0086680618.png
      :alt: **Figure 2** Deleting a backup

      **Figure 2** Deleting a backup

#. Optional: To delete multiple backups in a batch, click |image9| to select them, and then click the **Delete** button above the list. In the dialog box that is displayed, confirm the deletion information and click **OK**.

.. |image1| image:: /_static/images/en-us_image_0148548673.png
.. |image2| image:: /_static/images/en-us_image_0128947790.png
.. |image3| image:: /_static/images/en-us_image_0148561644.png
.. |image4| image:: /_static/images/en-us_image_0148562574.png
.. |image5| image:: /_static/images/en-us_image_0148562574.png
.. |image6| image:: /_static/images/en-us_image_0148563132.png
.. |image7| image:: /_static/images/en-us_image_0148548673.png
.. |image8| image:: /_static/images/en-us_image_0128947790.png
.. |image9| image:: /_static/images/en-us_image_0148405304.png
