
## Công nghệ sử dụng
* **Python:** Ngôn ngữ lập trình chính được sử dụng để phát triển ứng dụng này.
* **OpenCV (cv2):** Thư viện mã nguồn mở chuyên dụng cho thị giác máy tính, được sử dụng để đọc, ghi và xử lý ảnh.
* **NumPy:** Thư viện hỗ trợ tính toán số học hiệu quả với mảng và ma trận, cần thiết cho các phép toán trên dữ liệu ảnh.
* **Matplotlib:** Thư viện dùng để tạo các biểu đồ tĩnh, động và tương tác trong Python, được sử dụng để hiển thị ảnh.
* **PIL (Pillow):** Thư viện hỗ trợ xử lý ảnh, được dùng để hiển thị ảnh trong các cửa sổ riêng biệt.

## Thuật toán sử dụng
Ứng dụng này cung cấp 5 thuật toán xử lý ảnh cơ bản để cải thiện chất lượng ảnh thang độ xám:
1.  **Inverse (Đảo ngược ảnh):** Đảo ngược giá trị pixel của ảnh.
2.  **Gamma Correction (Hiệu chỉnh Gamma):** Điều chỉnh độ sáng và độ tương phản của ảnh.
3.  **Log Transform (Biến đổi Logarit):** Nén dải động của ảnh, làm nổi bật chi tiết ở vùng tối.
4.  **Histogram Equalization (Cân bằng biểu đồ):** Cải thiện độ tương phản bằng cách phân bổ lại các cường độ pixel.
5.  **Contrast Stretching (Kéo giãn độ tương phản):** Tăng độ tương phản bằng cách kéo giãn dải giá trị pixel.

## Giải thích cách hoạt động

Chương trình sẽ thực hiện các bước sau:
1.  **Lựa chọn phương pháp:** Người dùng được yêu cầu nhập một ký tự để chọn phương pháp xử lý ảnh mong muốn:
    * `I`: Inverse (Đảo ngược ảnh)
    * `G`: Gamma Correction (Hiệu chỉnh Gamma)
    * `L`: Log Transform (Biến đổi Logarit)
    * `H`: Histogram Equalization (Cân bằng biểu đồ)
    * `C`: Contrast Stretching (Kéo giãn độ tương phản)
2.  **Xử lý ảnh hàng loạt:**
    * Chương trình sẽ duyệt qua tất cả các tệp ảnh (định dạng .png, .jpg, .jpeg) trong thư mục `exercise`.
    * Mỗi ảnh sẽ được đọc dưới dạng ảnh thang độ xám (`cv2.IMREAD_GRAYSCALE`).
    * Áp dụng phương pháp xử lý ảnh đã chọn (`func`) lên ảnh gốc.
    * Lưu ảnh kết quả vào thư mục `output_menu` với tên tệp được đặt theo định dạng gốc_phương_pháp.png (ví dụ: `image01_I.png`).
3.  **Hiển thị kết quả:**
    * Đối với mỗi ảnh được xử lý, ảnh gốc và ảnh đã xử lý sẽ được hiển thị trong hai cửa sổ riêng biệt bằng cách sử dụng thư viện `PIL` (`img_pil.show()` và `result_pil.show()`).
    * Đồng thời, ảnh đã xử lý cũng được hiển thị bằng `matplotlib.pyplot` trong một cửa sổ đồ họa để dễ dàng so sánh trực quan.

### Các hàm xử lý ảnh chi tiết:

* **`inverse(img)`**:
    ```python
    def inverse(img): return 255 - img
    ```
    Hàm này đảo ngược giá trị pixel của ảnh. Pixel có giá trị 0 (đen) sẽ trở thành 255 (trắng) và ngược lại, tạo ra một ảnh âm bản.

* **`gamma_correction(img, gamma=2.2)`**:
    ```python
    def gamma_correction(img, gamma=2.2):
        return np.power(img / 255.0, gamma) * 255
    ```
    Hàm này thực hiện hiệu chỉnh gamma. Giá trị pixel được chuẩn hóa về khoảng [0, 1], sau đó được lũy thừa với giá trị `gamma` (mặc định là 2.2) và cuối cùng được mở rộng trở lại về khoảng [0, 255]. Giá trị gamma nhỏ hơn 1 làm sáng ảnh, lớn hơn 1 làm tối ảnh.

* **`log_transform(img)`**:
    ```python
    def log_transform(img): return np.log1p(img) / np.log(256) * 255
    ```
    Hàm này áp dụng phép biến đổi logarit. Nó nén dải động của ảnh, làm cho các chi tiết ở vùng tối của ảnh trở nên rõ ràng hơn trong khi các vùng sáng ít bị ảnh hưởng. `np.log1p(img)` được sử dụng để tránh lỗi khi logarit của 0.

* **`hist_equalization(img)`**:
    ```python
    def hist_equalization(img): return cv2.equalizeHist(img)
    ```
    Hàm này sử dụng `cv2.equalizeHist()` để cân bằng biểu đồ xám của ảnh. Nó phân phối lại các giá trị cường độ pixel để làm phẳng biểu đồ xám, dẫn đến tăng độ tương phản tổng thể của ảnh.

* **`contrast_stretch(img)`**:
    ```python
    def contrast_stretch(img): return ((img - img.min()) / (img.max() - img.min()) * 255).astype(np.uint8)
    ```
    Hàm này thực hiện kéo giãn độ tương phản tuyến tính. Nó ánh xạ các giá trị pixel tối thiểu và tối đa hiện có trong ảnh tới phạm vi đầy đủ của thang độ xám (0-255), giúp tăng độ tương phản của ảnh.