#python-sms-counter

**python-sms-counter** is a python library that helps to count characters of an SMS messages.



#### Install
```
$ pip install git+https://github.com/Shopyangu-engineering/python_sms_counter.git
```

#### Support
* Python 3


#### Usage
```python
from python_sms_counter import SMSCounter

>>> counter = SMSCounter.count('Lorem Ipsum is simply dummy text of the printing.');
>>> counter
>>> {'length': 49, 'messages': 1, 'remaining': 111, 'per_message': 70, 'encoding': 'GSM_7BIT'}

```


The meaning of the `length`, `remaining` and `per_message` values returned by `SMSCounter.count()` depend on the encoding. 

For GSM_7BIT_EX encoding, `length`, `remaining` and `per_message` count the number of 7-bit characters in the message, __including__ the escape character that must precede any characters in the "extended" character set. For example, the `length` of the message '€' is 2, because it takes 2 7bit characters to encode '€' in GSM_7BIT_EX.

For UTF16 and GSM_7BIT encoding, `length`, `remaining` and `per_message` count the number of characters (since all characters have an equal bit width).