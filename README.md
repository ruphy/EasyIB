# EasyIB: Interactive Brokers API
[![](https://img.shields.io/pypi/v/easyib.svg)](https://pypi.org/pypi/easyib/)
[![](https://img.shields.io/pypi/pyversions/easygib.svg)](https://pypi.org/pypi/easygib/)
[![](https://img.shields.io/pypi/l/easygib.svg)](https://pypi.org/pypi/easygib/)

EasyIB is a python wrapper for [Interactive Brokers Client Portal Web API](https://interactivebrokers.github.io/cpwebapi/).

# How to Install
```
pip install easyib
```

# Quickstart

### Historical Data
```python
import easyib

api = easyib.REST()

bars = api.get_bars("AAPL", period="1w", bar="1d")
print(bars)
```


### Submitting an order
```python
orders = [
    {
        "conid": api.get_conid("AAPL"),
        "orderType": "MKT",
        "side": "BUY",
        "quantity": 7,
        "tif": "GTC",
    }
]

api.submit_orders(orders)
```