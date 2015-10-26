##Buffer/Cache in Linux

By reading the information from disk only once and then keeping it in memory until no longer needed.This is called disk buffering, the memory used for the purpose is called the buffer cache.

Linux is borrowing unused memory for disk caching.

Disk caching makes the system much faster! There are no downsides

If applications want more memory, they just take it back from the disk cache.

The buffer cache caches disk blocks to optimize block I/O.

Although caching improves performance, there is some risk involved. If the computer crashes (due to a power failure, for example), the system may not have time to copy the cache back to the disk. In this case, whatever changes you made to the data will be lost. Usually, however, the cache system updates the disk frequently so that even if you lose some data, it will not be much

Types of disk cache

  - Write-back
  - Write-through

[Cache Experiment](http://www.linuxatemyram.com/play.html)


###write-through mode
<img src="http://i.imgur.com/7rGSwWV.png">


###write-back mode
<img src="http://i.imgur.com/uRrvbPz.png">


###none mode
<img src="http://i.imgur.com/BvhTAYt.png">
