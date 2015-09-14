##Lệnh wget, curl và crontab

###I. What both do
- Cả 2 đều có thể download được nội dung từ HTTP, HTTPs, FTP.
- Đều gửi được HTTP POST requests
- Hỗ trợ HTTP cookies
- Hoạt động mà không cần sự tương tác của người dùng, giống như scripts
- Hoàn toàn là mã nguồn mở và là phần mềm miễn phí
- Đều được phát triển từ những năm 90s.

<img src="http://i.imgur.com/k2vRnL0.png">


#####[wget command examples](http://www.labnol.org/software/wget-command-examples/28750/)
#####[cURL command examples](http://www.thegeekstuff.com/2012/04/curl-examples/)

###II. How they differ
#####1. Wget
- Wget được typed khi chỉ cần sử dụng left-hand trên bàn phím qwerty! =)))
- Hỗ trợ Public Suffix List cho việc xử lý cookie domains. Còn cURL thì không có (The Public Suffix List is a list of all known public suffixes, examples: .com, .co.uk, .vn, .edu.vn)
- Chỉ hỗ trợ GnuTLS hoặc OpenSSL cho SSL/TLS support (Secure Socket Layer/ Transport Security Layer)
- Hỗ trợ no SOCKs
- Hỗ trợ xác thực căn bản qua HTTP proxy
- Không yêu cầu thêm các options cho việc download một url, trong khi cURL cần bắt buộc phải có -o hoặc -O
- Wget chỉ dùng command-line only, không có lib hoặc bất kì một dạng nào khác.
- Wget (1995) ra đời sớm hơn cURL (cuối 1996)
- Có khả năng phục hồi download và download đệ quy

#####2. cURL
- Hỗ trợ một vài giao thức SOCKs cho việc truy cập proxy
(Socket Secure (SOCKS) is an Internet protocol that routes network packets between a client and server through a proxy server)
- Hỗ trợ gzip và tự động giải nén thư mục
- Hỗ trợ nhiều phương thức HTTP xác thực hơn, đặc biệt là over HTTP proxies: Basic, Digest, NTLM và Negotiate 
- Hỗ trợ nhiều giao thức hơn. cURL hỗ trợ FTP, FTPS, Gopher, HTTP, HTTPS, SCP, SFTP, TFTP, TELNET, DICT, LDAP, LDAPS, FILE, POP3, IMAP, SMB/CIFS, SMTP, RTMP and RTSP. Wget chỉ hỗ trợ HTTP, HTTPS and FTP.

<img src="http://i.imgur.com/FblGJH6.png">

###III. Crontab
crontab (CRON TABle - cron theo tiếng Greek là time, tab- table) là một file gồm lịch trình của các cron entries được thực thi tại một thời điểm xác định.
#####1. Crontab commands
- export EDITOR=vi; xác định trình chỉnh sửa khi mở file crontab
- crontab -e: chỉnh sửa file crontab, hoặc tạo một file mới nếu chưa tồn tại
- crontab -l: display file crontab
- crontab -r: remove file crontab
- crontab -v: display lần cuối cùng mà bạn edit file crontab (option này chỉ available trên một vài systems)

#####2. Crontab file
<img src="http://i.imgur.com/Y2XOzvf.png">

#####3. Crontab example
<img src="http://i.imgur.com/opHNLr8.png">

câu lệnh trên sẽ kiểm tra status của database các ngày trong tuần, kể cả cuối tuần, từ 9a.m - 6p.m
