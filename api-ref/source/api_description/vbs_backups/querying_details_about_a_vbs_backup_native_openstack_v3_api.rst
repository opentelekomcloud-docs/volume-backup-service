:original_name: en-us_topic_0143705537.html

.. _en-us_topic_0143705537:

Querying Details About a VBS Backup (Native OpenStack V3 API)
=============================================================

Function
--------

This API is used to query details about a VBS backup.

URI
---

-  URI format

   GET /v3/{project_id}/backups/{backup_id}

-  Parameter description

   ========== ========= ===========
   Parameter  Mandatory Description
   ========== ========= ===========
   project_id Yes       Project ID
   backup_id  Yes       Backup ID
   ========== ========= ===========

Request
-------

None

Response
--------

-  Parameter description

   +----------------------------------+------------+-----------------------------------------------+
   | Parameter                        | Type       | Description                                   |
   +==================================+============+===============================================+
   | backup                           | dict       | List of queried backups                       |
   +----------------------------------+------------+-----------------------------------------------+
   | status                           | string     | Backup status                                 |
   +----------------------------------+------------+-----------------------------------------------+
   | description                      | string     | Backup description                            |
   +----------------------------------+------------+-----------------------------------------------+
   | links                            | list<link> | Backup URL                                    |
   +----------------------------------+------------+-----------------------------------------------+
   | availability_zone                | string     | AZ where the backup resides                   |
   +----------------------------------+------------+-----------------------------------------------+
   | volume_id                        | string     | Source disk ID of the backup                  |
   +----------------------------------+------------+-----------------------------------------------+
   | fail_reason                      | string     | Cause of the backup failure                   |
   +----------------------------------+------------+-----------------------------------------------+
   | id                               | string     | Backup ID                                     |
   +----------------------------------+------------+-----------------------------------------------+
   | size                             | int        | Backup size                                   |
   +----------------------------------+------------+-----------------------------------------------+
   | object_count                     | int        | Number of objects on OBS for the disk data    |
   +----------------------------------+------------+-----------------------------------------------+
   | container                        | string     | Container of the backup                       |
   +----------------------------------+------------+-----------------------------------------------+
   | name                             | string     | Backup name                                   |
   +----------------------------------+------------+-----------------------------------------------+
   | created_at                       | string     | Backup creation time                          |
   +----------------------------------+------------+-----------------------------------------------+
   | os-backup-project-attr:tenant_id | string     | ID of the project that owns the VBS backup    |
   +----------------------------------+------------+-----------------------------------------------+
   | updated_at                       | string     | Update time of the backup                     |
   +----------------------------------+------------+-----------------------------------------------+
   | data_timestamp                   | string     | Current time                                  |
   +----------------------------------+------------+-----------------------------------------------+
   | has_dependent_backups            | boolean    | Whether a dependent backup exists             |
   +----------------------------------+------------+-----------------------------------------------+
   | snapshot_id                      | string     | ID of the snapshot associated with the backup |
   +----------------------------------+------------+-----------------------------------------------+
   | is_incremental                   | boolean    | Whether the backup is an incremental backup   |
   +----------------------------------+------------+-----------------------------------------------+

-  **description** parameter description

   +-----------+--------+----------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                              |
   +===========+========+==========================================================================================================+
   | DESC      | string | Backup description                                                                                       |
   +-----------+--------+----------------------------------------------------------------------------------------------------------+
   | INC       | int    | Whether the backup request was an incremental backup call. **1**: incremental backup; **0**: full backup |
   +-----------+--------+----------------------------------------------------------------------------------------------------------+

-  **link** parameter description

   +-----------+--------+----------------------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                                          |
   +===========+========+======================================================================================================================+
   | href      | string | URL of the last backup queried                                                                                       |
   +-----------+--------+----------------------------------------------------------------------------------------------------------------------+
   | rel       | string | Relationship between the query result and **href**. The value **next** indicates that some backups are not obtained. |
   +-----------+--------+----------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "backup": {
              "status": "error",
              "description": null,
              "links": [{
                  "href": "http://192.168.82.222:8776/v2/b23b579f08c84228b9b4673c46f0c442/backups/1d1139d8-8989-49d3-8aa1-83eb691e6db2",
                  "rel": "self"
              },
              {
                  "href": "http://192.168.82.222:8776/b23b579f08c84228b9b4673c46f0c442/backups/1d1139d8-8989-49d3-8aa1-83eb691e6db2",
                  "rel": "bookmark"
              }],
              "availability_zone": null,
              "volume_id": "2748f2f2-4394-4e6e-af8d-8dd34496c024",
              "fail_reason": "Connection to swift failed: [Errno 111] ECONNREFUSED",
              "id": "1d1139d8-8989-49d3-8aa1-83eb691e6db2",
              "size": 1,
              "object_count": null,
              "container": "volumebackups",
              "name": null,
              "created_at": "2013-06-27T08:48:03.000000",
              "os-backup-project-attr:project_id": "b23b579f08c84228b9b4673c46f0c442",
              "snapshot_id": "66a574c0-4415-499e-b0b1-3f340d7f7932",
              "updated_at": "2019-03-27T12:36:17.596602",
              "data_timestamp": "2019-03-16T11:56:00.917245",
              "has_dependent_backups": false,
              "is_incremental": false
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
