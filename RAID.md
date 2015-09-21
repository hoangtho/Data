##Redundant Array of Independent Disks
Là hệ thống hoạt động bằng cách kết nối một dãy các ổ cứng có chi phí thấp lại với nhau để hình thành một thiết bị nhớ đơn có dung lượng lớn hỗ trợ hiệu quả cao và đáng tin cậy hơn

Ban đầu, RAID được sử dụng như một giải pháp phòng hộ vì nó cho phép ghi dữ liệu lên nhiều đĩa cứng cùng lúc. Về sau, RAID đã có nhiều biến thể cho phép không chỉ đảm bảo an toàn dữ liệu mà còn giúp gia tăng đáng kể tốc độ truy xuất dữ liệu từ đĩa cứng.
 
- Dự phòng
- Hiệu quả cao
- Giá thành thấp

####1. RAID 0
- Cấp độ 0 được đưa ra không thể cung cấp cấp độ dự phòng nào cho các dữ liệu được lưu trữ.
- Đòi hỏi tối thiểu phải có 2 ổ đĩa.
- Sử dụng kỹ thuật "stripping". Striping” phân chia khối dữ liệu đơn như trong hình vẽ và trải chúng qua các ổ cứng => Tác dụng của striping là làm tăng hiệu quả thực thi.
- Thuận lợi 
   + Tăng hiệu quả lưu trữ
- Bất lợi  
   + Không có ổ dự phòng
  
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9b/RAID_0.svg/220px-RAID_0.svg.png">

####2. RAID 1
- Sử dụng kỹ thuật mirroring (nhân bản dữ liệu)
- Cần 2 ổ cứng riêng biệt, có cùng dung lượng. Một ở hoạt động, một ổ dự phòng.
- Thuận lợi 
   + Cung cấp dự phòng dữ liệu toàn diện
- Bất lợi 
   + Không tăng hiệu suất thực thi
   + Dung lượng của hệ thống RAID bằng dung lượng của 1 ổ đơn 
   
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b7/RAID_1.svg/150px-RAID_1.svg.png">   
    
####3. RAID 0+1
- Được sinh ra nhằm tận dụng lợi thể của RAID 0 và 1. Đòi hỏi tối thiểu là 4 ổ cứng.
- Các kĩ thuật “mirroring” và “striping” kết hợp với nhau tạo ra hiệu quả dự phòng
- Dữ liệu sẽ được ghi đồng thời lên 4 đĩa cứng với 2 ổ dạng Striping tăng tốc và 2 ổ dạng Mirroring sao lưu. 4 ổ đĩa này phải giống hệt nhau và khi đưa vào hệ thống RAID 0+1, dung lượng cuối cùng sẽ bằng ½ tổng dung lượng 4 ổ
- Thuận lợi 
   + Tăng hiệu quả thực thi
   + Dữ liệu được dự phòng toàn bộ
- Bất lợi 
   + Giá thành đắt (min ~ 4 ổ cứng)
   + Tốc độ truy xuất dữ liệu giảm một nửa
 
<img src="http://www.datarc.ru/wp-content/uploads/2015/03/raid-0-1.png">


####4. RAID 10
- Gần giống RAID 1+0

<img src="http://media.tumblr.com/tumblr_l5cy0pFgUF1qc42sv.jpg">

####5. RAID 5
- Phù hợp với hệ thống máy để bàn, cần từ 3-5 ổ cứng. 
- Sử dụng kỹ thuật "stripping with parity" (chẵn lẻ) để dự phòng dữ liệu.
- Dung lượng đĩa cứng cuối cùng bằng tổng dung lượng đĩa sử dụng trừ đi một ổ
- Thuận lợi 
   + Tăng dung lượng lưu trữ
   + Dữ liệu được dự phòng toàn bộ
   + Khả năng hoán đổi nhanh 24x7
- Bất lợi 
   + Giá thành cao
   + Hiệu quả thực thi giảm trong quá trình phục hồi
         
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/RAID_5.svg/300px-RAID_5.svg.png">

####6. RAID 2

<img src="http://i.imgur.com/aORu8as.png">

RAID 2 gồm hai cụm ổ đĩa, cụm thứ nhất chứa các dữ liệu được phân tách giống như là RAID 0, cụm thứ hai chứa các mã ECC dành cho sửa chữa lỗi ở cụm thứ nhất. Sự hoạt động của các ổ đĩa ở RAID 2 là đồng thời để đảm bảo rằng các dữ liệu được đọc đúng, chính do vậy chúng không hiệu quả bằng một số loại RAID khác nên ít được sử dụng.

####7. RAID 3

Là bản cải tiến của RAID 0. Cần tối thiểu 3 ô cứng.

<img src="http://i.imgur.com/7phY9jn.png" style="width: 150px; height=100;">

