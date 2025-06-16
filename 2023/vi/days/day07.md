# Ngày 7: Tổng quan về Lập trình an toàn

Lập trình an toàn là thực hành viết phần mềm theo cách đảm bảo an ninh cho hệ thống và dữ liệu mà nó xử lý. Nó bao gồm việc thiết kế, viết hóa và kiểm thử phần mềm với tư duy an ninh để ngăn chặn các lỗ hổng và bảo vệ chống lại các cuộc tấn công tiềm ẩn.

Có một số nguyên tắc chính của lập trình an toàn mà các nhà phát triển nên tuân theo:

1. Xác thực đầu vào: Điều quan trọng là phải xác thực tất cả các đầu vào của người dùng để đảm bảo rằng nó ở định dạng mong đợi và không chứa bất kỳ mã độc hại hoặc ký tự không mong muốn nào. Điều này có thể đạt được thông qua việc sử dụng các biểu thức chính quy, kiểm tra kiểu dữ liệu và các kỹ thuật xác thực khác.
2. Mã hóa đầu ra: Dữ liệu đầu ra nên được mã hóa đúng cách để ngăn chặn bất kỳ cuộc tấn công tiêm nhiễm nào. Ví dụ, đầu ra HTML nên được escaped đúng cách để ngăn chặn các cuộc tấn công cross-site scripting (XSS), và các truy vấn SQL nên được tham số hóa để ngăn chặn các cuộc tấn công SQL injection.
3. Kiểm soát truy cập: Kiểm soát truy cập bao gồm việc hạn chế truy cập vào các tài nguyên hoặc dữ liệu chỉ cho những người dùng được ủy quyền truy cập. Điều này có thể bao gồm việc triển khai các giao thức xác thực và ủy quyền, cũng như thực thi các nguyên tắc quyền tối thiểu để đảm bảo rằng người dùng chỉ có các quyền truy cập cần thiết để thực hiện nhiệm vụ của họ.
4. Xử lý lỗi: Xử lý lỗi là quá trình xử lý đúng cách các lỗi và ngoại lệ có thể xảy ra trong quá trình thực thi chương trình. Điều này có thể bao gồm việc ghi lại lỗi, hiển thị các thông báo phù hợp cho người dùng và giảm thiểu tác động của lỗi đối với an ninh hệ thống.
5. Mã hoá: Mã hoá nên được sử dụng để bảo vệ dữ liệu và giao tiếp nhạy cảm, chẳng hạn như mật khẩu, giao dịch tài chính và các tài liệu nhạy cảm. Điều này có thể đạt được thông qua việc sử dụng các thuật toán mã hóa và các thực hành quản lý khóa an toàn.
6. Mô hình hóa mối đe dọa (Threat Modeling): Tài liệu, định vị, giải quyết (Document, locate, address, and validate) và xác thực là bốn bước của mô hình hóa mối đe dọa. Để lập trình an toàn, bạn cần kiểm tra phần mềm của mình để tìm các khu vực dễ bị tấn công. Mô hình hóa mối đe dọa là một quá trình nhiều giai đoạn nên được tích hợp vào vòng đời phần mềm từ phát triển, kiểm thử đến sản xuất.
7. Lưu trữ an toàn: Lưu trữ an toàn bao gồm việc lưu trữ và xử lý đúng cách dữ liệu nhạy cảm, chẳng hạn như mật khẩu và thông tin cá nhân, để ngăn chặn truy cập trái phép hoặc giả mạo. Điều này có thể bao gồm việc sử dụng mã hóa, băm và các biện pháp bảo mật khác để bảo vệ dữ liệu khi lưu trữ và truyền tải.
8. Kiến trúc an toàn: Kiến trúc an toàn là nền tảng của một hệ thống an toàn. Điều này bao gồm việc thiết kế các hệ thống với tư duy an ninh, sử dụng các khung và thư viện an toàn, và tuân theo các mẫu thiết kế an toàn.

Có một số công cụ và kỹ thuật có thể được sử dụng để đảm bảo rằng mã là an toàn, bao gồm Kiểm thử An ninh Ứng dụng Tĩnh (SAST), Phân tích Thành phần Phần mềm (SCA), và Đánh giá Mã An toàn (Secure Code Review).

### Kiểm thử An ninh Ứng dụng Tĩnh (SAST)

SAST là một phương pháp kiểm thử mã phần mềm để tìm các lỗ hổng an ninh trong giai đoạn phát triển. Nó bao gồm việc phân tích mã nguồn của một chương trình mà không thực thi nó, tìm kiếm các lỗ hổng như các cuộc tấn công tiêm nhiễm, cross-site scripting (XSS), và các vấn đề an ninh phổ biến khác. Các công cụ SAST có thể được tích hợp vào quá trình phát triển phần mềm để cung cấp phản hồi liên tục và cảnh báo về các lỗ hổng tiềm ẩn khi mã đang được viết.

### Phân tích Thành phần Phần mềm (SCA)

SCA là một phương pháp phân tích các thành phần và thư viện bên thứ ba được sử dụng trong một ứng dụng phần mềm. Nó giúp xác định bất kỳ lỗ hổng hoặc rủi ro an ninh nào có thể tồn tại trong các thành phần này, và có thể cảnh báo cho các nhà phát triển về nhu cầu cập nhật hoặc thay thế chúng. SCA có thể được thực hiện thủ công hoặc bằng cách sử dụng các công cụ tự động.

### Đánh giá Mã An toàn (Secure Code Reviews)

Đánh giá Mã An toàn là quá trình xem xét mã phần mềm với mục tiêu xác định và giải quyết các lỗ hổng an ninh tiềm ẩn. Nó thường được thực hiện bởi một nhóm các chuyên gia an ninh quen thuộc với các thực hành viết mã (coding) phổ biến và các thực hành an ninh tốt nhất. Đánh giá Mã An toàn có thể được thực hiện thủ công hoặc bằng cách sử dụng các công cụ tự động, và có thể bao gồm sự kết hợp của các kỹ thuật SAST và SCA.

Tóm lại, lập trình an toàn là một thực hành quan trọng giúp bảo vệ phần mềm và người dùng của nó khỏi các lỗ hổng an ninh và các cuộc tấn công. Bằng cách tuân theo các thực hành tốt nhất và giữ phần mềm luôn được cập nhật, các nhà phát triển có thể giúp đảm bảo rằng phần mềm của họ an toàn nhất có thể.

### Tài liệu tham khảo

- [Secure Coding Best Practices | OWASP Top 10 Proactive Control](https://www.youtube.com/watch?v=8m1N2t-WANc)

- [Secure coding practices every developer should know](https://snyk.io/learn/secure-coding-practices/)

- [10 Secure Coding Practices You Can Implement Now](https://codesigningstore.com/secure-coding-practices-to-implement)

- [Secure Coding Guidelines And Best Practices For Developers](https://www.softwaretestinghelp.com/guidelines-for-secure-coding/)

Trong phần tiếp theo trong [ngày 8](day08.md), chúng ta sẽ thảo luận chi tiết hơn về Kiểm thử An ninh Ứng dụng Tĩnh (SAST).
