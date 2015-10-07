####1.0 Check a particualar partition ext4 is journaled
sudo dumpe2fs /dev/sda1 | more
hoặc tune2fs -l /dev/sda1 | grep features
(Chú ý dòng features: has_journal)

<img src="http://i.imgur.com/KAgdE3C.png">

####1.1 Disable journaling
- umount thư mục (ví dụ: umount /data)
- tune2fs -O ^has_journal /dev/sda1
(delete or remove has_journal feature)

<img src="http://i.imgur.com/Gc6dv4w.png">


