:original_name: en-us_topic_0043410562.html

.. _en-us_topic_0043410562:

Disassociating Resources from a Backup Policy
=============================================

Function
--------

This API is used to disassociate one or more resources from a backup policy.

URI
---

-  URI format

   POST /v2/{project_id}/backuppolicyresources/{policy_id}/deleted_resources

-  Parameter description

   ========== ========= ================
   Parameter  Mandatory Description
   ========== ========= ================
   project_id Yes       Project ID
   policy_id  Yes       Backup policy ID
   ========== ========= ================

Request
-------

-  Parameter description

   +-------------+-----------+------------+-------------------------------------------+
   | Parameter   | Mandatory | Type       | Description                               |
   +=============+===========+============+===========================================+
   | resources   | Yes       | list<dict> | Information about the associated resource |
   +-------------+-----------+------------+-------------------------------------------+
   | resource_id | Yes       | string     | Resource ID                               |
   +-------------+-----------+------------+-------------------------------------------+

-  Example request

   .. code-block::

      {
          "resources": [
              {
                  "resource_id": "bce8d47a-af17-4169-901f-4c7ae9f29c2c"
              }
          ]
      }

Response
--------

-  Parameter description

   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                     |
   +=======================+=======================+=================================================================================+
   | success_resources     | list<dict>            | List of successfully disassociated resources                                    |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | resource_id           | string                | Resource ID                                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | fail_resources        | list<dict>            | List of the resources that fail to be disassociated                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | resource_id           | string                | Resource ID                                                                     |
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
          "success_resources": [],
          "fail_resources": [
          {
               "resource_id": "bbba7509-f457-4732-97f1-a8e24b6ed9bc"
          }]
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
