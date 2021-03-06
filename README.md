#Featured Posts Slider for Google Blogger (by Label)

This code is only working with jQuery (tested with 2.2.2 and above) and optionally also with <a href="http://fortawesome.github.io/Font-Awesome/icons/">Font Awesome</a> if you want to use the same arrows for the slider as I used. Anyway, be careful to use a right version of jQuery and not having an old version left and forgotten in your template if you're inserting a more recent one.<br />

To install copy the jQuery (you can get it e.g. <a href="https://developers.google.com/speed/libraries/#jquery">here</a>) and Font Awesome (grab it <a href="http://fontawesome.io/get-started/">here</a> if you don't have it already) implementation code above the &lt;/head&gt;-Tag of your template, then insert somewhere below &lt;body&gt; but before &lt;/body&gt; the Code from my Javascript-file inside &lt;script&gt; and <co&lt;/script&gt;. After that copy the basic HTML I provide in the HTML-file here at the point of your template where you want to use the slider and call the "LoadFeaturedPosts"-Function below.<br />
<em>Notice:</em> The code for calling the function must be <em>below</em> the full Javascript you can get from my file here. Otherwise the slider won't work. Furthermore, take caution use a correct version of your URL which means for blogspot-urls something like "yourblog.blogspot.com" with no "www" and no "http://" or "https://".<br />

e.g. like this (explanation for the meaning of the variables below):<br />
  &lt;script&gt;<br />
    var noimg = "http://yoursite.com/someimg.jpg";<br />
    var MaximumPosts = 5;<br />
    var imgresolution = 1000;<br />
    var Blog = "www.geekgefluester.de"; // Your Blog-URL<br />
    var Label = "Feature";<br />
<br />
    LoadFeaturedPosts(MaximumPosts, noimg, imgresolution, Blog, Label);<br />
  &lt;/script&gt;<br />
  <br />
  <em>Explanation:</em><br />
  noimg = An URL to the image that should be shown if a post has no own image<br />
  MaximumPosts = The count of posts that should be shown. (Be careful to use a number for MaximumPosts that isn't larger than the total number of posts you labelled with you special Label. In my example, there must be at least 5 posts with the Label "Feature" otherwise this won't work.)<br />
  imgresolution = The resolution in which your images should be shown<br />
  Label = "The Label with which you mark the posts for your slider<br />
  <br />
  
Insert the CSS before "]]&gt;&lt;/b:skin&gt;" into your Template and you're done. <br />
<em>Notice:</em> The CSS isn't fully responsive yet which means you'll probably have to make some changes if you want to use this for mobile devices as well.<br />
<br />
