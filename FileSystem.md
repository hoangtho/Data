##Linux File System
####1. Ext2 (second standard file system)
- Khi khởi động, hệ điều hành luôn luôn có 1 chương trình để kiểm tra tính toàn vẹn của hệ thống file đó là fsck (unmount, hệ thống file có dấu hiệu bất thường). Tuy nhiên, quá trình kiểm tra và khôi phục này có thể lâu hay chậm tùy thuộc vào dung lượng của ổ cứng.  
- Không có tính năng journal
  -> journaling chỉ được sử dụng khi ghi dữ liệu lên ổ cứng, khắc phục vấn đề khi ổ cứng gặp vấn đề. Nếu không có journaling, hệ thống sẽ không biết được file có được ghi đầy đủ lên ổ đĩa hay không.
- Max file size từ 16gb - 32gb
- ext2 file system max từ 2tb - 32tb
- ext2 thường được dùng cho flash-based storage media (như SD cards, and USB flash drives)
- Kiến trúc Ext2 dùng cấu trúc dữ liệu được gọi là nút định dạng (inode) để tham chiếu và định vị tập tin cũng như các dữ liệu tương ứng. Bảng inode chứa các thông tin gồm loại tập tin, kích thước, quyền truy cập, con trỏ đến những khối dữ liệu liên quan và các thuộc tính khác.


####2. Ext3 



*So sánh ext2 và ext3
<img src="http://i.imgur.com/X2gRKyF.png">
