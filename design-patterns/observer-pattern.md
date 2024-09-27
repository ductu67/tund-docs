# Observer pattern

Giả sử có một lớp `Subject` đại diện cho một số liệu nào đó (ví dụ, nhiệt độ) và khi giá trị nhiệt độ thay đổi, bạn muốn các thành phần khác (như hiển thị nhiệt độ và gửi cảnh báo) cũng được cập nhật\
**Trước khi sử dụng Observer pattern**:

```python
class TemperatureSensor:
    def __init__(self):
        self._temperature = 0

    def set_temperature(self, temperature):
        self._temperature = temperature
        self.update_display()
        self.send_alert()

    def update_display(self):
        print(f"Display: Current temperature is {self._temperature}°C")

    def send_alert(self):
        if self._temperature > 30:
            print("Alert: Temperature is too high!")
        else:
            print("Temperature is normal.")

# Sử dụng chương trình
sensor = TemperatureSensor()
sensor.set_temperature(25)
# Output:
# Display: Current temperature is 25°C
# Temperature is normal.

sensor.set_temperature(35)
# Output:
# Display: Current temperature is 35°C
# Alert: Temperature is too high!

```

#### **Nhược điểm:**

* Các phương thức liên quan đến việc cập nhật (hiển thị, cảnh báo) được tích hợp trực tiếp trong lớp `TemperatureSensor`.
* Nếu muốn thêm một thành phần mới (ví dụ: lưu dữ liệu vào file), bạn phải sửa mã của lớp `TemperatureSensor`, làm vi phạm nguyên tắc **Open/Closed Principle**.

**Sau khi sử dụng Observer pattern**:

```python
from abc import ABC, abstractmethod

class Observer(ABC):
    @abstractmethod
    def update(self, temperature):
        pass

class TemperatureSensor:
    def __init__(self):
        self._temperature = 0
        self._observers = []

    def add_observer(self, observer: Observer):
        self._observers.append(observer)

    def notify_observers(self):
        for observer in self._observers:
            observer.update(self._temperature)
            
    def set_temperature(self, temperature):
        self._temperature = temperature
        self.notify_observers()
    

class TemperatureDisplay(Observer):
    def update(self, temperature):
        print(f"Display: Current temperature is {temperature}°C")

class TemperatureAlert(Observer):
    def update(self, temperature):
        if temperature > 30:
            print("Alert: Temperature is too high!")
        else:
            print("Temperature is normal.")

# Tạo đối tượng sensor (Subject)
sensor = TemperatureSensor()

# Thêm các observer (hiển thị và cảnh báo)
display = TemperatureDisplay()
alert = TemperatureAlert()

sensor.add_observer(display)
sensor.add_observer(alert)

# Cập nhật nhiệt độ
sensor.set_temperature(25)
# Output:
# Display: Current temperature is 25°C
# Temperature is normal.

sensor.set_temperature(35)
# Output:
# Display: Current temperature is 35°C
# Alert: Temperature is too high!

```
