# Linux-TTY-Patch
Let `/dev/concole` or `/dev/tty*` support ALL UTF-8 charset. 4.20 has change, some languages has problems, also it appear in previous versions. now(v.4.20) it only work to display CJK charset, but you can ues `setfont` form `kbd` package to solve that.
 ## How To Use
 Change to you kernel source directory, and patch this like other patch. 
```
$patch -Np1 < *you want apply core*
$patch -Np1 < *you want apply fonts*
```
  
  In 4.20, you need put font file in fbdev/core dir, don't patch up the fonts patch. And you must enable `8x16` font, cjk font is `16x16(8x8 + 8x8)`. If you want other languages support, tpye `man setfont` to get info. This may batter then change kernel, and the new patch only affects CJK.  
  
  The unicode bitmap fonts file is here:  
    `drivers/video/fbdev/core/fonts_utf8.h`  
  In old version, font file on:  
    `drivers/video/console/fonts_utf8.h`  
  
  ## About
  I edit it make it can use on linux kernel 4.20. And i have't contacted the original author of this patch, this patch is too old. Bat the patch may batter then CJKTTY. It handled separately the wide character from the general character, this make it can custom glyph. CJK font cannot be change yet.
