# Linux-TTY-UTF-8-Patch
Let TTY of the Linux kernel support UTF-8 (like CJKTTY  
 ## How to use
 ### Chang to you kernel directory. 
	$pacth -Np1 < *you want apply core*
	$pacth -Np1 < *you want apply fonts*
   and recommend enable 8x16 font, utf8 font on 'drivers/video/fbdev/core/fonts_utf8.h' .
   you can chang it youself.

  ## About
  I edit it make it can use on linux kernel 4.20.  
  and I have not contacted the original author of this patch, it to old.  
  this batter then CJKTTY, i think.
