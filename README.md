# Linux-TTY-UTF-8-Patch
Let TTY of the Linux kernel support UTF-8 (like CJKTTY  
让文本控制台支持显示UTF-8字符（像CJKTTY一样  
 ## How to use
  Chang to you kernel source directory.  
  切换到内核源码目录。  
```
$pacth -Np1 < *you want apply core*
$pacth -Np1 < *you want apply fonts*
```
   and recommend enable 8x16 font;  
   utf8 font on drivers/video/console/fonts_utf8.h  
   you can chang it youself. 4.20 is different;  
   font file on drivers/video/fbdev/core/fonts_utf8.  
   please put font file in there.  
   
   推荐开启 8x16 字体,我的意思是不要用8x8或者其他大小的字体，可能会出问题。  
   字库位置在上面，你可以自己修改成喜欢的，4.20 请自行复制字库到core文件夹里。  
   在第七次修复的版本里，其实什么都没有改，只是强制了一些东西，字体文件依然在fbdev里。  
  ## About
  I edit it make it can use on linux kernel 4.20.  
  我修改了这个补丁让它可以支持4.20。  
  but I have not contacted the original author of this patch, this patch to old.  
  不过我没有联系到原作者，这个补丁太老了。  
  this batter then CJKTTY, i think.  
  个人感觉这个老补丁要好于隔壁CJKTTY，但它的实现方式。。。可能这个修改的过于直接了；  
  不过反正它也没办法合并到内核主线，谁在乎呢？  
