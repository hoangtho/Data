##Buffer/Cache in Linux

By reading the information from disk only once and then keeping it in memory until no longer needed.This is called disk buffering, the memory used for the purpose is called the buffer cache.

Linux is borrowing unused memory for disk caching.

Disk caching makes the system much faster! There are no downsides

If applications want more memory, they just take it back from the disk cache.

The buffer cache caches disk blocks to optimize block I/O.

[Cache Experiment](http://www.linuxatemyram.com/play.html)
