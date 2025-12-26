# Nghiên cứu và xây dựng mô hình AI nhận diện sai lệch nhận thức trong văn bản hội thoại

## Giới thiệu
Khoá luận này tập trung vào bài toán **nhận diện và phân loại sai lệch nhận thức (cognitive biases)** trong **văn bản hội thoại tiếng Việt**, một hướng nghiên cứu còn tương đối mới trong cộng đồng Xử lý Ngôn ngữ Tự nhiên (NLP) tại Việt Nam.

Mục tiêu của nghiên cứu là xây dựng một hệ thống học máy có khả năng:
- Tự động nhận diện sự tồn tại của sai lệch nhận thức trong hội thoại
- Phân loại các loại sai lệch nhận thức phổ biến
- Cung cấp khả năng **giải thích mô hình (Explainable AI)** nhằm tăng tính minh bạch và khả năng ứng dụng trong các lĩnh vực liên ngành như tâm lý học và khoa học xã hội

**Lưu ý**: Đề tài chỉ dừng lại ở mức **nhận diện và phân loại**, không đi sâu vào việc can thiệp, điều trị hay tác động tâm lý đối với người tham gia hội thoại.

---

## Cơ sở lý thuyết
Khóa luận được xây dựng dựa trên:
- Lý thuyết **Cognitive Behavioral Therapy (CBT)** của Aaron T. Beck
- Khái niệm **sai lệch nhận thức** (cognitive distortions)
- Phân tầng nhận thức: suy nghĩ tự động, lược đồ nhận thức (schema) và niềm tin cốt lõi (core beliefs)

---

## 📊 Dữ liệu
- **Bộ dữ liệu**: Dịch từ các bộ dữ liệu: C2D2 (Cognitive Distortion Dialogue Dataset), Da Dataset (Generalizable Cross-Lingual Cognitive Distortion Detection), PsyQA (Detection and Positive Reconstruction of Cognitive Distortions in Text)
- **Loại dữ liệu**: Dữ liệu câu đơn từ các tình huống trong cuộc sống tiếng Việt 
- **Nhãn**: Các loại sai lệch nhận thức phổ biến
- **Tình trạng truy cập**: Dữ liệu **có điều kiện** (restricted access), cần gửi email xin phép chủ sở hữu

Vì lý do bản quyền, **bộ dữ liệu không được public trực tiếp trong repository này**.

---

## Mô hình sử dụng
Nghiên cứu tập trung vào các mô hình **được tiền huấn luyện riêng cho tiếng Việt**, bao gồm:

- **PhoBERT (Base / Large)** – Encoder-only, phù hợp cho bài toán phân loại
- **ViDeBERTa-Base** – Cải tiến từ RoBERTa cho tiếng Việt
- **BARTpho (Syllable-level)** – Seq2Seq, được dùng cho các thí nghiệm so sánh

Lý do lựa chọn các mô hình này là do khả năng **hiểu ngữ cảnh và đặc thù ngôn ngữ tiếng Việt** tốt hơn so với các mô hình đa ngôn ngữ.

Ngoài ra còn sử dụng mô hình Qwen2.5-1.5B-Instruct và Qwen2.5-3B-Instruct để thử nghiệm hiệu quả trong bài toán này và kèm thêm phần giải thích.

---

## Phương pháp
- Fine-tuning các mô hình Transformer cho bài toán phân loại
- Trích xuất đặc trưng ngôn ngữ:
  - Ngữ nghĩa
  - Cú pháp
  - Cảm xúc (sentiment)
  - Tương tác hội thoại
- Áp dụng **Explainable AI**:
  - Attention visualization
  - Feature importance
  - Phân tích token-level

---

## Đánh giá
- Các chỉ số đánh giá:
  - Accuracy
  - Precision
  - Recall
  - F1-score
- So sánh hiệu năng giữa các mô hình
- Phân tích định tính kết quả dựa trên góc nhìn tâm lý học

---

