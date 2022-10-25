:original_name: en-us_topic_0043410561.html

.. _en-us_topic_0043410561:

Associating Resources with a Backup Policy
==========================================

Function
--------

This API is used to associate one or more resources with a backup policy.

URI
---

-  URI format

   POST /v2/{project_id}/backuppolicyresources

-  Parameter description

   ========== ========= ===========
   Parameter  Mandatory Description
   ========== ========= ===========
   project_id Yes       Project ID
   ========== ========= ===========

Request
-------

-  Parameter description

   +------------------+-----------------+-----------------+--------------------------------------------+
   | Parameter        | Mandatory       | Type            | Description                                |
   +==================+=================+=================+============================================+
   | backup_policy_id | Yes             | string          | Backup policy ID                           |
   +------------------+-----------------+-----------------+--------------------------------------------+
   | resources        | Yes             | list<dict>      | Information about the associated resource  |
   +------------------+-----------------+-----------------+--------------------------------------------+
   | resource_id      | Yes             | string          | Resource ID                                |
   +------------------+-----------------+-----------------+--------------------------------------------+
   | resource_type    | Yes             | string          | Resource type. The options are as follows: |
   |                  |                 |                 |                                            |
   |                  |                 |                 | -  volume                                  |
   +------------------+-----------------+-----------------+--------------------------------------------+

-  Example request

   .. code-block::

      {
          "backup_policy_id":"915d1fd8-63cb-4054-a2b0-2778210e3a75",
          "resources":[{
              "resource_id":"0f187b65-8d0e-4fc0-9096-3b55d330531e",
              "resource_type":"volume"
              },{
              "resource_id":"0f187b65-8d0e-4fc0-9096-3b55d330531d",
              "resource_type":"volume"
          }]
      }

Response
--------

-  Parameter description

   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                     |
   +=======================+=======================+=================================================================================+
   | success_resources     | list<dict>            | List of successfully associated resources                                       |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | resource_id           | string                | Resource ID                                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | resource_type         | string                | Resource type                                                                   |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | availability_zone     | string                | AZ to which the resource belongs                                                |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | os_vol_host_attr      | string                | Point of delivery (POD) to which the resource belongs                           |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | fail_resources        | list<dict>            | List of the resources that fail to be associated                                |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | resource_id           | string                | Resource ID                                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | resource_type         | string                | Resource type                                                                   |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | availability_zone     | string                | AZ to which the resource belongs                                                |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | os_vol_host_attr      | string                | POD to which the resource belongs                                               |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | message               | string                | Error message returned after an error occurs                                    |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | code                  | string                | Error code returned after an error occurs                                       |
   |                       |                       |                                                                                 |
   |                       |                       | For details about error codes, see :ref:`Error Codes <en-us_topic_0022472083>`. |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "success_resources": [
              {
                  "resource_id": "bce8d47a-af17-4169-901f-4c7ae9f29c2c",
                  "os_vol_host_attr": "pod01.eu-de-01",
                  "availability_zone": "eu-de-01",
                  "resource_type": "volume"
              }
          ],
          "fail_resources": [ ]
      }

   or

   .. code-block::

      {
          "error": {
              "code": "XXXX",
              "message": "XXX"
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
