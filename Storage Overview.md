##Storage Overview

Storage được chia thành 2 loại chính: Ephermeral và Pesistant
+ Ephemeral: file storage
+ Persistant: Block Storage (cinder) và Object Storage (Swift)

###1. File Storage
- Loại lưu trữ này chỉ tồn tại trong một vòng đời của instance (máy ảo). Khi máy ảo bị xóa bỏ, dữ liệu cũng bị mất theo.


###2. Block Storage
- File được chia nhỏ ra thành các blocks có kích cỡ bằng nhau. Mỗi block có một địa chỉ riêng, nhưng không bao gồm metadata của dữ liệu.
- Thường được sử dụng trong môi trường Storage Area Network (SAN)
- Dữ liệu được lưu vào các volumns, hay còn gọi là block. Mối volumn/block có vai trò như một hard drive riêng biệt. 
- Vì mồi một block có vai trò như một hard drive, do vậy dạng lưu trữ block storage hiệu quả trong việc lưu trữ các loại application khác nhau như file systems và databases.
- Block storage đương nhiên sẽ phức tạp và giá thành cao hơn File storage, nhưng nó lại flexible và better performance.
- Block storage chỉ có thể truy cập được dữ liệu khi có OS.
- Use cases:
  + databases, vì DB requires consistent I/O performance và low-latency connectivity. 
  
<img src="http://cdn.druva.com/wp-content/uploads/Screen-Shot-2014-08-18-at-11.02.02-AM.png">

###3. Object Storage
- File dữ liệu không được chia nhỏ ra giống như Block Storage, mà tất cả được lưu trong một object bao gồm data, metadata và the unique identifier.
- Dữ liệu có thể đc truy xuất thông qua REST APIs hoặc http/https
- Kiểu lưu trữ này thường sẽ tạo từ 2-3 bản coppies của file gốc và lưu trữ
- Tính năng ưu việt nhất của object storage so với hai loại tradition storage ở trên là khả năng mở rộng scalability
(file storage và blockstorage đều có thể mở rộng được, nhưng phải kết hợp nhiều systems => management!)
- Objects are immutable; edits are saved as a new object
- Use cases: 
  + Thích hợp cho việc lưu trữ các dạng unstuctured data như image, video, music.
