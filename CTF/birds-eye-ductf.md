# Bird's Eye View - DownUnderCTF

<!-- wp:paragraph -->
<p>One of the challenges in the GREATEST CTF on the planet (DownUnderCTF) was called Bird's Eye View. The challenge reads as follows:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":125,"width":373,"height":291,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-full is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-26-at-5.41.03-am.png" alt="challenge" class="wp-image-125" width="373" height="291"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>You are provided with view.jpg file and the task is to find out what the name of the picnic area is. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's open it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":126,"width":-202,"height":-113,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/view-1024x576.jpg" alt="" class="wp-image-126" width="-202" height="-113"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Seems like a generic picture of a national park. This CTF is based in Australia and the OSINT challenges are presumably Australian. I thought at this stage to perform a Reverse Image Search with Google. Which produced this result:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":127,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-26-at-5.47.29-am-1024x640.png" alt="" class="wp-image-127"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Well, this is overwhelming...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I clicked on a few of the results but they didn't look anything like the the source image. I performed more image searches using Bing, and other services. I then re-read the challenge.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":128,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image size-full"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-26-at-6.00.38-am.png" alt="" class="wp-image-128"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The word 'EXAMINE' stood out to me and I thought about it for a moment and remembered that images carry extra data about the image in the file. This is the stuff that tells you the camera that was used, the time and date <strong>AND</strong> GPS coordinates! This is called EXIF data:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":129,"width":626,"height":262,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-26-at-6.03.01-am-1024x428.png" alt="" class="wp-image-129" width="626" height="262"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I opened the image again and used the shortcut Command+I to open the Information panel. And then navigated to the EXIF GPS data:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":131,"width":326,"height":391,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-full is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-26-at-5.42.10-am.png" alt="" class="wp-image-131" width="326" height="391"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>YES!!! There it is!</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I looked this up on Google Maps and got this result:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":132,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-26-at-5.42.44-am-1024x785.png" alt="" class="wp-image-132"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The flag is: <strong>DUCTF{HoopPine}</strong></p>
<!-- /wp:paragraph -->
