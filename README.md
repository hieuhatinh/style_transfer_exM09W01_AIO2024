# Exercise M09W01 - Style Transfer

## 1. Giới thiệu: 
**Style transfer** là sự kết hợp giữa trí tuệ nhân tạo và nghệ thuật (art), đây là lĩnh vực thú vị nơi
mà thẩm mỹ của nghệ thuật hình ảnh được kết hợp với nội dung số hóa. Quá trình này bao gồm
việc áp dụng style (phong cách) nghệ thuật từ một hình ảnh và áp dụng nó lên nội dung (content)
của một hình ảnh khác, từ đó tạo ra một hình ảnh mới thể hiện bản chất của cả hai.

![Style Transfer](/readme_img/style_transfer.jpg)

## 2. Neural Representations of Content and Style:
![Neural Style Transfer Pipeline](/readme_img/pipeline_neural_st.png)

Bài toán này dựa trên việc sử dụng Mạng Nơ-ron Tích chập (CNNs), đặc biệt là các mạng được
huấn luyện trước (pretrain) như VGGNet, có khả năng nắm bắt các đặc trưng của hình ảnh theo
từng cấp bậc- từ các cạnh và kết cấu cơ bản đến các biểu diễn nội dung phức tạp hơn.

**Content Representation**: Nội dung (content) của một hình ảnh được học bởi feature map của
một số layer trong mạng, thường là các lớp sâu hơn nơi mạng đã trừu tượng hóa khỏi dữ liệu pixel
thô và thay vào đó biểu diễn các đặc điểm cấp cao hơn như hình dạng và đối tượng.

**Style Representation:** Phong cách (style) của một hình ảnh được học bởi các tương quan giữa
các đặc điểm trong các layer khác nhau của mạng. Điều này được biểu diễn toán học bởi ma trận
Gram, nắm bắt được phân phối của các đặc điểm

## 3. Loss Functions:
**Content Loss:** Đo lường mức độ nội dung của hình ảnh được tạo ra từ model sai lệch so với nội
dung của hình ảnh nội dung gốc . Nó thường được tính toán bằng MSE của hình ảnh nội dung
và hình ảnh được tạo ra trong một hoặc nhiều layer của CNN.

**Style Loss:** Đo lường sự khác biệt về phong cách giữa hình ảnh được tạo ra và hình ảnh tham
khảo phong cách . MSE được sử dụng giữa các ma trận Gram của các biểu diễn phong cách của
hình ảnh được tạo ra và hình ảnh phong cách qua nhiều layer của CNN.

**Total Loss:** Là hàm kết hợp content và style loss, thường là tổng hoặc kết hợp với các tham số
để điều chỉnh lượng loss phù hợp

## 4. Multi-modal Style Transfer
![Multi-modal Style Transfer](/readme_img/multi-model_st.png "AIO 2024")

## 5.  Image Style Transfer With Transformers:
Phương pháp sử dụng Transformer model cho Style Transfer. Phương pháp này giải quyết những hạn chế của CNN trong việc nắm bắt thông tin toàn cục. Nó sử dụng 2 transformer encoder cho nội dung và phong cách tương ứng và một multi-layer transformer decoder để tạo phong cách cho nội dung. Một Content-Aware Positional Encoding (CAPE) được đưa vào để cải thiện positional encoding cho style transfer

![Style Transfer with Transformers](/readme_img/st_transformer.png "AIO 2024")