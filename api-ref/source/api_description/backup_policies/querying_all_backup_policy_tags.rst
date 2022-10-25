:original_name: en-us_topic_0067142130.html

.. _en-us_topic_0067142130:

Querying All Backup Policy Tags
===============================

Function
--------

This API is used to query tags of all backup policies.

URI
---

-  URI format

   GET /v2/{project_id}/backuppolicy/tags

-  Parameter description

   ========== ========= ===========
   Parameter  Mandatory Description
   ========== ========= ===========
   project_id Yes       Project ID
   ========== ========= ===========

-  Example request

   .. code-block:: text

      GET /v2/{project_id}/backuppolicy/tags

Request
-------

None

Response
--------

-  Parameter description

   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                     |
   +=======================+=======================+=================================================================================+
   | tags                  | list<dict>            | List of tag details                                                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | key                   | string                | Tag key                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | values                | list<string>          | List of tag values                                                              |
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
        "tags": [
          {
            "key": "RUNNING",
            "values":[
            "0781095c-b8ab-4ce5-99f3-4c5f6ff75319",
            "2016-12-03T06:24:34.467"
            ]
          },
          {
            "key": "WAITING",
            "values":[
            "0781095c-b8ab-4ce5-99f3-4c5f6ff75319",
            "2016-12-03T06:24:34.467"
            ]
          }
        ]
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
