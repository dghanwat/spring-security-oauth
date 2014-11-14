spring-security-oauth
=====================

A Spike to try out Spring Security and OAuth 2

Build the source
=====================


The source code is a maven project and can be build using maven command “mvn clean install” 


Deploy the code
=====================

The source code is shipped with a maven jetty plugin. Jetty server can be started using maven command “mvn jetty:run” 

Authenticate the User and Generate Token
=====================

Request 

curl -v -u web-client:web-client --data "username=user1&password=user1&grant_type=password" -X POST http://127.0.0.1:8080/authentication/oauth/token
Response
{"access_token":"f949a7cc-faee-401b-abb0-71f7c6705a42","token_type":"bearer","refresh_token":"911ddc07-8b79-4f11-aaa6-d8d44f1d1bd5","expires_in":59,"scope":"read trust write"}

Accessing Protected Resource
=====================

Request 
curl -H "Authorization:Bearer c1b018ed-036c-44a7-ac14-642c95a82cdc"  -X GET http://127.0.0.1:8080/authentication/resources/MyResource/getMyInfo
Response
Protected Resource(getMyInfo) Accessed !!!! Returning from Myresource getMyInfo
