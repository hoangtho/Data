If you maintain a system of fair complexity or require
high-availability, you should seriously consider a journaling file
system
- - - 

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

#####Advantages of Journaling

Advantages of Journaling Filesystems

Although some of the advantages of journaling filesystems have been discussed earlier, this section summarizes the most important performance and reliability improvements provided by journaling filesystems. These are

    Faster system restart time after a crash because the computer does not have to examine each filesystem in its entirety to guarantee its consistency. Journaling filesystems can be made consistent by simply replaying outstanding, complete entries in the log. Incomplete entries in the log are simply discarded when the log is replayed.

    Greater flexibility. Journaling filesystems often create and allocate inodes as they are needed, rather than preallocating a specific number of inodes when the filesystem is created. This removes limitations on the number of files and directories that can be created on that partition. Not having to manage lists of inodes that have not yet been allocated also reduces some of the overhead associated with maintaining filesystem metadata and reduces the overhead involved if you subsequently want to change the size of a journaling filesystem.

    Faster file and directory access. All the journaling filesystems discussed in this book use more sophisticated algorithms for storing and accessing files and directories than do traditional non-journaling filesystems. The JFS, ReiserFS, and XFS journaling filesystems all use advanced data structures such as B-Trees, B+Trees, or B*Trees to speed up looking up and storing inodes.

    Writing to the log can be optimized. Like all filesystem updates made by non-journaling filesystems, writes to the log used by a journaling filesystem must be made synchronously. However, the logs used by journaling filesystems typically can be written to more quickly than a filesystem itself for two main reasons: they can be written to in raw fashion rather than having to go through the filesystem, and log writes almost always consist of appending data rather than inserting it. Most logs are preallocated, fixed-size, circular, and use custom read and write routines.




