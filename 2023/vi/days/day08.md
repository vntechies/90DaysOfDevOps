# Ngày 8: Tổng quan về SAST

Kiểm tra bảo mật ứng dụng tĩnh (SAST) là một phương pháp đánh giá bảo mật của ứng dụng bằng cách phân tích mã nguồn của ứng dụng mà không cần thực thi mã. SAST còn được gọi là kiểm thử hộp trắng vì nó liên quan đến việc kiểm tra cấu trúc và hoạt động nội bộ của một ứng dụng.

SAST được thực hiện sớm trong vòng đời phát triển phần mềm (SDLC) vì nó cho phép các nhà phát triển xác định và sửa chữa các lỗ hổng trước khi ứng dụng được triển khai. Điều này giúp ngăn chặn các vi phạm bảo mật và giảm thiểu rủi ro của các sự cố bảo mật có thể tốn kém.

Một trong những lợi ích chính của SAST là nó có thể xác định các lỗ hổng mà các phương pháp kiểm tra khác như kiểm tra động hoặc kiểm tra thủ công có thể không phát hiện được. Điều này là do SAST phân tích toàn bộ mã nguồn và có thể xác định các lỗ hổng mà các phương pháp kiểm tra khác có thể không phát hiện được.

Có một số loại lỗ hổng mà SAST có thể xác định, bao gồm:

- **Lỗ hổng xác thực đầu vào**: Những lỗ hổng này xảy ra khi một ứng dụng không xác thực đầy đủ đầu vào của người dùng, cho phép kẻ tấn công nhập mã độc hoặc dữ liệu có thể làm tổn hại đến bảo mật của ứng dụng.
- **Lỗ hổng cross-site scripting (XSS)**: Những lỗ hổng này cho phép kẻ tấn công chèn các tập lệnh độc hại vào các ứng dụng web, cho phép chúng đánh cắp thông tin nhạy cảm hoặc thao túng ứng dụng vì lợi ích riêng của chúng.
- **Lỗ hổng tiêm nhiễm (injection)**: Những lỗ hổng này cho phép kẻ tấn công chèn mã độc hoặc dữ liệu vào ứng dụng, cho phép chúng truy cập trái phép vào thông tin nhạy cảm hoặc thực hiện các hành động trái phép.
- **Chức năng và thư viện không an toàn**: Những lỗ hổng này xảy ra khi một ứng dụng sử dụng các chức năng hoặc thư viện không an toàn có thể bị kẻ tấn công khai thác.
- **Cấu hình bảo mật sai**: Những lỗ hổng này xảy ra khi một ứng dụng không được cấu hình đúng cách, cho phép kẻ tấn công truy cập vào thông tin nhạy cảm hoặc thực hiện các hành động trái phép.

### Công cụ SAST (miễn phí)

