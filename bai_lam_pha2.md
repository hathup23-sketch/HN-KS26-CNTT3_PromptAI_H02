# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:**PHAM THI THU HA
- **Lớp:**CNTT3
- **Link repository Pha2:**https://github.com/hathup23-sketch/HN-KS26-CNTT3_PromptAI_H02
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé vào cổng ra JSON

**KET QUA AI**

```text
[
  {
    "loai_ve": "VECH",
    "ngay_choi": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_tu": "nho",
    "ghi_chu": null
  },
  {
    "loai_ve": "VECN",
    "ngay_choi": "2027-01-03",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_tu": null,
    "ghi_chu": "Một người đang bó bột tay"
  },
  {
    "loai_ve": "VEVIP",
    "ngay_choi": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_tu": "lon",
    "ghi_chu": "một bạn đi xe lăn"
  }
]
```

**Link trò chuyện:**https://share.gemini.google/ZZGcjz5fOwXu

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Tiền vé người lớn: Đoàn có 8 người lớn, mua vé VECN nên phép tính là:$8 \times 250.000 = 2.000.000\text{ đồng}$Tiền vé trẻ em: Có 4 trẻ cao từ 1 m đến 1,4 m (1,05 m; 1,15 m; 1,2 m; 1,3 m), mỗi vé tính 60% giá vé người lớn ($250.000 \times 60\% = 150.000\text{ đồng}$); 2 bé dưới 1 m được miễn phí (0 đồng). Phép tính là:$4 \times (250.000 \times 0,6) + 2 \times 0 = 4 \times 150.000 = 600.000\text{ đồng}$Tiền vé: Cộng tiền vé người lớn và tiền vé trẻ em:$2.000.000 + 600.000 = 2.600.000\text{ đồng}$Giảm giá đoàn: Đoàn có 8 người lớn (đủ điều kiện giảm 10% trên tiền vé). Số tiền được giảm là:$2.600.000 \times 10\% = 260.000\text{ đồng}$
Tiền vé sau giảm là:$2.600.000 - 260.000 = 2.340.000\text{ đồng}$Phụ thu: Đoàn thuê 6 áo phao, giá 40.000 đồng/chiếc (không giảm giá). Phép tính là:$6 \times 40.000 = 240.000\text{ đồng}$Tổng tiền: Cộng tiền vé sau giảm và phụ thu:$2.340.000 + 240.000 = 2.580.000\text{ đồng}$[RESULT:2.580.000đồng]
```

**Link trò chuyện:**https://share.gemini.google/4jO2xcuI66BI

### b) Kiểm tra kết quả AI

AI trả lời đúng đưa ra đc [RESULT:2.580.000đồng]

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "dong_khu_choi",
  "so_khach": 4,
  "so_khu_bi_dong": 2,
  "tom_tat": "Khách hàng 4 người khiếu nại khu trượt nước và sóng nhân tạo đóng cửa cả ngày không báo trước."
}
```

**Link trò chuyện:**https://share.gemini.google/l7TMFUErMI5F

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 0/5 | **Câu bị lỗi:** "Vé chiều bên em 150k thôi ạ, mát rượi luôn. Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha."<br>

<br>**Lý do sai:** Không có cơ sở đối chiếu giá vé chuẩn và chính sách hoàn tiền khi đóng cửa do thời tiết vì `<thang_diem>` không cung cấp thông tin chuẩn. Hơn nữa, việc cam kết "hoàn tiền mặt 100%" mà chưa có xác nhận chính sách chuẩn tiềm ẩn rủi ro sai lệch quy định. | "Dạ, giá vé vào buổi chiều hiện tại bên em là [giá chuẩn theo bảng giá]. Trường hợp khu vực đóng cửa do thời tiết xấu, bên em áp dụng chính sách [chính sách chuẩn theo quy định, ví dụ: hoàn tiền/đổi vé] cho quý khách ạ." |
| **Đầy đủ (30%)** | 0/3 | **Câu bị lỗi:** "Hello chị! Vé chiều bên em 150k thôi ạ, mát rượi luôn. Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha. Cần gì ới em nhé!"<br>

<br>**Lý do sai:** Câu trả lời không thể hiện việc đáp ứng đầy đủ hai câu hỏi của khách (do thiếu dữ liệu câu hỏi gốc) và hoàn toàn thiếu lời mời khách cung cấp ngày chơi, số lượng vé để tiến hành đặt vé. | "Dạ em xin giải đáp [nội dung trả lời câu hỏi 1 và câu hỏi 2]. Để em hỗ trợ đặt vé cho mình, chị vui lòng cho em xin ngày đi chơi và số lượng vé dự kiến ạ." |
| **Giọng điệu (20%)** | 0.5/2 | **Câu bị lỗi:** "Hello chị! Vé chiều bên em 150k thôi ạ, mát rượi luôn. Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha. Cần gì ới em nhé!"<br>

<br>**Lý do sai:** Sử dụng các từ ngữ mang tính suồng sã, thiếu chuẩn mực trong tư vấn dịch vụ chuyên nghiệp như "Hello", "mát rượi luôn", "nha", "ới", "nhé". | "Dạ em chào chị ạ! Giá vé chiều bên em là [giá chuẩn]. Nếu mưa dẫn đến đóng cửa, bên em sẽ [chính sách chuẩn] ạ. Chị cho em xin ngày đi và số lượng vé để em đặt giúp mình nhé. Chị cần hỗ trợ thêm thông tin nào cứ báo em ạ." |
| **Tổng điểm** | **0.5/10** | — | — |
```

**Link trò chuyện:**https://share.gemini.google/njhmksq0dNgz
