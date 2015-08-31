##Tìm hiểu về lệnh apt-get update, apt-get upgrade và apt-get dist-upgrade

1. apt-get update
- Lệnh này chỉ liệt kê ra (mà không thực thi download) tất cả các packages của phiên bản mới nhất cho các dịch vụ đã được cài trên server.
- Dựa vào lệnh này, cũng có thể biết được các packages mà mình sẽ download về thuộc server của nước nào. 
<img src="http://i.imgur.com/VnGNULy.png">
2. apt-get upgrade
- Lệnh này sẽ tiến hành download và upgrade tất cả các package mới cho các dịch vụ đã cài trên máy server
3. apt-get dist-upgrade
- upgrade các package có liên quan đến kernel
