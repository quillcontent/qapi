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

# Quill Platform API Reference
> ### API endpoint: 
https://qapi.quill-plaform.com/v1/

This is a developer reference for the Quill Platform HTTP API, which allows Quill's Clients to programmatically retrieve content.

The Quill API is organised around REST. Our API has predictable, resource-oriented URLs, and uses HTTP response codes to indicate API errors. We use built-in HTTP features, like HTTP verbs, which are understood by off-the-shelf HTTP clients. 

<aside class="notice">JSON is returned by all API responses, including errors.</aside>

<aside class="warning">All API requests should be made over HTTPS.</aside>

<aside class="warning">We reserve the right to rate-limit any application if we feel you are not following fair-use.</aside>

<aside class="notice">If you require faster access without rate limit please contact us.</aside>

<aside class="notice">Questions or comments? Please email: <code>support@quillcontent.com</code></aside>

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

<aside class="warning">API requests without authentication will fail.</aside>

# Resources

## Deliverables
```shell
curl -X GET -H "x-quill-token: <YOUR API TOKEN>" -H "https://qapi.quill-platform.com/v1/deliverables/<ID>"
```

```http
GET /v1/deliverables/<ID> HTTP/1.1
Host: qapi.quill-platform.com
x-quill-token: <YOUR API TOKEN>
```

> The above command returns the following JSON:

```json
{
    "data": [
        {
            "id":                   "TASK_6dff19a5-92df-46e7-840c-xxxxxxxxxxxx",
            "fields": [
              {
                    "id":           "FILD_6111d080-f3e2-45ec-a914-xxxxxxxxxxxx",
                    "label":        "Product heading",
                    "value":        "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
                    "completed_at": "2015-01-01T12:01:00.000Z"
                },
                {
                    "id":           "FILD_5e1fd080-f3e2-45ec-a914-xxxxxxxxxxxx",
                    "label":        "Product description",
                    "value":        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum vel vulputate neque, a sodales libero. Nulla condimentum velit ipsum, eget ullamcorper massa cursus vitae. Ut turpis tortor, condimentum ut mattis in, porttitor vel justo. Sed tincidunt et risus volutpat dignissim. Nulla pretium placerat dui, ut lobortis mauris sollicitudin non. Nam eu enim ac felis sollicitudin commodo. Aenean velit enim, suscipit sed augue eu, varius fermentum urna. Suspendisse potenti.",
                    "completed_at": "2015-01-01T12:01:00.000Z"
                }
            ]
        }
    ],
    "meta": {
        "page": 1,
        "items_count": 1,
        "pages_count": 1
    }
}
```

This endpoint retrieves all your content deliverables for the ID you've been provdied by your Quill Account Manager.

### HTTP Request

`GET /deliverables/<ID>`

<aside class="success">A 200 ok response represents a succesful request.</aside>

### URL Parameters

Parameter | Description
--------- | ------- | -----------
ID | The ID of your group of content deliverables.

### Response Properties

Property | Description
--------- | ------- | -----------
data | The primary data response from the Quill Platform which is an array data structure. This array contains all your apporved content for the provided ID.
meta | The meta data reponse from the Quill Platform contains usful supplimental data such as pagination information. 

# Pagination

Endpoints that are a list method provide the ability to page through the results. Results are defaulted to 50 per page and the responses contains the paging data within the "meta" data structure.


```shell
curl -X GET -H "x-quill-token: <YOUR API TOKEN>" "https://qapi.quill-platform.com/v1/deliverables/<ID>?page=1"
```

```http
GET /v1/deliverables/<ID>?page=1 HTTP/1.1
Host: qapi.quill-platform.com
```

> Paging meta data is returned in the following JSON structure:

```json
{
  "data":[],
  "meta": {
        "page": 1,
        "items_count": 1,
        "pages_count": 1
    }
}
```


You can request other pages but providing the ```page``` query parameter.

### URL Parameters

Parameter | Description
--------- | ------- | -----------
page | The page of results you're looking to access 


