# DACN-DriveAware
Đồ án chuyên ngành - Học máy &amp; Ứng dụng - Bùi Nhựt Phi

# DriveAware: Hệ thống cảnh báo buồn ngủ và mất tập trung cho tài xế dựa trên chỉ số PERCLOS và mốc khuôn mặt

## Câu định vị: Đồ án giải quyết vấn đề phát hiện sớm các dấu hiệu buồn ngủ và mất tập trung nhằm giảm nguy cơ lái xe không an toàn cho tài xế phương tiện cơ giới đường bộ từ 4 bánh trở lên, đo bằng: Độ chính xác khi phát hiện trạng thái tài xế, tỷ lệ cảnh báo nhầm và thời gian phản hồi của hệ thống AI trong điều kiện thử nghiệm.

## Bảng đối chứng Trước – Sau:
| Thành phần | Trạng thái Trước | Trạng thái Sau | Mục tiêu / Kỳ vọng | Công cụ / Phương pháp đo | Bằng chứng lưu trữ |

| **1. Chỉ số chính** | Số cảnh báo nhầm cao do nhiễu | Giảm ít nhất 50% số cảnh báo nhầm | Giảm $\ge 50\%$ cảnh báo giả | Đếm số lần cảnh báo sai trên 1 giờ video | Thư mục `/eval_logs/` | <br>
| **2. Độ chính xác** | Recall biến động theo góc nhìn và kính đeo | Recall duy trì ổn định | Recall $\ge 90\%$ | So sánh với nhãn chuẩn | Bảng kết quả Chương 4 | <br>
| **3. Độ trễ** | Phản hồi nhanh nhưng không lọc nhiễu | Độ trễ trung vị nằm trong ngưỡng cho phép | Trung vị $\le 650$ ms | Đo bằng Timestamp trong vòng lặp frame | Log hệ thống realtime | <br>
| **4. Mô hình xử lý** | Chỉ dùng ngưỡng EAR đơn lẻ | Kết hợp PERCLOS, MAR, Head Pose và Hysteresis | Tích hợp đa tín hiệu theo thời gian | Code Python / MediaPipe / PyTorch | Thư mục `/src/` | <br>
| **5. Dữ liệu kiểm thử** | Chạy trên bộ video thô | Chạy trên tập eval độc lập | Đảm bảo không rò rỉ dữ liệu | Bộ video test có nhãn thời gian | Thư mục `/dataset/` | <br>
| **6. Triển khai** | Script chạy dòng lệnh đơn lẻ | Giao diện giám sát + Cảnh báo âm thanh + Log ẩn danh | Hoàn thiện bản MVP ứng dụng thực tế | Chạy trực tiếp qua camera/video mô phỏng | Video Demo & Báo cáo | <br>
