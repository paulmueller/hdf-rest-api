DELETE Dataset
==============

Description
-----------

The implementation of the DELETE operation deletes the dataset named in the URI. All attributes and links of the dataset will also be deleted. In addition any links from other groups to the deleted group will be removed.

Requests
--------

### Syntax

``` sourceCode
DELETE /datasets/<id> HTTP/1.1
Host: DOMAIN
Authorization: <authorization_string>
```

*&lt;id&gt;* is the UUID of the requested dataset to be deleted.

### Request Parameters

This implementation of the operation does not use request parameters.

### Request Headers

This implementation of the operation uses only the request headers that are common to most requests. See ../CommonRequestHeaders

Responses
---------

### Response Headers

This implementation of the operation uses only response headers that are common to most responses. See ../CommonResponseHeaders.

### Response Elements

On success, a JSON response will be returned with the following elements:

#### hrefs

An array of links to related resources. See ../Hypermedia.

### Special Errors

This implementation of the operation does not return special errors. For general information on standard error codes, see ../CommonErrorResponses.

Examples
--------

### Sample Request

``` sourceCode
DELETE /datasets/289bb654-a2c6-11e4-97d8-3c15c2da029e HTTP/1.1
Content-Length: 0
User-Agent: python-requests/2.3.0 CPython/2.7.8 Darwin/14.0.0
host: tall_dset112_deleted.test.hdfgroup.org
Accept: */*
Accept-Encoding: gzip, deflate
```

### Sample Response

``` sourceCode
HTTP/1.1 200 OK
Date: Fri, 23 Jan 2015 06:07:49 GMT
Content-Length: 287
Content-Type: application/json
Server: TornadoServer/3.2.2
```

``` sourceCode
{
"hrefs": [
    {"href": "http://tall_dset112_deleted.test.hdfgroup.org/datasets", "rel": "self"}, 
    {"href": "http://tall_dset112_deleted.test.hdfgroup.org/groups/289b4873-a2c6-11e4-adfb-3c15c2da029e", "rel": "root"}, 
    {"href": "http://tall_dset112_deleted.test.hdfgroup.org/", "rel": "home"}
  ]
}
```

Related Resources
-----------------

-   GET\_Datasets
-   GET\_Dataset
-   POST\_Dataset

