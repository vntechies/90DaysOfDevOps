# Ngày 13: Các nguyên tắc lập trình an toàn bổ sung

## Quét secret trong Git

Quét secret trong repository là quá trình tìm kiếm các thông tin nhạy cảm như mật khẩu, API key, hoặc khóa mã hóa riêng tư đã vô tình được commit và đẩy lên repository (ví dụ GitHub hoặc GitLab). 

Quá trình này thường sử dụng các công cụ tự động để dò tìm các mẫu hoặc từ khóa đặc trưng cho thông tin nhạy cảm. Mục tiêu là phát hiện và loại bỏ các secret bị lộ nhằm bảo vệ khỏi các rủi ro bảo mật hoặc truy cập trái phép.

### Quét secret Git với Gitleaks

Gitleaks là một công cụ có thể tích hợp vào repository GitHub dưới dạng GitHub Action, giúp quét mã nguồn để phát hiện các thông tin nhạy cảm như thông tin đăng nhập, token, hoặc các secret khác. Action này sẽ chạy công cụ gitleaks trên mã nguồn của chúng ta để kiểm tra xem có secret nào bị commit lên repository hay không.

Để thiết lập Gitleaks GitHub Action, chúng ta cần tạo một file workflow mới tại `.github/workflows/git-secret-scan.yml` trong repository của mình với nội dung sau:

```yaml
name: gitleaks
on:
  pull_request:
  push:
jobs:
  scan:
    name: gitleaks
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - uses: gitleaks/gitleaks-action@v2
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Workflow này thực hiện các bước sau:

1. Định nghĩa workflow tên là `Dependency-Check` chạy trên mọi lần push hoặc pull request.
2. Sử dụng runner `ubuntu-latest`.
3. Chạy quét gitleaks trên toàn bộ repository.
4. Nếu phát hiện secret, action sẽ báo lỗi và dừng pipeline.

Trong ví dụ demo, chúng ta đã thêm AWS Keys vào file .env nên pipeline đã bị lỗi.

![](images/day13-1.png)

Các công cụ quét secret khác

- [**AWS git-secrets**](https://github.com/awslabs/git-secrets)
- **[GitGuardian ggshield](https://github.com/GitGuardian/ggshield)**
- **[TruffleHog](https://github.com/trufflesecurity/trufflehog)**

### Tham khảo
- [Gitleaks GitHub](https://github.com/zricethezav/gitleaks)
- [Gitleaks GitHub Action](https://github.com/gitleaks/gitleaks-action)

## Tạo Dockerfile tốt hơn với Hadolint

Hadolint là một công cụ kiểm tra (linter) cho Dockerfile, giúp phát hiện các lỗi phổ biến và đưa ra gợi ý cải thiện. Hadolint có thể sử dụng trực tiếp trên dòng lệnh, tích hợp vào pipeline CI/CD, hoặc tích hợp vào các trình soạn thảo mã nguồn để kiểm tra thời gian thực.

Để thiết lập kiểm tra Dockerfile với hadolint trên Github Actions, làm theo các bước sau:

1. Tạo file workflow mới, ví dụ `.github/workflows/dockerfile-lint.yml`
2. Thêm nội dung sau vào file để thiết lập workflow:

```yaml
name: Lint Dockerfile
on:
  push:
    branches:
      - main
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2 
      - uses: hadolint/hadolint-action@v2.1.0
        with:
          dockerfile: Dockerfile
```

1. Workflow này sẽ chạy mỗi khi có push lên nhánh "main" và kiểm tra file "Dockerfile" bằng hadolint.
2. Commit và đẩy file workflow mới lên repository.
3. Lần tới khi bạn push lên nhánh "main", Github Actions sẽ tự động chạy kiểm tra và phản hồi nếu phát hiện vấn đề trong Dockerfile.

### Tài liệu tham khảo

- [Hadolint GitHub](https://github.com/hadolint/hadolint)
- [Hadolint Online](https://hadolint.github.io/hadolint/)
- [20 best practices cho Dockerfile](https://sysdig.com/blog/dockerfile-best-practices/)


Tiếp theo, chúng ta sẽ bắt đầu chủ đề **Xây dựng liên tục, Tích hợp liên tục, Kiểm thử liên tục** với [Ngày 14](day14.md), tập trung vào quét lỗ hổng container image dựa trên bài viết của [Anton Sankov](https://twitter.com/a_sankov).