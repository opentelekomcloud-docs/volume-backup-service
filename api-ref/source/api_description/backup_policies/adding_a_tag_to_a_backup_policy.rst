:original_name: en-us_topic_0098527676.html

.. _en-us_topic_0098527676:

Adding a Tag to a Backup Policy
===============================

Function
--------

This API is used to add a tag to a backup policy.

URI
---

-  URI format

   POST /v2/{project_id}/backuppolicy/{policy_id}/tags

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

   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                           |
   +===========+===========+========+=======================================================================================================================+
   | tag       | Yes       | dict   | Tag to be added                                                                                                       |
   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------+
   | key       | Yes       | string | Tag key. It contains 1 to 36 characters, chosen from letters, digits, hyphens (-), and underscores (_).               |
   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------+
   | value     | Yes       | string | Tag value. A tag value consists of 0 to 43 characters, chosen from letters, digits, hyphens (-), and underscores (_). |
   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      {
          "tag":{
              "key":"0f187b65-8d0e-4fc0-9096-3b55d330531e",
              "value":"volume"
          }
      }

Response
--------

-  Parameter description

   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                     |
   +=======================+=======================+=================================================================================+
   | message               | string                | Error message returned after an error occurs                                    |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | code                  | string                | Error code returned after an error occurs                                       |
   |                       |                       |                                                                                 |
   |                       |                       | For details about error codes, see :ref:`Error Codes <en-us_topic_0022472083>`. |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "error": {
              "message": "XXXX",
              "code": "XXX"
          }
      }

Status Code
-----------

-  Normal

   204

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
