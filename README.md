# Deep Learning Neural Style Transfer

Neural style transfer is an optimization algorithm used to take a “content” image and a “style” image, and
blend them together so the output image contains the same objects of the content image, but “rendered” in
the style of the style image: https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/
Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf In this project, you will implement your own neural style
transfer algorithm to mix content images with style images.
* Use a pre-trained image classification network (eg. 19-layer VGG network) to build the content and style
representations, implement the weighted loss function (with content & style loss), and run gradient descent
over the output image.
* Pick two content images and two style images (paintings, photographs, etc), and test your algorithm over
the 4 resulting combinations of content and style.
* Study how the results would change with respect to training iterations, different random seeds and relative
weight of content & style loss in the loss function. Discuss any findings that you find of interest.
* This project can be done without a GPU, and an advanced version of this project would involve a GPU.
* There are numerous examples of code doing similar things on the internet, though you are expected to do
your own work for this project. If you source any key ideas from elsewhere, you must reference the source of
those ideas
