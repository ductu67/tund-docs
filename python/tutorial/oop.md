---
description: >-
  Object-Oriented Programming - Trong Python, mọi thứ đều là một đối tượng, và
  có thể định nghĩa các lớp và đối tượng để tái sử dụng mã, tạo ra các phương
  thức và thuộc tính để tương tác với dữ liệu
---

# OOP

1.  **Kế thừa (Inheritance):**

    * Kế thừa là tính năng trong OOP cho phép một lớp (class) con kế thừa các thuộc tính và phương thức từ một lớp cha.
    * Ví dụ:

    ```python
    class Animal:
        def speak(self):
            print("Animal speaks")

    class Dog(Animal):  # Lớp Dog kế thừa từ lớp Animal
        def bark(self):
            print("Dog barks")

    dog = Dog()
    dog.speak()  # Output: Animal speaks
    dog.bark()   # Output: Dog barks
    ```
2.  **Đa hình (Polymorphism):**

    * Đa hình là khả năng của các đối tượng để có các hành vi khác nhau dựa trên loại đối tượng của chúng.
    * Ví dụ:

    ```python
    class Animal:
        def speak(self):
            pass

    class Dog(Animal):
        def speak(self):
            print("Dog barks")

    class Cat(Animal):
        def speak(self):
            print("Cat meows")

    def make_sound(animal):
        animal.speak()

    dog = Dog()
    cat = Cat()

    make_sound(dog)  # Output: Dog barks
    make_sound(cat)  # Output: Cat meows
    ```
3.  **Đóng gói (Encapsulation):**

    * Đóng gói là việc gói các dữ liệu (biến) và phương thức (hàm) liên quan vào trong một lớp.
    * Python không hỗ trợ encapsulation nhưng bạn có thể sử dụng các hàm getter và setter để truy cập và thiết lập giá trị của biến trong lớp.
    * Ví dụ:

    ```python
    class Person:
        def __init__(self, name, age):
            self._name = name
            self._age = age

        def get_name(self):
            return self._name

        def set_name(self, name):
            self._name = name

        def get_age(self):
            return self._age

        def set_age(self, age):
            self._age = age

    person = Person("Alice", 30)
    print(person.get_name())  # Output: Alice
    person.set_age(25)
    print(person.get_age())   # Output: 25
    ```
