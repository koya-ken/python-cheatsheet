# zero padding

## example

```python
num = 3
print(f'{num:0>3}')
```

# xpath

## required

```shell
pip install lxml
```

## example

```python
import lxml
from lxml import html

html_str = '<html>xxxx</html>'
content = html.fromstring(html_str)
xpath = "//*[@class='xxxx']//a[@xxxx='xxxx']/@href"
content.xpath(xpath)
```

# parse uri

## example

```python
from urllib.parse import urlparse

def getroot(url):
    uri = urlparse(url)
    result = f'{uri.scheme}://{uri.netloc}'
    return result

def removequery(url):
    uri = urlparse(url)
    result = f'{uri.scheme}://{uri.netloc}{uri.path}'
    return result
```

# get mimetype from url

## example

```python
import urllib.request

def get_mimetype(url):
    with urllib.request.urlopen(url) as response:
        info = response.info()
        return info.get_content_type(),info.get_content_maintype(),info.get_content_subtype()
```
