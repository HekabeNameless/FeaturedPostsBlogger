#Featured Posts Slider for Google Blogger

This code is only working with jQuery (tested with 2.2.2 and above) and optionally also with <a href="http://fortawesome.github.io/Font-Awesome/icons/">Font Awesome</a> if you want to use the same arrows for the slider as I used.<br />

To install copy the jQuery and Font Awesome implementation code above the &lt;/head&gt;-Tag of your template, then insert the basic HTML I provide in the HTML-file here inside the &lt;body&gt; at the point of your template where you want to use it and call the "LoadFeaturedPosts"-Function below.<br />

e.g. like this:<br />
  &lt;script&gt;<br />
    var noimg = "http://yoursite.com/someimg.jpg";<br />
    var MaximumPosts = 5;<br />
    var imgresolution = 1000;<br />
    var Blog = "www.geekgefluester.de";<br />
    var Label = "Feature";<br />
<br />
    LoadFeaturedPosts(MaximumPosts, noimg, imgresolution, Blog, Label);<br />
  &lt;/script&gt;<br />
  <br />
  
  
Insert the CSS before "]]&gt;&lt;/b:skin&gt;" into your Template and you're done. <br />
<em>Notice:</em> The CSS isn't fully responsive yet which means you'll probably have to make some changes if you want to use this for mobile devices as well.
