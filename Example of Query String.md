```python
import requests
```


```python
url_get = 'http://httpbin.org/get'
```


```python
payload = {"name":"Kamran","ID":"123"}
```


```python
r = requests.get(url_get, params = payload)
```


```python
r.url
```




    'http://httpbin.org/get?name=Kamran&ID=123'




```python
r.request.body
```


```python
r
```




    <Response [200]>




```python
r.status_code
```




    200




```python
r.text
```




    '{\n  "args": {\n    "ID": "123", \n    "name": "Kamran"\n  }, \n  "headers": {\n    "Accept": "*/*", \n    "Accept-Encoding": "gzip, deflate, br", \n    "Host": "httpbin.org", \n    "User-Agent": "python-requests/2.26.0", \n    "X-Amzn-Trace-Id": "Root=1-6238baee-51231cfb78f54be6408259a6"\n  }, \n  "origin": "103.103.56.249", \n  "url": "http://httpbin.org/get?name=Kamran&ID=123"\n}\n'




```python
r.headers['Content-Type']
```




    'application/json'




```python
r.json()
```




    {'args': {'ID': '123', 'name': 'Kamran'},
     'headers': {'Accept': '*/*',
      'Accept-Encoding': 'gzip, deflate, br',
      'Host': 'httpbin.org',
      'User-Agent': 'python-requests/2.26.0',
      'X-Amzn-Trace-Id': 'Root=1-6238baee-51231cfb78f54be6408259a6'},
     'origin': '103.103.56.249',
     'url': 'http://httpbin.org/get?name=Kamran&ID=123'}




```python
r.json()['args']
```




    {'ID': '123', 'name': 'Kamran'}




```python

```
