# Ngày 9: Triển khai SAST với SonarCloud

SonarCloud là một nền tảng dựa trên đám mây cung cấp phân tích mã tĩnh để giúp các nhà phát triển tìm và sửa các vấn đề về chất lượng mã trong dự án của họ. Nó được thiết kế để hoạt động với nhiều ngôn ngữ lập trình và công cụ khác nhau, bao gồm Java, C#, JavaScript và nhiều hơn nữa.

SonarCloud cung cấp một loạt các tính năng để giúp các nhà phát triển cải thiện chất lượng mã của họ, bao gồm:

- **Phân tích mã tĩnh**: SonarCloud phân tích mã nguồn của một dự án và kiểm tra các vấn đề như vi phạm coding style, lỗi tiềm ẩn, lỗ hổng bảo mật và các vấn đề khác. Nó cung cấp cho các nhà phát triển một báo cáo chi tiết về các vấn đề mà nó tìm thấy, cùng với các gợi ý về cách khắc phục chúng.
- **Đánh giá mã**: SonarCloud tích hợp với các công cụ đánh giá mã như GitHub Pull request, cho phép các nhà phát triển nhận phản hồi về mã của họ từ đồng nghiệp trước khi nó được merge vào nhánh chính. Điều này giúp phát hiện sớm các vấn đề trong quá trình phát triển, giảm nguy cơ lỗi và các vấn đề khác tồn tại trong sản phẩm cuối cùng.
- **Tích hợp liên tục**: SonarCloud có thể được tích hợp vào một pipeline tích hợp liên tục (CI), cho phép nó tự động chạy phân tích mã tĩnh trên mỗi lần commit mã. Điều này giúp các nhà phát triển phát hiện sớm các vấn đề và sửa chúng nhanh chóng, cải thiện chất lượng tổng thể của mã nguồn.
- **Hợp tác**: SonarCloud bao gồm các công cụ cho sự hợp tác nhóm, chẳng hạn như khả năng gán các vấn đề cho các thành viên cụ thể trong nhóm và theo dõi tiến trình đánh giá mã và giải quyết vấn đề.
- **Tùy chỉnh**: SonarCloud cho phép các nhà phát triển tùy chỉnh các quy tắc và cấu hình được sử dụng cho phân tích mã tĩnh, để họ có thể điều chỉnh phân tích phù hợp với nhu cầu cụ thể và tiêu chuẩn mã hóa của nhóm.

Tóm lại, SonarCloud là một công cụ tốt cho các nhà phát triển muốn cải thiện chất lượng mã của họ và giảm nguy cơ các vấn đề trong sản phẩm cuối cùng. Nó giúp các nhóm hợp tác và phát hiện sớm các vấn đề trong quá trình phát triển, dẫn đến phát triển nhanh hơn, hiệu quả hơn và ít lỗi hơn trong sản phẩm cuối cùng.

