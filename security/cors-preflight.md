## [🪴 View In My Digital Garden: Security Attack - CORS Pre-Flight Requests](https://www.aniqa.io/wiki/security/cors-preflight)


---

**CORS Pre-Flight Request** = [CORS](/wiki/security/cors) request that checks if CORS protocol is accepted and if the server is using the correct methods and headers

Servers may *block* requests to **modify** resources on the server but are likely to allow regular `GET` requests to go through since **no changes are being made**. Whether or not it gets blocked or allowed is determined by **Preflight Requests**. 

**Preflight Requests are triggered when any of the following HTTP Method requests are made** - *HTTP Methods that potentially modify the website in response to user or server behaviors*:
```
PUT
DELETE
CONNECT
OPTIONS
TRACE
PATCH
```

**Preflight Requests** = `OPTIONS` **header that uses the following HTTP Request Headers:**
- `Access-Control-Request-Method`
- `Access-Control-Request-Headers`
- `ORIGIN`

#### The Why Behind Preflight
Called **preflight** because it is **sent before the main request** to determine if the **communication line is safe** ➞ then, server will respond and indicate whether or not the request is safe
- [x] server responds that request is **SAFE** = original request will be allowed
- [ ] server responds that request is **NOT safe** = original request is blocked

## Complete Preflight Request & CORS Process
#### ➞ Preflight Request
**Client's [Browser] sends the following to the [Server]:**
```http
OPTIONS /img HTTP/1.1
ORIGIN: mywebserver.com
Access-Control-Request-Method: DELETE
```

**[Server] receives the HTTP request header and subsequently, responds with**:
```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Access-Control-Allow-Method: DELETE, GET
```




#### ➞ Original (CORS) Request
**Client's [Browser] sends the original request** (in this case, `DELETE`) **to the Server**:
```
DELETE /img HTTP/1.1
ORIGIN: mywebserver.com
Access-Control-Request-Method: DELETE
```

- `Access-Control-Request-Method` is the HTTP method that the main request is using

**[Server] will then receive the request and process it + respond if it was successful or not (using HTTP status code)**
```http
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
```

- `Access-Control-Allow-Origin` allows servers to specifies how resources are shared with external domains 
  - `*` value - requested resources that can be shared with any domain (`*` meaning *all*)
  - single or list of `domain` value - requested resources can only be shared to the specified domain(s)
