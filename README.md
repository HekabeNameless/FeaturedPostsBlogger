# FeaturedPostsBlogger
Featured Posts Slider for Google Blogger

This code is only working with jQuery (tested with 2.2.2 and above) and optionally also with Font Awesome if you want to use the same arrows for the slider as I used.

To install copy the jQuery and Font Awesome implementation code above the </head>-Tag of your template, then insert the basic HTML I provide in the HTML-file here at the point of your tempalte where you want to use it and call the "LoadFeaturedPosts"-Function below.

e.g. like this:
  <script>
    var noimg = "http://yoursite.com/someimg.jpg";
    var MaximumPosts = 5;
    var imgresolution = 1000;
    var Blog = "www.geekgefluester.de";
    var Label = "Feature";

    LoadFeaturedPosts(MaximumPosts, noimg, imgresolution, Blog, Label);
  </script>
  
Insert the CSS before "]]></b:skin>" into your Template and you're done. Notice: The CSS isn't fully responsive yet which means you'll probably have to make some changes if you want to use this for mobile devices as well.
