# 1. Thiết kế giải pháp

**Bối cảnh:** Sử dụng AI để kiểm tra đơn hàng và phân bổ xe giao hàng trong công ty logistics.

Kết hợp 3 kỹ thuật:
- Chain-of-Thought: Phân tích theo từng bước.
- Prompt Chaining: Chia công việc thành nhiều prompt liên kết.
- Rolling Summary: Tóm tắt để tránh mất ngữ cảnh.

# 2. Prompt thực thi

**Prompt 1:** Kiểm tra đơn hàng, phát hiện dữ liệu thiếu, sai hoặc trùng.

**Prompt 2:** Phân loại đơn hàng theo khu vực và khối lượng.

**Prompt 3:** Phân bổ đơn hàng cho các xe, đảm bảo không vượt tải trọng.

**Prompt 4:** Kiểm tra kết quả, sửa lỗi nếu có và tạo bản tóm tắt để tiếp tục khi bị gián đoạn.

# 3. Kết quả chạy thử

**Dữ liệu đầu vào:**

| Mã đơn | Khu vực | Khối lượng |
|---|---|---:|
| DH01 | Hà Nội | 200 kg |
| DH02 | Hà Nội | 300 kg |
| DH03 | Bắc Ninh | 400 kg |
| DH04 | Bắc Ninh | 200 kg |

Mỗi xe có tải trọng tối đa 600 kg.

**Kết quả:**

| Xe | Đơn hàng | Tổng khối lượng |
|---|---|---:|
| Xe A | DH01, DH02 | 500 kg |
| Xe B | DH03, DH04 | 600 kg |

***Không trùng đơn, không vượt tải trọng.***
