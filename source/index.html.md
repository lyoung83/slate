---
title: Nymbl Marketplace v1.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2
---

# Nymbl Marketplace v1.0

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


Base URLs:

* <a href="http://localhost:4000/">http://localhost:4000/</a>

* <a href="ws://localhost:4000/">ws://localhost:4000/</a>





# Authentication


* API Key
    - Parameter Name: **Authorization**, in: header.



# Session

## Unified.V1.SessionController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/users/sign_in \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/users/sign_in HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/sign_in',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/sign_in',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/users/sign_in',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/users/sign_in', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/sign_in");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/users/sign_in`

Creates a user session and logs the current user

<h3 id="Unified.V1.SessionController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
email|form_data|string|true|User's email address
password|form_data|string|true|User's selected password


> Example responses

```json
{
  "version": "string",
  "message": "string",
  "errors": "string",
  "entities": {
    "user": {
      "username": "string",
      "is_admin": true,
      "email": "string",
      "discourse_user_id": 0,
      "description": "string",
      "company_name": "string",
      "authToken": "string",
      "active": true
    }
  }
}
```
<h3 id="Unified.V1.SessionController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created|[Session](#schemasession)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Comment

## Unified.V1.CommentController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/posts/{post_id}/comments \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/posts/{post_id}/comments HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/{post_id}/comments',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts/{post_id}/comments',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/posts/{post_id}/comments',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/posts/{post_id}/comments', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/{post_id}/comments");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/posts/{post_id}/comments`

creates a comment on post

<h3 id="Unified.V1.CommentController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
content|form_data|string|false|The Comment's Content
post_id|path|integer|true|What post the comment belongs to


> Example responses

