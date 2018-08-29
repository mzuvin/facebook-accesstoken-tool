# facebook-accesstoken-tool
facebook accesstoken never expire

```python
import requests
import re
def get_token(username, password):
    data = {"email" : username, "pass"  : password}
    headers    = {"User-Agent": "Mozilla/5.0 (Windows NT 6.2; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.87 Safari/537.36"}
    s = requests.Session()
    s.get("http://www.facebook.com")
    s.post("https://www.facebook.com/login.php?login_attempt=1&1wv=110", data=data)
    r = s.get("https://www.facebook.com/"+str(username), headers=headers)
    regex = r"access_token:\"([A-Za-z0-9]+)\""
    token=re.findall(regex,r.text)
    print token[0]
    return token[0]

get_token("username","password")
```
