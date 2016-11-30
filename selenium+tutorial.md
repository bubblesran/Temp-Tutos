

```python
from selenium import webdriver
```

Start a driver with phantomJS.
This is like to open phantomJS-like browser. The param is path for phantomJS. 


```python
driver = webdriver.PhantomJS('./phantomjs-2.1.1-windows/bin/phantomjs.exe')
```

Use the method get to open an url


```python
driver.get('http://xxx')
```

Use find_element_*method to locate elements in web page.
To locate the element, F12 in chrome is useful.
send_keys to fill in text.
click() to click buttons.


```python
driver.find_element_by_name("login").clear()
driver.find_element_by_name("login").send_keys('xxx')
driver.find_element_by_name("password").clear()
driver.find_element_by_name("password").send_keys('xxx')
driver.find_element_by_class_name("submit").click()
```

is_enabled can be used to test if button element is still enable.


```python
driver.find_element_by_xpath('xxx').is_enabled()
```







Switch among web frames by the method swith_to_frame.
Remenber: always call switch_to_default_content after done with a frame


```python
driver.switch_to_frame('menuFrame')
```


```python
driver.find_element_by_css_selector("xxx").click()
```


```python
driver.switch_to_default_content()
driver.switch_to_frame('mainFrame')
```

Select can be used to deal with selection elements


```python
from selenium.webdriver.support.ui import Select
```


```python
sel = driver.find_element_by_css_selector('xxx')
Select(sel).select_by_value('xxx')
```


```python
driver.close()
```
