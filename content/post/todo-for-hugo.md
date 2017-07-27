+++
date = "2017-03-08T13:27:28+05:00"
draft = true
title = "todo"
+++

* Register Google Analytics account (edit in head-meta.html)

* Make sure OpenGraph tags are being populated correctly from front-end matter
    * Twitter Cards
        * Summary Card
            * Images must conform to
                * Aspect Ratio of 1:1
                * Minimum Dimensions: 144x144
                * Maximum Dimensions: 4096x4096
                * Less than 5MB in size
                * Only JPG, PNG, WEBP, and GIF supported
        * Summary Large Image Card
            * Images must conform to
                * Aspect Ratio of 2:1
                * Minimum Dimensions: 300x157
                * Maximum Dimensions: 4096x4096
                * Less than 5MB in size
                * Only JPG, PNG, WEBP, and GIF supported
        * App Card
            * Images n/a
        * Player Card
            * Make this image the same dimensions as your player
            * Images with fewer than 68,600 pixels (a 262x262 square image, or a 350x196 16:9 image) will cause the player card not to render
            * Less than 5MB in size
            * Only JPG, PNG, WEBP, and GIF supported
    * Facebook
        * Image Support
            * Regular Posts
                * Use images that are at least 1200 x 630 pixels for the best display on high resolution devices
                * At the minimum, you should use images that are 600 x 315 pixels to display link page posts with larger images
                * Images can be up to 8MB in size
                * If your image is smaller than 600 x 315 px, it will still display in the link page post, but the size will be much smaller
                * Try to keep your images as close to 1.91:1 aspect ratio as possible to display the full image in News Feed without any cropping
                * The minimum image size is 200 x 200 pixels. If you try to use an image smaller than this you will see an error in the Sharing Debugger
            * Game Apps
                * Open Graph Stories Images appear in a square format. Image ratios for these apps should be 600 x 600 px
                * Non-open Graph Stories Images appear in a rectangular format. You should use a 1.91:1 image ratio, such as 600 x 314 px
