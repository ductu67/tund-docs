# Iterators

Iterator là một đối tượng chứa một số lượng giá trị có thể đếm được.

Iterator là một đối tượng có thể được lặp lại, nghĩa là bạn có thể duyệt qua tất cả các giá trị.

Iterator là một đối tượng thực hiện giao thức iterator, bao gồm các phương thức **iter**() và **next**() .

```python
string = "GFG"
ch_iterator = iter(string)
 
print(next(ch_iterator))
print(next(ch_iterator))
print(next(ch_iterator))

// G
// F
// H
```
