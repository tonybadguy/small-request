# small-request

[![npm version](https://badge.fury.io/js/small-request.svg)](https://badge.fury.io/js/small-request) [![Build Status](https://travis-ci.org/tonybadguy/small-request.svg?branch=master)](https://travis-ci.org/tonybadguy/small-request) [![codecov](https://codecov.io/gh/tonybadguy/small-request/branch/master/graph/badge.svg)](https://codecov.io/gh/tonybadguy/small-request) [![bitHound Overall Score](https://www.bithound.io/github/tonybadguy/small-request/badges/score.svg)](https://www.bithound.io/github/tonybadguy/small-request)

This Node.js module is a thin wrapper around the Node.js http/https request functions that provides:
* a Promise interface
* handling of response chunking
* auto-selection of the http/https request function

The promise is resolved when:
* a response is received from the server regardless of status code

The promise is rejected when:
* any other exception is encountered

## Example usage:

```
const request = require('simple-request');

request.send({
  url: 'https://httpbin.org/get'
}).then(response => {
  console.log(response.data);
});
```

## RequestModel
The request.send(requestModel) function takes in an object with the following fields:
* url (string)
* headers (object)
* body (string)
* method (string, default = 'GET')

## ResponseModel
The promise returned by request.send() resolves to an object with the following fields:
* body (string)
* headers (object)
* statusCode (number)