- **[SonarCloud](https://www.sonarsource.com/products/sonarcloud/)**: SonarCloud là một dịch vụ phân tích mã nguồn dựa trên đám mây được thiết kế để phát hiện các vấn đề về chất lượng mã trong hơn 25 ngôn ngữ lập trình khác nhau, liên tục đảm bảo tính duy trì, độ tin cậy và bảo mật của mã của bạn.
- **[Snyk](https://snyk.io/)**: Snyk là một nền tảng cho phép bạn quét, ưu tiên và sửa chữa các lỗ hổng bảo mật trong mã của bạn, các dependencies mã nguồn mở, hình ảnh container và cấu hình Hạ tầng dưới dạng mã (IaC).
- **[Semgrep](https://semgrep.dev/)**: Semgrep là một công cụ phân tích tĩnh mã nguồn mở nhanh chóng để tìm lỗi, phát hiện các lỗ hổng dependencies và thực thi các tiêu chuẩn mã.

## SAST hoạt động như thế nào?

Các công cụ SAST thường sử dụng nhiều kỹ thuật khác nhau để phân tích mã nguồn, bao gồm pattern matching, phân tích dựa trên quy tắc và phân tích luồng dữ liệu.

Pattern matching liên quan đến việc tìm kiếm các mẫu cụ thể trong mã có thể chỉ ra một lỗ hổng, chẳng hạn như việc sử dụng một thư viện đã biết là dễ bị tấn công hoặc thực thi yêu cầu của người dùng mà không kiểm tra đúng cách.

Phân tích dựa trên quy tắc liên quan đến việc sử dụng một tập hợp các quy tắc được xác định trước để xác định các lỗ hổng tiềm ẩn, chẳng hạn như việc sử dụng mật mã yếu hoặc thiếu xác thực đầu vào.

Phân tích luồng dữ liệu liên quan đến việc theo dõi luồng dữ liệu qua ứng dụng và xác định các lỗ hổng tiềm ẩn có thể phát sinh do kết quả, chẳng hạn như xử lý dữ liệu nhạy cảm một cách không an toàn.

## Cân nhắc khi sử dụng công cụ SAST

1. Điều quan trọng là phải đảm bảo rằng công cụ được cấu hình đúng cách và được sử dụng theo cách phù hợp với các thực hành tốt nhất. Điều này có thể bao gồm việc đặt mức độ nhạy cảm (sensitivity level) của công cụ để đảm bảo rằng nó xác định đúng các lỗ hổng, cũng như cấu hình công cụ để bỏ qua một số loại lỗ hổng được biết là vô hại.
2. Các công cụ SAST không thay thế cho việc review mã thủ công. Mặc dù các công cụ này có thể xác định nhiều lỗ hổng tiềm ẩn, nhưng chúng có thể không xác định được tất cả và điều quan trọng là các nhà phát triển phải review mã thủ công để đảm bảo rằng nó an toàn.
3. SAST chỉ là một khía cạnh của chương trình bảo mật ứng dụng toàn diện. Mặc dù nó có thể là một công cụ quan trọng để xác định các lỗ hổng tiềm ẩn, nhưng nó không thay thế cho các biện pháp bảo mật khác, chẳng hạn như thực hành viết mã an toàn, kiểm tra trong môi trường sản xuất và giám sát và bảo trì liên tục.

### Thách thức của SAST

- **Dương tính giả (False positives)**: Các công cụ SAST tự động đôi khi có thể xác định các lỗ hổng tiềm ẩn không thực sự là lỗ hổng. Điều này có thể dẫn đến một số lượng lớn các false positives cần được xem xét thủ công, làm tăng thời gian và chi phí của quá trình kiểm tra.
- **Phạm vi hạn chế**: SAST chỉ có thể xác định các lỗ hổng trong mã nguồn được phân tích. Nếu một ứng dụng sử dụng các thư viện hoặc API bên ngoài, chúng có thể không được cover bởi quá trình SAST.
- **Độ phức tạp của mã**: SAST có thể khó khăn hơn đối với các mã nguồn lớn hơn hoặc mã nguồn được viết bằng các ngôn ngữ khó phân tích.
- **Kiểm tra hạn chế**: SAST không thực thi mã và do đó không thể xác định các lỗ hổng có thể chỉ xảy ra khi mã được thực thi.

Mặc dù có nhiều thách thức, SAST là một phương pháp đánh giá bảo mật ứng dụng có giá trị và có thể giúp các tổ chức ngăn chặn các vi phạm bảo mật và giảm thiểu rủi ro của các sự cố bảo mật tốn kém. Bằng cách xác định và sửa chữa các lỗ hổng sớm trong SDLC, các tổ chức có thể xây dựng các ứng dụng an toàn hơn và cải thiện bảo mật tổng thể của hệ thống của họ.

### Tài liệu tham khảo

- [SAST- Static Analysis with lab by Practical DevSecOps](https://www.youtube.com/watch?v=h37zp5g5tO4)
- [SAST – All About Static Application Security Testing](https://www.mend.io/resources/blog/sast-static-application-security-testing/)
- [SAST Tools : 15 Top Free and Paid Tools](https://www.appsecsanta.com/sast-tools)

Trong phần tiếp theo [Ngày 9](day09.md), chúng ta sẽ thảo luận về SonarCloud và tích hợp nó với các công cụ CI/CD khác nhau.
