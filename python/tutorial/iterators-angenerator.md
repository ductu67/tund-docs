# Iterators  angenerator

Iterator là một đối tượng chứa một số lượng giá trị có thể đếm được.

Iterator là một đối tượng có thể được lặp lại, nghĩa là bạn có thể duyệt qua tất cả các giá trị.

Iterator là một đối tượng thực hiện giao thức iterator, bao gồm các phương thức **iter**() và **next**() .

```python
string = "GFG"
ch_iterator = iter(string)
 
print(next(ch_iterator))
print(next(ch_iterator))

// G
// F
```

**Generator** là một cách đơn giản và mạnh mẽ để tạo ra iterator trong Python, sử dụng từ khóa `yield` để sinh ra các giá trị một cách lười biếng.

```python
 

# A generator function that yields 1 for first time, 
# 2 second time and 3 third time 
def simpleGeneratorFun(): 
    yield 1            
    yield 2            
    yield 3            
   
# Driver code to check above generator function 
for value in simpleGeneratorFun():  
    print(value)

# 1
# 2
# 3
```

Khi nào bạn nên sử dụng mỗi loại:

* Sử dụng iterator khi bạn cần tạo ra một đối tượng có thể lặp qua một tập hợp dữ liệu.
* Sử dụng generator khi bạn muốn tạo ra một dãy giá trị một cách hiệu quả, đặc biệt là khi làm việc với các dãy số lớn hoặc vô hạn.
