# 101 Web1 Challenge

<p>I got to go to CrikeyCon this year (2022) and was able to take part in the CTF challenges there. I'm still a newbie when it comes to CTF's so I thought I'd do a basic challenge in the 101 section. I then go into what the vulnerability this challenge represents here and a real world example.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Here is the first challenge:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":84,"width":305,"height":283,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-full is-resized"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-07-at-12.39.59-pm.png" alt="challenge" class="wp-image-84" width="305" height="283"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>No hints huh? I navigated to the link and was met with this webpage:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":87,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-07-at-12.43.08-pm-1024x559.png" alt="" class="wp-image-87"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>My first thought was to inspect the source code like a "true hacker". (You can do this by either right-clicking and selecting 'View Source', or pressing F12).</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":88,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-07-at-12.45.17-pm-1024x868.png" alt="" class="wp-image-88"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After opening the collapsed HTML I read through the comments to see if the 'developers' left anything important exposed. And wouldn't you know it, the a line saying this: </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":89,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image size-full"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-07-at-12.47.10-pm.png" alt="" class="wp-image-89"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>"Do we still need /devtesting5 ?" This seems like an interesting rabbit hole to go down. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>So, entering the url again: https://101-web1.crikeyconctf.com/devtesting5/ we get to this page:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":91,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://meliendrez.tech/wp-content/uploads/2022/09/Screen-Shot-2022-09-07-at-12.49.56-pm-1024x280.png" alt="" class="wp-image-91"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>And there's the flag!</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>What's the issue here?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>So, this is a simple CTF challenge but it highlights a vulnerability that could lead to problems. In this challenge what is exposed is a file path to '/devtesting5' which means that a folder is exposed that should not be. Clearly, this is meant to be a development testing folder and this could contain sensitive source code or databases with improper authentication protocols in place. This vulnerability leads to attackers being able to access potentially confidential data or gain unauthorised access to the webserver. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A great example of this kind of vulnerability in the wild was the case in Missouri back in 2021 where teacher Social Security Numbers were exposed in the HTML of the schools webpage. You can read about this <a href="https://www.stltoday.com/news/local/education/missouri-teachers-social-security-numbers-at-risk-on-state-agency-s-website/article_f3339700-ece0-54a1-9a45-f300321b7c82.html">here</a>. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>To mitigate this proper code checks need to be put in place. This would include extensive reviews of the HTML code/comments. For this site/challenge the page is simple and static but in full pages a vulnerability like this may be harder to spot, especially when there are hundreds of lines of HTML and JavaScript. It's important to check comments and code for filepath information that may be exposed to secure web pages from this kind of vulnerability. </p>
<!-- /wp:paragraph -->
