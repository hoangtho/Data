#Redundant Array of Independent Disks
Là hệ thống hoạt động bằng cách kết nối một dãy các ổ cứng có chi phí thấp lại với nhau để hình thành một thiết bị nhớ đơn có dung lượng lớn hỗ trợ hiệu quả cao và đáng tin cậy hơn

Ban đầu, RAID được sử dụng như một giải pháp phòng hộ vì nó cho phép ghi dữ liệu lên nhiều đĩa cứng cùng lúc. Về sau, RAID đã có nhiều biến thể cho phép không chỉ đảm bảo an toàn dữ liệu mà còn giúp gia tăng đáng kể tốc độ truy xuất dữ liệu từ đĩa cứng.
 
- Dự phòng
- Hiệu quả cao
- Giá thành thấp

####1. RAID 0
- Cấp độ 0 được đưa ra không thể cung cấp cấp độ dự phòng nào cho các dữ liệu được lưu trữ.
- Đòi hỏi tối thiểu phải có 2 ổ đĩa.
- Sử dụng kỹ thuật "stripping". Striping” phân chia khối dữ liệu đơn như trong hình vẽ và trải chúng qua các ổ cứng => Tác dụng của striping là làm tăng hiệu quả thực thi.
- Tốc độ đọc/ghi đều nhanh (great performance)
- Thuận lợi 
   + Tăng hiệu quả lưu trữ
- Bất lợi  
   + Không có ổ dự phòng
  
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9b/RAID_0.svg/220px-RAID_0.svg.png">

####2. RAID 1
- Sử dụng kỹ thuật mirroring (nhân bản dữ liệu)
- Cần 2 ổ cứng riêng biệt, có cùng dung lượng. Một ở hoạt động, một ổ dự phòng.
- Tốc độ đọc nhanh (exelent read speed), tốc độ ghi chỉ bằng một ổ cứng đơn.
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
- Phù hợp với hệ thống máy để bàn, min ~ 3 ổ cứng 
- Sử dụng kỹ thuật "stripping with parity" (chẵn lẻ) để dự phòng dữ liệu.
- Dung lượng đĩa cứng cuối cùng bằng tổng dung lượng đĩa sử dụng trừ đi một ổ
- Tốc độ đọc nhanh, tốc độ ghi hơi chậm hơn bởi parity cần được tính toán trong quá trình ghi.
- Thuận lợi 
   + Tăng dung lượng lưu trữ
   + Dữ liệu được dự phòng toàn bộ
   + Khả năng hoán đổi nhanh 24x7
- Bất lợi 
   + Giá thành cao
   + Hiệu quả thực thi giảm trong quá trình phục hồi
         
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/RAID_5.svg/300px-RAID_5.svg.png">

####6. RAID 2,3,4,7

Các RAID này đều tồn tại, nhưng không có tính ứng dụng cao, và không được triển khai phổ biến

####7. RAID không sinh ra để thay thế cho back-up
- Back-up sẽ hữu dụng trong trường hợp tất cả các ổ cứng cùng gặp sự cố (mất điện, bị đánh cắp, thiên tai...)
- Ưu điểm lớn nhất của back-up là xử lý được lỗi người dùng. Nếu không may người dùng làm mất mát dữ liệu, hoặc xóa nhầm một vài file quan trọng mà không hề ý thức được việc này, thì back-up sẽ được coi là một vị cứu tinh!


####8. RAID Performance
##### RAID 0 (4 ổ cứng)

SeqWrite
<img src="http://i.imgur.com/3VXswDw.png">

RandRead
<img src="http://i.imgur.com/NgooKKj.png">


RandWrite
<img src="http://i.imgur.com/enuUISH.png">

SeqRead
<img src="http://i.imgur.com/qcOvOvK.png">

RandReadWrite (mix)
<img src="http://i.imgur.com/8iqxuQ1.png">

SeqReadWrite (mix)
<img src="http://i.imgur.com/UT7bBpk.png">


##### RAID 1 (2 ổ cứng)

dd if=/dev/zero of=file1 bs=1024 count=200000

<img src="http://i.imgur.com/t9d9Fes.png">

RandRead
<img src="http://i.imgur.com/dSPsVyN.png">

RandWrite
<img src="http://i.imgur.com/5cNy3jL.png">

RandReadWrite (mix)
<img src="http://i.imgur.com/UQchmhp.png">

SeqRead
<img src="http://i.imgur.com/aZgvufX.png">

SeqWrite
<img src="http://i.imgur.com/Qd6z3jC.png">

SeqReadWrite
<img src="http://i.imgur.com/rEoIC14.png">


##### RAID5 (4 ổ cứng)

RandRead
<img src="http://i.imgur.com/7oN3Qxp.png">

RandWrite
<img src="http://i.imgur.com/twePRfW.png">

RandReadWrite (Mix)
<img src="http://i.imgur.com/wQ4nRHJ.png">

SeqRead
<img src="http://i.imgur.com/dO9qXDD.png">

SeqWrite
<img src="http://i.imgur.com/GBarmIv.png">

SeqReadWrite (Mix)
<img src="http://i.imgur.com/1VxwYxq.png">



