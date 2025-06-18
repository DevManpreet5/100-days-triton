0. do check softmax (day 4) again

1. The fundamental rule is: Use axis only when you have genuinely multi-dimensional tensor structures that you created intentionally. for example if i want to calc max for softmax for 1d vector , dont use axis=0 . u can use it for 2d onwards , attentionb mech , batch processing.

2. lets say u want to operate something on every x index for eg in color inversion u wanna subtract 255 from 1 to 3 index then 4th index keep same then for next subtract then 4th keep same , u need to use newoffsets=offsets%4 then tl.where (offsets<3,a-255,a)

3. tl.atomic_add ensures no race condition when writing to result_ptr[0]
