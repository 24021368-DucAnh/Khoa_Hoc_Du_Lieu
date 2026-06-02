# 🧠 Phân Tích Rủi Ro Trầm Cảm Ở Sinh Viên (Student Depression Analysis)

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg?logo=jupyter&logoColor=white)
![Data Science](https://img.shields.io/badge/Data%20Science-Data%208-success.svg)
![UET](https://img.shields.io/badge/VNU-UET-red.svg)

> **Đề tài nghiên cứu môn Khoa học Dữ liệu - Trường Đại học Công nghệ (UET - VNU)**
> 
> **Phương pháp luận:** Áp dụng nghiêm ngặt khung tư duy từ giáo trình [Computational and Inferential Thinking (Data 8)](https://inferentialthinking.com/).

---

## 🎯 Đặt Vấn Đề: Phía sau giảng đường là những "Khoảng tối" chưa được gọi tên

Đại học thường được ví von là khoảng thời gian rực rỡ nhất của tuổi trẻ. Thế nhưng, đằng sau những điểm số GPA lấp lánh hay những tấm bằng xuất sắc, thực trạng thực tế lại là một bức tranh ngột ngạt hơn rất nhiều. 

Sinh viên ngày nay đang phải đối mặt với một "cơn bão hoàn hảo" của vô vàn áp lực. Đó là những đêm thức trắng ôn thi, nỗi lo nợ môn, gánh nặng tài chính khi sinh hoạt phí leo thang, và cả những áp lực đồng trang lứa (Peer pressure) vô hình nhưng sắc lẹm. Đáng buồn thay, những dấu hiệu của sự kiệt quệ tâm lý — như mất ngủ triền miên hay thói quen ăn uống độc hại — thường bị phớt lờ và gắn mác là "sinh viên thì phải thế", hoặc bị đánh giá một cách định tính là "kém chịu đựng".

**🔍 Câu hỏi nghiên cứu cốt lõi:** > *"Đánh giá tác động của các vấn đề học tập, tài chính và mối quan hệ xã hội ảnh hưởng thế nào đến rủi ro Trầm cảm ở sinh viên?"*

Đứng trước thực trạng đó, nhóm chúng tôi quyết định không nhìn nhận vấn đề tâm lý học dưới góc độ cảm tính, mà giải quyết nó bằng **lăng kính của Khoa học Dữ liệu (Data Science)**.

---

## 📖 Giải Quyết Vấn Đề (The Data Story)

Dự án được triển khai theo đúng 3 giai đoạn của tư duy Khoa học Dữ liệu để lượng hóa những "nỗi đau vô hình" thành con số:

### 1. Biến cảm tính thành Định lượng (Data Preprocessing & EDA)
Chúng tôi bắt đầu với tập dữ liệu thô từ Kaggle. Sau quá trình làm sạch nghiêm ngặt (loại bỏ nhiễu từ người đi làm, xử lý missing values bằng Median), chúng tôi thu được **27,837 mẫu hồ sơ sinh viên tinh khiết**. 
Thông qua Thống kê mô tả và Trực quan hóa, bức tranh bắt đầu lộ diện: Nhóm sinh viên mắc trầm cảm đang phải gánh chịu mức **Áp lực học tập** ($\mu = 4.12$) và **Áp lực tài chính** ($\mu = 3.45$) cao vượt trội so với nhóm bình thường (chỉ ở mức $\mu = 2.28$ và $1.95$).

### 2. Loại bỏ sự ngẫu nhiên bằng Toán học (Statistical Inference)
Những chênh lệch trên màn hình có phải do trùng hợp ngẫu nhiên? Để trả lời, chúng tôi ứng dụng **Định lý Giới hạn Trung tâm (CLT)** để chứng minh tính hợp lệ của phân phối mẫu. Sau đó, sử dụng **A/B Testing** và **Permutation Test**, chúng tôi đã chứng minh bằng toán học ($P\text{-value} < 0.05$) rằng sự khác biệt về tâm lý do áp lực tạo ra là có ý nghĩa thống kê thực sự.

### 3. Xây dựng hệ thống Cảnh báo sớm (Prediction & Machine Learning)
Không chỉ dừng lại ở việc kết luận, chúng tôi lượng hóa sức nặng của từng yếu tố bằng **Hồi quy đa biến (Multiple Regression)** và đưa toàn bộ các đặc trưng này vào mô hình phân lớp **k-Nearest Neighbors (k-NN)**. Kết quả là tạo ra một cỗ máy có khả năng nhận diện sớm những sinh viên có rủi ro cao, mở ra hướng ứng dụng thực tiễn cho các phòng công tác sinh viên.

---

## 💡 Kết Quả Nổi Bật (Key Findings)

- 🚨 **Áp lực học tập là thủ phạm số 1:** Có mối tương quan tuyến tính dương mạnh mẽ nhất ($r \approx 0.45$). Việc chịu mức áp lực cao nhất (5/5) đẩy xác suất rủi ro mắc bệnh vọt lên tới **45%**.
- 🛌 **Lối sống hủy diệt:** Ngủ dưới 5 tiếng/ngày kết hợp với chế độ ăn uống không lành mạnh là "combo" đẩy rủi ro tâm lý lên mức báo động đỏ.
- 🛡️ **Yếu tố bảo vệ:** Sự hài lòng với việc học (Study Satisfaction) có tương quan âm ($r \approx -0.25$), hoạt động như một tấm khiên bảo vệ vững chắc cho tâm lý sinh viên.
- 🤖 **Hiệu suất Mô hình:** Mô hình k-NN đạt độ chính xác (Accuracy) ổn định vượt qua mức Baseline, chứng minh tiềm năng của việc dùng AI để sàng lọc rủi ro tâm lý dựa trên khảo sát diện rộng.

*(Lưu ý học thuật: Các chỉ số tương quan r chỉ ra xu hướng đồng biến/nghịch biến, tuân thủ nguyên tắc "Correlation does not imply Causation" của Data 8).*

---

## 📂 Cấu Trúc Repository

```text
📦 student-depression-analysis
 ┣ 📂 data/
 ┃ ┣ 📂 raw/                # Dữ liệu gốc chưa qua xử lý
 ┃ ┗ 📂 clean/              # Dữ liệu đã làm sạch (0 missing, target nhị phân)
 ┣ 📂 notebooks/
 ┃ ┣ 📜 A_EDA.ipynb         # Thành viên A: Data Prep, EDA, Probability, CLT Simulation
 ┃ ┗ 📜 B_Inference.ipynb   # Thành viên B: A/B Testing, Bootstrapping, Regression, k-NN
 ┣ 📂 output/
 ┃ ┗ 📂 figures/            # Chứa các biểu đồ trực quan hóa (.png) phục vụ báo cáo
 ┣ 📜 README.md             # Tài liệu mô tả dự án (File này)
 ┗ 📜 requirements.txt      # Danh sách các thư viện Python cần thiết
```

---

## 🚀 Hướng Dẫn Cài Đặt & Chạy Code

Dự án được viết hoàn toàn bằng Python trên môi trường Jupyter Notebook. Để chạy lại toàn bộ quy trình:

**Bước 1: Clone dự án về máy**
```bash
git clone [https://github.com/24021368-DucAnh/Khoa_Hoc_Du_Lieu.git](https://github.com/24021368-DucAnh/Khoa_Hoc_Du_Lieu.git)
cd Khoa_Hoc_Du_Lieu
```

**Bước 2: Cài đặt thư viện**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

**Bước 3: Chạy Notebook theo thứ tự**
1. Mở và chạy toàn bộ file `notebooks/A_EDA.ipynb` trước. Code sẽ tự động làm sạch dữ liệu, vẽ biểu đồ và xuất ra file `data/clean/student_depression_clean.csv`.
2. Mở và chạy tiếp file `notebooks/B_Inference.ipynb` để thực hiện các suy luận thống kê và huấn luyện mô hình Machine Learning.

---

## 👥 Nhóm Thực Hiện

* **Ngọ Bùi Đức Anh**
  * **Vai trò:** Data Engineer & Data Analyst
  * **Nhiệm vụ:** Data Cleaning, Descriptive Statistics, Empirical Probability, CLT Simulation, EDA, Correlation Analysis.

* **Phan Doãn Thanh Bằng**
  * **Vai trò:** Data Scientist & ML Engineer
  * **Nhiệm vụ:** Hypothesis Testing, A/B Testing, Bootstrapping, Simple/Multiple Regression, k-NN Classification.

---
*Cảm ơn Thầy đã theo dõi và đánh giá đề tài nghiên cứu của nhóm!*