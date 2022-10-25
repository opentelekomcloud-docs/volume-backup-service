:original_name: en-us_topic_0043410564.html

.. _en-us_topic_0043410564:

Enabling or Disabling a Backup Policy
=====================================

Function
--------

This API is used to enable or disable a backup policy. After a backup policy is enabled, it will be scheduled based on the specified time. After a backup policy is disabled, it will not be scheduled.

Set the backup policy status to **ON** or **OFF**. For details, see :ref:`Modifying a Backup Policy <en-us_topic_0043410559>`.

+-----------------+-----------------+-----------------+----------------------+
| Parameter       | Mandatory       | Type            | Description          |
+=================+=================+=================+======================+
| status          | Yes             | string          | Backup policy status |
|                 |                 |                 |                      |
|                 |                 |                 | -  ON                |
|                 |                 |                 | -  OFF               |
+-----------------+-----------------+-----------------+----------------------+
