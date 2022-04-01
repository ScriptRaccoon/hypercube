# Hypercube with CSS

This is an attempt of a visualization of the hypercube (4-dimensional cube) with CSS - without JavaScript.

Demo: https://hypercubecss.netlify.app

You can move your mouse to apply rotations to the hypercube. Horizontal movement applies a rotation to the last two coordinates in 4D. Vertical movement applies a rotation along the Y-axis in 3D.

To achieve this control without JavaScript, we have 400 area elements which cover the screen and whose hover events change CSS variables which encode the rotation. (This has to be done via a loop, which is the only reason I need Sass here. It compiles down to a large CSS file, which is still CSS, though.)

Currently only the 16 points of the hypercube are shown, projected onto 3D. Drawing the lines appears to be very hard, perhaps not even possible with CSS only. One main obstacle here is that, although Sass has trigonometric functions, these can only be used for fixed parameters, but for our rotations we need to apply them to dynamic CSS variables. For this reason the code also uses a rough Taylor expansion of the sine and cosine functions.

There is a bug as soon as we reach the 16th area column (so when you move to the right far enough). There is an obvious discontinuity of the points. I do not know why that happens.
