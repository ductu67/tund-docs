---
description: >-
  Python có hỗ trợ cho "type hints" tùy chọn (còn được gọi là "type
  annotations").Những "type hints" là một cú pháp đặc biệt cho phép khai báo
  kiểu của biến.
---

# Python Types Intro

Type hints example:

```python
def get_full_name(first_name: str, last_name: str):
    full_name = first_name.title() + " " + last_name.title()
    return full_name


print(get_full_name("john", "doe"))
```
