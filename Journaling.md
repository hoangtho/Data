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

- Faster system restart time after a crash because the computer does not have to examine each filesystem in its entirety to guarantee its consistency. Journaling filesystems can be made consistent by simply replaying outstanding, complete entries in the log. Incomplete entries in the log are simply discarded when the log is replayed.

- Greater flexibility. Journaling filesystems often create and allocate inodes as they are needed, rather than preallocating a specific number of inodes when the filesystem is created. This removes limitations on the number of files and directories that can be created on that partition. Not having to manage lists of inodes that have not yet been allocated also reduces some of the overhead associated with maintaining filesystem metadata and reduces the overhead involved if you subsequently want to change the size of a journaling filesystem.

- Faster file and directory access. All the journaling filesystems discussed in this book use more sophisticated algorithms for storing and accessing files and directories than do traditional non-journaling filesystems. The JFS, ReiserFS, and XFS journaling filesystems all use advanced data structures such as B-Trees, B+Trees, or B*Trees to speed up looking up and storing inodes.

- Writing to the log can be optimized. Like all filesystem updates made by non-journaling filesystems, writes to the log used by a journaling filesystem must be made synchronously. However, the logs used by journaling filesystems typically can be written to more quickly than a filesystem itself for two main reasons: they can be written to in raw fashion rather than having to go through the filesystem, and log writes almost always consist of appending data rather than inserting it. Most logs are preallocated, fixed-size, circular, and use custom read and write routines.



##### 1.3Change journaling mode
tune2fs -o journal_data /dev/sda#

-o: journal_data, journal_data_writeback, journal_data_ordered

##### 1.4Enable journaling mode
tune2fs -O has_journal /dev/sda#

##### 1.5Change journaling size
tune2fs -J size=$SIZE /dev/sda#

A larger journal may give you better performance (at the cost of more disk space and longer recovery times)


####2. Journaling Mode
#####2.1 Writeback 
In writeback mode, only file system metadata is journaled; data blocks are written directly to their fixed location. This mode does not enforce any ordering between the journal and fixed-location data writes, and because of this, writeback mode has the weakest consistency semantics of the three modes. Although it guarantees consistent file system metadata, it does not provide any guarantee as to the consistency of data blocks.

#####2.2 Ordered
In ordered journaling mode, again only metadata writes are journaled; however, data writes to their fixed location
are ordered before the journal writes of the metadata. Incontrast to writeback mode, this mode provides more sensible consistency semantics, where both the data and the metadata are guaranteed to be consistent after recovery

#####2.3 Data
In full data journaling mode, ext3 logs both metadata and data to the journal. This decision implies that when a process writes a data block, it will typically be written out to disk twice: once to the journal, and then later to
its fixed ext2 location. Data journaling mode provides the same strong consistency guarantees as ordered journaling
mode; however, it has different performance characteristics, in some cases worse, and surprisingly, in some cases,
better.

####3. Test journaling performance
no journaling

<img src="http://i.imgur.com/MVdMYvv.png">

has journaling

<img src="http://i.imgur.com/hX7YE7S.png">

#####Using FIO

no journaling 

<img src="http://i.imgur.com/3tj2JHy.png">

has journaling

<img src="http://i.imgur.com/fflDvSo.png">




