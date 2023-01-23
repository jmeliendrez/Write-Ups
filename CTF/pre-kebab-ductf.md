# Pre-Kebab Challenge - DownUnderCTF

<!-- wp:paragraph -->
<p>This challenge was pretty fun and straightforward. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":142,"width":474,"height":405,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-full is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-28-at-12.54.26-am.png" alt="" class="wp-image-142" width="474" height="405"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>As you can see the challenge is to look at the image and figure out from where it was taken.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Here is the image:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":143,"width":647,"height":363,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/OSINTGEO-1024x576.jpg" alt="" class="wp-image-143" width="647" height="363"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>A quick reverse image search produces this result:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":144,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-28-at-12.59.18-am-1024x567.png" alt="" class="wp-image-144"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>This building looks like the first result - The Epping Club. I quickly checked this on the website and confirmed that it was. At this point I entered the name DUCTF{TheEppingClub}. This came back with 'Incorrect'!! I was confused. I re-read the challenge and realised that it was not what building is in the picture but where the photo was taken.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>At this stage I got onto Google Maps Street View to compare what is in the picture to what is on the street. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":148,"width":478,"height":263,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-28-at-1.09.33-am-1-1024x565.png" alt="" class="wp-image-148" width="478" height="263"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>One thing that stands out is that there is a sign missing from the front of the building shown in our picture.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":149,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/OSINTGEO-edited.jpg" alt="" class="wp-image-149"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It looks like the black and orange sign says 'SUPERCELLARS'. This clue could mean that that it was taken from either a pub or a bottle shop. Looking away from the building in street view, it becomes appparent where the photo was taken from.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":150,"width":563,"height":279,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-28-at-1.24.10-am-1024x509.png" alt="" class="wp-image-150" width="563" height="279"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Zooming out we see this:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":151,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-28-at-1.24.41-am-1024x271.png" alt="" class="wp-image-151"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>There's a building behind the bottle shop that has a window high enough to be able to that the photo from.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>That build is:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":152,"width":545,"height":370,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-28-at-1.26.00-am-1024x697.png" alt="" class="wp-image-152" width="545" height="370"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The Epping Hotel. I entered this at DUCTF{TheEppingHotel} and this time it was correct!!</p>
<!-- /wp:paragraph -->
