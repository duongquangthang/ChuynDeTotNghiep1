# PHÁT HIỆN NHÓM NGUY CƠ CAO VỀ SỨC KHỎE TÂM THẦN THÔNG QUA PHÂN TÍCH TƯƠNG TÁC ĐỒ THỊ VÀ THUẬT TOÁN PHÁT HIỆN CỘNG ĐỒNG

Mục tiêu của đề tài là xây dựng mô hình nhận diện các nhóm sinh viên có nguy cơ cao về sức khỏe tâm thần dựa trên lý thuyết đồ thị và phát hiện cộng đồng, qua đó hỗ trợ phát hiện sớm và giám sát nguy cơ trong môi trường giáo dục

---

## Mô tả dự án

Dự án này xây dựng pipeline phân tích dữ liệu, bao gồm:

- Tiền xử lý dữ liệu
- Chuẩn hóa dữ liệu
- Xây dựng đồ thị:
  - **K-Nearest Neighbors (KNN)**
  - **Mutual KNN graph**
- So sánh cấu trúc đồ thị theo giá trị k
- Áp dụng các thuật toán phát hiện cộng đồng:
  - Girvan-Newman
  - Label Propagation
  - Louvain
  - Leiden
- Phân tích risk score để xác định nhóm nguy cơ cao

---

## Dataset

### File dữ liệu chính:

student_lifestyle_100k.xlsx

### Sau tiền xử lý, dataset được chia thành:

student_lifestyle_200.xlsx  
student_lifestyle_500.xlsx  
student_lifestyle_1000.xlsx  
student_lifestyle_5000.xlsx  
student_lifestyle_100000.xlsx  

---

## Cài đặt môi trường
### 1. Yêu cầu hệ thống

- Python ≥ 3.8
- Jupyter Notebook / Jupyter Lab

### 2. Cài đặt thư viện

Chạy trong notebook hoặc terminal:

pip install pandas numpy scikit-learn networkx matplotlib seaborn openpyxl  
pip install python-louvain igraph leidenalg

---

## Hướng dẫn chạy dự án

### 1. Clone hoặc tải project về
git clone <repo-url>  
cd <ten-project>

Hoặc tải file student_lifestyle.ipynb về máy và mở trực tiếp.

### 2. Cài đặt thư viện cần thiết (nếu chưa có)

Thực hiện giống phần Cài đặt môi trường ở trên

### 3. Mở Jupyter Notebook

Sau đó mở file chính: student_lifestyle.ipynb

### 4. Thực thi từng bước trong notebook

- Chạy lần lượt các cell theo thứ tự:

Cell 1: TIỀN XỬ LÍ DỮ LIỆU
- Load dataset
- Chuẩn hóa tên cột
- Encode biến (Gender, Depression)
- Xóa dữ liệu trùng lặp

Cell 2: CHUẨN HÓA DỮ LIỆU
- MinMaxScaler
- Chọn feature:
  - CGPA
  - Sleep duration
  - Study hours
  - Social media hours
  - Physical activity
  - Stress level

Cell 3: SO SÁNH K-NN VÀ MUTUAL K-NN
- Xây dựng graph
- So sánh cấu trúc theo k
- Phân tích density & components

Cell 4: SO SÁNH CÁC THUẬT TOÁN PHÁT HIỆN CỘNG ĐỒNG
Các thuật toán phát hiện cộng đồng:
- Girvan-Newman
- Label Propagation
- Louvain
- Leiden
So sánh:
- Modularity
- Số lượng cộng đồng
- Runtime

Cell 5: SO SÁNH CÁC THUẬT TOÁN PHÁT HIỆN CỘNG ĐỒNG VỚI 10 LẦN THỰC NGHIỆM
- Đánh giá độ ổn định thuật toán
- So sánh theo metric:
  - Modularity
  - Runtime
  - Number of communities

Cell 6: VẼ CỘNG ĐỒNG BẰNG KNN VÀ MUTUAL KNN TRÊN TẬP 200 ĐỈNH VÀ 500 ĐỈNH
- 200 nodes
- 500 nodes
- So sánh cấu trúc graph

Cell 7: SỬ DỤNG LEIDEN + MUTUAL K-NN ĐỂ PHÁT HIỆN CỘNG ĐỒNG VÀ NHÓM NGUY CƠ CAO VỀ SỨC KHỎE TÂM THẦN VỚI DATASET 5000 NODES
- Phát hiện cộng đồng quy mô lớn
- Tính risk score
- Xác định nhóm nguy cơ cao

#### Lưu ý: 
- Luôn chạy notebook theo đúng thứ tự cell
- Dataset phải đặt cùng thư mục với notebook
- Với Leiden algorithm, cần cài igraph và leidenalg
- Nên sử dụng Run All để đảm bảo pipeline nhất quán
- Thời gian chạy toàn bộ chương trình khoảng 1h 








