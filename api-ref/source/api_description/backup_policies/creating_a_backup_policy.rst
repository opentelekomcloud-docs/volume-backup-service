:original_name: en-us_topic_0043410517.html

.. _en-us_topic_0043410517:

Creating a Backup Policy
========================

Function
--------

This API is used to create a backup policy. A tenant can create a maximum of 10 backup policies.

URI
---

-  URI format

   POST /v2/{project_id}/backuppolicy

-  Parameter description

   ========== ========= ===========
   Parameter  Mandatory Description
   ========== ========= ===========
   project_id Yes       Project ID
   ========== ========= ===========

Request
-------

-  Parameter description

   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                       | Mandatory                                                         | Type            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   +=================================+===================================================================+=================+=====================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | backup_policy_name              | Yes                                                               | string          | Backup policy name                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                                 |                                                                   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |                                 |                                                                   |                 | The name is a string of 1 to 64 characters consisting of letters, digits, underscores (_), and hyphens (-). It cannot start with **default**.                                                                                                                                                                                                                                                                                                                       |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | scheduled_policy                | Yes                                                               | dict            | Details about the scheduling policy                                                                                                                                                                                                                                                                                                                                                                                                                                 |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | start_time                      | Yes                                                               | string          | Backup execution time (UTC), in the format of **HH:mm**                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                                 |                                                                   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |                                 |                                                                   |                 | You need to set the execution time to a full hour. You can set multiple execution times, and use commas (,) to separate one time from another. To set multiple backup execution times, enter them in ascending order by local time. For example, if your local time is 2 hours ahead of UTC and you want to perform backups at the local times 00:00, 02:00, and 04:00, set this parameter to **22:00,00:00,02:00** (UTC times) and **time_zone** to **UTC+02:00**. |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | frequency                       | No (Either this field or **week_frequency** must be specified.)   | integer         | Backup interval (1 to 14 days). Set either this parameter or **week_frequency**. If you set both, this parameter is used.                                                                                                                                                                                                                                                                                                                                           |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | week_frequency                  | No (Either this field or **frequency** must be specified.)        | list<string>    | Defines on which days of each week backup jobs are executed. The value can be one or more of the following:                                                                                                                                                                                                                                                                                                                                                         |
   |                                 |                                                                   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |                                 |                                                                   |                 | SUN, MON, TUE, WED, THU, FRI, SAT                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rentention_num                  | No (Either this field or **rentention_day** must be specified.)\\ | integer         | Number (from 2 to 14) of retained backups. Set either this parameter or **rentention_day**. If you set both, this parameter is used.                                                                                                                                                                                                                                                                                                                                |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rentention_day                  | No (Either this field or **rentention_num** must be specified.)   | integer         | Retention days of backups. The value is an integer ranging from 2 to 99999. If you enter a floating point number, the number will be rounded down to the nearest integer when you send the request.                                                                                                                                                                                                                                                                 |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | remain_first_backup_of_curMonth | No                                                                | string          | Whether to retain the first backup in the current month                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                                 |                                                                   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |                                 |                                                                   |                 | -  Y                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |                                 |                                                                   |                 | -  N                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                          | Yes                                                               | string          | Backup policy status                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |                                 |                                                                   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |                                 |                                                                   |                 | -  ON                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
   |                                 |                                                                   |                 | -  OFF                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags                            | No                                                                | list<dict>      | Tags to be configured for the backup policy                                                                                                                                                                                                                                                                                                                                                                                                                         |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | key                             | Yes                                                               | string          | Tag key. It contains 1 to 36 characters, A tag key can contain only letters, digits, hyphens (-), and underscores (_).                                                                                                                                                                                                                                                                                                                                              |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value                           | Yes                                                               | string          | Tag value. A tag value consists of 0 to 43 characters. A tag value can contain only letters, digits, hyphens (-), and underscores (_).                                                                                                                                                                                                                                                                                                                              |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | time_zone                       | No                                                                | string          | Time zone. The value is in the UTC+/-HH:mm format.                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                                 |                                                                   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |                                 |                                                                   |                 | This parameter specifies the time zone of the local time with the Daylight Saving Time (DST) offset, for example, UTC+08:00 or UTC-02:00. If execution times are in different days after converting into UTC times, this parameter must be used with **week_frequency** and **start_time**.                                                                                                                                                                         |
   +---------------------------------+-------------------------------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      {
          "backup_policy_name": "policy_01",
          "scheduled_policy" : {
              "remain_first_backup_of_curMonth" : "Y",
              "rentention_day" : 30,
              "week_frequency" : ["SUN","WED"],
              "start_time" : "12:00",
              "status" : "ON"
          },
          "tags":[{
            "key":"key",
            "value":"value"
          }],
          "time_zone": "UTC+08:00"
      }

Response
--------

-  Parameter description

   +-----------------------+-----------------------+---------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                     |
   +=======================+=======================+=================================================================================+
   | backup_policy_id      | string                | Backup policy ID returned if the operation is successful                        |
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
        "backup_policy_id": "af8a20b0-117d-4fc3-ae53-aa3968a4f870"
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
