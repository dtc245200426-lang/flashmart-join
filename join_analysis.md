\# Phân tích JOIN



Trong báo cáo Marketing, tôi sử dụng LEFT JOIN vì cần giữ lại tất cả khách hàng, kể cả khách hàng chưa từng phát sinh đơn hàng.



Tôi sử dụng COUNT(o.order\_id) thay vì COUNT(\*) vì COUNT(o.order\_id) chỉ đếm những giá trị order\_id khác NULL. Khi một khách hàng chưa có đơn hàng, LEFT JOIN vẫn giữ khách hàng đó nhưng các cột của Orders có giá trị NULL. Vì vậy COUNT(o.order\_id) trả về 0.



Nếu sử dụng COUNT(\*), dòng được LEFT JOIN tạo ra cho khách hàng chưa mua hàng vẫn có thể được tính, làm total\_orders thành 1 và sai yêu cầu.



Đối với sản phẩm chưa bán, tôi dùng LEFT JOIN kết hợp WHERE o.order\_id IS NULL để tìm các sản phẩm không có đơn hàng tương ứng.

