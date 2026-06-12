---
Thema:
  - "[[Webentwicklung]]"
---

# HTTP Status code
## Means

|     |               |                                                                          |
| --- | ------------- | ------------------------------------------------------------------------ |
| 1xx | Informational | It means the request has been received and the process is continuing     |
| 2xx | Success       | It means the action was successfully received, understood, and accepted. |
| 3xx | Redirection   | It means further action must be taken in order to complete the request.  |
| 4xx | Client Error  | It means the request contains incorrect syntax or cannot be fulfilled    |
| 5xx | Server Error  | It means the server failed to fulfill an apparently valid request.       |
## 1xx. Information

|     |                     |                                                                                                                                                   |
| --- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| 100 | Continue            | Only a part of the request has been received by the server, but as long as it has not been rejected, the client should continue with the request. |
| 101 | Switching Protocols | The server switches protocol.                                                                                                                     |
| 102 | Processing          | An interim response used to inform the client that the server has accepted the complete request, but has not yet completed it.                    |
| 103 | Early Hints         | Indicates to the client that the server is likely to send a final response with the header fields included in the informational response.         |
## 2xx. Successful 

|     |                             |                                                                                                                                                                                                               |
| --- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200 | OK                          | The request is OK                                                                                                                                                                                             |
| 201 | Created                     | The request is complete, and a new resource is created                                                                                                                                                        |
| 202 | Accepted                    | The request is accepted for processing, but the processing is not complete                                                                                                                                    |
| 203 | Non-Authoritive Information | The information in the entity header is from a local or third-party copy, not from the original server                                                                                                        |
| 204 | No Content                  | A status code and a header are given in the response, but there is no entity-body in the reply                                                                                                                |
| 205 | Reset Content               | The browser should clear the form used for this transaction for additional input                                                                                                                              |
| 206 | Partial Content             | The server is returning partial data of the size requested. Used in response to a request specifying a Range header. The server must specify the range included in the response with the Content-Range header |
| 207 | Multi Status                | Provides status for multiple independent operations                                                                                                                                                           |
| 208 | Already Reported            | Used inside a DAV: propstat response element to avoid enumerating the internal members of multiple bindings to the same collection repeatedly                                                                 |
| 226 | IM Used                     | The server has fulfilled a request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance                                 |
## 3xx. Redirection
| Code | Name | Description |
|------|-------|-------------|
| 300 | Multiple Choices | A link list. The user can select a link and go to that location. Maximum five addresses. |
| 301 | Moved Permanently | The requested page has moved to a new URL. |
| 302 | Found | The requested page has moved temporarily to a new URL. |
| 303 | See Other | The requested page can be found under a different URL. |
| 304 | Not Modified | Response to an If-Modified-Since or If-None-Match header; the URL has not been modified since the specified date. |
| 305 | Use Proxy | The requested URL must be accessed through the proxy mentioned in the Location header. |
| 306 | Unused | Previously used; no longer used, but the code is reserved. |
| 307 | Temporary Redirect | The requested page has moved temporarily to a new URL. |
| 308 | Permanent Redirect | The request and all future requests should be repeated using another URI. |
## 4xx. Client Error
| Code | Name                                                                                     | Description                                                                           |
| ---- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| 400  | Bad Request                                                                              | The server did not understand the request.                                            |
| 401  | Unauthorized                                                                             | The requested page needs a username and a password.                                   |
| 402  | Payment Required                                                                         | You can not use this code yet.                                                        |
| 403  | Forbidden                                                                                | Access is forbidden to the requested page.                                            |
| 404  | Not Found                                                                                | The server can not find the requested page.                                           |
| 405  | Method Not Allowed                                                                       | The method specified in the request is not allowed.                                   |
| 406  | Not Acceptable                                                                          | The server can only generate a response that is not accepted by the client.           |
| 407  | Proxy Authentication Required       | You must authenticate with a proxy server before this request can be served.          |
| 408  | Request Timeout                  | The request took longer than the server was prepared to wait.                         |
| 409  | Conflict                           | The request could not be completed because of a conflict.                             |
| 410  | Gone                             | The requested page is no longer available.                                            |
| 411  | Length Required                  | The Content-Length is not defined. The server will not accept the request without it. |
| 412  | Precondition Failed                  | The precondition given in the request evaluated to false.                             |
| 413  | Payload Too Large                 | The server will not accept the request because the request entity is too large.       |
| 414  | URI Too Long                       | The server will not accept the request because the URL is too long.                   |
| 415  | Unsupported Media Type             | The server will not accept the request because the media type is not supported.       |
| 416  | Range Not Satisfiable                 | The requested byte range is not available and is out of bounds.                       |
| 417  | Expectation Failed                | The expectation given in an Expect header field could not be met.                     |
| 421  | Misdirected Request                 | The request was directed at a server that cannot produce a response.                  |
| 426  | Upgrade Required                   | The server refuses to perform the request using the current protocol.                 |
| 428  | Precondition Required                   | The origin server requires the request to be conditional.                             |
| 429  | Too Many Requests                       | Too many requests in a given amount of time.                                          |
| 431  | Request Header Fields Too Large         | The header fields are too large.                                                      |
| 451  | Unavailable For Legal Reasons | Access to the resource is denied due to a legal demand.                               |
## 5xx. Server Error
| Code | Name                            | Description                                                                                      |
| ---- | ------------------------------- | ------------------------------------------------------------------------------------------------ |
| 500  | Internal Server Error           | The request was not completed. The server met an unexpected condition.                           |
| 501  | Not Implemented                 | The request was not completed. The server did not support the functionality required.            |
| 502  | Bad Gateway                     | The request was not completed. The server received an invalid response from the upstream server. |
| 503  | Service Unavailable             | The request was not completed. The server is temporarily overloading or down.                    |
| 504  | Gateway Timeout                 | The gateway has timed out.                                                                       |
| 505  | HTTP Version Not Supported      | The server does not support the HTTP protocol version.                                           |
| 506  | Variant Also Negotiates         | Transparent content negotiation for the request results in a circular reference.                 |
| 507  | Insufficient Storage            | The server is unable to store the representation needed to complete the request.                 |
| 508  | Loop Detected                   | The server detected an infinite loop while processing the request.                               |
| 510  | Not Extended                    | Further extensions to the request are required for the server to fulfill it.                     |
| 511  | Network Authentication Required | The client needs to authenticate to gain network access.                                         |
