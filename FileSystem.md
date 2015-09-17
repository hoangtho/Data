##Linux File System

####1. Ext
- The ext file-system uses a system called inodes to track information about the files stored in the virtual directory. The inode system creates a separate table on each physical device, called the inode table , to store the file information. Each stored file in the virtual directory has an entry in  the inode table. The extended part of the name comes from the additional data that it tracks on each file, which consists of:

    The file name
    The file size
    The owner of the file
    The group the file belongs to
    Access permissions for the file
    Pointers to each disk block that contains data from the file

Linux references each inode in the inode table using a unique number (called the inode number ), assigned by the file system as data files are created. The file system uses the inode number to identify the file rather than having to use the full file name and path.

####1. Ext2 (second extended file system)
- ext2 được sinh ra để khắc phục một vài hạn chế của ext như dung lượng file chỉ 2gb, file name size 255 characters
- Khi khởi động, hệ điều hành luôn luôn có 1 chương trình để kiểm tra tính toàn vẹn của hệ thống file đó là fsck (unmount, hệ thống file có dấu hiệu bất thường). Tuy nhiên, quá trình kiểm tra và khôi phục này có thể lâu hay chậm tùy thuộc vào dung lượng của ổ cứng.  
- Không có tính năng journal
  -> Thay vì ghi trực tiếp vào storage device và sau đó update lên inode table. Thì journaling file system sẽ ghi thông tin lên một file tạm thời (được gọi là journal). Sau khi data được ghi thành công lên storage device và inode table, thì journal entry sẽ bị xóa đi.
  -> journaling chỉ được sử dụng khi ghi dữ liệu lên ổ cứng, khắc phục vấn đề khi ổ cứng gặp vấn đề. Nếu không có journaling, hệ thống sẽ không biết được file có được ghi đầy đủ lên ổ đĩa hay không.
- Max file size từ 16gb - 32gb
- ext2 file system max từ 2tb - 32tb
- ext2 thường được dùng cho flash-based storage media (như SD cards, and USB flash drives)
- Kiến trúc Ext2 dùng cấu trúc dữ liệu được gọi là nút định dạng (inode) để tham chiếu và định vị tập tin cũng như các dữ liệu tương ứng. Bảng inode chứa các thông tin gồm loại tập tin, kích thước, quyền truy cập, con trỏ đến những khối dữ liệu liên quan và các thuộc tính khác.
- Nhóm các data blocks cho một file => file system không phải search toàn bộ physical device để tìm được data block khi read.
- 


####2. Ext3 (third extended file system)
- Hỗ trợ cơ chế journaling file system (tuy an toàn hơn, nhưng chậm hơn)



<img src="http://i.imgur.com/X2gRKyF.png">

*So sánh ext2 và ext3
