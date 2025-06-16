### Ngày 11: Triển khai SCA với OWASP Dependency Check

OWASP Dependency Check là một công cụ mã nguồn mở kiểm tra các dependencies của dự án để tìm các lỗ hổng đã được biết. Nó có thể được sử dụng để xác định các dependencies có lỗ hổng đã biết và xác định xem có bất kỳ lỗ hổng nào trong số đó có trong ứng dụng hay không.

Công cụ này hoạt động bằng cách quét các dependencies của một dự án và kiểm tra chúng với cơ sở dữ liệu các lỗ hổng đã biết. Nếu tìm thấy lỗ hổng, công cụ sẽ báo cáo lỗ hổng cùng với mã định danh CVE (Common Vulnerabilities and Exposures) liên quan, một mã định danh tiêu chuẩn cho các lỗ hổng an ninh mạng đã được công khai.

Để sử dụng OWASP Dependency Check, bạn sẽ cần bao gồm nó như một phần của quy trình xây dựng của mình. Có các tích hợp sẵn có cho nhiều công cụ xây dựng khác nhau, bao gồm Maven, Gradle và Ant. Bạn cũng có thể sử dụng giao diện dòng lệnh (CLI) để quét các dependencies của mình.

OWASP Dependency Check đặc biệt hữu ích để xác định các lỗ hổng trong các thư viện và framework của bên thứ ba mà ứng dụng của bạn sử dụng. Các loại dependencies này có thể giới thiệu các lỗ hổng vào ứng dụng của bạn nếu chúng không được quản lý đúng cách. Bằng cách quét các dependencies của bạn thường xuyên, bạn có thể đảm bảo rằng bạn nhận thức được bất kỳ lỗ hổng nào và thực hiện các bước để giải quyết chúng.

Điều quan trọng cần lưu ý là OWASP Dependency Check không phải là sự thay thế cho các thực hành mã hóa an toàn và nên được sử dụng cùng với các biện pháp bảo mật khác. Cũng quan trọng là cập nhật các dependencies thường xuyên để đảm bảo rằng bạn đang sử dụng phiên bản an toàn nhất có thể.

### Tích hợp Dependency Check với GitHub Actions

Để sử dụng Dependency Check với GitHub Actions, bạn có thể tạo một tệp workflow trong thư mục `.github/workflows` của kho lưu trữ của bạn. Dưới đây là một ví dụ về workflow chạy Dependency Check trên mỗi lần đẩy lên nhánh `main`:

```yaml
name: Dependency-Check
on:
  push:
    branches:
      - main
  pull_request:
    types: [opened, synchronize, reopened]
jobs:
  dependency-check:
    name: Dependency-Check
    runs-on: ubuntu-latest
    steps: 
      - name: Download OWASP Dependency Check
        run: |
          VERSION=$(curl -s https://jeremylong.github.io/DependencyCheck/current.txt)
          curl -sL "https://github.com/jeremylong/DependencyCheck/releases/download/v$VERSION/dependency-check-$VERSION-release.zip" --output dependency-check.zip
          unzip dependency-check.zip
      - name: Run Dependency Check
        run: |
          ./dependency-check/bin/dependency-check.sh --out report.html --scan .
          rm -rf dependency-check*

      - name: Upload Artifacts
        uses: actions/upload-artifact@v2
        with:
          name: artifacts
          path: report.html
```

Workflow này thực hiện các bước sau:

1. Định nghĩa một workflow gọi là `Dependency-Check` chạy trên mỗi lần đẩy lên nhánh `main`.
2. Chỉ định rằng workflow sẽ chạy trên runner `ubuntu-latest`.
3. Tải xuống và cài đặt Dependency Check.
4. Chạy Dependency Check trên thư mục hiện tại (`.`) và tạo một báo cáo trong tệp report.html.
5. Xóa các tệp Dependency Check đã tải xuống.
6. Upload tệp báo cáo như một artifact.

Bạn có thể tải xuống báo cáo từ Artifacts và mở nó trong trình duyệt.

![](images/day11-1.png)

Bạn có thể tùy chỉnh workflow này để phù hợp với nhu cầu của mình. Ví dụ, bạn có thể chỉ định các nhánh khác nhau để chạy workflow, hoặc chỉ định các dependencies khác nhau để kiểm tra. Bạn cũng có thể cấu hình Dependency Check để tạo báo cáo ở định dạng cụ thể (ví dụ: HTML, XML, JSON) và lưu nó vào kho lưu trữ.

### Tài liệu tham khảo

- [Dependency Check Documentation](https://jeremylong.github.io/DependencyCheck/)
- [Source Code of the repo I used for SCA implementation](https://github.com/prateekjaindev/nodejs-todo-app-demo)

Trong phần tiếp theo ở [ngày 12](day12.md), chúng ta sẽ thảo luận về review bảo mật cho code.
