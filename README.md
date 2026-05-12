# part-2-cnn-computer-vision

**What is Convolution?**

A small window of size 3×3 is moved across the image, step by step. At each position, the pixels under that window are looked at and checked for a specific pattern. This process is repeated across the whole image and the results are saved in something called a feature map, which shows where that pattern was found.
The interesting part is that the model is not told what patterns to look for. It figures that out on its own during training. In the beginning, simple things like edges and lines are picked up. In the later layers, more detailed things like the shape of a scratch or a dent are recognised.

**Why is Pooling Used?**

After convolution, the amount of data becomes very large. Pooling is used to make it smaller. In MaxPooling, the image is divided into small 2×2 blocks and only the largest value from each block is kept. So a 64×64 image becomes 32×32, half the size.
This also helps the model in another way. If a defect moves slightly in the image, the result stays mostly the same. So the model can still recognise the defect even if it appears in a slightly different position.

**Why is ReLU Used?**

After each convolution step, ReLU is applied. It does one simple thing, any negative number is changed to zero, and positive numbers are kept as they are.
This is needed because without it, the model can only learn very simple straight-line patterns no matter how many layers are added. ReLU allows the model to learn curves, shapes, and complex patterns like defects.
Older methods like sigmoid were tried before but they caused a problem where the model stopped learning in deep networks. ReLU does not have this problem, so training is faster and works better.

**Why CNNs are Better than Regular Networks for Images?**

In a regular network, the image is converted into a long list of numbers and each pixel is treated separately. The connection between neighbouring pixels is completely lost. This requires a very large number of calculations and the model does not understand the structure of the image at all.
In a CNN, a small filter is applied to one small area of the image at a time. This matches how images actually work, a scratch or a dent exists in one area, not spread across the whole image. The same filter is also reused across the entire image, so far fewer calculations are needed.
Because of this, CNNs understand images much better and work far more efficiently, which is why they are used for tasks like detecting defects on product surfaces.
