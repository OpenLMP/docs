# Authentication API

## Introduction

With each API call that require to be authenticated, you'll need to set request headers, including an OAuth 2.0 access token.

## Authorization Request Header Field

When sending the access token in the `Authorization` request header defined by HTTP/1.1, the client uses the `Bearer` authentication scheme to transmit the access token.

Example :

~~~
GET /v1/entities/foo HTTP/1.1
Host: server.example.com
Authorization: Bearer [Token]
~~~

## Get an access token

### Resource URL
`https://server.example.com/v1/oauth2/token`

### Parameters

`grant_type` **required**. Specifies the type of grant being requested by the client.

### Example Request

~~~
POST /v1/token HTTP/1.1
Host: server.example.com
Authorization: Basic [Base64 encoded bearer token credentials]
Content-Type: application/x-www-form-urlencoded;charset=UTF-8

grant_type=client_credentials
~~~

### Example Response

~~~
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8

{"token_type":"bearer","access_token":"[Bearer Token]"}
~~~

[Back to index](index.md)