Tìm hiểu thêm về SonarCloud [tại đây](https://docs.sonarcloud.io/)

### Tích hợp SonarCloud với GitHub Actions

- Đăng ký tài khoản [SonarCloud](https://sonarcloud.io/) bằng tài khoản GitHub của bạn.
- Từ bảng điều khiển, nhấp vào “Import an organization from GitHub”
  
![](images/day09-1.png)
  
- Ủy quyền và cài đặt ứng dụng SonarCloud để truy cập tài khoản GitHub của bạn.
  
![](images/day09-2.png)
  
- Chọn kho lưu trữ (gói miễn phí chỉ hỗ trợ các kho lưu trữ công khai) bạn muốn phân tích và nhấp vào "Install"
![](images/day09-3.png)
  
- Trong SonarCloud, bạn có thể tạo một tổ chức.

![](images/day09-4.png)
![](images/day09-5.png)

- Bây giờ nhấp vào “Analyze a new Project”

![](images/day09-6.png)

- Nhấp vào thiết lập để thêm dự án.

![](images/day09-7.png)

- Bây giờ trên bảng điều khiển SonarCloud, bạn có thể thấy dự án.

![](images/day09-8.png)

- Để thiết lập GitHub Actions, nhấp vào dự án, sau đó vào **Information** > **Last analysis method**

![](images/day09-9.png)

- Nhấp vào **GitHub Actions**

![](images/day09-10.png)

- Điều này sẽ hiển thị một số bước để tích hợp SonarCloud với GitHub actions. Ở đầu trang, bạn sẽ thấy SONAR_TOKEN, chúng ta sẽ thêm nó làm Bí mật GitHub sau.

![](images/day09-11.png)

- Tiếp theo, bạn sẽ thấy tệp yaml cho GitHub Workflow

![](images/day09-12.png)

- Bạn cũng sẽ thấy một tệp cấu hình mà chúng ta sẽ phải thêm vào kho mã nguồn

![](images/day09-13.png)
![](images/day09-14.png)

- Ở cuối trang, tắt phân tích tự động (Automatic Analysis)
![](images/day09-15.png)

- Bây giờ đi đến code repo và thêm cấu hình `sonar-project.properties` vào thư mục gốc.

```yaml
sonar.projectKey=prateekjaindev_nodejs-todo-app-demo
sonar.organization=prateekjaindev

# Đây là tên và phiên bản hiển thị trong giao diện SonarCloud.
#sonar.projectName=nodejs-todo-app-demo
#sonar.projectVersion=1.0

# Đường dẫn tương đối với tệp sonar-project.properties. Thay "\" bằng "/" trên Windows.
#sonar.sources=.

# Mã hóa của mã nguồn. Mặc định là mã hóa hệ thống mặc định
#sonar.sourceEncoding=UTF-8
```

- Cập nhật hoặc thêm workflow GitHub actions với công việc sau trong thư mục `.github/workflows`

```yaml
name: SonarScan
on:
  push:
    branches:
      - main
  pull_request:
    types: [opened, synchronize, reopened]
jobs:
  sonarcloud:
    name: SonarCloud
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0  # Shallow clones should be disabled for a better relevancy of analysis
      - name: SonarCloud Scan
        uses: SonarSource/sonarcloud-github-action@master
        env:
           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}  # Needed to get PR information, if any
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```
- Bây giờ vào GitHub và thêm secrets GitHub có tên SONAR_TOKEN.
![](images/day09-16.png)
- Ngay khi bạn commit các thay đổi, workflow sẽ được kích hoạt.
![](images/day09-17.png)
- Bây giờ sau mỗi lần commit, bạn có thể kiểm tra các báo cáo cập nhật trên bảng điều khiển SonarCloud.
![](images/day09-18.png)

### Cổng quản lý chất lượng (Quality Gates)

Cổng quản lý chất lượng là một chỉ số cho biết liệu mã của bạn có đáp ứng mức chất lượng tối thiểu cần thiết cho dự án của bạn hay không. Nó bao gồm một tập hợp các điều kiện được áp dụng cho kết quả của mỗi lần phân tích. Nếu kết quả phân tích đáp ứng hoặc vượt quá các điều kiện của cổng quản lý chất lượng thì nó sẽ hiển thị trạng thái **Passed**, ngược lại, nó sẽ hiển thị trạng thái **Failed**.

Mặc định SonarCloud đi kèm với cổng chất lượng mặc định “Sonar way”. Bạn có thể chỉnh sửa hoặc tạo mới trong Cài đặt Tổ chức.
![](images/day09-19.png)

### Tài liệu tham khảo

- [Tài liệu SonarCloud](https://docs.sonarcloud.io/)
- [SonarCloud Documentation](https://docs.sonarcloud.io/)
- [How to create Quality gates on SonarQube](https://www.youtube.com/watch?v=8_Xt9vchlpY)
- [Source Code of the repo I used for SAST implementation](https://github.com/prateekjaindev/nodejs-todo-app-demo)

Trong phần tiếp theo trong [ngày 10](day10.md), chúng ta sẽ thảo luận về Phân tích thành phần phần mềm (SCA).
