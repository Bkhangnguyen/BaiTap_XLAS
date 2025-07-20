# Nhập Môn Xử Lý Ảnh Số - Lab 4  
## Phân Vùng Ảnh & Biến Đổi Ảnh Nhị Phân

**Sinh viên:** Nguyễn Bảo Khang 
**MSSV:** 2374802010211 

---

### Nhận xét

Bài Lab 4 tập trung vào các kỹ thuật phân vùng ảnh (segmentation) và các phép biến đổi hình thái học (morphological operations) trên ảnh nhị phân. Đây là những công cụ quan trọng giúp phân tách đối tượng khỏi nền, loại bỏ nhiễu và cải thiện cấu trúc ảnh.

#### Các nội dung chính:
- **Phân ngưỡng Otsu**: Tự động tìm ngưỡng tách đối tượng và nền từ ảnh xám.
- **Phân ngưỡng thích nghi**: Tính ngưỡng cục bộ cho ảnh có độ sáng không đồng đều.
- **Thuật toán Watershed**: Phân vùng các vật thể dính liền nhau.
- **Biến đổi hình thái học**: Gồm Dilation, Erosion, Opening, Closing để xử lý hình dạng đối tượng.

---

###  Công nghệ sử dụng

- Python  
- OpenCV  
- Pillow (PIL)  
- NumPy  
- ImageIO  
- Matplotlib  
- Scikit-image  

---

### Cài đặt và thực thi

1. **Cài đặt các thư viện cần thiết:**

   ```bash
   pip install pillow numpy matplotlib imageio opencv-python scikit-image

### Cấu trúc thư mục
├── TH4.ipynb      
├── Ball.gif        
├── dalat.jpg
├── ho_xuan_huong.jpg
├── exercise/
│   └── dalat.jpg
├── README.md       