```json
{
  "post_id": 0,
  "content": "string",
  "author_id": 0
}
```
<h3 id="Unified.V1.CommentController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Success|[Comment](#schemacomment)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.CommentController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/posts/{post_id}/comments \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/posts/{post_id}/comments HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/{post_id}/comments',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts/{post_id}/comments',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/posts/{post_id}/comments',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/posts/{post_id}/comments', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/{post_id}/comments");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/posts/{post_id}/comments`

Lists all comments on the post

<h3 id="Unified.V1.CommentController.index-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
post_id|path|integer|true|What post the comment belongs to


> Example responses

```json
{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.CommentController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Post](#schemapost)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.CommentController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/posts/:post_id/comments/:id \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/posts/:post_id/comments/:id HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/:post_id/comments/:id',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts/:post_id/comments/:id',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/posts/:post_id/comments/:id',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/posts/:post_id/comments/:id', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/:post_id/comments/:id");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/posts/:post_id/comments/:id`

updates a comment on post

<h3 id="Unified.V1.CommentController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
content|form_data|string|true|The Comment's Content
post_id|path|integer|true|What post the comment belongs to


> Example responses

```json
{
  "post_id": 0,
  "content": "string",
  "author_id": 0
}
```
<h3 id="Unified.V1.CommentController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Comment](#schemacomment)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.CommentController.show

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/posts/:post_id/comments/:id \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/posts/:post_id/comments/:id HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/:post_id/comments/:id',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts/:post_id/comments/:id',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/posts/:post_id/comments/:id',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/posts/:post_id/comments/:id', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/:post_id/comments/:id");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/posts/:post_id/comments/:id`

shows a comment on post

<h3 id="Unified.V1.CommentController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
post_id|path|integer|true|What post the comment belongs to


> Example responses

```json
{
  "post_id": 0,
  "content": "string",
  "author_id": 0
}
```
<h3 id="Unified.V1.CommentController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Comment](#schemacomment)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.CommentController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/posts/:post_id/comments/:id

```

```http
DELETE http://localhost:4000/api/v1/posts/:post_id/comments/:id HTTP/1.1
Host: localhost:4000


```

```javascript

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/:post_id/comments/:id',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:4000/api/v1/posts/:post_id/comments/:id',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'http://localhost:4000/api/v1/posts/:post_id/comments/:id',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('http://localhost:4000/api/v1/posts/:post_id/comments/:id', params={

)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/:post_id/comments/:id");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/posts/:post_id/comments/:id`

updates a comment on post

<h3 id="Unified.V1.CommentController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
post_id|path|integer|true|What post the comment belongs to


<h3 id="Unified.V1.CommentController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Order

## Unified.V1.OrderController.get_addresses

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/orders/{order_id}/get_addresses \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/orders/{order_id}/get_addresses HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/get_addresses',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/get_addresses',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/orders/{order_id}/get_addresses',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/orders/{order_id}/get_addresses', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/get_addresses");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/orders/{order_id}/get_addresses`

Gets all addresses in a Company's directory

> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.get_addresses-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Request|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.show_complete

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/{user_id}/orders/complete \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/{user_id}/orders/complete HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/orders/complete',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/orders/complete',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/{user_id}/orders/complete',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/{user_id}/orders/complete', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/orders/complete");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/{user_id}/orders/complete`

Shows the complete orders from the server for a particular user

<h3 id="Unified.V1.OrderController.show_complete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|The user's ID


> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.show_complete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.switch_active

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/{user_id}/switch_active \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/{user_id}/switch_active HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/switch_active',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/switch_active',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/{user_id}/switch_active',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/{user_id}/switch_active', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/switch_active");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/{user_id}/switch_active`

Switches the current active order for a user or creates a new one

<h3 id="Unified.V1.OrderController.switch_active-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|The user's ID
order_id|form_data|binary|true|ID of the order that you want to be active
active_id|form_data|binary|true|The ID of the currently active order


> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.switch_active-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.show_active

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/{user_id}/orders \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/{user_id}/orders HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/orders',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/orders',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/{user_id}/orders',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/{user_id}/orders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/{user_id}/orders`

Shows the current active order from the server for a particular user

<h3 id="Unified.V1.OrderController.show_active-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|The user's ID


> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.show_active-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/orders \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/orders HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/orders',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/orders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/orders`

create an order on the server

<h3 id="Unified.V1.OrderController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
confirmation_status|form_data|boolean|true|Set this to true
product_total|form_data|decimal|true|can send 0.00
order_state|form_data|string|true|Set to incomplete
user_id|form_data|integer|true|ID of the user that wants the order
active|form_data|boolean|true|Set to true to begin order


> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Success|[Order](#schemaorder)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/orders \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/orders HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/orders',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/orders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/orders`

Lists all orders on the server

> Example responses

```json
[
  {
    "total": null,
    "state": "string",
    "slug": "string",
    "saved": true,
    "product_total": null,
    "order_state": "string",
    "order_items": [
      {
        "sku": "string",
        "quantity": 0,
        "price": null,
        "name": "string",
        "description": "string"
      }
    ],
    "deleted": true,
    "confirmation_status": true,
    "active": true
  }
]
```
<h3 id="Unified.V1.OrderController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Orders](#schemaorders)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.add_address

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/orders/{order_id}/add_address \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/orders/{order_id}/add_address HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/add_address',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/add_address',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/orders/{order_id}/add_address',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/orders/{order_id}/add_address', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/add_address");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/orders/{order_id}/add_address`

Adds a single address to a Company's directory

<h3 id="Unified.V1.OrderController.add_address-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
address|form_data|Address|true|address to add


> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.add_address-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.show_saved

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/{user_id}/saved_orders \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/{user_id}/saved_orders HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/saved_orders',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/saved_orders',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/{user_id}/saved_orders',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/{user_id}/saved_orders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/saved_orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/{user_id}/saved_orders`

Shows all the saved orders for a particular user

<h3 id="Unified.V1.OrderController.show_saved-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|The user's ID


> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.show_saved-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/orders/{id} \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/orders/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{id}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/orders/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/orders/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/orders/{id}`

Updates an order on the server

> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/orders/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/orders/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/orders/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/orders/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/orders/{id}`

Shows an order from the server

<h3 id="Unified.V1.OrderController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|The order's ID


> Example responses

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```
<h3 id="Unified.V1.OrderController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Order](#schemaorder)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/orders/{id}

```

```http
DELETE http://localhost:4000/api/v1/orders/{id} HTTP/1.1
Host: localhost:4000


```

```javascript

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:4000/api/v1/orders/{id}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'http://localhost:4000/api/v1/orders/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('http://localhost:4000/api/v1/orders/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/orders/{id}`

Sets an order to deleted

<h3 id="Unified.V1.OrderController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|The order's id


<h3 id="Unified.V1.OrderController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Game

## Unified.V1.GameController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/game/{vendor_id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/game/{vendor_id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/game/{vendor_id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/game/{vendor_id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/game/{vendor_id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/game/{vendor_id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/game/{vendor_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/game/{vendor_id}`

Gets all of a users points and placement for a single vendor's community category

<h3 id="Unified.V1.GameController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
vendor_id|path|string|true|ID of the vendor's category that you want the information for


> Example responses

```json
{
  "user_id": 0,
  "points": 0,
  "organization_name": "string",
  "last_name": "string",
  "first_name": "string",
  "category": "string"
}
```
<h3 id="Unified.V1.GameController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GameResult](#schemagameresult)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.GameController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/game \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/game HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/game',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/game',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/game',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/game', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/game");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/game`

Gets all of a users points and placement for vendor community categories

> Example responses

```json
{
  "user_id": 0,
  "rankings": [
    {
      "rank": 0,
      "points": 0,
      "category": "string"
    }
  ],
  "organization_name": "string",
  "last_name": "string",
  "first_name": "string"
}
```
<h3 id="Unified.V1.GameController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GameResultUser](#schemagameresultuser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.GameController.leaders

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/game/{vendor_id}/leaders \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/game/{vendor_id}/leaders HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/game/{vendor_id}/leaders',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/game/{vendor_id}/leaders',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/game/{vendor_id}/leaders',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/game/{vendor_id}/leaders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/game/{vendor_id}/leaders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/game/{vendor_id}/leaders`

Gets the top 25 point earners for a vendor's category

<h3 id="Unified.V1.GameController.leaders-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
vendor_id|path|string|true|ID of the vendor's category that you want the information for


> Example responses

```json
[
  {
    "rank": 0,
    "points": 0,
    "member": {
      "organization_name": "string",
      "last_name": "string",
      "first_name": "string",
      "description": "string",
      "avatar": "string"
    }
  }
]
```
<h3 id="Unified.V1.GameController.leaders-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Leaderboard](#schemaleaderboard)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Conversation

## Unified.V1.ConversationController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/conversations/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/conversations/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/conversations/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/conversations/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/conversations/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/conversations/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/conversations/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/conversations/{id}`

Display (return) a conversation

<h3 id="Unified.V1.ConversationController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|The conversation's ID


> Example responses

```json
{
  "users": [
    {
      "username": "string",
      "user_profile": {
        "organization_name": "string",
        "last_name": "string",
        "first_name": "string",
        "description": "string",
        "avatar": "string"
      },
      "is_admin": true,
      "email": "string",
      "discourse_user_id": 0,
      "discourse_api_key": "string",
      "description": "string",
      "company_name": "string",
      "active": true
    }
  ],
  "messages": [
    {
      "user_id": 0,
      "conversation_id": 0,
      "body": "string"
    }
  ],
  "id": 0,
  "converation_memberships": [
    {
      "user_id": 0,
      "conversation_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.ConversationController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Conversation](#schemaconversation)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ConversationController.get_messages

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/conversations/messages \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/conversations/messages HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/conversations/messages',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/conversations/messages',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/conversations/messages',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/conversations/messages', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/conversations/messages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/conversations/messages`

Display (return) messages between a group of users

<h3 id="Unified.V1.ConversationController.get_messages-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_ids|form_data|array|true|The conversation's user_IDs


> Example responses

```json
{
  "users": [
    {
      "username": "string",
      "user_profile": {
        "organization_name": "string",
        "last_name": "string",
        "first_name": "string",
        "description": "string",
        "avatar": "string"
      },
      "is_admin": true,
      "email": "string",
      "discourse_user_id": 0,
      "discourse_api_key": "string",
      "description": "string",
      "company_name": "string",
      "active": true
    }
  ],
  "messages": [
    {
      "user_id": 0,
      "conversation_id": 0,
      "body": "string"
    }
  ],
  "id": 0,
  "converation_memberships": [
    {
      "user_id": 0,
      "conversation_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.ConversationController.get_messages-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Conversation](#schemaconversation)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ConversationController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/conversations \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/conversations HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/conversations',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/conversations',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/conversations',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/conversations', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/conversations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/conversations`

Create a new conversation for the current user

<h3 id="Unified.V1.ConversationController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_ids|form_data|array|true|IDs of the users involved in the conversation


> Example responses

```json
[
  {
    "users": [
      {
        "username": "string",
        "user_profile": {
          "organization_name": "string",
          "last_name": "string",
          "first_name": "string",
          "description": "string",
          "avatar": "string"
        },
        "is_admin": true,
        "email": "string",
        "discourse_user_id": 0,
        "discourse_api_key": "string",
        "description": "string",
        "company_name": "string",
        "active": true
      }
    ],
    "messages": [
      {
        "user_id": 0,
        "conversation_id": 0,
        "body": "string"
      }
    ],
    "id": 0,
    "converation_memberships": [
      {
        "user_id": 0,
        "conversation_id": 0
      }
    ]
  }
]
```
<h3 id="Unified.V1.ConversationController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Conversations](#schemaconversations)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ConversationController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/conversations \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/conversations HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/conversations',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/conversations',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/conversations',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/conversations', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/conversations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/conversations`

Lists all conversations for a given user. User is determined by CurrentUser plug

> Example responses

```json
[
  {
    "users": [
      {
        "username": "string",
        "user_profile": {
          "organization_name": "string",
          "last_name": "string",
          "first_name": "string",
          "description": "string",
          "avatar": "string"
        },
        "is_admin": true,
        "email": "string",
        "discourse_user_id": 0,
        "discourse_api_key": "string",
        "description": "string",
        "company_name": "string",
        "active": true
      }
    ],
    "messages": [
      {
        "user_id": 0,
        "conversation_id": 0,
        "body": "string"
      }
    ],
    "id": 0,
    "converation_memberships": [
      {
        "user_id": 0,
        "conversation_id": 0
      }
    ]
  }
]
```
<h3 id="Unified.V1.ConversationController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created|[Conversations](#schemaconversations)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Product

## Unified.V1.ProductController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/products/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/products/{id} HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/products/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/products/{id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/products/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/products/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/products/{id}`

Updates a product

> Body parameter

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the product to update
body|body|[Product](#schemaproduct)|true|Product properties to change
» upc|body|string|false|upc code for product
» uom|body|string|false|How product is measured
» status|body|string|false|product status
» slug|body|string|false|Product category Identifier
» sku|body|string|false|Manufacturer unique product identifier
» qty_avail|body|integer|false|Amount in stock at this moment
» name|body|string|false|Name of the Product
» discontinue_on|body|string(ISO-8601)|false|Date to discontinue
» description|body|string|false|Product description 255 character limit
» case_qty|body|integer|false|How many products in one unit
» base_price|body|decimal|false|base price for product
» available_on|body|string(ISO-8601)|false|Date made available


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/products/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/products/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/products/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/products/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/products/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/products/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/products/{id}`

List one product

<h3 id="Unified.V1.ProductController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the product you want to view


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/products/{id}

```

```http
DELETE http://localhost:4000/api/v1/products/{id} HTTP/1.1
Host: localhost:4000


```

```javascript

$.ajax({
  url: 'http://localhost:4000/api/v1/products/{id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:4000/api/v1/products/{id}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'http://localhost:4000/api/v1/products/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('http://localhost:4000/api/v1/products/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/products/{id}`

Deletes a product

<h3 id="Unified.V1.ProductController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of product to be deleted


<h3 id="Unified.V1.ProductController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/products \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/products HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/products',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/products',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/products',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/products', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/products`

Creates a product

> Body parameter

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[Product](#schemaproduct)|true|Product to upload only works with a vendor type user
» upc|body|string|false|upc code for product
» uom|body|string|false|How product is measured
» status|body|string|false|product status
» slug|body|string|false|Product category Identifier
» sku|body|string|false|Manufacturer unique product identifier
» qty_avail|body|integer|false|Amount in stock at this moment
» name|body|string|false|Name of the Product
» discontinue_on|body|string(ISO-8601)|false|Date to discontinue
» description|body|string|false|Product description 255 character limit
» case_qty|body|integer|false|How many products in one unit
» base_price|body|decimal|false|base price for product
» available_on|body|string(ISO-8601)|false|Date made available


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Product](#schemaproduct)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/products \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/products HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/products',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/products',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/products',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/products', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/products`

Lists all based on company relationship to mfg

> Example responses

```json
[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]
```
<h3 id="Unified.V1.ProductController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Products](#schemaproducts)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.add_logo

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/vendors/{vendor_id}/add_logo \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/vendors/{vendor_id}/add_logo HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/vendors/{vendor_id}/add_logo',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = 'null';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/vendors/{vendor_id}/add_logo',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/vendors/{vendor_id}/add_logo',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/vendors/{vendor_id}/add_logo', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/vendors/{vendor_id}/add_logo");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/vendors/{vendor_id}/add_logo`

Add a logo to the vendor's profile also hosted on s3, decoded from a base64 string

> Body parameter

<h3 id="Unified.V1.ProductController.add_logo-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
vendor_id|path|integer|true|ID of the vendor to add the log to
body|body|object|false|Base64 encoded logo


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.add_logo-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Product](#schemaproduct)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.add_image

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/products/{product_id}/images \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/products/{product_id}/images HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/products/{product_id}/images',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/products/{product_id}/images',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/products/{product_id}/images',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/products/{product_id}/images', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products/{product_id}/images");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/products/{product_id}/images`

Places an image of the product on s3, url is a base64 encoded string

<h3 id="Unified.V1.ProductController.add_image-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
product_id|path|integer|true|ID of the product to associate the photo with
url|form_data|long|true|Base64 encoded image


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.add_image-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Product](#schemaproduct)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.all_products

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/all_products \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/all_products HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/all_products',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/all_products',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/all_products',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/all_products', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/all_products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/all_products`

Lists all products on the platform

> Example responses

```json
[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]
```
<h3 id="Unified.V1.ProductController.all_products-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Products](#schemaproducts)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.search

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/products/search \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/products/search HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/products/search',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/products/search',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/products/search',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/products/search', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products/search");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/products/search`

searches database for matching products based on params sent

<h3 id="Unified.V1.ProductController.search-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
name|form_data|string|false|Name of the product
description|form_data|string|false|Description of the product
manufacturer|form_data|string|false|Manufacturer name


> Example responses

```json
[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]
```
<h3 id="Unified.V1.ProductController.search-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Products](#schemaproducts)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ProductController.create_multiple

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/products/{vendor_id}/product_upload \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/products/{vendor_id}/product_upload HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/products/{vendor_id}/product_upload',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/products/{vendor_id}/product_upload',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/products/{vendor_id}/product_upload',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/products/{vendor_id}/product_upload', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/products/{vendor_id}/product_upload");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/products/{vendor_id}/product_upload`

Creates a collection products from a mass upload returns a map with completed products and errors from database if any

> Body parameter

```json
[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]
```
<h3 id="Unified.V1.ProductController.create_multiple-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
vendor_id|path|integer|true|ID of the vendor to upload products
body|body|[Products](#schemaproducts)|true|Products to upload


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.ProductController.create_multiple-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Product](#schemaproduct)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# EmailAccount

## Unified.V1.EmailAccountController.connect_token_callback

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/email_accounts/connect_token_callback \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/email_accounts/connect_token_callback HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/email_accounts/connect_token_callback',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/email_accounts/connect_token_callback',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/email_accounts/connect_token_callback',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/email_accounts/connect_token_callback', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/email_accounts/connect_token_callback");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/email_accounts/connect_token_callback`

Connect a Contextio callback - email handler

> Example responses

```json
{
  "status": 0,
  "connect_token_used": 0,
  "connect_token_token": "string",
  "connect_token_expires": 0,
  "connect_token_browser_redirect_url": "string",
  "account_suspended": "string",
  "account_created": "string",
  "account_account": "string"
}
```
<h3 id="Unified.V1.EmailAccountController.connect_token_callback-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Email](#schemaemail)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.EmailAccountController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/email_accounts/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/email_accounts/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/email_accounts/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/email_accounts/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/email_accounts/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/email_accounts/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/email_accounts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/email_accounts/{id}`

Display a given email account

<h3 id="Unified.V1.EmailAccountController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|The ID of the email account from the Database


> Example responses

```json
{
  "status": 0,
  "connect_token_used": 0,
  "connect_token_token": "string",
  "connect_token_expires": 0,
  "connect_token_browser_redirect_url": "string",
  "account_suspended": "string",
  "account_created": "string",
  "account_account": "string"
}
```
<h3 id="Unified.V1.EmailAccountController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Email](#schemaemail)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.EmailAccountController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/email_accounts/{id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:4000/api/v1/email_accounts/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/email_accounts/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/email_accounts/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:4000/api/v1/email_accounts/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:4000/api/v1/email_accounts/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/email_accounts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/email_accounts/{id}`

Delete a given email account

<h3 id="Unified.V1.EmailAccountController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|The ID of the email account from the Database


> Example responses

```json
{
  "status": 0,
  "connect_token_used": 0,
  "connect_token_token": "string",
  "connect_token_expires": 0,
  "connect_token_browser_redirect_url": "string",
  "account_suspended": "string",
  "account_created": "string",
  "account_account": "string"
}
```
<h3 id="Unified.V1.EmailAccountController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Email](#schemaemail)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.EmailAccountController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/email_accounts \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/email_accounts HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/email_accounts',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/email_accounts',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/email_accounts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/email_accounts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/email_accounts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/email_accounts`

Create a new email account

<h3 id="Unified.V1.EmailAccountController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
status|form_data|integer|false|The number status representing the contact time
connect_token_token|form_data|string|false|connect token for contextio
connect_token_browser_redirect_url|form_data|string|false|redirect for contextio browser
connect_token_expires|form_data|integer|false|Token expiration
connect_token_used|form_data|integer|false|If token is used, represented by number
account_account|form_data|string|false|The account for email
account_created|form_data|string(ISO-8601)|false|When the account was created
account_suspended|form_data|string(ISO-8601)|false|When the account is suspended if applicable


> Example responses

```json
[
  {
    "status": 0,
    "connect_token_used": 0,
    "connect_token_token": "string",
    "connect_token_expires": 0,
    "connect_token_browser_redirect_url": "string",
    "account_suspended": "string",
    "account_created": "string",
    "account_account": "string"
  }
]
```
<h3 id="Unified.V1.EmailAccountController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Emails](#schemaemails)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Invoice

## Unified.V1.InvoiceController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/orders/{order_id}/invoices \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/orders/{order_id}/invoices HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/invoices',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/invoices',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/orders/{order_id}/invoices',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/orders/{order_id}/invoices', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/invoices");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/orders/{order_id}/invoices`

Creates all of the necessary invoices for an order

<h3 id="Unified.V1.InvoiceController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The order's ID
total|form_data|decimal|true|The order's total
address_id|form_data|integer|false|ID of the shipping address on the platform


> Example responses

```json
[
  {
    "total": null,
    "items": [
      {
        "sku": "string",
        "quantity": "string",
        "price": null,
        "description": "string"
      }
    ]
  }
]
```
<h3 id="Unified.V1.InvoiceController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Invoices](#schemainvoices)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.InvoiceController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/orders/{order_id}/invoices \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/orders/{order_id}/invoices HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/invoices',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/invoices',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/orders/{order_id}/invoices',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/orders/{order_id}/invoices', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/invoices");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/orders/{order_id}/invoices`

Lists all the invoices for an order

<h3 id="Unified.V1.InvoiceController.index-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The order's ID


> Example responses

```json
[
  {
    "total": null,
    "items": [
      {
        "sku": "string",
        "quantity": "string",
        "price": null,
        "description": "string"
      }
    ]
  }
]
```
<h3 id="Unified.V1.InvoiceController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Invoices](#schemainvoices)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.InvoiceController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/orders/{order_id}/invoices/{id} \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/orders/{order_id}/invoices/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/orders/{order_id}/invoices/{id}`

Updates an invoice for an order (only the address)

<h3 id="Unified.V1.InvoiceController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The order's ID
id|path|integer|true|the ID of the invoice
address_id|form_data|integer|false|ID of the shipping address on the platform


> Example responses

```json
{
  "total": null,
  "items": [
    {
      "sku": "string",
      "quantity": "string",
      "price": null,
      "description": "string"
    }
  ]
}
```
<h3 id="Unified.V1.InvoiceController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Invoice](#schemainvoice)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.InvoiceController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/orders/{order_id}/invoices/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/orders/{order_id}/invoices/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/orders/{order_id}/invoices/{id}`

Shows one of the invoices for an order

<h3 id="Unified.V1.InvoiceController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The order's ID
id|path|integer|true|the ID of the invoice


> Example responses

```json
{
  "total": null,
  "items": [
    {
      "sku": "string",
      "quantity": "string",
      "price": null,
      "description": "string"
    }
  ]
}
```
<h3 id="Unified.V1.InvoiceController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Invoice](#schemainvoice)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.InvoiceController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}

```

```http
DELETE http://localhost:4000/api/v1/orders/{order_id}/invoices/{id} HTTP/1.1
Host: localhost:4000


```

```javascript

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/invoices/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/orders/{order_id}/invoices/{id}`

Deletes an Invoice for an order

<h3 id="Unified.V1.InvoiceController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The order's ID
id|path|integer|true|the ID of the invoice


<h3 id="Unified.V1.InvoiceController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# CommunicationSetting

## Unified.V1.CommunicationSettingController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/communication_settings/:id \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/communication_settings/:id HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/communication_settings/:id',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/communication_settings/:id',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/communication_settings/:id',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/communication_settings/:id', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/communication_settings/:id");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/communication_settings/:id`

Display a given communicaion setting

<h3 id="Unified.V1.CommunicationSettingController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|Communication Setting Id
threshold_json|form_data|map|false|An array containing the setting changes
threshold_enabled|form_data|boolean|false|True or false value


> Example responses

```json
{
  "threshold_json": null,
  "threshold_enabled": true
}
```
<h3 id="Unified.V1.CommunicationSettingController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[CommunicationSetting](#schemacommunicationsetting)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.CommunicationSettingController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/communication_settings/:id \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/communication_settings/:id HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/communication_settings/:id',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/communication_settings/:id',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/communication_settings/:id',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/communication_settings/:id', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/communication_settings/:id");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/communication_settings/:id`

Display a given communicaion setting

<h3 id="Unified.V1.CommunicationSettingController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|Communication Setting Id


> Example responses

```json
{
  "threshold_json": null,
  "threshold_enabled": true
}
```
<h3 id="Unified.V1.CommunicationSettingController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created|[CommunicationSetting](#schemacommunicationsetting)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Broker

## Unified.V1.Admin.BrokerController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/admin/broker/:id \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/admin/broker/:id HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/admin/broker/:id',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/admin/broker/:id',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/admin/broker/:id',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/admin/broker/:id', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/admin/broker/:id");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT api/v1/admin/broker/:id`

Updates a brokers attributes

> Example responses

```json
{
  "links": {
    "self": "string"
  },
  "included": [
    null
  ],
  "data": {
    "type": "string",
    "relationships": {},
    "links": {},
    "id": "string",
    "attributes": {
      "status": "string",
      "owner": "string",
      "company": "string"
    }
  }
}
```
<h3 id="Unified.V1.Admin.BrokerController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Broker](#schemabroker)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.Admin.BrokerController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/admin/broker/:id \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/admin/broker/:id HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/admin/broker/:id',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/admin/broker/:id',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/admin/broker/:id',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/admin/broker/:id', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/admin/broker/:id");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/admin/broker/:id`

Gets a specified broker

> Example responses

```json
{
  "links": {
    "self": "string"
  },
  "included": [
    null
  ],
  "data": {
    "type": "string",
    "relationships": {},
    "links": {},
    "id": "string",
    "attributes": {
      "status": "string",
      "owner": "string",
      "company": "string"
    }
  }
}
```
<h3 id="Unified.V1.Admin.BrokerController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Broker](#schemabroker)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# ContactGroup

## Unified.V1.ContactGroupController.add_members

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/contact_groups/{contact_group_id}/contacts \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/contact_groups/{contact_group_id}/contacts HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contact_groups/{contact_group_id}/contacts',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contact_groups/{contact_group_id}/contacts',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/contact_groups/{contact_group_id}/contacts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/contact_groups/{contact_group_id}/contacts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contact_groups/{contact_group_id}/contacts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/contact_groups/{contact_group_id}/contacts`

Add members an existing contact group

<h3 id="Unified.V1.ContactGroupController.add_members-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
contact_group_id|path|integer|true|Contact Group ID
member_ids|form_data|array|true|Collection of the contact IDs to add to group


> Example responses

```json
{
  "name": "string",
  "created_by_user_id": 0,
  "contacts": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```
<h3 id="Unified.V1.ContactGroupController.add_members-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ContactGroup](#schemacontactgroup)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactGroupController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/contact_groups/{id} \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/contact_groups/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contact_groups/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contact_groups/{id}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/contact_groups/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/contact_groups/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contact_groups/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/contact_groups/{id}`

Update an existing contact group

<h3 id="Unified.V1.ContactGroupController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|Contact Group ID
name|form_data|string|false|Name of the User
created_by_user_id|form_data|integer|false|User Id of the user that created the contacts


> Example responses

```json
{
  "name": "string",
  "created_by_user_id": 0,
  "contacts": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```
<h3 id="Unified.V1.ContactGroupController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[ContactGroup](#schemacontactgroup)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactGroupController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/contact_groups/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/contact_groups/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contact_groups/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contact_groups/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/contact_groups/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/contact_groups/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contact_groups/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/contact_groups/{id}`

Diplay a given contact group

<h3 id="Unified.V1.ContactGroupController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|Contact group ID


> Example responses

```json
{
  "name": "string",
  "created_by_user_id": 0,
  "contacts": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```
<h3 id="Unified.V1.ContactGroupController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[ContactGroup](#schemacontactgroup)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactGroupController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/contact_groups/{id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:4000/api/v1/contact_groups/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contact_groups/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contact_groups/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:4000/api/v1/contact_groups/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:4000/api/v1/contact_groups/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contact_groups/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/contact_groups/{id}`

Update an existing contact group

<h3 id="Unified.V1.ContactGroupController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the group to be deleted


> Example responses

```json
{
  "name": "string",
  "created_by_user_id": 0,
  "contacts": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```
<h3 id="Unified.V1.ContactGroupController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[ContactGroup](#schemacontactgroup)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactGroupController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/contact_groups \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/contact_groups HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contact_groups',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contact_groups',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/contact_groups',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/contact_groups', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contact_groups");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/contact_groups`

Create a new contact group for the current user

<h3 id="Unified.V1.ContactGroupController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
name|form_data|string|true|Name of the Contact Group
created_by_user_id|form_data|integer|true|User Id of the user that created the contact group


> Example responses

```json
{
  "name": "string",
  "created_by_user_id": 0,
  "contacts": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```
<h3 id="Unified.V1.ContactGroupController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[ContactGroup](#schemacontactgroup)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactGroupController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/contact_groups \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/contact_groups HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contact_groups',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contact_groups',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/contact_groups',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/contact_groups', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contact_groups");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/contact_groups`

Lists all contact groups for a given user. User is determined by CurrentUser plug

> Example responses

```json
[
  {
    "name": "string",
    "created_by_user_id": 0,
    "contacts": [
      {
        "to_webook_id": "string",
        "position": "string",
        "pipeline_reminder_date": null,
        "pipeline_reminder": 0,
        "pipeline_custom": true,
        "pipeline_assignee": "string",
        "pipeline": "string",
        "phone_numbers_json": null,
        "last_name": "string",
        "is_customer": true,
        "from_webhook_id": "string",
        "first_name": "string",
        "emails_json": null,
        "description": "string",
        "created_by_user_id": 0,
        "contact_user_id": 0,
        "company": "string",
        "addresses_json": null
      }
    ]
  }
]
```
<h3 id="Unified.V1.ContactGroupController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[ContactGroups](#schemacontactgroups)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# OrderItem

## Unified.V1.OrderItemController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/orders/{order_id}/order_items/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/orders/{order_id}/order_items/{id} HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "sku": "string",
  "quantity": 0,
  "price": null,
  "name": "string",
  "description": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/orders/{order_id}/order_items/{id}`

Updates a single order_item on an order

> Body parameter

```json
{
  "sku": "string",
  "quantity": 0,
  "price": null,
  "name": "string",
  "description": "string"
}
```
<h3 id="Unified.V1.OrderItemController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The ID of the order the product is placed on
id|path|integer|true|The ID of the order item the on the order
body|body|[OrderItem](#schemaorderitem)|true|The updated order item params
» sku|body|string|false|Product SKU
» quantity|body|integer|false|Prouct quantity
» price|body|decimal|false|Product Price
» name|body|string|false|Name of the Product on an order
» description|body|string|false|product description


> Example responses

```json
{
  "sku": "string",
  "quantity": 0,
  "price": null,
  "name": "string",
  "description": "string"
}
```
<h3 id="Unified.V1.OrderItemController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[OrderItem](#schemaorderitem)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderItemController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/orders/{order_id}/order_items/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/orders/{order_id}/order_items/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/orders/{order_id}/order_items/{id}`

Shows a single order_item on an order

<h3 id="Unified.V1.OrderItemController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The ID of the order the product is placed on
id|path|integer|true|The ID of the order item the on the order


> Example responses

```json
{
  "sku": "string",
  "quantity": 0,
  "price": null,
  "name": "string",
  "description": "string"
}
```
<h3 id="Unified.V1.OrderItemController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[OrderItem](#schemaorderitem)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderItemController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/orders/{order_id}/order_items/{id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:4000/api/v1/orders/{order_id}/order_items/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/order_items/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/orders/{order_id}/order_items/{id}`

Deletes a single order_item on an order

<h3 id="Unified.V1.OrderItemController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The ID of the order the product is placed on
id|path|integer|true|The ID of the order item the on the order to be deleted


> Example responses

```json
{
  "sku": "string",
  "quantity": 0,
  "price": null,
  "name": "string",
  "description": "string"
}
```
<h3 id="Unified.V1.OrderItemController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Success|[OrderItem](#schemaorderitem)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderItemController.create_multiple

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/orders/{order_id}/multiple_items \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/orders/{order_id}/multiple_items HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/multiple_items',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/multiple_items',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/orders/{order_id}/multiple_items',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/orders/{order_id}/multiple_items', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/multiple_items");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/orders/{order_id}/multiple_items`

creates multiple order_items on an order with an array of current products

> Body parameter

```json
[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]
```
<h3 id="Unified.V1.OrderItemController.create_multiple-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The ID of the order the product is placed on
body|body|[Products](#schemaproducts)|true|the product to place on the order


> Example responses

```json
[
  {
    "sku": "string",
    "quantity": 0,
    "price": null,
    "name": "string",
    "description": "string"
  }
]
```
<h3 id="Unified.V1.OrderItemController.create_multiple-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[OrderItems](#schemaorderitems)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderItemController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/orders/{order_id}/order_items \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/orders/{order_id}/order_items HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/order_items',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/order_items',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/orders/{order_id}/order_items',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/orders/{order_id}/order_items', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/order_items");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/orders/{order_id}/order_items`

creates an order_item on an order

> Body parameter

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.OrderItemController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
order_id|path|integer|true|The ID of the order the product is placed on
body|body|[Product](#schemaproduct)|true|the product to place on the order
» upc|body|string|false|upc code for product
» uom|body|string|false|How product is measured
» status|body|string|false|product status
» slug|body|string|false|Product category Identifier
» sku|body|string|false|Manufacturer unique product identifier
» qty_avail|body|integer|false|Amount in stock at this moment
» name|body|string|false|Name of the Product
» discontinue_on|body|string(ISO-8601)|false|Date to discontinue
» description|body|string|false|Product description 255 character limit
» case_qty|body|integer|false|How many products in one unit
» base_price|body|decimal|false|base price for product
» available_on|body|string(ISO-8601)|false|Date made available


> Example responses

```json
{
  "sku": "string",
  "quantity": 0,
  "price": null,
  "name": "string",
  "description": "string"
}
```
<h3 id="Unified.V1.OrderItemController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Success|[OrderItem](#schemaorderitem)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.OrderItemController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/orders/{order_id}/order_items \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/orders/{order_id}/order_items HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/orders/{order_id}/order_items',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/orders/{order_id}/order_items',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/orders/{order_id}/order_items',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/orders/{order_id}/order_items', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/orders/{order_id}/order_items");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/orders/{order_id}/order_items`

Lists all order_items on an order

> Example responses

```json
[
  {
    "sku": "string",
    "quantity": 0,
    "price": null,
    "name": "string",
    "description": "string"
  }
]
```
<h3 id="Unified.V1.OrderItemController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[OrderItems](#schemaorderitems)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Pipeline

## Unified.V1.PipelineController.update_hot

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/{user_id}/pipelines/{id}/hot \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/{user_id}/pipelines/{id}/hot HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}/hot',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/pipelines/{id}/hot',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}/hot',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/{user_id}/pipelines/{id}/hot', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/pipelines/{id}/hot");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/{user_id}/pipelines/{id}/hot`

