:original_name: en-us_topic_0113236392.html

.. _en-us_topic_0113236392:

Querying Quotas
===============

Function
--------

This API is used to query tenant quotas.

URI
---

-  URI

   GET /v2/{project_id}/cloudbackups/quota

-  Parameter description

   =========== ========= ===========
   Parameter   Mandatory Description
   =========== ========= ===========
   tenant \_id Yes       Project ID
   =========== ========= ===========

Request
-------

-  Parameter description

None

-  Example request

.. code-block::

     GET /v2/{project_id}/cloudbackups/quota

Response
--------

-  Parameter description

   ========= ========= =================== ==========================
   Parameter Mandatory Type                Description
   ========= ========= =================== ==========================
   quotas    Yes       map<string, string> Quota resource information
   ========= ========= =================== ==========================

-  Parameter description of field **quota**

   ========= ========= =================== ===============
   Parameter Mandatory Type                Description
   ========= ========= =================== ===============
   resources Yes       List<resource_resp> Quota resources
   ========= ========= =================== ===============

-  Parameter description of field **resource_resp**

   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                    |
   +=================+=================+=================+================================================================+
   | reserved        | Yes             | Integer         | Reserved amount                                                |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | used            | Yes             | Integer         | Used amount                                                    |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | quota           | Yes             | Integer         | Quota size. **-1** indicates no restriction on the quota size. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | type            | Yes             | String          | Type                                                           |
   |                 |                 |                 |                                                                |
   |                 |                 |                 | Enum:[ backup_gigabytes ,backups]                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "quotas": {
              "resources":[{
                  "type" :"backups",
                  "used" : 114,
                  "reserved" : 0,
                  "quota" : 5014
               },
               {
                   "type": "backup_ gigabytes",
                   "used" : 4838,
                   "reserved" : 0,
                   "quota" : -1
                }]
           }
      }

Return Values
-------------

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
