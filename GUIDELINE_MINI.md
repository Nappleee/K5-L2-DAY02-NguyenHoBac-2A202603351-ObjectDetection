# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Phương tiện chở người, thường có 4 bánh, kích thước nhỏ hoặc trung bình. |  Sedan, hatchback, SUV, coupe. |
| `truck` | Phương tiện được thiết kế chủ yếu để vận chuyển hàng hóa, thường có khoang chở hàng riêng hoặc thùng hàng. | Xe tải nhỏ, xe tải lớn, xe ben, xe đầu kéo. |
| `bus` |  	Phương tiện vận chuyển hành khách với sức chứa lớn, thường có nhiều hàng ghế và khoang hành khách rộng. | Xe buýt nội thành, xe khách, xe buýt trường học. |
| `van` | Phương tiện có thân xe dạng hộp, kích thước trung bình, thường dùng để chở người hoặc hàng hóa. | Minivan, cargo van, passenger van.|

## Quy tắc chung

- Box bám sát vật thể nghĩa là: Bounding box phải bao quanh toàn bộ phần vật thể nhìn thấy
- Vật thể bị che khuất: Chỉ gán nhãn khi có đủ đặc điểm để xác định đó là một phương tiện và phân biệt được lớp. Box bao quanh phần nhìn thấy, không ước lượng phần bị che khuất 
- Vật thể bị cắt bởi rìa ảnh: Vẫn gán nhãn nếu phần còn lại đủ để nhận diện lớp. Box kéo sát đến rìa ảnh, không mở rộng ra ngoài khung hình.
- Vật thể rất nhỏ/mơ hồ: không gán nhãn.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_028` | xe ở góc trái có kích thước lớn hơn so với xe bình thường, dáng giống một chiếc suv mà na ná một chiếc van| chọn car | suv thì vẫn là car|
| `drive_009`|xe con ở giữ hai xe tải và khách, bị che một nửa | vẫn label là car | vẫn nhìn được do độ cao của ảnh thấp hơn so với mấy xe không bị che bên cạnh |
| `drive_033` | xe khách ở góc trái màn hình bị cắt nửa | không label | do cảm giác có thể bị nhầm với xe tải | 