updates the just hot reminder date in the user's pipeline

> Example responses

```json
{
  "user_id": 0,
  "hot_reminder": 0,
  "hot_date": "string",
  "cold_reminder": 0,
  "cold_date": "string"
}
```
<h3 id="Unified.V1.PipelineController.update_hot-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Pipeline](#schemapipeline)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PipelineController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/{user_id}/pipelines/{id} \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/{user_id}/pipelines/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/pipelines/{id}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/{user_id}/pipelines/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/pipelines/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/{user_id}/pipelines/{id}`

updates the hot and cold reminders in the user's pipeline

> Example responses

```json
{
  "user_id": 0,
  "hot_reminder": 0,
  "hot_date": "string",
  "cold_reminder": 0,
  "cold_date": "string"
}
```
<h3 id="Unified.V1.PipelineController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Pipeline](#schemapipeline)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PipelineController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/{user_id}/pipelines/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/{user_id}/pipelines/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/pipelines/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/{user_id}/pipelines/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/pipelines/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/{user_id}/pipelines/{id}`

gets all of the pipeline attributes for a current user

> Example responses

```json
{
  "user_id": 0,
  "hot_reminder": 0,
  "hot_date": "string",
  "cold_reminder": 0,
  "cold_date": "string"
}
```
<h3 id="Unified.V1.PipelineController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Pipeline](#schemapipeline)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PipelineController.update_cold

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/{user_id}/pipelines/{id}/cold \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/{user_id}/pipelines/{id}/cold HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}/cold',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/pipelines/{id}/cold',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/{user_id}/pipelines/{id}/cold',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/{user_id}/pipelines/{id}/cold', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/pipelines/{id}/cold");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/{user_id}/pipelines/{id}/cold`

