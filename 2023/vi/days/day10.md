# Ngày 10: Tổng quan về Phân tích Thành phần Phần mềm

Phân tích thành phần phần mềm (SCA) là một quy trình giúp các nhà phát triển xác định các thư viện mã nguồn mở, frameworks và thành phần được bao gồm trong các dự án phần mềm của họ. Các công cụ SCA quét mã nguồn của một dự án phần mềm và cung cấp một báo cáo liệt kê tất cả các thư viện mã nguồn mở, frameworks và thành phần đang được sử dụng. Báo cáo này bao gồm thông tin về giấy phép và lỗ hổng của các thư viện và thành phần mã nguồn mở này, cũng như bất kỳ rủi ro bảo mật nào có thể liên quan đến chúng.

Có nhiều lợi ích khi sử dụng các công cụ SCA trong các dự án phát triển phần mềm. Những lợi ích này bao gồm:

1. **Cải thiện bảo mật**: Bằng cách xác định các thư viện và thành phần mã nguồn mở đang được sử dụng trong một dự án, các nhà phát triển có thể đánh giá các rủi ro bảo mật liên quan đến các thư viện và thành phần này. Điều này cho phép họ thực hiện các biện pháp thích hợp để khắc phục bất kỳ lỗ hổng nào và bảo vệ phần mềm của họ khỏi các cuộc tấn công tiềm ẩn.
2. **Tăng cường tuân thủ**: Các công cụ SCA giúp các nhà phát triển đảm bảo rằng họ đang sử dụng các thư viện và thành phần mã nguồn mở tuân thủ các giấy phép thích hợp. Điều này đặc biệt quan trọng đối với các công ty có chính sách tuân thủ nghiêm ngặt và cần đảm bảo rằng họ không vi phạm bất kỳ quyền sở hữu trí tuệ của bên thứ ba nào.
3. **Cải thiện hiệu quả**: Các công cụ SCA có thể giúp các nhà phát triển tiết kiệm thời gian và công sức bằng cách tự động hóa quá trình xác định và theo dõi các thư viện và thành phần mã nguồn mở. Điều này cho phép các nhà phát triển tập trung vào các nhiệm vụ quan trọng hơn, chẳng hạn như xây dựng và kiểm thử phần mềm của họ.
4. **Giảm rủi ro**: Bằng cách sử dụng các công cụ SCA, các nhà phát triển có thể xác định và khắc phục các lỗ hổng trong các thư viện và thành phần mã nguồn mở trước khi chúng trở thành vấn đề. Điều này giúp giảm rủi ro của các vi phạm bảo mật và các vấn đề khác có thể làm tổn hại đến uy tín của phần mềm và công ty.
5. **Nâng cao chất lượng**: Bằng cách xác định và giải quyết bất kỳ lỗ hổng nào trong các thư viện và thành phần mã nguồn mở, các nhà phát triển có thể cải thiện chất lượng tổng thể của phần mềm của họ. Điều này dẫn đến trải nghiệm người dùng tốt hơn và mức độ hài lòng của khách hàng cao hơn.

Ngoài những lợi ích này, các công cụ SCA cũng có thể giúp các nhà phát triển xác định bất kỳ vấn đề pháp lý tiềm ẩn nào có thể phát sinh từ việc sử dụng các thư viện và thành phần mã nguồn mở. Ví dụ, nếu một nhà phát triển đang sử dụng một thư viện được cấp phép theo giấy phép copyleft, họ có thể phải chia sẻ bất kỳ thay đổi nào họ thực hiện đối với thư viện với cộng đồng.

Mặc dù có những lợi ích này, nhưng cũng có một số thách thức liên quan đến SCA:

1. **Quy mô**: Khi việc sử dụng phần mềm mã nguồn mở trở nên phổ biến hơn, số lượng thành phần cần được phân tích đã tăng lên đáng kể. Điều này có thể khiến các tổ chức khó theo dõi tất cả các thành phần mà họ đang sử dụng và xác định bất kỳ vấn đề tiềm ẩn nào.
2. **Độ phức tạp**: Nhiều ứng dụng phần mềm được tạo thành từ một số lượng lớn các thành phần, một số trong đó có thể đã được thêm vào nhiều năm trước và không còn được duy trì đều đặn. Điều này có thể khiến việc hiểu đầy đủ phạm vi của một ứng dụng và xác định bất kỳ vấn đề tiềm ẩn nào trở nên khó khăn.
3. **Dương tính giả (False positives)**: Các công cụ SCA có thể tạo ra một số lượng lớn các cảnh báo, một số trong đó có thể là dương tính giả. Điều này có thể gây khó chịu cho các nhà phát triển phải xem xét và loại bỏ các cảnh báo này, và nó cũng có thể dẫn đến sự thiếu tin tưởng vào chính công cụ SCA.
4. **Thiếu tiêu chuẩn hóa**: Không có cách tiêu chuẩn để thực hiện SCA, và các công cụ và phương pháp khác nhau có thể tạo ra các kết quả khác nhau. Điều này có thể khiến các tổ chức khó so sánh kết quả của các công cụ SCA khác nhau và xác định công cụ nào là tốt nhất cho nhu cầu của họ.

Nhìn chung, các công cụ SCA cung cấp một số lợi ích cho các nhà phát triển phần mềm và có thể giúp cải thiện bảo mật, tuân thủ, hiệu quả, quản lý rủi ro và chất lượng của các dự án phần mềm. Bằng cách sử dụng các công cụ này, các nhà phát triển có thể đảm bảo rằng họ đang sử dụng các thư viện và thành phần mã nguồn mở tuân thủ các giấy phép thích hợp, không có lỗ hổng và có chất lượng cao. Điều này giúp bảo vệ uy tín của phần mềm và công ty, và dẫn đến trải nghiệm người dùng tốt hơn.

### Công cụ SCA (Mã nguồn mở hoặc Miễn phí)

- **[OWASP Dependency Check](https://owasp.org/www-project-dependency-check/)**: Dependency-Check là một công cụ Phân tích Thành phần Phần mềm (SCA) cố gắng phát hiện các lỗ hổng công khai được tiết lộ trong các phụ thuộc của một dự án. Nó làm điều này bằng cách xác định xem có một định danh Common Platform Enumeration (CPE) cho một phụ thuộc nhất định hay không. Nếu tìm thấy, nó sẽ tạo ra một báo cáo liên kết đến các mục CVE liên quan.
- **[Snyk](https://snyk.io/product/open-source-security-management/)**: Snyk Open Source cung cấp một giải pháp SCA ưu tiên cho nhà phát triển, giúp các nhà phát triển tìm, ưu tiên và khắc phục các lỗ hổng bảo mật và vấn đề giấy phép trong các phụ thuộc mã nguồn mở.

### Tài nguyên

- [Phân tích Thành phần Phần mềm (SCA): Những điều bạn nên biết](https://www.aquasec.com/cloud-native-academy/supply-chain-security/software-composition-analysis-sca/)
- [Phân tích Thành phần Phần mềm 101: Biết những gì bên trong ứng dụng của bạn - Magno Logan](https://www.youtube.com/watch?v=qyVDHH4T1oo)

Trong phần tiếp theo [Ngày 11](day11.md), chúng ta sẽ thảo luận về Dependency Check và tích hợp nó với GitHub Actions.
