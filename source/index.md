---
title: Quill Platform API Reference

language_tabs:
  - shell
  - http

toc_footers:
  - <a href='http://www.quillcontent.com'>Quill Content</a>

includes:
  - errors

search: true
---

# Introduction

This document has been produced to document the HTTP API, which allows Quill's Clients to programmatically retrieve content from the Quill Platform.

The Quill API is organised around REST. Our API has predictable, resource-oriented URLs, and uses HTTP response codes to indicate API errors. We use built-in HTTP features, like HTTP verbs, which are understood by off-the-shelf HTTP clients. JSON is returned by all API responses, including errors.

<aside class="notice">
Questions or comments? Email: <code>support@quillcontent.com</code>
</aside>


# Authentication

In order to properly authenticate with the API you must you send your API key in the header of each request. 

Your API keys carry many privileges, so be sure to keep them secret! Do not share your secret API keys in publicly accessible areas.
Authentication to the API is performed via custom HTTP header with a key of 
`x-quill-token:<YOUR API TOKEN>`. 
You do not need to provide a password.

Your API key will be provided by your Quill Account Manager.

```shell
curl -X GET -H "x-quill-token: <YOUR API TOKEN>" 'https://qapi.quill-platform.com/v1'
```

```http
GET /v1 HTTP/1.1
Host: qapi.quill-platform.com
x-quill-token: <YOUR API TOKEN>
Cache-Control: no-cache
```

<aside class="notice">
You must replace <code>YOUR API TOKEN</code> with your provided API key.
</aside>

<aside class="warning">All API requests should be made over HTTPS.</aside>

<aside class="warning">API requests without authentication will fail.</aside>

# Accessing Endpoints
  
The API is reachable at https://qapi.quill-plaform.com/v1/<RESOURCE>

<aside class="warning">We reserve the right to rate-limit any application if we feel you are not following fair-use.
</aside>

<aside class="notice">If you require faster access without rate limit please contact us.</aside>

# Resources

## Deliverables

```shell
curl -X GET -H "x-quill-token: <YOUR API TOKEN>" -H "Cache-Control: no-cache" 'https://qapi.quill-platform.com/v1/deliverables/<ID>'
```

```http
GET /v1/deliverables/<ID> HTTP/1.1
Host: qapi.quill-platform.com
x-quill-token: <YOUR API TOKEN>
Cache-Control: no-cache
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "<ID>",
    "attrs": {
      "created_at": "2015-11-25T10:25:24.059Z"
    }
  },
  "meta": {}
}
```

This endpoint retrieves all your content deliverables for the ID you've been provdied by your Quill Account Manager.

### HTTP Request

`GET /deliverables/:id`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | The ID of your group of content deliverables 

<aside class="success">
200 OK
</aside>


