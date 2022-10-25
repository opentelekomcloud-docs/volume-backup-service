:original_name: en-us_topic_0078214151.html

.. _en-us_topic_0078214151:

Sharing a Backup
================

Function
--------

This API is used to share a backup to another project.

URI
---

-  URI format

   POST /v2/{project_id}/os-vendor-backup-sharing

-  Parameter description

   ========== ========= ===========
   Parameter  Mandatory Description
   ========== ========= ===========
   project_id Yes       Project ID
   ========== ========= ===========

Request
-------

-  Parameter description

   +----------------+-----------+--------------+-------------------------------------------------+
   | Parameter      | Mandatory | Type         | Description                                     |
   +================+===========+==============+=================================================+
   | shared         | Yes       | dict         | Information about the backup sharing            |
   +----------------+-----------+--------------+-------------------------------------------------+
   | backup_id      | Yes       | string       | ID of the backup to be shared                   |
   +----------------+-----------+--------------+-------------------------------------------------+
   | to_project_ids | Yes       | list<string> | IDs of projects with which the backup is shared |
   +----------------+-----------+--------------+-------------------------------------------------+

-  Example request

   .. code-block::

      {
          "shared": {
              "to_project_ids": [
                  "722513ed0a324dadaabe5b2d0fe848c9",
                  "722513ed0a324dadaabe5b2d0fe84919"
              ],
              "backup_id": "066b1e37-9305-4057-97e5-2e99b21fc71d"
          }
      }

Response
--------

-  Parameter description

   +-----------------+-----------+--------+-------------------------------------------------+
   | Parameter       | Mandatory | Type   | Description                                     |
   +=================+===========+========+=================================================+
   | shared          | Yes       | dict   | Information about the backup sharing            |
   +-----------------+-----------+--------+-------------------------------------------------+
   | backup_id       | Yes       | string | Backup ID                                       |
   +-----------------+-----------+--------+-------------------------------------------------+
   | id              | Yes       | string | Backup sharing ID                               |
   +-----------------+-----------+--------+-------------------------------------------------+
   | to_project_id   | Yes       | string | ID of the project to which the backup is shared |
   +-----------------+-----------+--------+-------------------------------------------------+
   | from_project_id | Yes       | string | ID of the project that shares the backup        |
   +-----------------+-----------+--------+-------------------------------------------------+
   | created_at      | Yes       | string | Creation time of the backup sharing             |
   +-----------------+-----------+--------+-------------------------------------------------+
   | updated_at      | Yes       | string | Update time of the backup sharing               |
   +-----------------+-----------+--------+-------------------------------------------------+
   | deleted         | Yes       | string | Whether the backup sharing has been canceled    |
   +-----------------+-----------+--------+-------------------------------------------------+
   | deleted_at      | Yes       | string | Deletion time                                   |
   +-----------------+-----------+--------+-------------------------------------------------+

-  Example response

   .. code-block::

      {
          "shared": [
              {
                  "backup_id": "066b1e37-9305-4057-97e5-2e99b21fc71d",
                  "deleted": null,
                  "created_at": null,
                  "updated_at": null,
                  "to_project_id": "722513ed0a324dadaabe5b2d0fe848c9",
                  "from_project_id": "c13f5220dc1949b0b741ea81a7cd5554",
                  "deleted_at": null,
                  "id": "8332443e-9866-41d8-8a58-a898cf5db030"
              }
          ]
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
