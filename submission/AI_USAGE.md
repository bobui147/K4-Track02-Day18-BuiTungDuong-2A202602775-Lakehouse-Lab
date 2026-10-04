# Khai báo sử dụng AI

## Công cụ

- OpenAI Codex.

## Phạm vi hỗ trợ

- Đọc README, checkpoints, rubric, rules và hướng dẫn nộp bài.
- Kiểm tra môi trường Windows, chạy smoke test, pytest và tám notebook.
- Thực thi các notebook bằng `nbconvert` để lưu output thật.
- Đối chiếu các metric với ngưỡng rubric và kiểm tra notebook không có output lỗi.
- Tạo cấu trúc `submission/`, bản nháp reflection và ảnh minh chứng từ output đã chạy.

## Cam kết

Không tạo số liệu hoặc output giả, không xóa assertion và không hạ ngưỡng PASS. Mọi metric trong notebook đến từ lần chạy thực tế trên repo này. Người nộp có trách nhiệm đọc lại, tự giải thích được mã nguồn/kết quả và chỉnh phần reflection nếu quan điểm cá nhân chưa được phản ánh chính xác.
