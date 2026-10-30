# Bài 7: Giải cứu dữ liệu nhóm startup bị mất trên máy tính cá nhân

## Phần 1: Phân tích vấn đề

**1. Đánh giá rủi ro từng hạng mục**

- **Business Plan (20 trang):** rủi ro 100%, mức **Cao**. Chỉ lưu trên ổ đĩa, không có bản sao lưu hay Cloud. Hỏng ổ cứng là mất hết.
- **Mã nguồn giao diện (HTML/CSS):** rủi ro 75% - 80%, mức **Cao**. Lưu trên USB, dễ hỏng phần cứng, nhiễm virus hoặc lỗi file khi rút ra đột ngột.
- **Database danh sách test user:** rủi ro 50% - 60%, mức **Trung bình**. Lưu trên file Excel máy cá nhân của thành viên B, bản cập nhật đã trễ 2 tuần. Không mất trắng dữ liệu gốc nhưng mất 2 tuần công sức cập nhật và kiểm tra.
- **Slide Pitch (PowerPoint):** rủi ro 30% - 40%, mức **Thấp**. Lưu trên Zalo Cloud, file vẫn còn nhưng không rõ là bản mới nhất, có nguy cơ ghi đè bản cũ lên bản mới.
- **Tài liệu SRS (Word):** rủi ro 30% - 40%, mức **Thấp**. Gửi qua lại bằng file đính kèm Email nhiều lần. Không mất dữ liệu nhưng tốn thời gian tìm kiếm, dễ tổng hợp sai bản chính thức.

**2. Thuật ngữ: Version Sprawl** (phân mảnh phiên bản, nhiều phiên bản sinh ra không kiểm soát)

- **Nguyên nhân:** nhóm sửa file, gửi qua Zalo/Email, người khác tải về sửa tiếp rồi lại gửi đi. Mỗi người sửa độc lập trên máy riêng, không có cơ chế khóa file, nên liên tục sinh ra thêm các bản "rác".
- **Hậu quả với dự án phần mềm:**
  - Xung đột và ghi đè dữ liệu: thành viên C có thể lấy nhầm bản cũ của A để sửa tiếp, xóa mất tính năng B vừa hoàn thiện hôm qua.
  - Lãng phí thời gian vì phải so sánh từng dòng giữa các bản.

## Phần 2: Sửa lỗi và nghiệm thu

**3. Quy trình lưu trữ mới**

1. **Local:** mở file trực tiếp từ ổ đĩa D, chỉnh sửa, nhấn `Ctrl + S` để lưu trên máy.
2. **Auto Sync:** cài Google Drive for Desktop và bật **Sync with Google Drive**. Khi nhấn `Ctrl + S`, file tự đồng bộ lên Cloud và hiện biểu tượng tích xanh.
3. **Cloud:** file nằm trong Drive của nhóm CampusPay, tự động ghi lại lịch sử chỉnh sửa (Version History), các thành viên khác thấy ngay phiên bản mới nhất.

**4. Biểu tượng trạng thái trên File Explorer**

- **Hai mũi tên xoay tròn màu xanh dương:** file đang đồng bộ.
- **Dấu chấm than màu đỏ:** quá trình đồng bộ bị gián đoạn (ví dụ gập máy đột ngột).
- **Dấu tích xanh lá:** file đã an toàn trên Cloud.

**Nếu gập máy ngay khi đang đồng bộ:** quá trình tải lên bị ngắt vì mất kết nối Internet giữa chừng. Nội dung mới sửa vẫn nằm trên ổ cứng máy đó, nhưng trên Cloud vẫn chỉ có phiên bản cũ.

**Việc cần làm trước khi tắt hoặc gập máy:** kiểm tra biểu tượng trạng thái, đảm bảo file vừa sửa đã chuyển sang **tích xanh** thay vì đang xoay tròn.
