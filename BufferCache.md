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


- - - 

I/O Mode:

    io=native for block device based VMs.
    io=threads for file-based VMs.


###Guest Test Performance

####1. Write-back cache mode w/ default IO mode
#####iozone test - test file I/O performance
iozone -a -i0 -i1 -i2 -s512M -r64k
<img src="http://i.imgur.com/EYuZM6Q.png">


#####dd read test: one process
<img src="http://i.imgur.com/zvr8qjC.png">


#####dd write test: one process
<img src="http://i.imgur.com/jcQQvBO.png">


#####FIO random read
<img src="http://i.imgur.com/Z2gPgax.png">



#####FIO random write
<img src="http://i.imgur.com/kdNHWWU.png">


#####FIO seq read
<img src="http://i.imgur.com/t6Dxw3r.png">


#####FIO seq write
<img src="http://i.imgur.com/d2Y8IiA.png">

####1. Write-back cache mode w/ native IO mode

#####iozone test - test file I/O performance
iozone -a -i0 -i1 -i2 -s512M -r64k
<img src="http://i.imgur.com/8WVF9MP.png">

#####dd read test: one process
<img src="http://i.imgur.com/I19hpTs.png">

#####dd write test: one process
<img src="http://i.imgur.com/aDx7qlJ.png">


#####FIO random write
<img src="http://i.imgur.com/OKmCRP3.png">

#####FIO random read
<img src="http://i.imgur.com/FTkBG4b.png">

#####FIO seq read
<img src="http://i.imgur.com/yfa680k.png">


#####FIO seq write
<img src="http://i.imgur.com/xImRarq.png">
