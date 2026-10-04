# Reflection

Anti-pattern tôi thấy dễ gặp nhất là **coi file nhỏ chỉ là vấn đề hiệu năng truy vấn**. Với dữ liệu quan sát LLM, mỗi request có thể được ghi thành một file để giảm độ trễ ingest. Cách này đơn giản lúc đầu, nhưng khi lưu lượng tăng, metadata, thao tác liệt kê object và chi phí maintenance đều tăng mạnh. NB2 và NB6 cho thấy compaction giảm rõ số file, cải thiện file skipping và chi phí vận hành.

Để phòng tránh, tôi sẽ đặt mục tiêu kích thước file, gom dữ liệu theo micro-batch, theo dõi tỷ lệ metadata:data và số file mỗi partition. Compaction nên chạy theo ngưỡng; clustering chỉ dành cho cột thường được lọc. Tôi sẽ đo trước/sau bằng file count, min/max statistics và latency thay vì mặc định OPTIMIZE luôn có lợi. Retention phải an toàn cho reader đang chạy; orphan chưa từng commit cần quy trình đối chiếu riêng vì VACUUM không nhìn thấy chúng.

Tôi dùng AI để chạy kiểm thử, đóng gói notebook, rà rubric và soạn bản nháp; chi tiết tại [AI_USAGE.md](AI_USAGE.md). Tôi chịu trách nhiệm đọc lại và giải thích kết quả.
