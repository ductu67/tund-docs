# Decorators

**Python decorators là gì? Đưa ra một ví dụ về cách sử dụng decorators:**

* Decorators là các hàm hoặc lớp trong Python được sử dụng để thay đổi hoặc mở rộng hành vi của một hàm hoặc phương thức.

```python
def uppercase_decorator(func):
    def wrapper(text):
        return func(text).upper()
    return wrapper

@uppercase_decorator
def greet(name):
    return f"Hello, {name}"

print(greet("John"))  # Output: HELLO, JOHN

```
