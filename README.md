This Library for RobotFramework
=====================================================

Introduction
---------------

RobotFramework-IFHttpLibrary is an Interface testing library for `RobotFramework`
It includes post, get, delete, put method to send http requests,and also use MySql 
datebase to verify the Correctness of response datas.

It support Python 2.x and MySql database only.

Installation
------------

Using ``pip``
'''''''''''''

The recommended installation method is using
`pip <http://pip-installer.org>`__::

   pip install robotframework-interfacelibrary

The main benefit of using ``pip`` is that it automatically installs all
dependencies needed by the library. Other nice features are easy upgrading
and support for un-installation::

    pip install --upgrade robotframework-interfacelibrary
    pip uninstall robotframework-interfacelibrary

Usage Guider:
----------------------------------------
Here is a sample test case.

|                     |                         |                     |                       |                                    |                            |                |
| --------------------| ------------------------| ------------------- | --------------------- | -----------------------------------|----------------------------|--------------- |
| *** Settings ***    |                         |                     |                       |                                    |　　　　                    |                |
| Library             | String                  |                     |                       |                                    |                            |                |
| Library             | Collections             |                     |                       |                                    |                            |                |
| Library             | InterfaceLibrary        |                     |                       |                                    |                            |                |
| Test Cases          |                         |                     |                       |                                    |　　　　                    |                |
| Post Requests       |                         |                     |                       |                                    |　　　                      |                |
|                     | Create Session          | &{enviro}[host]     | &{enviro}[port]       | alise                              |                            |                |
|                     | Conncet To Datebase     | ${host}             | ${user}               | ${password}                        | ${database}                | ${port}        |
|                     | ${res}                  | Post Request        | /activity/addActivity | {'activityName':'${activityName}'} | None                       |                |
|                     | Check Code              | ${resp}             | 200                   |                                    |                            |                |
|                     | ${res}                  |Post File Request    | /cgi-bin/file/upload  | {'file':open('logo.jpg','rb')}     | {'type':'jpg'}             |


 

* Web端：通过Cookie登录访问。
  设置环境变量keyword:
  create session
  connect to database
  post/get request  登录接口
* Mobile端:包括PC,Mobile,通过Proxy访问需要加密，根据项目需求可扩展测试库增加相应的加密算法关键字，
  定制request headers,加密请求体body，再调用encrypt post 关键字发送加密http 请求。
 
Project Contributors
--------------------
* `Wuqi <wuqi@yixin.im>`_
* `WeiYaTing <hzweiyating@corp.netease.com>`_

.. _Robot Framework: http://robotframework.org
.. _requests: http://docs.python-requests.org/en/master
.. _mysql: https://github.com/sanpingz/mysql-connector
