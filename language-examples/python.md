# Language Examples

## Python

### Capture GIF using Python:

Building a query to capture a GIF using Python is as simple as:

```python
#!/usr/bin/python
 
import hmac
import hashlib
import urllib
 
 
def giflayer(access_key, url, args):
    
    # encode URL
    query = urllib.urlencode(dict(url=url, **args))
 
    return "http://apilayer.net/api/capture?access_key=%s&%s" % (access_key, query)

# set optional parameters (leave blank if unused)
params = {
    'start': '',
    'end': '',
    'duration': '',
    'size': '',
    'crop': '',
    'fps': '',
    'trailer': '',
    'export': ''
};
 
# set your access key and video URL 
access_key = "YOUR_ACCESS_KEY"
url = "https://www.youtube.com/watch?v=3W6hZR29l5o"
 
print giflayer (access_key, url, params)  
```
