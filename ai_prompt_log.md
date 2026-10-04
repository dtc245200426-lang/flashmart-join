\# Nhật ký hỏi đáp với AI



\## Câu hỏi 1

Trong MySQL, JOIN khi không ghi LEFT hoặc RIGHT hoạt động như thế nào?



\## Trả lời

JOIN mặc định là INNER JOIN. Nó chỉ giữ những bản ghi có giá trị khớp ở cả hai bảng. Vì vậy khách hàng chưa có đơn hàng sẽ không xuất hiện.



\## Câu hỏi 2

Khi dùng LEFT JOIN, tại sao nên dùng COUNT(o.order\_id) thay vì COUNT(\*)?



\## Trả lời

COUNT(o.order\_id) bỏ qua giá trị NULL nên khách hàng chưa có đơn hàng được đếm là 0. COUNT(\*) đếm dòng kết quả nên có thể cho kết quả 1.



\## Câu hỏi 3

MySQL thường xử lý JOIN như thế nào?



\## Trả lời

MySQL Optimizer lựa chọn thứ tự truy cập bảng và phương án thực thi phù hợp. Nested-loop là một cơ chế quan trọng để xử lý JOIN, trong đó dữ liệu từ một nguồn được dùng để tìm các bản ghi phù hợp ở nguồn còn lại.

