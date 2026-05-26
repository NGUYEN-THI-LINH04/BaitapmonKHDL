# BaitapmonKHDL
Link youtube: https://youtu.be/4h85vv_rx7U
# PHÂN CỤM SINH VIÊN LỚP K58KTP BẰNG THUẬT TOÁN K-MEANS

## Giới thiệu

Đề bài thực hiện phân cụm sinh viên lớp **K58KTP** thành **3 nhóm học lực** bằng thuật toán **K-Means Clustering** dựa trên dữ liệu điểm học tập từ file Excel.

### Mục tiêu
- Phân cụm sinh viên dựa trên kết quả học tập.
- Chia lớp thành 3 nhóm:
  - **Học tốt**
  - **Trung bình**
  - **Cần cải thiện**
- Trực quan hóa kết quả bằng biểu đồ.
- Xuất kết quả phân cụm ra file Excel.

---

# Công nghệ sử dụng

### Ngôn ngữ lập trình
- Python 3.x

### Môi trường thực hiện
- Jupyter Notebook (.ipynb)
- PyCharm
- Anaconda

### Thư viện sử dụng

Cài đặt thư viện bằng lệnh:

```bash
pip install pandas numpy matplotlib scikit-learn openpyxl
```

Hoặc:

```bash
conda install pandas numpy matplotlib scikit-learn openpyxl
```

---

# Dữ liệu đầu vào

File dữ liệu sử dụng:

```text
TỔNG HỢP ĐIỂM K58KTP.xlsx
```

Dữ liệu bao gồm:

- Mã số sinh viên
- Tên sinh viên
- Điểm các môn học

Sau khi xử lý:

```text
71 sinh viên
52 môn học
```

---

# Các bước thực hiện

## Bước 1: Import thư viện (Cell 1)

Import các thư viện cần thiết như:
- pandas
- numpy
- matplotlib
- scikit-learn

Mục đích:
- Xử lý dữ liệu
- Phân cụm K-Means
- Trực quan hóa kết quả

---

## Bước 2: Cấu hình hiển thị dữ liệu (Cell 2)

Thiết lập hiển thị dữ liệu trong notebook để bảng dữ liệu hiển thị đầy đủ và dễ quan sát hơn.

---

## Bước 3: Đọc file Excel (Cell 3)

Sử dụng `pandas` để đọc file Excel chứa bảng điểm sinh viên.

Kết quả dữ liệu:

```text
56 dòng × 74 cột
```

---

## Bước 4: Tách và làm sạch dữ liệu (Cell 4–5)

Tiến hành:
- Tách MSSV
- Tách tên sinh viên
- Tách danh sách môn học
- Tách bảng điểm

Sau đó sử dụng hàm:

```python
clean_score()
```

để:
- sửa lỗi Excel đọc nhầm điểm thành ngày tháng
- chuẩn hóa dữ liệu điểm

Kết quả:

```text
71 sinh viên
52 môn học
```

---

## Bước 5: Tạo bảng dữ liệu phân tích (Cell 6)

Tạo bảng:

```python
student_df
```

Trong đó:
- mỗi dòng là một sinh viên
- mỗi cột là một môn học

Mục đích:
- Đưa dữ liệu về định dạng phù hợp cho Machine Learning

---

## Bước 6: Kiểm tra dữ liệu thiếu (Cell 7)

Kiểm tra các giá trị bị thiếu trong bảng điểm trước khi đưa vào mô hình.

---

## Bước 7: Xử lý dữ liệu và chuẩn hóa (Cell 8)

Sử dụng:

```python
SimpleImputer(strategy='mean')
```

để xử lý dữ liệu thiếu.

Sử dụng:

```python
StandardScaler()
```

để chuẩn hóa dữ liệu.

Mục đích:
- Đưa dữ liệu về cùng thang đo
- Tăng độ ổn định của mô hình

---

## Bước 8: Phân cụm bằng K-Means (Cell 9)

Áp dụng:

```python
KMeans(n_clusters=3)
```

để chia sinh viên thành 3 nhóm:
- Học tốt
- Trung bình
- Cần cải thiện

---

## Bước 9: Đánh giá mô hình (Cell 10)

Sử dụng:

```python
silhouette_score()
```

Kết quả:

```text
0.0922
```

---

## Bước 10: Tính điểm trung bình và gán nhóm học lực (Cell 11–14)

Thực hiện:
- Tính điểm trung bình của từng sinh viên
- Tính điểm trung bình từng cluster
- Gán nhóm học lực
- Tính điểm trung bình từng nhóm

Các nhóm gồm:
- Học tốt
- Trung bình
- Cần cải thiện

---

## Bước 11: Thống kê kết quả (Cell 15)

Kết quả phân cụm:

| Nhóm học lực | Số lượng |
|--------------|----------|
| Trung bình | 28 |
| Cần cải thiện | 24 |
| Học tốt | 19 |

---

## Bước 12: Trực quan hóa dữ liệu (Cell 16–18)

Sử dụng:
- Biểu đồ tròn
- Biểu đồ phân cụm K-Means (PCA)
- Biểu đồ cột

Mục đích:
- Trực quan hóa kết quả phân cụm
- So sánh số lượng sinh viên giữa các nhóm

---

## Bước 13: Xuất file Excel (Cell 19)

Xuất file:

```text
ket_qua_phan_cum.xlsx
```

Bao gồm:
- Thông tin sinh viên
- Điểm trung bình
- Nhóm học lực
- Biểu đồ
- Bảng dữ liệu được tô màu trực quan

---

# Hướng dẫn chạy chương trình

## Bước 1: Clone project

```bash
git clone <link-github-cua-ban>
```

---

## Bước 2: Cài đặt thư viện

```bash
pip install pandas numpy matplotlib scikit-learn openpyxl
```

---

## Bước 3: Đặt file Excel

Đặt file:

```text
TỔNG HỢP ĐIỂM K58KTP.xlsx
```

vào cùng thư mục với notebook.

---

## Bước 4: Chạy notebook

Mở file:

```text
phan_cum_kmeans.ipynb
```

Sau đó chọn:

```text
Run All Cells
```

hoặc chạy lần lượt từng cell từ trên xuống dưới.

---

# Kết quả đầu ra

Chương trình sẽ:

✅ Phân cụm sinh viên thành 3 nhóm học lực  
✅ Hiển thị biểu đồ trực quan  
✅ Xuất file Excel kết quả:

```text
ket_qua_phan_cum.xlsx
```

---

# Nhận xét kết quả

Sau khi phân cụm:

- Nhóm **Trung bình** chiếm số lượng lớn nhất (**28 sinh viên**)
- Nhóm **Cần cải thiện** gồm **24 sinh viên**
- Nhóm **Học tốt** gồm **19 sinh viên**

Kết quả cho thấy phần lớn sinh viên trong lớp đang ở mức học lực trung bình và vẫn còn một số sinh viên cần cải thiện kết quả học tập.

Các biểu đồ giúp trực quan hóa dữ liệu và hỗ trợ đánh giá tình hình học tập của lớp một cách tổng quan.
