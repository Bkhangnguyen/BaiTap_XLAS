

## Giải thích bt1 :
### Các hàm xử lý ảnh :
1.   def inverse(img): return 255 - img
    Hàm này đảo ngược giá trị pixel của ảnh. Pixel có giá trị 0 (đen) sẽ trở thành 255 (trắng) và ngược lại, tạo ra một ảnh âm bản.

2.    def gamma_correction(img, gamma=2.2):
        return np.power(img / 255.0, gamma) * 255

    Hàm này thực hiện hiệu chỉnh gamma. Giá trị pixel được chuẩn hóa về khoảng [0, 1], sau đó được lũy thừa với giá trị `gamma` (mặc định là 2.2) và cuối cùng được mở rộng trở lại về khoảng [0, 255]. Giá trị gamma nhỏ hơn 1 làm sáng ảnh, lớn hơn 1 làm tối ảnh.

3.    def log_transform(img): return np.log1p(img) / np.log(256) * 255

    Hàm này áp dụng phép biến đổi logarit. Nó nén dải động của ảnh, làm cho các chi tiết ở vùng tối của ảnh trở nên rõ ràng hơn trong khi các vùng sáng ít bị ảnh hưởng. `np.log1p(img)` được sử dụng để tránh lỗi khi logarit của 0.

4.    def hist_equalization(img): return cv2.equalizeHist(img)

    Hàm này sử dụng `cv2.equalizeHist()` để cân bằng biểu đồ xám của ảnh. Nó phân phối lại các giá trị cường độ pixel để làm phẳng biểu đồ xám, dẫn đến tăng độ tương phản tổng thể của ảnh.

5.   def contrast_stretch(img): return ((img - img.min()) / (img.max() - img.min()) * 255).astype(np.uint8)

    Hàm này thực hiện kéo giãn độ tương phản tuyến tính. Nó ánh xạ các giá trị pixel tối thiểu và tối đa hiện có trong ảnh tới phạm vi đầy đủ của thang độ xám (0-255), giúp tăng độ tương phản của ảnh.

## Giải thích bt 2

1. Người dùng nhập phím `F`, `L`, hoặc `H` để chọn phương pháp.
2. Chương trình đọc tất cả ảnh trong thư mục `exercise/`.
3. Ảnh được xử lý bằng phương pháp đã chọn.
4. Kết quả được lưu vào thư mục `output_menu/`.
5. Ảnh gốc và ảnh kết quả được hiển thị bằng `PIL` và `matplotlib`
6. Chương trình sử dụng dictionary mapping để ánh xạ phím sang tên và hàm xử lý.

### Các hàm xử lý ảnh
1. fast_fourier_transform(image)
Biến đổi ảnh sang miền tần số.
Hiển thị phổ biên độ (magnitude spectrum).

2. butterworth_lowpass(image, d0=30, n=2)
Lọc thông thấp: loại bỏ chi tiết cao (nhiễu).
Dùng hàm Butterworth với tần số cắt d0.

3.  butterworth_highpass(image, d0=30, n=2)
Lọc thông cao: giữ lại chi tiết cao (viền, cạnh).
Dùng hàm Butterworth dạng high-pass.

## Giải thích bt 3
1. Đọc ảnh màu (BGR), chuyển sang RGB.
2. Ngẫu nhiên đảo thứ tự 3 kênh màu RGB bằng random.shuffle().
3. Chuyển ảnh sau khi hoán màu sang ảnh xám (grayscale) để áp dụng các phép biến đổi.
4. Chọn ngẫu nhiên 1 phép biến đổi ảnh từ danh sách bài 1.
5. Áp dụng hàm biến đổi lên ảnh xám.
6. Lưu ảnh kết quả vào thư mục output_bai3/ và hiển thị bằng PIL và matplotlib.


