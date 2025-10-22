# Frida Gadget Auto Release

🤖 Tự động kiểm tra và phát hành phiên bản Frida Gadget mới nhất

## 📋 Tính năng

- ✅ Tự động kiểm tra phiên bản Frida mới mỗi ngày
- ✅ Tải xuống Frida Gadget cho nhiều nền tảng và kiến trúc
- ✅ Đóng gói và tạo release tự động
- ✅ Theo dõi phiên bản trong repository
- ✅ Tránh tạo release trùng lặp

## 🎯 Nền tảng được hỗ trợ

### Android
- ARM (32-bit)
- ARM64 (64-bit)
- x86 (32-bit)
- x86_64 (64-bit)

### iOS
- Universal (ARM64)

### Linux
- x86 (32-bit)
- x86_64 (64-bit)
- ARM (32-bit)
- ARM64 (64-bit)

## 📦 File tải xuống

Mỗi release bao gồm:
- `frida-gadget-{version}-android.zip` - Tất cả kiến trúc Android
- `frida-gadget-{version}-ios.zip` - Kiến trúc iOS
- `frida-gadget-{version}-linux.zip` - Tất cả kiến trúc Linux
- `frida-gadget-{version}-all-platforms.zip` - Tất cả nền tảng

## 🔄 Cách hoạt động

1. **Kiểm tra tự động**: Workflow chạy mỗi ngày lúc 00:00 UTC
2. **So sánh phiên bản**: Kiểm tra `version.txt` trong repo với phiên bản mới nhất từ Frida
3. **Tải xuống**: Nếu có phiên bản mới, tải về tất cả Frida Gadget
4. **Đóng gói**: Giải nén và nén lại thành ZIP files theo nền tảng
5. **Tạo Release**: Tự động tạo GitHub Release với các file đính kèm
6. **Cập nhật version**: Lưu phiên bản mới vào `version.txt` và `version-info.json`

## 📄 File theo dõi phiên bản

### version.txt
Chứa phiên bản hiện tại (ví dụ: `17.4.0`)

### version-info.json
Chứa thông tin chi tiết:
```json
{
  "version": "17.4.0",
  "updated_at": "2025-10-22 03:40:58 UTC",
  "release_url": "https://github.com/lehuutho2828/your-repo/releases/tag/17.4.0",
  "frida_release_url": "https://github.com/frida/frida/releases/tag/17.4.0",
  "platforms": {
    "android": ["arm", "arm64", "x86", "x86_64"],
    "ios": ["universal"],
    "linux": ["x86", "x86_64", "arm", "arm64"]
  }
}
```

## 🚀 Chạy thủ công

1. Vào tab **Actions** trong repository
2. Chọn workflow **Frida Gadget Release**
3. Click **Run workflow**
4. Chọn branch và click **Run workflow**

## ⚙️ Cấu hình

Workflow được cấu hình trong `.github/workflows/frida-gadget-release.yml`

### Thay đổi lịch chạy

Sửa dòng cron trong workflow:
```yaml
schedule:
  - cron: '0 0 * * *'  # Chạy mỗi ngày lúc 00:00 UTC
```

### Permissions

Workflow yêu cầu quyền:
- `contents: write` - Để tạo release và commit file version

## 📊 Kiểm tra phiên bản hiện tại

Xem phiên bản hiện tại trong file [version.txt](version.txt)

Xem thông tin chi tiết trong file [version-info.json](version-info.json)

## 🔗 Liên kết

- [Frida Official Releases](https://github.com/frida/frida/releases)
- [Frida Documentation](https://frida.re/docs/home/)

## 📝 License

Workflow này là mã nguồn mở. Frida Gadget tuân theo license của [Frida Project](https://github.com/frida/frida).
