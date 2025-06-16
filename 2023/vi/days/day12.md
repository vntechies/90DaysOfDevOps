# Ngày 12: Các nguyên tắc lập trình an toàn

Đánh giá mã nguồn an toàn là quá trình kiểm tra và đánh giá mức độ an toàn của một ứng dụng hoặc hệ thống phần mềm bằng cách xem xét mã nguồn để phát hiện các lỗ hổng hoặc điểm yếu tiềm ẩn. Quá trình này là một phần thiết yếu nhằm đảm bảo ứng dụng được bảo mật và có thể chống lại các cuộc tấn công từ tội phạm mạng.

Có một số bước trong quy trình đánh giá mã nguồn an toàn:

1. **Xác định phạm vi đánh giá**: Bước đầu tiên là xác định phạm vi đánh giá, bao gồm loại ứng dụng được đánh giá và các mối quan tâm về bảo mật cần được giải quyết.
2. **Thiết lập nhóm đánh giá**: Nhóm đánh giá nên bao gồm những người có chuyên môn ở các lĩnh vực khác nhau như bảo mật, lập trình và kiểm thử. Nhóm cũng nên có những người am hiểu về ứng dụng được đánh giá.
3. **Chuẩn bị mã nguồn để đánh giá**: Trước khi bắt đầu đánh giá, mã nguồn cần được tổ chức lại để dễ hiểu và dễ kiểm tra hơn. Việc này có thể bao gồm chia nhỏ mã nguồn thành các phần nhỏ hơn hoặc thêm chú thích để giải thích mục đích của từng đoạn mã.
4. **Tiến hành đánh giá**: Trong quá trình đánh giá, nhóm sẽ kiểm tra mã nguồn để phát hiện các lỗ hổng và điểm yếu. Việc này có thể bao gồm kiểm tra các thực hành lập trình không an toàn như sử dụng mật khẩu cứng trong mã, dữ liệu chưa mã hóa, hoặc các lỗ hổng trong kiến trúc ứng dụng.

5. **Ghi nhận phát hiện**: Khi nhóm phát hiện các lỗ hổng hoặc điểm yếu, họ cần ghi nhận lại trong một báo cáo. Báo cáo nên bao gồm chi tiết về lỗ hổng, tác động tiềm ẩn và khuyến nghị cách khắc phục.
6. **Khắc phục lỗ hổng**: Sau khi hoàn thành đánh giá, nhóm nên phối hợp với nhóm phát triển để sửa các lỗ hổng hoặc điểm yếu đã phát hiện. Việc này có thể bao gồm cập nhật mã nguồn, triển khai thêm các biện pháp bảo mật hoặc cả hai.

Có nhiều công cụ và kỹ thuật hỗ trợ quá trình đánh giá mã nguồn an toàn, bao gồm:

1. **Công cụ phân tích tĩnh**: Các công cụ này phân tích mã nguồn mà không cần thực thi, giúp phát hiện các lỗ hổng như tràn bộ đệm, SQL injection, và cross-site scripting.
2. **Công cụ phân tích động**: Các công cụ này phân tích mã khi đang thực thi, cho phép nhóm đánh giá phát hiện các lỗ hổng mà phân tích tĩnh không nhận ra được.
3. **Hướng dẫn đánh giá mã nguồn**: Nhiều tổ chức xây dựng các hướng dẫn đánh giá mã nguồn, nêu rõ các loại lỗ hổng cần kiểm tra và các thực hành tốt nhất để khắc phục.
4. **Đánh giá ngang hàng (peer review)**: Đây là quá trình các lập trình viên khác cùng kiểm tra mã nguồn, giúp phát hiện thêm các lỗ hổng tiềm ẩn.

Đánh giá mã nguồn an toàn là một quá trình liên tục, nên được thực hiện ở nhiều giai đoạn trong vòng đời phát triển phần mềm. Điều này bao gồm kiểm tra mã trước khi triển khai lên môi trường sản xuất cũng như kiểm tra định kỳ để đảm bảo ứng dụng luôn an toàn theo thời gian.

Tóm lại, đánh giá mã nguồn an toàn là một thành phần quan trọng để đảm bảo ứng dụng được bảo mật. Bằng cách phát hiện và xử lý các lỗ hổng ngay từ sớm trong quá trình phát triển, tổ chức có thể giảm thiểu rủi ro bị tấn công và bảo vệ hệ thống, dữ liệu khỏi các mối đe dọa tiềm ẩn.

Tôi khuyến khích bạn xem video này để hiểu cách phân tích mã nguồn giúp phát hiện lỗ hổng trong các dự án lớn của doanh nghiệp.

[![Final video of fixing issues in your code in VS Code](https://img.youtube.com/vi/fb-t3WWHsMQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=fb-t3WWHsMQ)

### Tài liệu tham khảo

- [How to Analyze Code for Vulnerabilities](https://www.youtube.com/watch?v=A8CNysN-lOM&t)
- [What Is A Secure Code Review And Its Process?](https://valuementor.com/blogs/source-code-review/what-is-a-secure-code-review-and-its-process/)

Vào phần tiếp trong [ngày 13](day13.md), chúng ta sẽ thảo luận về các nguyên tắc lập trình an toàn bổ sung với một số bài thực hành.