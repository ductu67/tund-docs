# Global Interpreter Lock (GIL)

* GIL là một cơ chế bảo vệ trong Python mà chỉ cho phép một luồng thực thi (thread) hoạt động tại một thời điểm trong một tiến trình Python.
* GIL được thiết kế để đảm bảo an toàn cho việc sử dụng bộ nhớ và tài nguyên của Python, nhưng nó cũng làm giảm hiệu suất của đa luồng trong các ứng dụng Python.
* Với GIL, các tiến trình đa luồng không thể đồng thời thực hiện mã Python trên nhiều CPU cores, dù máy tính có nhiều cores.
