# Linux-TTY-Patch
Let `/dev/concole` or `/dev/tty*` support ALL UTF-8 charset. 4.20 has change, some languages have problems, and it also appears in previous versions. now(v4.20) it works only to display CJK charset, but you can use `setfont` from `kbd` package to solve that.
## How To Use
Change to your kernel source directory, and patch this like other patch.
```
$patch -Np1 < *core you want to apply*
$patch -Np1 < *fonts you want to apply*
```
  
  In 4.20, you need put font file in `fbdev/core` dir, don't patch up the fonts patch. And you must enable `8x16` font, cjk font is `16x16(8x8 + 8x8)`. If you want other languages support, type `man setfont` to get info. This may better than changing kernel, and the new patch only affects CJK.  
  
  The unicode bitmap fonts file is here:  
    `drivers/video/fbdev/core/fonts_utf8.h`  
  In old version, font file on:  
    `drivers/video/console/fonts_utf8.h`  
  
  ## About
  I edit it to make it be able to use on linux kernel 4.20. And I have't contacted the original author of this patch, this patch is too old. But the patch may better than CJKTTY. It handled separately the wide character from the general character, this make it be able to present custom glyph. CJK font cannot be changed yet.