updates the just cold reminder date in the user's pipeline

> Example responses

```json
{
  "user_id": 0,
  "hot_reminder": 0,
  "hot_date": "string",
  "cold_reminder": 0,
  "cold_date": "string"
}
```
<h3 id="Unified.V1.PipelineController.update_cold-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Pipeline](#schemapipeline)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PipelineController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/{user_id}/pipelines \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/{user_id}/pipelines HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/pipelines',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/pipelines',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/{user_id}/pipelines',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/{user_id}/pipelines', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/pipelines");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/{user_id}/pipelines`

Creates all of the default pipelines for a current user

> Example responses

```json
{
  "user_id": 0,
  "hot_reminder": 0,
  "hot_date": "string",
  "cold_reminder": 0,
  "cold_date": "string"
}
```
<h3 id="Unified.V1.PipelineController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Pipeline](#schemapipeline)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PipelineController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/{user_id}/pipelines \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/{user_id}/pipelines HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/{user_id}/pipelines',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/{user_id}/pipelines',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/{user_id}/pipelines',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/{user_id}/pipelines', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/{user_id}/pipelines");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/{user_id}/pipelines`

Lists all of a user's contacts that have been placed in pipelines

> Example responses

```json
{
  "pipeline": {
    "user_id": 0,
    "hot_reminder": 0,
    "hot_date": "string",
    "cold_reminder": 0,
    "cold_date": "string"
  },
  "hot": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ],
  "custom": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ],
  "cold": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ],
  "closed": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```
<h3 id="Unified.V1.PipelineController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Pipelines](#schemapipelines)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# User

## Unified.V1.UserController.community_show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/users/community/{discourse_user_id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/users/community/{discourse_user_id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/community/{discourse_user_id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/community/{discourse_user_id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/users/community/{discourse_user_id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/users/community/{discourse_user_id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/community/{discourse_user_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/users/community/{discourse_user_id}`

Gets the user profile to display on community

<h3 id="Unified.V1.UserController.community_show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
discourse_user_id|path|integer|true|The discourse user ID of a user


> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.community_show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[User](#schemauser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.follow_user

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/users/{user_id}/follow_user \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/users/{user_id}/follow_user HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{user_id}/follow_user',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{user_id}/follow_user',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/users/{user_id}/follow_user',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/users/{user_id}/follow_user', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{user_id}/follow_user");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/users/{user_id}/follow_user`

Follows a specific User

> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.follow_user-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Ok|[User](#schemauser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/users \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/users HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/users',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/users', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/users`

Creates a user(unused)

<h3 id="Unified.V1.UserController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
first_name|form_data|string|true|First name of user
last_name|form_data|string|true|Last name of user
company_name|form_data|string|true|First name of user
email|form_data|string|true|Email address for user
password|form_data|string|true|user's chosen password name of user
username|form_data|string|true|User's chosen username
phone_numbers|form_data|string|false|Array of a User's phone numbers


> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[User](#schemauser)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessible Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/users \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/users HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/users',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/users', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/users`

Lists all users

> Example responses

```json
[
  {
    "username": "string",
    "user_profile": {
      "organization_name": "string",
      "last_name": "string",
      "first_name": "string",
      "description": "string",
      "avatar": "string"
    },
    "is_admin": true,
    "email": "string",
    "discourse_user_id": 0,
    "discourse_api_key": "string",
    "description": "string",
    "company_name": "string",
    "active": true
  }
]
```
<h3 id="Unified.V1.UserController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Users](#schemausers)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/users/{id} \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/users/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{id}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/users/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/users/{id}`

Updates the user information

<h3 id="Unified.V1.UserController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|Database ID of a user


> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[User](#schemauser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/users/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/users/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/users/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/users/{id}`

Shows one user

<h3 id="Unified.V1.UserController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|Database ID of a user


> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[User](#schemauser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/users/{id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:4000/api/v1/users/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:4000/api/v1/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:4000/api/v1/users/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/users/{id}`

Deletes the user

<h3 id="Unified.V1.UserController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|Database ID of a user


> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|[User](#schemauser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.add_avatar

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/users/{user_id}/avatar \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/users/{user_id}/avatar HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{user_id}/avatar',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{user_id}/avatar',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/users/{user_id}/avatar',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/users/{user_id}/avatar', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{user_id}/avatar");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/users/{user_id}/avatar`

Places a user's avatar on s3

> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.add_avatar-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|[User](#schemauser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.UserController.unfollow_user

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/users/{user_id}/unfollow_user \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/users/{user_id}/unfollow_user HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{user_id}/unfollow_user',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{user_id}/unfollow_user',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/users/{user_id}/unfollow_user',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/users/{user_id}/unfollow_user', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{user_id}/unfollow_user");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/users/{user_id}/unfollow_user`

Unfollows a specific User

> Example responses

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```
<h3 id="Unified.V1.UserController.unfollow_user-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Ok|[User](#schemauser)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Post

## Unified.V1.PostController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/posts/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/posts/{id} HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts/{id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/posts/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/posts/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/posts/{id}`

Updates a single post

> Body parameter

```json
{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.PostController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the post to show
body|body|[Post](#schemapost)|true|The post content, title, and images
» visibility|body|string|false|Who should be able to see this post VENDOR, BROKER, RETAILER
» title|body|string|false|Post title
» page_id|body|integer|false|The user page that the post is on
» has_image|body|boolean|false|does this post have images
» content|body|string|false|The Post's content
» images|body|[[PostImage](#schemapostimage)]|false|A collection of Post Images
»» post_id|body|integer|false|ID of the post the image belongs to
»» image|body|string|false|The persisted filname of the image
» comments|body|[[Comment](#schemacomment)]|false|A collection of user comments
»» post_id|body|integer|false|The id of the associated post
»» content|body|string|false|The Comment content
»» author_id|body|integer|false|The id of the user


> Example responses

```json
{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.PostController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Post](#schemapost)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PostController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/posts/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/posts/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/posts/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/posts/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/posts/{id}`

Shows a single post

<h3 id="Unified.V1.PostController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the post to show


> Example responses

```json
{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.PostController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Post](#schemapost)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PostController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/posts/{id}

```

```http
DELETE http://localhost:4000/api/v1/posts/{id} HTTP/1.1
Host: localhost:4000


```

```javascript

$.ajax({
  url: 'http://localhost:4000/api/v1/posts/{id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:4000/api/v1/posts/{id}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'http://localhost:4000/api/v1/posts/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('http://localhost:4000/api/v1/posts/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/posts/{id}`

Deletes a single post

<h3 id="Unified.V1.PostController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the post to show


<h3 id="Unified.V1.PostController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|NO Content|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PostController.user_posts

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/user_posts/{user_id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/user_posts/{user_id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/user_posts/{user_id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/user_posts/{user_id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/user_posts/{user_id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/user_posts/{user_id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/user_posts/{user_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/user_posts/{user_id}`

Lists all posts for a specific user's page

<h3 id="Unified.V1.PostController.user_posts-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|User id of the author's post you want to see


> Example responses

```json
[
  {
    "visibility": "string",
    "title": "string",
    "page_id": 0,
    "images": [
      {
        "post_id": 0,
        "image": "string"
      }
    ],
    "has_image": true,
    "content": "string",
    "comments": [
      {
        "post_id": 0,
        "content": "string",
        "author_id": 0
      }
    ]
  }
]
```
<h3 id="Unified.V1.PostController.user_posts-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Posts](#schemaposts)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PostController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/posts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/posts HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/posts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/posts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/posts`

Create a single post on the server

> Body parameter

```json
{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.PostController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[Post](#schemapost)|true|The post content, title, and images
» visibility|body|string|false|Who should be able to see this post VENDOR, BROKER, RETAILER
» title|body|string|false|Post title
» page_id|body|integer|false|The user page that the post is on
» has_image|body|boolean|false|does this post have images
» content|body|string|false|The Post's content
» images|body|[[PostImage](#schemapostimage)]|false|A collection of Post Images
»» post_id|body|integer|false|ID of the post the image belongs to
»» image|body|string|false|The persisted filname of the image
» comments|body|[[Comment](#schemacomment)]|false|A collection of user comments
»» post_id|body|integer|false|The id of the associated post
»» content|body|string|false|The Comment content
»» author_id|body|integer|false|The id of the user


> Example responses

```json
{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}
```
<h3 id="Unified.V1.PostController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Post](#schemapost)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.PostController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/posts \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/posts HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/posts',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/posts',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/posts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/posts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/posts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/posts`

Lists all posts on the server

> Example responses

```json
[
  {
    "visibility": "string",
    "title": "string",
    "page_id": 0,
    "images": [
      {
        "post_id": 0,
        "image": "string"
      }
    ],
    "has_image": true,
    "content": "string",
    "comments": [
      {
        "post_id": 0,
        "content": "string",
        "author_id": 0
      }
    ]
  }
]
```
<h3 id="Unified.V1.PostController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Posts](#schemaposts)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Contact

## Unified.V1.ContactController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/contacts \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/contacts HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contacts',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contacts',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/contacts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/contacts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contacts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/contacts`

Create a new contact for the current user

<h3 id="Unified.V1.ContactController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
first_name|form_data|string|true|Contact's first name
last_name|form_data|string|true|Contact's last name
company|form_data|string|false|Company the contact represents
position|form_data|string|false|Contact's position with company
description|form_data|string|false|Contact's job description
is_customer|form_data|boolean|false|Is this a customer?
emails_json|form_data|array|true|Array of emails for contact
phone_numbers_json|form_data|array|false|Array of phone numbers for contact
addresses_json|form_data|array|false|Array of addresses for contact
from_webhook_id|form_data|integer|false|Webhook ID for ContextIO
to_webook_id|form_data|integer|false|Webhook ID for ContextIO
created_by_user_id|form_data|integer|true|ID of the user that created the contacts
contact_user_id|form_data|integer|false|ID of contact on the platform


> Example responses

```json
[
  {
    "to_webook_id": "string",
    "position": "string",
    "pipeline_reminder_date": null,
    "pipeline_reminder": 0,
    "pipeline_custom": true,
    "pipeline_assignee": "string",
    "pipeline": "string",
    "phone_numbers_json": null,
    "last_name": "string",
    "is_customer": true,
    "from_webhook_id": "string",
    "first_name": "string",
    "emails_json": null,
    "description": "string",
    "created_by_user_id": 0,
    "contact_user_id": 0,
    "company": "string",
    "addresses_json": null
  }
]
```
<h3 id="Unified.V1.ContactController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Contacts](#schemacontacts)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/contacts \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/contacts HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contacts',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contacts',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/contacts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/contacts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contacts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/contacts`

Lists all contacts for a given user. User is determined by CurrentUser plug

> Example responses

```json
[
  {
    "to_webook_id": "string",
    "position": "string",
    "pipeline_reminder_date": null,
    "pipeline_reminder": 0,
    "pipeline_custom": true,
    "pipeline_assignee": "string",
    "pipeline": "string",
    "phone_numbers_json": null,
    "last_name": "string",
    "is_customer": true,
    "from_webhook_id": "string",
    "first_name": "string",
    "emails_json": null,
    "description": "string",
    "created_by_user_id": 0,
    "contact_user_id": 0,
    "company": "string",
    "addresses_json": null
  }
]
```
<h3 id="Unified.V1.ContactController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created|[Contacts](#schemacontacts)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactController.update

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/contacts/{id} \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/contacts/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contacts/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contacts/{id}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/contacts/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/contacts/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contacts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/contacts/{id}`

Update (return) a contact

<h3 id="Unified.V1.ContactController.update-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|The ID of the Contact to be updated
first_name|form_data|string|false|Contact's first name
last_name|form_data|string|false|Contact's last name
company|form_data|string|false|Company the contact represents
position|form_data|string|false|Contact's position with company
description|form_data|string|false|Contact's job description
is_customer|form_data|boolean|false|Is this a customer?
emails_json|form_data|array|false|Array of emails for contact
phone_numbers_json|form_data|array|false|Array of phone numbers for contact
addresses_json|form_data|array|false|Array of addresses for contact
from_webhook_id|form_data|integer|false|Webhook ID for ContextIO
to_webook_id|form_data|integer|false|Webhook ID for ContextIO
created_by_user_id|form_data|integer|false|ID of the user that created the contacts
contact_user_id|form_data|integer|false|ID of contact on the platform


> Example responses

```json
{
  "to_webook_id": "string",
  "position": "string",
  "pipeline_reminder_date": null,
  "pipeline_reminder": 0,
  "pipeline_custom": true,
  "pipeline_assignee": "string",
  "pipeline": "string",
  "phone_numbers_json": null,
  "last_name": "string",
  "is_customer": true,
  "from_webhook_id": "string",
  "first_name": "string",
  "emails_json": null,
  "description": "string",
  "created_by_user_id": 0,
  "contact_user_id": 0,
  "company": "string",
  "addresses_json": null
}
```
<h3 id="Unified.V1.ContactController.update-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Contact](#schemacontact)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/contacts/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/contacts/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contacts/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contacts/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/contacts/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/contacts/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contacts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/contacts/{id}`

Display (return) a contact

<h3 id="Unified.V1.ContactController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|The ID of the contact


> Example responses

```json
{
  "to_webook_id": "string",
  "position": "string",
  "pipeline_reminder_date": null,
  "pipeline_reminder": 0,
  "pipeline_custom": true,
  "pipeline_assignee": "string",
  "pipeline": "string",
  "phone_numbers_json": null,
  "last_name": "string",
  "is_customer": true,
  "from_webhook_id": "string",
  "first_name": "string",
  "emails_json": null,
  "description": "string",
  "created_by_user_id": 0,
  "contact_user_id": 0,
  "company": "string",
  "addresses_json": null
}
```
<h3 id="Unified.V1.ContactController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Contact](#schemacontact)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/contacts/{id}

```

```http
DELETE http://localhost:4000/api/v1/contacts/{id} HTTP/1.1
Host: localhost:4000


```

```javascript

$.ajax({
  url: 'http://localhost:4000/api/v1/contacts/{id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:4000/api/v1/contacts/{id}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'http://localhost:4000/api/v1/contacts/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('http://localhost:4000/api/v1/contacts/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contacts/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/contacts/{id}`

Delete a contact

<h3 id="Unified.V1.ContactController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of contact to be deleted


<h3 id="Unified.V1.ContactController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# SavedProduct

## Unified.V1.SavedProductController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/users/{user_id}/saved_products \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/users/{user_id}/saved_products HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{user_id}/saved_products',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{user_id}/saved_products',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/users/{user_id}/saved_products',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/users/{user_id}/saved_products', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{user_id}/saved_products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/users/{user_id}/saved_products`

Creates or shows a user's saved product based on a product on the platform

<h3 id="Unified.V1.SavedProductController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|A user's ID on the platform
product_id|form_data|integer|true|The database ID of the selected product


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.SavedProductController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Product](#schemaproduct)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Uprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.SavedProductController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/users/{user_id}/saved_products

```

```http
GET http://localhost:4000/api/v1/users/{user_id}/saved_products HTTP/1.1
Host: localhost:4000


```

```javascript

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{user_id}/saved_products',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:4000/api/v1/users/{user_id}/saved_products',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:4000/api/v1/users/{user_id}/saved_products',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('http://localhost:4000/api/v1/users/{user_id}/saved_products', params={

)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{user_id}/saved_products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/users/{user_id}/saved_products`

gets all of a user's saved products

<h3 id="Unified.V1.SavedProductController.index-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|A user's ID on the platform


<h3 id="Unified.V1.SavedProductController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.SavedProductController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/users/{user_id}/saved_products/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/users/{user_id}/saved_products/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/users/{user_id}/saved_products/{id}`

Shows a user's previously saved product

<h3 id="Unified.V1.SavedProductController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|A user's ID on the platform
id|path|integer|true|The database ID of the selected saved product


> Example responses

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```
<h3 id="Unified.V1.SavedProductController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Product](#schemaproduct)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.SavedProductController.delete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:4000/api/v1/users/{user_id}/saved_products/{id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:4000/api/v1/users/{user_id}/saved_products/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/users/{user_id}/saved_products/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /api/v1/users/{user_id}/saved_products/{id}`

Deletes a user's previously saved product, and returns the remaining saved products

<h3 id="Unified.V1.SavedProductController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
user_id|path|integer|true|A user's ID on the platform
id|path|integer|true|The database ID of the selected saved product


> Example responses

```json
[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]
```
<h3 id="Unified.V1.SavedProductController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Products](#schemaproducts)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Uprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# ContactCommunication

## Unified.V1.ContactCommunicationController.delete

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:4000/api/v1/communications/{id} \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:4000/api/v1/communications/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/communications/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/communications/{id}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:4000/api/v1/communications/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('http://localhost:4000/api/v1/communications/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/communications/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /api/v1/communications/{id}`

Updates a single communication

<h3 id="Unified.V1.ContactCommunicationController.delete-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the contact communication


> Example responses

```json
[
  {
    "user_id": 0,
    "type": "string",
    "note": "string",
    "contact_id": 0,
    "communication_date": null
  }
]
```
<h3 id="Unified.V1.ContactCommunicationController.delete-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|[ContactCommunications](#schemacontactcommunications)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactCommunicationController.show

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/communications/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/communications/{id} HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/communications/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/communications/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/communications/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/communications/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/communications/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/communications/{id}`

Gets a single contact communciation

<h3 id="Unified.V1.ContactCommunicationController.show-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|integer|true|ID of the contact communication


> Example responses

```json
{
  "user_id": 0,
  "type": "string",
  "note": "string",
  "contact_id": 0,
  "communication_date": null
}
```
<h3 id="Unified.V1.ContactCommunicationController.show-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ContactCommunication](#schemacontactcommunication)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactCommunicationController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/communications \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/communications HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/communications',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/communications',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/communications',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/communications', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/communications");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/communications`

Creates a new contact communication for the user

<h3 id="Unified.V1.ContactCommunicationController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
communication_date|form_data|string|true|Date of communication
note|form_data|string|true|Details of the communication
type|form_data|string|true|Communication Type
user_id|form_data|integer|true|ID of the user that made the communication
contact_id|form_data|integer|true|ID of the contact the communication was with


> Example responses

```json
{
  "user_id": 0,
  "type": "string",
  "note": "string",
  "contact_id": 0,
  "communication_date": null
}
```
<h3 id="Unified.V1.ContactCommunicationController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[ContactCommunication](#schemacontactcommunication)
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactCommunicationController.index

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/communications \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/communications HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/communications',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/communications',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/communications',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/communications', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/communications");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/communications`

Gets all contact communications

> Example responses

```json
[
  {
    "user_id": 0,
    "type": "string",
    "note": "string",
    "contact_id": 0,
    "communication_date": null
  }
]
```
<h3 id="Unified.V1.ContactCommunicationController.index-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ContactCommunications](#schemacontactcommunications)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## Unified.V1.ContactCommunicationController.contact_communication

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:4000/api/v1/contacts/{contact_id}/communications \
  -H 'Accept: application/json'

```

```http
GET http://localhost:4000/api/v1/contacts/{contact_id}/communications HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/contacts/{contact_id}/communications',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/contacts/{contact_id}/communications',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:4000/api/v1/contacts/{contact_id}/communications',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:4000/api/v1/contacts/{contact_id}/communications', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/contacts/{contact_id}/communications");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /api/v1/contacts/{contact_id}/communications`

Gets all communications for a single contact

<h3 id="Unified.V1.ContactCommunicationController.contact_communication-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
contact_id|path|integer|true|ID of the contact the communication was with


> Example responses

```json
[
  {
    "user_id": 0,
    "type": "string",
    "note": "string",
    "contact_id": 0,
    "communication_date": null
  }
]
```
<h3 id="Unified.V1.ContactCommunicationController.contact_communication-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ContactCommunications](#schemacontactcommunications)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Registration

## Unified.V1.RegistrationController.create

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/v1/registration \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/v1/registration HTTP/1.1
Host: localhost:4000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:4000/api/v1/registration',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:4000/api/v1/registration',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/v1/registration',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/v1/registration', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:4000/api/v1/registration");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /api/v1/registration`

Creates a user for the unified app

<h3 id="Unified.V1.RegistrationController.create-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
first_name|form_data|string|true|First name of user
last_name|form_data|string|true|Last name of user
company_name|form_data|string|true|First name of user
email|form_data|string|true|Email address for user
password|form_data|string|true|user's chosen password name of user
username|form_data|string|true|User's chosen username
phone_numbers|form_data|string|false|Array of a User's phone numbers


> Example responses

```json
{
  "version": "string",
  "message": "string",
  "errors": "string",
  "entities": {
    "user": {
      "username": "string",
      "is_admin": true,
      "email": "string",
      "discourse_user_id": 0,
      "description": "string",
      "company_name": "string",
      "authToken": "string",
      "active": true
    }
  }
}
```
<h3 id="Unified.V1.RegistrationController.create-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created|[Session](#schemasession)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None
422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Schemas

## ContactGroups

<a name="schemacontactgroups"></a>

```json
[
  {
    "name": "string",
    "created_by_user_id": 0,
    "contacts": [
      {
        "to_webook_id": "string",
        "position": "string",
        "pipeline_reminder_date": null,
        "pipeline_reminder": 0,
        "pipeline_custom": true,
        "pipeline_assignee": "string",
        "pipeline": "string",
        "phone_numbers_json": null,
        "last_name": "string",
        "is_customer": true,
        "from_webhook_id": "string",
        "first_name": "string",
        "emails_json": null,
        "description": "string",
        "created_by_user_id": 0,
        "contact_user_id": 0,
        "company": "string",
        "addresses_json": null
      }
    ]
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[ContactGroup](#schemacontactgroup)]|false|A collection contact groups
» name|string|false|Name of the contact group
» created_by_user_id|integer|false|User Id of the user that created the contact group
» contacts|[[Contact](#schemacontact)]|false|An array of user's contacts
»» to_webook_id|string|false|Webhook ID for ContextIO
»» position|string|false|Contact's position with company
»» pipeline_reminder_date|date|false|Starting date for reminders
»» pipeline_reminder|integer|false|Days between active contact reminders
»» pipeline_custom|boolean|false|Is this a custom pipeline
»» pipeline_assignee|string|false|Who assigned this contact to the pipeline
»» pipeline|string|false|What pipline this contact is in
»» phone_numbers_json|map|false|Map of phone numbers for contact
»» last_name|string|false|Contact's last name
»» is_customer|boolean|false|Is this a customer?
»» from_webhook_id|string|false|Webhook ID for ContextIO
»» first_name|string|false|Contact's first name
»» emails_json|map|false|Map of emails for contact
»» description|string|false|Contact's job description
»» created_by_user_id|integer|false|ID of the user that created the contacts
»» contact_user_id|integer|false|ID of contact on the platform
»» company|string|false|Company the contact represents
»» addresses_json|map|false|Map of addresses for contact



## Addresses

<a name="schemaaddresses"></a>

```json
[
  {
    "zip": "string",
    "type": "string",
    "state": "string",
    "line_2": "string",
    "line_1": "string",
    "label": "string",
    "city": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Address](#schemaaddress)]|false|A collection of orders
» zip|string|false|Zip Code
» type|string|false|Type of address Billing, Shipping, etc...
» state|string|false|Abbreviated state
» line_2|string|false|Second Line of an address
» line_1|string|false|First line of an address
» label|string|false|Label for the address
» city|string|false|City abbreviation



## Contact

<a name="schemacontact"></a>

```json
{
  "to_webook_id": "string",
  "position": "string",
  "pipeline_reminder_date": null,
  "pipeline_reminder": 0,
  "pipeline_custom": true,
  "pipeline_assignee": "string",
  "pipeline": "string",
  "phone_numbers_json": null,
  "last_name": "string",
  "is_customer": true,
  "from_webhook_id": "string",
  "first_name": "string",
  "emails_json": null,
  "description": "string",
  "created_by_user_id": 0,
  "contact_user_id": 0,
  "company": "string",
  "addresses_json": null
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
to_webook_id|string|false|Webhook ID for ContextIO
position|string|false|Contact's position with company
pipeline_reminder_date|date|false|Starting date for reminders
pipeline_reminder|integer|false|Days between active contact reminders
pipeline_custom|boolean|false|Is this a custom pipeline
pipeline_assignee|string|false|Who assigned this contact to the pipeline
pipeline|string|false|What pipline this contact is in
phone_numbers_json|map|false|Map of phone numbers for contact
last_name|string|false|Contact's last name
is_customer|boolean|false|Is this a customer?
from_webhook_id|string|false|Webhook ID for ContextIO
first_name|string|false|Contact's first name
emails_json|map|false|Map of emails for contact
description|string|false|Contact's job description
created_by_user_id|integer|false|ID of the user that created the contacts
contact_user_id|integer|false|ID of contact on the platform
company|string|false|Company the contact represents
addresses_json|map|false|Map of addresses for contact



## ContactCommunication

<a name="schemacontactcommunication"></a>

```json
{
  "user_id": 0,
  "type": "string",
  "note": "string",
  "contact_id": 0,
  "communication_date": null
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user_id|integer|false|ID of the user that made the communication
type|string|false|Communication Type
note|string|false|Details of the communication
contact_id|integer|false|ID of the contact the communication was with
communication_date|date|false|Date of communication



## CommunicationSettings

<a name="schemacommunicationsettings"></a>

```json
[
  {
    "threshold_json": null,
    "threshold_enabled": true
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[CommunicationSetting](#schemacommunicationsetting)]|false|A collection of a User's communication settings
» threshold_json|map|false|Values for threshold
» threshold_enabled|boolean|false|if thresholds have been enabled



## ConversationMembership

<a name="schemaconversationmembership"></a>

```json
{
  "user_id": 0,
  "conversation_id": 0
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user_id|integer|false|User that owns the conversation membership
conversation_id|integer|false|Conversation ID that memebership belongs to



## Leaderboard

<a name="schemaleaderboard"></a>

```json
[
  {
    "rank": 0,
    "points": 0,
    "member": {
      "organization_name": "string",
      "last_name": "string",
      "first_name": "string",
      "description": "string",
      "avatar": "string"
    }
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[LeaderboardUser](#schemaleaderboarduser)]|false|Rankings and User information organized by points scored
» rank|integer|false|The User's rank in the leaderboard
» points|integer|false|Points a user has scored
» member|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
»» organization_name|string|false|The User's company name
»» last_name|string|false|The User's last name
»» first_name|string|false|The User's first name
»» description|string|false|The User's job description
»» avatar|string|false|filename of the user's persisted avatar



## Broker

<a name="schemabroker"></a>

```json
{
  "links": {
    "self": "string"
  },
  "included": [
    null
  ],
  "data": {
    "type": "string",
    "relationships": {},
    "links": {},
    "id": "string",
    "attributes": {
      "status": "string",
      "owner": "string",
      "company": "string"
    }
  }
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
links|object|false|No description
» self|string|false|the link that generated the current response document.
data|[BrokerResource](#schemabrokerresource)|true|A user's contact group
» type|string|false|The JSON-API resource type
» relationships|object|false|No description
» links|object|false|No description
» id|string|false|The JSON-API resource ID
» attributes|object|false|No description
»» status|string|false|The status of the broker
»» owner|string|false|The name of the broker owner
»» company|string|false|The Broker Company name
included|[Unknown]|false|Included resources



## Rankings

<a name="schemarankings"></a>

```json
[
  {
    "rank": 0,
    "points": 0,
    "category": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Ranking](#schemaranking)]|false|A collection of Rankings for points categories
» rank|integer|false|The user's ranking
» points|integer|false|Points a user has accumulated in a category
» category|string|false|The category a user has scored points in



## Products

<a name="schemaproducts"></a>

```json
[
  {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Product](#schemaproduct)]|false|A collection of Products
» upc|string|false|upc code for product
» uom|string|false|How product is measured
» status|string|false|product status
» slug|string|false|Product category Identifier
» sku|string|false|Manufacturer unique product identifier
» qty_avail|integer|false|Amount in stock at this moment
» name|string|false|Name of the Product
» discontinue_on|string(ISO-8601)|false|Date to discontinue
» description|string|false|Product description 255 character limit
» case_qty|integer|false|How many products in one unit
» base_price|decimal|false|base price for product
» available_on|string(ISO-8601)|false|Date made available



## Messages

<a name="schemamessages"></a>

```json
[
  {
    "user_id": 0,
    "conversation_id": 0,
    "body": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Message](#schemamessage)]|false|A collection of Messages
» user_id|integer|false|ID of the user that sent the message
» conversation_id|integer|false|Conversation ID that message belongs to
» body|string|false|The message's message



## GameResult

<a name="schemagameresult"></a>

```json
{
  "user_id": 0,
  "points": 0,
  "organization_name": "string",
  "last_name": "string",
  "first_name": "string",
  "category": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user_id|integer|false|ID of the game participant on the unified platform
points|integer|false|Points a user has accumulated in a category
organization_name|string|false|Name of the game participants organization
last_name|string|false|Last name of the game participant
first_name|string|false|First name of the game participant
category|string|false|The category a user has scored points in



## OrderItems

<a name="schemaorderitems"></a>

```json
[
  {
    "sku": "string",
    "quantity": 0,
    "price": null,
    "name": "string",
    "description": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[OrderItem](#schemaorderitem)]|false|A collection of Order Items
» sku|string|false|Product SKU
» quantity|integer|false|Prouct quantity
» price|decimal|false|Product Price
» name|string|false|Name of the Product on an order
» description|string|false|product description



## Users

<a name="schemausers"></a>

```json
[
  {
    "username": "string",
    "user_profile": {
      "organization_name": "string",
      "last_name": "string",
      "first_name": "string",
      "description": "string",
      "avatar": "string"
    },
    "is_admin": true,
    "email": "string",
    "discourse_user_id": 0,
    "discourse_api_key": "string",
    "description": "string",
    "company_name": "string",
    "active": true
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[User](#schemauser)]|false|A collection of Users
» username|string|false|The selected username for the user
» user_profile|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
»» organization_name|string|false|The User's company name
»» last_name|string|false|The User's last name
»» first_name|string|false|The User's first name
»» description|string|false|The User's job description
»» avatar|string|false|filename of the user's persisted avatar
» is_admin|boolean|false|Whether or not this user has admin permissions
» email|string|false|The given email for the user
» discourse_user_id|integer|false|The community generated user_id for the user
» discourse_api_key|string|false|The community generated apiKey for the user
» description|string|false|The job title of the user
» company_name|string|false|The name of the company this user represents
» active|boolean|false|Whether or not this user is active



## LeaderboardUser

<a name="schemaleaderboarduser"></a>

```json
{
  "rank": 0,
  "points": 0,
  "member": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  }
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rank|integer|false|The User's rank in the leaderboard
points|integer|false|Points a user has scored
member|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
» organization_name|string|false|The User's company name
» last_name|string|false|The User's last name
» first_name|string|false|The User's first name
» description|string|false|The User's job description
» avatar|string|false|filename of the user's persisted avatar



## Comments

<a name="schemacomments"></a>

```json
[
  {
    "post_id": 0,
    "content": "string",
    "author_id": 0
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Comment](#schemacomment)]|false|A collection of user comments
» post_id|integer|false|The id of the associated post
» content|string|false|The Comment content
» author_id|integer|false|The id of the user



## ContactCommunications

<a name="schemacontactcommunications"></a>

```json
[
  {
    "user_id": 0,
    "type": "string",
    "note": "string",
    "contact_id": 0,
    "communication_date": null
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[ContactCommunication](#schemacontactcommunication)]|false|A collection of contact communications
» user_id|integer|false|ID of the user that made the communication
» type|string|false|Communication Type
» note|string|false|Details of the communication
» contact_id|integer|false|ID of the contact the communication was with
» communication_date|date|false|Date of communication



## Orders

<a name="schemaorders"></a>

```json
[
  {
    "total": null,
    "state": "string",
    "slug": "string",
    "saved": true,
    "product_total": null,
    "order_state": "string",
    "order_items": [
      {
        "sku": "string",
        "quantity": 0,
        "price": null,
        "name": "string",
        "description": "string"
      }
    ],
    "deleted": true,
    "confirmation_status": true,
    "active": true
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Order](#schemaorder)]|false|A collection of orders
» total|decimal|false|Total amount for the order
» state|string|false|state of the order(Unused)
» slug|string|false|Name for the order for saving
» saved|boolean|false|if a user wants to save a particular order
» product_total|decimal|false|The amount of individual products on the order
» order_state|string|false|State of the order
» deleted|boolean|false|If a user no longer wants to reference an order
» confirmation_status|boolean|false|If the customer actually want's this order
» active|boolean|false|If this the user's currently active order
» order_items|[[OrderItem](#schemaorderitem)]|false|A collection of Order Items
»» sku|string|false|Product SKU
»» quantity|integer|false|Prouct quantity
»» price|decimal|false|Product Price
»» name|string|false|Name of the Product on an order
»» description|string|false|product description



## OrderItem

<a name="schemaorderitem"></a>

```json
{
  "sku": "string",
  "quantity": 0,
  "price": null,
  "name": "string",
  "description": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
sku|string|false|Product SKU
quantity|integer|false|Prouct quantity
price|decimal|false|Product Price
name|string|false|Name of the Product on an order
description|string|false|product description



## PostImages

<a name="schemapostimages"></a>

```json
[
  {
    "post_id": 0,
    "image": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[PostImage](#schemapostimage)]|false|A collection of Post Images
» post_id|integer|false|ID of the post the image belongs to
» image|string|false|The persisted filname of the image



## GameResults

<a name="schemagameresults"></a>

```json
[
  {
    "user_id": 0,
    "points": 0,
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "category": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[GameResult](#schemagameresult)]|false|A collection of Game Results
» user_id|integer|false|ID of the game participant on the unified platform
» points|integer|false|Points a user has accumulated in a category
» organization_name|string|false|Name of the game participants organization
» last_name|string|false|Last name of the game participant
» first_name|string|false|First name of the game participant
» category|string|false|The category a user has scored points in



## Invoice

<a name="schemainvoice"></a>

```json
{
  "total": null,
  "items": [
    {
      "sku": "string",
      "quantity": "string",
      "price": null,
      "description": "string"
    }
  ]
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
total|decimal|false|The Invoice total
items|[[InvoiceItem](#schemainvoiceitem)]|false|A collection of Invoice Items
» sku|string|false|The unique identification number
» quantity|string|false|The amount purchased
» price|decimal|false|The item's cost
» description|string|false|The description of the product purchased



## Conversations

<a name="schemaconversations"></a>

```json
[
  {
    "users": [
      {
        "username": "string",
        "user_profile": {
          "organization_name": "string",
          "last_name": "string",
          "first_name": "string",
          "description": "string",
          "avatar": "string"
        },
        "is_admin": true,
        "email": "string",
        "discourse_user_id": 0,
        "discourse_api_key": "string",
        "description": "string",
        "company_name": "string",
        "active": true
      }
    ],
    "messages": [
      {
        "user_id": 0,
        "conversation_id": 0,
        "body": "string"
      }
    ],
    "id": 0,
    "converation_memberships": [
      {
        "user_id": 0,
        "conversation_id": 0
      }
    ]
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Conversation](#schemaconversation)]|false|A collection of conversations
» id|integer|false|Conversation ID
» users|[[User](#schemauser)]|false|A collection of Users
»» username|string|false|The selected username for the user
»» user_profile|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
»»» organization_name|string|false|The User's company name
»»» last_name|string|false|The User's last name
»»» first_name|string|false|The User's first name
»»» description|string|false|The User's job description
»»» avatar|string|false|filename of the user's persisted avatar
»» is_admin|boolean|false|Whether or not this user has admin permissions
»» email|string|false|The given email for the user
»» discourse_user_id|integer|false|The community generated user_id for the user
»» discourse_api_key|string|false|The community generated apiKey for the user
»» description|string|false|The job title of the user
»» company_name|string|false|The name of the company this user represents
»» active|boolean|false|Whether or not this user is active
» messages|[[Message](#schemamessage)]|false|A collection of Messages
»» user_id|integer|false|ID of the user that sent the message
»» conversation_id|integer|false|Conversation ID that message belongs to
»» body|string|false|The message's message
» converation_memberships|[[ConversationMembership](#schemaconversationmembership)]|false|A collection of conversation memberships
»» user_id|integer|false|User that owns the conversation membership
»» conversation_id|integer|false|Conversation ID that memebership belongs to



## Order

<a name="schemaorder"></a>

```json
{
  "total": null,
  "state": "string",
  "slug": "string",
  "saved": true,
  "product_total": null,
  "order_state": "string",
  "order_items": [
    {
      "sku": "string",
      "quantity": 0,
      "price": null,
      "name": "string",
      "description": "string"
    }
  ],
  "deleted": true,
  "confirmation_status": true,
  "active": true
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
total|decimal|false|Total amount for the order
state|string|false|state of the order(Unused)
slug|string|false|Name for the order for saving
saved|boolean|false|if a user wants to save a particular order
product_total|decimal|false|The amount of individual products on the order
order_state|string|false|State of the order
deleted|boolean|false|If a user no longer wants to reference an order
confirmation_status|boolean|false|If the customer actually want's this order
active|boolean|false|If this the user's currently active order
order_items|[[OrderItem](#schemaorderitem)]|false|A collection of Order Items
» sku|string|false|Product SKU
» quantity|integer|false|Prouct quantity
» price|decimal|false|Product Price
» name|string|false|Name of the Product on an order
» description|string|false|product description



## BrokerResource

<a name="schemabrokerresource"></a>

```json
{
  "type": "string",
  "relationships": {},
  "links": {},
  "id": "string",
  "attributes": {
    "status": "string",
    "owner": "string",
    "company": "string"
  }
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|string|false|The JSON-API resource type
relationships|object|false|No description
links|object|false|No description
id|string|false|The JSON-API resource ID
attributes|object|false|No description
» status|string|false|The status of the broker
» owner|string|false|The name of the broker owner
» company|string|false|The Broker Company name



## Pipelines

<a name="schemapipelines"></a>

```json
{
  "pipeline": {
    "user_id": 0,
    "hot_reminder": 0,
    "hot_date": "string",
    "cold_reminder": 0,
    "cold_date": "string"
  },
  "hot": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ],
  "custom": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ],
  "cold": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ],
  "closed": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
pipeline|[Pipeline](#schemapipeline)|false|A user's contact Pipeline
» user_id|integer|false|The owner's ID
» hot_reminder|integer|false|Days in between reminders for hot contacts
» hot_date|string(ISO-8601)|false|Reminder date for the contacts listed as hot
» cold_reminder|integer|false|Days in between reminders for cold contacts
» cold_date|string(ISO-8601)|false|Reminder date for the contacts listed as cold
hot|[[Contact](#schemacontact)]|false|An array of user's contacts
» to_webook_id|string|false|Webhook ID for ContextIO
» position|string|false|Contact's position with company
» pipeline_reminder_date|date|false|Starting date for reminders
» pipeline_reminder|integer|false|Days between active contact reminders
» pipeline_custom|boolean|false|Is this a custom pipeline
» pipeline_assignee|string|false|Who assigned this contact to the pipeline
» pipeline|string|false|What pipline this contact is in
» phone_numbers_json|map|false|Map of phone numbers for contact
» last_name|string|false|Contact's last name
» is_customer|boolean|false|Is this a customer?
» from_webhook_id|string|false|Webhook ID for ContextIO
» first_name|string|false|Contact's first name
» emails_json|map|false|Map of emails for contact
» description|string|false|Contact's job description
» created_by_user_id|integer|false|ID of the user that created the contacts
» contact_user_id|integer|false|ID of contact on the platform
» company|string|false|Company the contact represents
» addresses_json|map|false|Map of addresses for contact
custom|[[Contact](#schemacontact)]|false|An array of user's contacts
» to_webook_id|string|false|Webhook ID for ContextIO
» position|string|false|Contact's position with company
» pipeline_reminder_date|date|false|Starting date for reminders
» pipeline_reminder|integer|false|Days between active contact reminders
» pipeline_custom|boolean|false|Is this a custom pipeline
» pipeline_assignee|string|false|Who assigned this contact to the pipeline
» pipeline|string|false|What pipline this contact is in
» phone_numbers_json|map|false|Map of phone numbers for contact
» last_name|string|false|Contact's last name
» is_customer|boolean|false|Is this a customer?
» from_webhook_id|string|false|Webhook ID for ContextIO
» first_name|string|false|Contact's first name
» emails_json|map|false|Map of emails for contact
» description|string|false|Contact's job description
» created_by_user_id|integer|false|ID of the user that created the contacts
» contact_user_id|integer|false|ID of contact on the platform
» company|string|false|Company the contact represents
» addresses_json|map|false|Map of addresses for contact
cold|[[Contact](#schemacontact)]|false|An array of user's contacts
» to_webook_id|string|false|Webhook ID for ContextIO
» position|string|false|Contact's position with company
» pipeline_reminder_date|date|false|Starting date for reminders
» pipeline_reminder|integer|false|Days between active contact reminders
» pipeline_custom|boolean|false|Is this a custom pipeline
» pipeline_assignee|string|false|Who assigned this contact to the pipeline
» pipeline|string|false|What pipline this contact is in
» phone_numbers_json|map|false|Map of phone numbers for contact
» last_name|string|false|Contact's last name
» is_customer|boolean|false|Is this a customer?
» from_webhook_id|string|false|Webhook ID for ContextIO
» first_name|string|false|Contact's first name
» emails_json|map|false|Map of emails for contact
» description|string|false|Contact's job description
» created_by_user_id|integer|false|ID of the user that created the contacts
» contact_user_id|integer|false|ID of contact on the platform
» company|string|false|Company the contact represents
» addresses_json|map|false|Map of addresses for contact
closed|[[Contact](#schemacontact)]|false|An array of user's contacts
» to_webook_id|string|false|Webhook ID for ContextIO
» position|string|false|Contact's position with company
» pipeline_reminder_date|date|false|Starting date for reminders
» pipeline_reminder|integer|false|Days between active contact reminders
» pipeline_custom|boolean|false|Is this a custom pipeline
» pipeline_assignee|string|false|Who assigned this contact to the pipeline
» pipeline|string|false|What pipline this contact is in
» phone_numbers_json|map|false|Map of phone numbers for contact
» last_name|string|false|Contact's last name
» is_customer|boolean|false|Is this a customer?
» from_webhook_id|string|false|Webhook ID for ContextIO
» first_name|string|false|Contact's first name
» emails_json|map|false|Map of emails for contact
» description|string|false|Contact's job description
» created_by_user_id|integer|false|ID of the user that created the contacts
» contact_user_id|integer|false|ID of contact on the platform
» company|string|false|Company the contact represents
» addresses_json|map|false|Map of addresses for contact



## UserProfile

<a name="schemauserprofile"></a>

```json
{
  "organization_name": "string",
  "last_name": "string",
  "first_name": "string",
  "description": "string",
  "avatar": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
organization_name|string|false|The User's company name
last_name|string|false|The User's last name
first_name|string|false|The User's first name
description|string|false|The User's job description
avatar|string|false|filename of the user's persisted avatar



## Conversation

<a name="schemaconversation"></a>

```json
{
  "users": [
    {
      "username": "string",
      "user_profile": {
        "organization_name": "string",
        "last_name": "string",
        "first_name": "string",
        "description": "string",
        "avatar": "string"
      },
      "is_admin": true,
      "email": "string",
      "discourse_user_id": 0,
      "discourse_api_key": "string",
      "description": "string",
      "company_name": "string",
      "active": true
    }
  ],
  "messages": [
    {
      "user_id": 0,
      "conversation_id": 0,
      "body": "string"
    }
  ],
  "id": 0,
  "converation_memberships": [
    {
      "user_id": 0,
      "conversation_id": 0
    }
  ]
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|integer|false|Conversation ID
users|[[User](#schemauser)]|false|A collection of Users
» username|string|false|The selected username for the user
» user_profile|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
»» organization_name|string|false|The User's company name
»» last_name|string|false|The User's last name
»» first_name|string|false|The User's first name
»» description|string|false|The User's job description
»» avatar|string|false|filename of the user's persisted avatar
» is_admin|boolean|false|Whether or not this user has admin permissions
» email|string|false|The given email for the user
» discourse_user_id|integer|false|The community generated user_id for the user
» discourse_api_key|string|false|The community generated apiKey for the user
» description|string|false|The job title of the user
» company_name|string|false|The name of the company this user represents
» active|boolean|false|Whether or not this user is active
messages|[[Message](#schemamessage)]|false|A collection of Messages
» user_id|integer|false|ID of the user that sent the message
» conversation_id|integer|false|Conversation ID that message belongs to
» body|string|false|The message's message
converation_memberships|[[ConversationMembership](#schemaconversationmembership)]|false|A collection of conversation memberships
» user_id|integer|false|User that owns the conversation membership
» conversation_id|integer|false|Conversation ID that memebership belongs to



## InvoiceItem

<a name="schemainvoiceitem"></a>

```json
{
  "sku": "string",
  "quantity": "string",
  "price": null,
  "description": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
sku|string|false|The unique identification number
quantity|string|false|The amount purchased
price|decimal|false|The item's cost
description|string|false|The description of the product purchased



## Contacts

<a name="schemacontacts"></a>

```json
[
  {
    "to_webook_id": "string",
    "position": "string",
    "pipeline_reminder_date": null,
    "pipeline_reminder": 0,
    "pipeline_custom": true,
    "pipeline_assignee": "string",
    "pipeline": "string",
    "phone_numbers_json": null,
    "last_name": "string",
    "is_customer": true,
    "from_webhook_id": "string",
    "first_name": "string",
    "emails_json": null,
    "description": "string",
    "created_by_user_id": 0,
    "contact_user_id": 0,
    "company": "string",
    "addresses_json": null
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Contact](#schemacontact)]|false|An array of user's contacts
» to_webook_id|string|false|Webhook ID for ContextIO
» position|string|false|Contact's position with company
» pipeline_reminder_date|date|false|Starting date for reminders
» pipeline_reminder|integer|false|Days between active contact reminders
» pipeline_custom|boolean|false|Is this a custom pipeline
» pipeline_assignee|string|false|Who assigned this contact to the pipeline
» pipeline|string|false|What pipline this contact is in
» phone_numbers_json|map|false|Map of phone numbers for contact
» last_name|string|false|Contact's last name
» is_customer|boolean|false|Is this a customer?
» from_webhook_id|string|false|Webhook ID for ContextIO
» first_name|string|false|Contact's first name
» emails_json|map|false|Map of emails for contact
» description|string|false|Contact's job description
» created_by_user_id|integer|false|ID of the user that created the contacts
» contact_user_id|integer|false|ID of contact on the platform
» company|string|false|Company the contact represents
» addresses_json|map|false|Map of addresses for contact



## GameResultUser

<a name="schemagameresultuser"></a>

```json
{
  "user_id": 0,
  "rankings": [
    {
      "rank": 0,
      "points": 0,
      "category": "string"
    }
  ],
  "organization_name": "string",
  "last_name": "string",
  "first_name": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user_id|integer|false|ID of the game participant on the unified platform
organization_name|string|false|Name of the game participants organization
last_name|string|false|Last name of the game participant
first_name|string|false|First name of the game participant
rankings|[[Ranking](#schemaranking)]|false|A collection of Rankings for points categories
» rank|integer|false|The user's ranking
» points|integer|false|Points a user has accumulated in a category
» category|string|false|The category a user has scored points in



## User

<a name="schemauser"></a>

```json
{
  "username": "string",
  "user_profile": {
    "organization_name": "string",
    "last_name": "string",
    "first_name": "string",
    "description": "string",
    "avatar": "string"
  },
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "discourse_api_key": "string",
  "description": "string",
  "company_name": "string",
  "active": true
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
username|string|false|The selected username for the user
user_profile|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
» organization_name|string|false|The User's company name
» last_name|string|false|The User's last name
» first_name|string|false|The User's first name
» description|string|false|The User's job description
» avatar|string|false|filename of the user's persisted avatar
is_admin|boolean|false|Whether or not this user has admin permissions
email|string|false|The given email for the user
discourse_user_id|integer|false|The community generated user_id for the user
discourse_api_key|string|false|The community generated apiKey for the user
description|string|false|The job title of the user
company_name|string|false|The name of the company this user represents
active|boolean|false|Whether or not this user is active



## Product

<a name="schemaproduct"></a>

```json
{
  "upc": "string",
  "uom": "string",
  "status": "string",
  "slug": "string",
  "sku": "string",
  "qty_avail": 0,
  "name": "string",
  "discontinue_on": "string",
  "description": "string",
  "case_qty": 0,
  "base_price": null,
  "available_on": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
upc|string|false|upc code for product
uom|string|false|How product is measured
status|string|false|product status
slug|string|false|Product category Identifier
sku|string|false|Manufacturer unique product identifier
qty_avail|integer|false|Amount in stock at this moment
name|string|false|Name of the Product
discontinue_on|string(ISO-8601)|false|Date to discontinue
description|string|false|Product description 255 character limit
case_qty|integer|false|How many products in one unit
base_price|decimal|false|base price for product
available_on|string(ISO-8601)|false|Date made available



## SessionUser

<a name="schemasessionuser"></a>

```json
{
  "username": "string",
  "is_admin": true,
  "email": "string",
  "discourse_user_id": 0,
  "description": "string",
  "company_name": "string",
  "authToken": "string",
  "active": true
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
username|string|false|The selected username for the user
is_admin|boolean|false|Whether or not this user has admin permissions
email|string|false|The given email for the user
discourse_user_id|integer|false|The community generated user_id for the user
description|string|false|The job title of the user
company_name|string|false|The name of the company this user represents
authToken|string|false|JSON Web Token issued to user to be used in the "Authorization" header
active|boolean|false|Whether or not this user is active



## SavedProducts

<a name="schemasavedproducts"></a>

```json
[
  {
    "user": {
      "username": "string",
      "user_profile": {
        "organization_name": "string",
        "last_name": "string",
        "first_name": "string",
        "description": "string",
        "avatar": "string"
      },
      "is_admin": true,
      "email": "string",
      "discourse_user_id": 0,
      "discourse_api_key": "string",
      "description": "string",
      "company_name": "string",
      "active": true
    },
    "product": {
      "upc": "string",
      "uom": "string",
      "status": "string",
      "slug": "string",
      "sku": "string",
      "qty_avail": 0,
      "name": "string",
      "discontinue_on": "string",
      "description": "string",
      "case_qty": 0,
      "base_price": null,
      "available_on": "string"
    },
    "date_saved": null
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[SavedProduct](#schemasavedproduct)]|false|A collection of Products
» user|[User](#schemauser)|false|A user of the Unfied App, may be a broker, retailer, or vendor rep
»» username|string|false|The selected username for the user
»» user_profile|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
»»» organization_name|string|false|The User's company name
»»» last_name|string|false|The User's last name
»»» first_name|string|false|The User's first name
»»» description|string|false|The User's job description
»»» avatar|string|false|filename of the user's persisted avatar
»» is_admin|boolean|false|Whether or not this user has admin permissions
»» email|string|false|The given email for the user
»» discourse_user_id|integer|false|The community generated user_id for the user
»» discourse_api_key|string|false|The community generated apiKey for the user
»» description|string|false|The job title of the user
»» company_name|string|false|The name of the company this user represents
»» active|boolean|false|Whether or not this user is active
» product|[Product](#schemaproduct)|false|A product made by a manufacturer
»» upc|string|false|upc code for product
»» uom|string|false|How product is measured
»» status|string|false|product status
»» slug|string|false|Product category Identifier
»» sku|string|false|Manufacturer unique product identifier
»» qty_avail|integer|false|Amount in stock at this moment
»» name|string|false|Name of the Product
»» discontinue_on|string(ISO-8601)|false|Date to discontinue
»» description|string|false|Product description 255 character limit
»» case_qty|integer|false|How many products in one unit
»» base_price|decimal|false|base price for product
»» available_on|string(ISO-8601)|false|Date made available
» date_saved|date|false|Date product was saved for later viewing



## Emails

<a name="schemaemails"></a>

```json
[
  {
    "status": 0,
    "connect_token_used": 0,
    "connect_token_token": "string",
    "connect_token_expires": 0,
    "connect_token_browser_redirect_url": "string",
    "account_suspended": "string",
    "account_created": "string",
    "account_account": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Email](#schemaemail)]|false|A collection of emails accounts
» status|integer|false|The number status representing the contact time
» connect_token_used|integer|false|If token is used, represented by number
» connect_token_token|string|false|connect token for contextio
» connect_token_expires|integer|false|Token expiration
» connect_token_browser_redirect_url|string|false|redirect for contextio browser
» account_suspended|string(ISO-8601)|false|When the account is suspended if applicable
» account_created|string(ISO-8601)|false|When the account was created
» account_account|string|false|The account for email



## ContactGroup

<a name="schemacontactgroup"></a>

```json
{
  "name": "string",
  "created_by_user_id": 0,
  "contacts": [
    {
      "to_webook_id": "string",
      "position": "string",
      "pipeline_reminder_date": null,
      "pipeline_reminder": 0,
      "pipeline_custom": true,
      "pipeline_assignee": "string",
      "pipeline": "string",
      "phone_numbers_json": null,
      "last_name": "string",
      "is_customer": true,
      "from_webhook_id": "string",
      "first_name": "string",
      "emails_json": null,
      "description": "string",
      "created_by_user_id": 0,
      "contact_user_id": 0,
      "company": "string",
      "addresses_json": null
    }
  ]
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|Name of the contact group
created_by_user_id|integer|false|User Id of the user that created the contact group
contacts|[[Contact](#schemacontact)]|false|An array of user's contacts
» to_webook_id|string|false|Webhook ID for ContextIO
» position|string|false|Contact's position with company
» pipeline_reminder_date|date|false|Starting date for reminders
» pipeline_reminder|integer|false|Days between active contact reminders
» pipeline_custom|boolean|false|Is this a custom pipeline
» pipeline_assignee|string|false|Who assigned this contact to the pipeline
» pipeline|string|false|What pipline this contact is in
» phone_numbers_json|map|false|Map of phone numbers for contact
» last_name|string|false|Contact's last name
» is_customer|boolean|false|Is this a customer?
» from_webhook_id|string|false|Webhook ID for ContextIO
» first_name|string|false|Contact's first name
» emails_json|map|false|Map of emails for contact
» description|string|false|Contact's job description
» created_by_user_id|integer|false|ID of the user that created the contacts
» contact_user_id|integer|false|ID of contact on the platform
» company|string|false|Company the contact represents
» addresses_json|map|false|Map of addresses for contact



## Posts

<a name="schemaposts"></a>

```json
[
  {
    "visibility": "string",
    "title": "string",
    "page_id": 0,
    "images": [
      {
        "post_id": 0,
        "image": "string"
      }
    ],
    "has_image": true,
    "content": "string",
    "comments": [
      {
        "post_id": 0,
        "content": "string",
        "author_id": 0
      }
    ]
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Post](#schemapost)]|false|A collection of Posts
» visibility|string|false|Who should be able to see this post VENDOR, BROKER, RETAILER
» title|string|false|Post title
» page_id|integer|false|The user page that the post is on
» has_image|boolean|false|does this post have images
» content|string|false|The Post's content
» images|[[PostImage](#schemapostimage)]|false|A collection of Post Images
»» post_id|integer|false|ID of the post the image belongs to
»» image|string|false|The persisted filname of the image
» comments|[[Comment](#schemacomment)]|false|A collection of user comments
»» post_id|integer|false|The id of the associated post
»» content|string|false|The Comment content
»» author_id|integer|false|The id of the user



## Email

<a name="schemaemail"></a>

```json
{
  "status": 0,
  "connect_token_used": 0,
  "connect_token_token": "string",
  "connect_token_expires": 0,
  "connect_token_browser_redirect_url": "string",
  "account_suspended": "string",
  "account_created": "string",
  "account_account": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
status|integer|false|The number status representing the contact time
connect_token_used|integer|false|If token is used, represented by number
connect_token_token|string|false|connect token for contextio
connect_token_expires|integer|false|Token expiration
connect_token_browser_redirect_url|string|false|redirect for contextio browser
account_suspended|string(ISO-8601)|false|When the account is suspended if applicable
account_created|string(ISO-8601)|false|When the account was created
account_account|string|false|The account for email



## Post

<a name="schemapost"></a>

```json
{
  "visibility": "string",
  "title": "string",
  "page_id": 0,
  "images": [
    {
      "post_id": 0,
      "image": "string"
    }
  ],
  "has_image": true,
  "content": "string",
  "comments": [
    {
      "post_id": 0,
      "content": "string",
      "author_id": 0
    }
  ]
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
visibility|string|false|Who should be able to see this post VENDOR, BROKER, RETAILER
title|string|false|Post title
page_id|integer|false|The user page that the post is on
has_image|boolean|false|does this post have images
content|string|false|The Post's content
images|[[PostImage](#schemapostimage)]|false|A collection of Post Images
» post_id|integer|false|ID of the post the image belongs to
» image|string|false|The persisted filname of the image
comments|[[Comment](#schemacomment)]|false|A collection of user comments
» post_id|integer|false|The id of the associated post
» content|string|false|The Comment content
» author_id|integer|false|The id of the user



## Ranking

<a name="schemaranking"></a>

```json
{
  "rank": 0,
  "points": 0,
  "category": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rank|integer|false|The user's ranking
points|integer|false|Points a user has accumulated in a category
category|string|false|The category a user has scored points in



## Message

<a name="schemamessage"></a>

```json
{
  "user_id": 0,
  "conversation_id": 0,
  "body": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user_id|integer|false|ID of the user that sent the message
conversation_id|integer|false|Conversation ID that message belongs to
body|string|false|The message's message



## Session

<a name="schemasession"></a>

```json
{
  "version": "string",
  "message": "string",
  "errors": "string",
  "entities": {
    "user": {
      "username": "string",
      "is_admin": true,
      "email": "string",
      "discourse_user_id": 0,
      "description": "string",
      "company_name": "string",
      "authToken": "string",
      "active": true
    }
  }
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
version|string|false|API version
message|string|false|Authentication Method
errors|string|false|errors from the server
entities|[Entities](#schemaentities)|false|No description
» user|[SessionUser](#schemasessionuser)|false|The response sent to after successful authentication
»» username|string|false|The selected username for the user
»» is_admin|boolean|false|Whether or not this user has admin permissions
»» email|string|false|The given email for the user
»» discourse_user_id|integer|false|The community generated user_id for the user
»» description|string|false|The job title of the user
»» company_name|string|false|The name of the company this user represents
»» authToken|string|false|JSON Web Token issued to user to be used in the "Authorization" header
»» active|boolean|false|Whether or not this user is active



## SavedProduct

<a name="schemasavedproduct"></a>

```json
{
  "user": {
    "username": "string",
    "user_profile": {
      "organization_name": "string",
      "last_name": "string",
      "first_name": "string",
      "description": "string",
      "avatar": "string"
    },
    "is_admin": true,
    "email": "string",
    "discourse_user_id": 0,
    "discourse_api_key": "string",
    "description": "string",
    "company_name": "string",
    "active": true
  },
  "product": {
    "upc": "string",
    "uom": "string",
    "status": "string",
    "slug": "string",
    "sku": "string",
    "qty_avail": 0,
    "name": "string",
    "discontinue_on": "string",
    "description": "string",
    "case_qty": 0,
    "base_price": null,
    "available_on": "string"
  },
  "date_saved": null
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user|[User](#schemauser)|false|A user of the Unfied App, may be a broker, retailer, or vendor rep
» username|string|false|The selected username for the user
» user_profile|[UserProfile](#schemauserprofile)|false|A User's profile that holds all public information
»» organization_name|string|false|The User's company name
»» last_name|string|false|The User's last name
»» first_name|string|false|The User's first name
»» description|string|false|The User's job description
»» avatar|string|false|filename of the user's persisted avatar
» is_admin|boolean|false|Whether or not this user has admin permissions
» email|string|false|The given email for the user
» discourse_user_id|integer|false|The community generated user_id for the user
» discourse_api_key|string|false|The community generated apiKey for the user
» description|string|false|The job title of the user
» company_name|string|false|The name of the company this user represents
» active|boolean|false|Whether or not this user is active
product|[Product](#schemaproduct)|false|A product made by a manufacturer
» upc|string|false|upc code for product
» uom|string|false|How product is measured
» status|string|false|product status
» slug|string|false|Product category Identifier
» sku|string|false|Manufacturer unique product identifier
» qty_avail|integer|false|Amount in stock at this moment
» name|string|false|Name of the Product
» discontinue_on|string(ISO-8601)|false|Date to discontinue
» description|string|false|Product description 255 character limit
» case_qty|integer|false|How many products in one unit
» base_price|decimal|false|base price for product
» available_on|string(ISO-8601)|false|Date made available
date_saved|date|false|Date product was saved for later viewing



## CommunicationSetting

<a name="schemacommunicationsetting"></a>

```json
{
  "threshold_json": null,
  "threshold_enabled": true
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
threshold_json|map|false|Values for threshold
threshold_enabled|boolean|false|if thresholds have been enabled



## PostImage

<a name="schemapostimage"></a>

```json
{
  "post_id": 0,
  "image": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
post_id|integer|false|ID of the post the image belongs to
image|string|false|The persisted filname of the image



## ConversationMemberships

<a name="schemaconversationmemberships"></a>

```json
[
  {
    "user_id": 0,
    "conversation_id": 0
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[ConversationMembership](#schemaconversationmembership)]|false|A collection of conversation memberships
» user_id|integer|false|User that owns the conversation membership
» conversation_id|integer|false|Conversation ID that memebership belongs to



## Invoices

<a name="schemainvoices"></a>

```json
[
  {
    "total": null,
    "items": [
      {
        "sku": "string",
        "quantity": "string",
        "price": null,
        "description": "string"
      }
    ]
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[Invoice](#schemainvoice)]|false|A collection of Invoices
» total|decimal|false|The Invoice total
» items|[[InvoiceItem](#schemainvoiceitem)]|false|A collection of Invoice Items
»» sku|string|false|The unique identification number
»» quantity|string|false|The amount purchased
»» price|decimal|false|The item's cost
»» description|string|false|The description of the product purchased



## InvoiceItems

<a name="schemainvoiceitems"></a>

```json
[
  {
    "sku": "string",
    "quantity": "string",
    "price": null,
    "description": "string"
  }
]
```

### Properties

Name|Type|Required|Description
---|---|---|---|
anonymous|[[InvoiceItem](#schemainvoiceitem)]|false|A collection of Invoice Items
» sku|string|false|The unique identification number
» quantity|string|false|The amount purchased
» price|decimal|false|The item's cost
» description|string|false|The description of the product purchased



## Comment

<a name="schemacomment"></a>

```json
{
  "post_id": 0,
  "content": "string",
  "author_id": 0
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
post_id|integer|false|The id of the associated post
content|string|false|The Comment content
author_id|integer|false|The id of the user



## Address

<a name="schemaaddress"></a>

```json
{
  "zip": "string",
  "type": "string",
  "state": "string",
  "line_2": "string",
  "line_1": "string",
  "label": "string",
  "city": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
zip|string|false|Zip Code
type|string|false|Type of address Billing, Shipping, etc...
state|string|false|Abbreviated state
line_2|string|false|Second Line of an address
line_1|string|false|First line of an address
label|string|false|Label for the address
city|string|false|City abbreviation



## Pipeline

<a name="schemapipeline"></a>

```json
{
  "user_id": 0,
  "hot_reminder": 0,
  "hot_date": "string",
  "cold_reminder": 0,
  "cold_date": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user_id|integer|false|The owner's ID
hot_reminder|integer|false|Days in between reminders for hot contacts
hot_date|string(ISO-8601)|false|Reminder date for the contacts listed as hot
cold_reminder|integer|false|Days in between reminders for cold contacts
cold_date|string(ISO-8601)|false|Reminder date for the contacts listed as cold



## Entities

<a name="schemaentities"></a>

```json
{
  "user": {
    "username": "string",
    "is_admin": true,
    "email": "string",
    "discourse_user_id": 0,
    "description": "string",
    "company_name": "string",
    "authToken": "string",
    "active": true
  }
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
user|[SessionUser](#schemasessionuser)|false|The response sent to after successful authentication
» username|string|false|The selected username for the user
» is_admin|boolean|false|Whether or not this user has admin permissions
» email|string|false|The given email for the user
» discourse_user_id|integer|false|The community generated user_id for the user
» description|string|false|The job title of the user
» company_name|string|false|The name of the company this user represents
» authToken|string|false|JSON Web Token issued to user to be used in the "Authorization" header
» active|boolean|false|Whether or not this user is active





