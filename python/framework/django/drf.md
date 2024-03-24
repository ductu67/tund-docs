# DRF

**Làm thế nào để tạo một API endpoint trong Django Rest Framework?**

* Để tạo một API endpoint trong Django Rest Framework (DRF), bạn cần định nghĩa một class-based view kế thừa từ các generics view như `APIView`, `ViewSet`, hoặc sử dụng các decorator như `@api_view`.&#x20;
* Sau đó, định nghĩa các phương thức HTTP như `get()`, `post()`, `put()`, `delete()` để xử lý các yêu cầu từ client và trả về các đối tượng `Response`.

**Giải thích ý nghĩa và cách sử dụng serializers trong DRF:**

* Serializers trong DRF là các công cụ giúp bạn chuyển đổi dữ liệu từ Python objects sang dạng JSON hoặc XML, và ngược lại.
* Serializer cũng giúp bạn validate dữ liệu đầu vào từ request. Để sử dụng serializer, bạn cần định nghĩa một class kế thừa từ `serializers.Serializer` hoặc `serializers.ModelSerializer`, và xác định các trường và rules cho việc serialize và deserialize.

**Phân biệt giữa function-based views và class-based views trong Django:**

* Function-based views là các views được xây dựng dựa trên hàm. Khi ứng dụng trở nên phức tạp, việc quản lý và tái sử dụng code có thể trở nên khó khăn.

```python
from django.http import JsonResponse

def my_view(request):
    # Xử lý yêu cầu và trả về response
    data = {'message': 'Hello, World!'}
    return JsonResponse(data)
```

* Class-based views là các views được xây dựng dựa trên các class.  Chúng cung cấp một cách tiếp cận tổ chức hơn, cho phép tái sử dụng code dễ dàng hơn bằng cách sử dụng kế thừa và mixins. CBVs cung cấp các phương thức chuẩn để xử lý các loại yêu cầu HTTP như `get()`, `post()`, `put()`, `delete()`...vv, giúp giảm bớt việc lặp lại code.

```python
from django.http import JsonResponse
from django.views import View

class MyView(View):
    def get(self, request):
        # Xử lý yêu cầu GET và trả về response
        data = {'message': 'Hello, World!'}
        return JsonResponse(data)
```

**Làm thế nào để tối ưu hóa hiệu suất của ứng dụng Django/DRF:**

* Để tối ưu hiệu suất của ứng dụng Django/DRF, bạn có thể thực hiện một số biện pháp như:
  * Sử dụng cache cho các truy vấn dữ liệu thường xuyên.
  * Tối ưu hóa câu truy vấn database bằng cách sử dụng indexes, select\_related() và prefetch\_related().
  * Sử dụng ghi log hiệu quả để phát hiện và khắc phục các vấn đề hiệu suất.
  * Sử dụng công cụ giám sát như Django Debug Toolbar hoặc Django Silk để theo dõi hiệu suất ứng dụng.

**Django có hỗ trợ caching không? Nếu có, làm thế nào để thực hiện caching trong Django/DRF:**

* Có, Django cung cấp hỗ trợ caching thông qua các backend caching như Memcached hoặc Redis. Để thực hiện caching trong Django/DRF, bạn có thể sử dụng decorator `@cache_page` để cache kết quả của một view, hoặc sử dụng các hàm cache như `cache.set()` và `cache.get()` để cache dữ liệu cụ thể.

**Phân biệt giữa token-based authentication và session-based authentication trong DRF:**

* Trong token-based authentication, mỗi yêu cầu được gửi từ client sẽ kèm theo một token được tạo ra từ server và được lưu trữ ở client-side. Token này sẽ được gửi cùng với mỗi yêu cầu tiếp theo để xác thực. Trong session-based authentication, server tạo ra một session cho mỗi user khi họ đăng nhập và gửi một cookie chứa session ID về client-side. Mỗi yêu cầu sau này sẽ chứa session ID để xác thực.
