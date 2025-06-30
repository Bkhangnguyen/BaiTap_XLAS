### Bài 1: Tịnh Tiến & Biến Đổi Sóng Ảnh Kiwi

#### Các bước làm :
- Chọn một ảnh quả kiwi bất kỳ
- Tịnh tiến kiwi 50 pixel sang phải, 30 pixel xuống dưới
- Áp dụng hiệu ứng sóng (wave effect) bằng hàm sin để biến dạng ảnh
- Lưu ảnh kết quả vào file `kiwi_wave.jpg`

#### Các code đã dùng:
- `cv2.warpAffine()` để thực hiện phép tịnh tiến
- `scipy.ndimage.map_coordinates()` hoặc `cv2.remap()` để áp dụng sóng sin lên tọa độ ảnh

### Bài 2: Gradient Màu Trái Cây & Ghép Ảnh Trong Suốt

#### Các bước làm :
- Chọn hai ảnh: đu đủ và dưa hấu
- Đổi màu:
  - Đu đủ: từ đỏ sang xanh lá
  - Dưa hấu: từ vàng → tím
- Ghép hai quả lên một nền trong suốt (alpha channel)
- Lưu kết quả dưới dạng ảnh `.png` có alpha: `fruits_gradient.png`

#### Các code đã dùng:
- Duyệt pixel theo hàng (hoặc trục y) để tạo màu gradient
- Kết hợp NumPy để áp dụng mask & tô màu từng pixel
- Dùng Pillow hoặc OpenCV hỗ trợ kênh alpha (`RGBA`)
- Ghép ảnh trên một canvas có kích thước lớn hơn

#### Thư mục :
├── kiwi.jpg                 # Ảnh kiwi dùng cho bài 1
├── kiwi_wave.jpg            # Kết quả sau biến đổi sóng
├── du_du.png                # Ảnh đu đủ
├── dua_hau.png              # Ảnh dưa hấu
├── fruits_composite.png      # Kết quả bài 2 

### Bài 3: Xoay và Phản Chiếu Ảnh

#### Các bước làm :
- Chọn hai ảnh: núi và thuyền
- Xoay cả hai đối tượng 45° (giữ nguyên kích thước gốc, `reshape=False`)
- Tạo hiệu ứng phản chiếu dọc (vertical mirror)
- Ghép hai ảnh đã xử lý lên một canvas trắng
- Lưu vào file `mountain_boat_mirror.jpg`

#### Code đã dùng:
- cv2.getRotationMatrix2D()
- cv2.warpAffine()
- cv2.flip()
- Ghép ảnh theo chiều ngang bằng NumPy

### Bài 4: Phép Biến Đổi Hình Học Tùy Chỉnh (Warp)

#### Các bước làm:
- Chọn ảnh một ngôi chùa bất kỳ
- Phóng to ảnh lên 5 lần (zoom)
- Áp dụng phép biến đổi hình học uốn cong (warping) bằng cách dịch pixel theo sóng sin
- Lưu vào file `pagoda_warped.jpg`

#### Code đã dùng :
- cv2.resize() để zoom
- cv2.remap() kết hợp `np.indices` để tạo bản đồ biến đổi (mapping)

### Bài 5: Menu Biến Đổi Tương Tác

#### Các bước làm:
- Xây dựng chương trình giao diện nhận nhiệm vụ
- Cho phép người dùng chọn 1 trong 3 ảnh
- Áp dụng 1 trong 5 phép biến đổi sau:

Tịnh tiến: Dời ảnh theo trục X, Y 
Xoay:  Xoay theo góc bất kỳ, tùy chọn giữ nguyên kích thước (`reshape=True/False`) 
Zoom: Phóng to hoặc thu nhỏ ảnh 
Gaussian Blur: Làm mờ ảnh bằng bộ lọc Gauss (hỏi giá trị sigma) 
Wave Transform:  Hiệu ứng sóng bằng phép biến đổi bản đồ pixel dạng sin 

#### Code đã dùng:
- Xây dựng menu bằng `input()`
- Các hàm biến đổi sử dụng OpenCV và NumPy
- Lưu kết quả ra `output_result.jpg`

## Thư mục
├── nui.jpg # Ảnh núi
├── thuyn.jpg # Ảnh thuyền
├── pagoda.jpg # Ảnh ngôi chùa
├── output_result.jpg # Kết quả bài 5
├── mountain_boat_mirror.jpg # Kết quả bài 3
├── pagoda_warped.jpg # Kết quả bài 4
├── README.md # Tài liệu hướng dẫn