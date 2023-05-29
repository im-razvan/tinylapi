### POST /v1/shorten_url

Shortens the given URL.

#### Request

| Parameter | Type   | Description           |
|-----------|--------|-----------------------|
| url       | string | The URL to be shortened |

The `url` parameter should be included in the request body as a form field.

#### Response

##### Success

- Status Code: `200 OK`
- Content Type: `text/plain`
- Example Response Body: `https://tinyl.at/AbCdE`

##### Error

- Status Code: `400 Bad Request`
- Content Type: `text/plain`
- Example Response Body: `Invalid url.`

#### Example

```python
import requests

url_to_shorten = "https://www.example.com"
api_endpoint = "https://tinyl.at/v1/shorten_url"

response = requests.post(api_endpoint, data={"url": url_to_shorten})

if response.status_code == 200:
    print("Shortened URL:", response.text)
else:
    print("Error:", response.text)
