:original_name: en-us_topic_0043430177.html

.. _en-us_topic_0043430177:

Querying Backup Jobs Triggered by a Backup Policy
=================================================

Function
--------

This API is used to query the status of backup jobs triggered by a backup policy.

URI
---

-  URI format

   GET /v2/{project_id}/backuppolicy/{policy_id}/backuptasks

-  Parameter description

   ========== ========= ================
   Parameter  Mandatory Description
   ========== ========= ================
   project_id Yes       Project ID
   policy_id  Yes       Backup policy ID
   ========== ========= ================

-  **Request filter** parameter description

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                       |
   +=================+=================+=================+===================================================================================+
   | sort_dir        | No              | string          | Sorting order. Possible values are **asc** (ascending) and **desc** (descending). |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+
   | limit           | No              | integer         | Maximum number of query results that can be returned. The default value is 20.    |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+
   | marker          | No              | string          | Start number from which backup jobs are queried. The value is the backup job ID.  |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+
   | job_id          | No              | string          | Backup job ID                                                                     |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+
   | status          | No              | string          | Backup job status                                                                 |
   |                 |                 |                 |                                                                                   |
   |                 |                 |                 | -  RUNNING                                                                        |
   |                 |                 |                 | -  EXECUTE_TIMEOUT                                                                |
   |                 |                 |                 | -  WAITING                                                                        |
   |                 |                 |                 | -  EXECUTE_FAIL                                                                   |
   |                 |                 |                 | -  EXECUTE_SUCCESS                                                                |
   |                 |                 |                 | -  SKIP                                                                           |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+
   | sort_key        | No              | string          | Keyword for sorting query results. The value must be **created_at**.              |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+
   | offset          | No              | integer         | Query offset. The default value is 0.                                             |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      GET /v2/{project_id}/backuppolicy/{policy_id}/backuptasks?limit=10

Request
-------

None

Response
--------

-  Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | count                 | integer               | Total number of queried jobs                                                                        |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | tasks                 | list<dict>            | Details about the backup jobs                                                                       |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | status                | string                | Backup job status                                                                                   |
   |                       |                       |                                                                                                     |
   |                       |                       | -  RUNNING                                                                                          |
   |                       |                       | -  EXECUTE_TIMEOUT                                                                                  |
   |                       |                       | -  WAITING                                                                                          |
   |                       |                       | -  EXECUTE_FAIL                                                                                     |
   |                       |                       | -  EXECUTE_SUCCESS                                                                                  |
   |                       |                       | -  SKIP                                                                                             |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | job_id                | string                | Backup job ID                                                                                       |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | created_at            | string                | Time the backup job was created. The time is in UTC format, for example, 2016-12-02T09:06:46.706.   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | finished_at           | string                | Time the backup job was completed. The time is in UTC format, for example, 2016-12-02T13:00:00.121. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | backup_name           | string                | Backup name                                                                                         |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | resource_id           | string                | Resource ID                                                                                         |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | resource_type         | string                | Resource type                                                                                       |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | vbs_job_id            | string                | VBS backup job ID                                                                                   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | message               | string                | Error message returned after an error occurs                                                        |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | code                  | string                | Error code returned after an error occurs                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about error codes, see :ref:`Error Codes <en-us_topic_0022472083>`.                     |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "tasks": [
          {
            "status": "RUNNING",
            "job_id": "0781095c-b8ab-4ce5-99f3-4c5f6ff75319",
            "created_at": "2016-12-03T06:24:34.467",
            "backup_name": "autobk_a61d",
            "resource_id": "f47a4ab5-11f5-4509-97f5-80ce0dd74e37",
            "resource_type": "volume"
          },
          {
            "status": "EXECUTE_SUCCESS",
            "job_id": "c11b5a18-4559-4731-b7b3-58e2bd89cdb9",
            "created_at": "2016-12-02T09:06:46.706",
            "finished_at": "2016-12-02T13:00:00.121",
            "backup_name": "autobk_e6d2",
            "resource_id": "f47a4ab5-11f5-4509-97f5-80ce0dd74e37",
            "resource_type": "volume"
          }
        ],
        "count": 2
      }

   or

   .. code-block::

      {
          "error": {
              "message": "XXXX",
              "code": "XXX"
          }
      }

Status Codes
------------

-  Normal

   200

-  Abnormal

   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | Status Code                       | Description                                                                                |
   +===================================+============================================================================================+
   | 400 Bad Request                   | The server failed to process the request.                                                  |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 401 Unauthorized                  | You must enter the username and password to access the requested page.                     |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 403 Forbidden                     | You are forbidden to access the requested page.                                            |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 404 Not Found                     | The server could not find the requested page.                                              |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 405 Method Not Allowed            | You are not allowed to use the method specified in the request.                            |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 406 Not Acceptable                | The response generated by the server could not be accepted by the client.                  |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 407 Proxy Authentication Required | You must use the proxy server for authentication so that the request can be processed.     |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 408 Request Timeout               | The request timed out.                                                                     |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 409 Conflict                      | The request could not be processed due to a conflict.                                      |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 500 Internal Server Error         | Failed to complete the request because of an internal service error.                       |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 501 Not Implemented               | Failed to complete the request because the server does not support the requested function. |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 502 Bad Gateway                   | Failed to complete the request because the request is invalid.                             |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 503 Service Unavailable           | Failed to complete the request because the service is unavailable.                         |
   +-----------------------------------+--------------------------------------------------------------------------------------------+
   | 504 Gateway Timeout               | A gateway timeout error occurred.                                                          |
   +-----------------------------------+--------------------------------------------------------------------------------------------+

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0022472083>`.
