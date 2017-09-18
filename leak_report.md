# Leak report

_Use this document to describe whatever memory leaks you find in `clean_whitespace.c` and how you might fix them. You should also probably remove this explanatory text._

Valgrind's leak report stated the following:

==12765== 46 bytes in 6 blocks are definitely lost in loss record 1 of 1
==12765==    at 0x4C2FA50: calloc (vg_replace_malloc.c:711)
==12765==    by 0x400678: strip (check_whitespace.c:41)
==12765==    by 0x4006E3: is_clean (check_whitespace.c:62)
==12765==    by 0x40076B: main (check_whitespace.c:87)

Therefore, it can be concluded that 46 bytes were lost that were allocated by calloc, which was called on line 41  of check_whitespace.c in the function strip.