# Nhập Môn Xử Lý Ảnh Số - Lab 5  
## Nhận Dạng Đối Tượng & Phân Tích Đặc Trưng Hình Dạng

**Môn học : Xử Lý Ảnh Số**
**Sinh viên:** Nguyễn Bảo Khang
**MSSV:** 2374802010211

---

### Chủ đề :

Bài thực hành Lab 5 tập trung vào kỹ thuật nhận dạng và phân tích hình dạng của các đối tượng trong ảnh nhị phân. Đây là bước nền tảng để giúp hệ thống "hiểu" và phân biệt được các vật thể khác nhau trong ảnh số.

---

### Nội dung :
#### 1. Phát hiện và đếm số đối tượng

- **Mục tiêu:**  
  Sử dụng các hàm phân vùng và gán nhãn (labeling) để xác định từng đối tượng riêng lẻ, từ đó thực hiện đếm số lượng.
  
- **Ứng dụng:**  
  Có thể áp dụng trong nhiều bài toán thực tế như: đếm số tế bào trong ảnh vi sinh, đếm đồng xu, đếm số vật thể chuyển động,...

#### 2. Phân tích đặc trưng hình dạng

- **Mục tiêu:**  
  Sau khi tách được từng đối tượng, tiến hành tính các thông số như:
  - Diện tích (Area)
  - Chu vi (Perimeter)
  - Tâm đối tượng (Centroid)
  - Hộp bao (Bounding box)
  - Độ tròn (Circularity)
  - Tỷ lệ chiều dài / chiều rộng

- **Ứng dụng:**  
  Các đặc trưng hình học này hỗ trợ việc phân loại, nhận diện, hoặc lọc ra các đối tượng theo tiêu chí cụ thể.

#### 3. Trực quan hóa kết quả

- **Mục tiêu:**  
  Gắn nhãn trực tiếp lên ảnh bằng các hình như bounding box, chấm tâm, hoặc chú thích văn bản.
- **Lợi ích:**  
  Giúp dễ dàng kiểm tra kết quả, phục vụ trình bày báo cáo và trực quan hóa quá trình xử lý ảnh.
---

### Công nghệ sử dụng

- Python  
- OpenCV  
- Pillow (PIL)  
- NumPy  
- Matplotlib  
- Scikit-image  

---

### Cài đặt và sử dụng

1. **Cài thư viện cần thiết:**

   ```bash
   pip install pillow numpy matplotlib imageio opencv-python scikit-image

2. **Chạy notebook:**

Mở file TH5.ipynb trong Jupyter Notebook.

Chạy từng ô lệnh (cell) để theo dõi toàn bộ quá trình xử lý.

Kiểm tra lại tên và vị trí ảnh nếu có lỗi không tìm thấy file.

3. **Tùy chỉnh thêm:**

Thay đổi ngưỡng phân vùng hoặc sử dụng ảnh khác để quan sát ảnh hưởng đến kết quả nhận dạng

### Cấu trúc thư mục ** XLA_lab5**
├── TH5.ipynb      
├── bird.png       
├── geometric.png
├── Lab_5_Image_Measure.docx
├── exercise/
│   └── dalat.jpg
├── label_output.jng 
├── label_output.png
├── README.md        

