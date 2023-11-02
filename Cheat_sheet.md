# Python `requests` Library Cheat Sheet

## Importing the Library
```
import requests
```
# Making Requests
## GET Request
```
response = requests.get('http://example.com')
```
## POST Request
```
response = requests.post('http://example.com', data={'key': 'value'})
```
## PUT Request
```
response = requests.put('http://example.com', data={'key': 'value'})
```
## DELETE Request
```
response = requests.delete('http://example.com')
```
## HEAD Request
```
response = requests.head('http://example.com')
```
## OPTIONS Request
```
response = requests.options('http://example.com')
```
---------------------------------------------------
--------------------------------------------------
## Passing Parameters In URLs
```
response = requests.get('http://example.com', params={'key1': 'value1', 'key2': 'value2'})
```
## Adding Headers
```
headers = {'user-agent': 'my-app/0.0.1'}
response = requests.get('http://example.com', headers=headers)
```
## Sending JSON Data
```
json_data = {'key': 'value'}
response = requests.post('http://example.com', json=json_data)
```
## Response Content and Status
```
print(response.text)
```
## JSON Response
```
json_response = response.json()
```
## Binary Response
```
binary_response = response.content
```
## Status Code
```
status_code = response.status_code
```
## Handling Response and Errors
```
if response.ok:
    # Proceed if the request was successful
else:
    # Handle errors or status codes like 404, 500, etc.
```
## Timeouts
```
response = requests.get('http://example.com', timeout=1)  # timeout in seconds
```
## Sessions (with context manager)
```
with requests.Session() as session:
    session.get('http://example.com')
```
## Cookies
```
cookies = dict(cookies_are='working')
response = requests.get('http://example.com', cookies=cookies)
```
## Redirects
```
response = requests.get('http://example.com', allow_redirects=True)
```
## SSL Certificate Verification
```
response = requests.get('https://example.com', verify=True)  # default
response = requests.get('https://example.com', verify=False)  # bypass verification
```
## Custom Authentication
```
from requests.auth import HTTPBasicAuth
response = requests.get('http://example.com', auth=HTTPBasicAuth('user', 'pass'))
```
## Streaming and Chunked Requests
```
response = requests.get('http://example.com', stream=True)
for chunk in response.iter_content(chunk_size=128):
    print(chunk)
```
