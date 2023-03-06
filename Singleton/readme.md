Singleton
Đảm bảo chỉ có duy nhất một instance được tạo ra và cung cấp method để có thể truy xuất được instance duy nhất đó mọi lúc mọi nơi trong chương trình.

Ưu điểm
Kiểm soát và giới hạn số lượng instance, shared resource. Ví dụ: Tái sử dụng kết nối đến database, kết nối SSH đến một server để thực hiện một số công việc mà không muốn mở một kết nối khác. Hay implement Logger, Configuration, Caching
Truy xuất instance ở cấp global
Instance chỉ phải khởi tạo trong lần truy xuất đầu tiên.
Nhược điểm
Trường hợp multithreaded cần có các xử lý đặc biệt để không tạo ra một object Singleton nhiều lần
Khiến unit test trở nên khó khăn. Ví dụ: Khi bạn chạy unit test thì với mỗi test case có thể thay đổi state của Singleton object. Không thể mock/stubs được Client code sử dụng Singleton vì có thể constructor của Singleton là private hoặc static methods.
Vi phạm “Single Responsibility Principle”. Ví dụ: Ngoài trách nhiệm cơ bản của nó, Singleton object còn kiểm soát số lượng instances hay còn thêm chức năng manage life-cycle.