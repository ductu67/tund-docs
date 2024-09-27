---
description: >-
  Cho phép chọn thuật toán (hoặc chiến lược) cụ thể để thực hiện công việc trong
  quá trình chạy mà không cần thay đổi mã nguồn
---

# Strategy pattern

**Trước khi sử dụng Strategy pattern**:

```python
class ShippingCostCalculator:
    def calculate_shipping_cost(self, method, weight):
        if method == 'ground':
            return weight * 1.5  # Chi phí vận chuyển đường bộ
        elif method == 'air':
            return weight * 3.0  # Chi phí vận chuyển đường không
        else:
            raise ValueError("Unsupported shipping method")

# Sử dụng chương trình
calculator = ShippingCostCalculator()

ground_shipping_cost = calculator.calculate_shipping_cost('ground', 10)
print(f"Ground shipping cost: {ground_shipping_cost}")  # Output: 15.0

air_shipping_cost = calculator.calculate_shipping_cost('air', 10)
print(f"Air shipping cost: {air_shipping_cost}")  # Output: 30.0

```

#### **Nhược điểm:**

* Khó mở rộng nếu có thêm nhiều phương thức vận chuyển mới.
* Code không linh hoạt: Việc thêm/chỉnh sửa phương thức vận chuyển yêu cầu thay đổi code trong hàm `calculate_shipping_cost`, vi phạm nguyên tắc **Open/Closed Principle**.

**Sau khi sử dụng Strategy pattern**:

```python
from abc import ABC, abstractmethod

class ShippingStrategy(ABC):
    @abstractmethod
    def calculate(self, weight):
        pass

class GroundShipping(ShippingStrategy):
    def calculate(self, weight):
        return weight * 1.5  # Chi phí vận chuyển đường bộ

class AirShipping(ShippingStrategy):
    def calculate(self, weight):
        return weight * 3.0  # Chi phí vận chuyển đường không

class ShippingCostCalculator:
    def __init__(self, strategy: ShippingStrategy):
        self._strategy = strategy

    def set_strategy(self, strategy: ShippingStrategy):
        self._strategy = strategy

    def calculate_shipping_cost(self, weight):
        return self._strategy.calculate(weight)

# Tạo đối tượng với chiến lược vận chuyển bằng đường bộ
calculator = ShippingCostCalculator(GroundShipping())
ground_shipping_cost = calculator.calculate_shipping_cost(10)
print(f"Ground shipping cost: {ground_shipping_cost}")  # Output: 15.0

# Thay đổi chiến lược thành vận chuyển bằng đường không
calculator.set_strategy(AirShipping())
air_shipping_cost = calculator.calculate_shipping_cost(10)
print(f"Air shipping cost: {air_shipping_cost}")  # Output: 30.0

```

#### **Ưu điểm sau khi sử dụng Strategy pattern:**

* **Mở rộng dễ dàng**: Nếu cần thêm các phương thức vận chuyển mới (ví dụ: đường biển, đường sắt), bạn chỉ cần tạo thêm một lớp mới kế thừa từ `ShippingStrategy` mà không cần chỉnh sửa lại logic trong `ShippingCostCalculator`.
* **Linh hoạt**: Bạn có thể thay đổi chiến lược vận chuyển một cách dễ dàng mà không cần phải sửa đổi mã nguồn của các phương thức tính toán hiện có.
