    // 1) Function for loading posts that are marked as featured
    function LoadFeaturedPosts(maxposts, noimage, resolution, blogurl, featurelabel) {
      var FeatureFeed = "http://" + blogurl + "/feeds/posts/summary/-/" + featurelabel + "?published&alt=json-in-script";

      $.ajax({
        url: FeatureFeed,
        type: "get",
        dataType: "jsonp",
        success: function(data) {
          console.log("Accessed feature feeed.");
          var h = /\/s\d{2,4}/;
          var Markup = "<div id='slidewrapup'>";
          for (var p = 0; p < maxposts; p++) {
            var PostUrl;
            for (var t = 0; t < data.feed.entry[p].link.length; t++) {
              PostUrl = data.feed.entry[p].link[t].href;
            }
            var PostTitle = data.feed.entry[p].title.$t;
            var imgUrl = (data.feed.entry[p].media$thumbnail !== null) ? data.feed.entry[p].media$thumbnail.url : noimage;
            var FinalimgUrl = imgUrl.replace(h, "/s" + resolution);
            var PostSummary = data.feed.entry[p].summary.$t;
            Markup += "<div class='slide'><div class='slidetext'><div class='featurecontent'><h2>" + PostTitle + "</h2>";
            Markup += "<div class='featuretext'><p>" + PostSummary + "...</p><div class='featuremore'><a href='" + PostUrl + "'>Mehr</a></div></div>";
            Markup += "</div></div><img src='" + FinalimgUrl + "'/></div>";
          }
          Markup += "</div>";
          $("#sliderinner").html(Markup);
          FeatureSlider(maxposts); //Beginne mit Sliderfunktion
        },
        error: function() {
          console.log("Could not access feed.");
        }
      });
    }

    // 2) Slider
    function FeatureSlider(slidecount) {

      var bubbles = "<bubbles>";
      for (var b = 0; b < slidecount; b++) {
        bubbles += "<div id='singlebubble'></div>";
      }
      bubbles += "</bubbles>";
      $("#currentcount").html(bubbles);
      $("#currentcount bubbles #singlebubble:nth-child(1)").addClass("bubble-active");

      var sliderWidth = $('#sliderwrap').outerWidth();
      var slider = $('#sliderinner #slidewrapup');
      var sliderCount = slidecount;
      slider.width(sliderCount * sliderWidth);
      var rightclickcount = 0;
      var leftclickcount = 0;

      $('#sliderinner .slide').css('width', sliderWidth);

      var slidewidth = $('#sliderinner .slide').width();
      $("#sliderinner .slide img").css('width', slidewidth);

      $('#right').click(function() {
        if (rightclickcount < slidecount - 1) {
          $('#sliderinner').animate({
            left: '-=' + sliderWidth
          }, 500);
          var realcountbefore = rightclickcount + 1;
          $("#currentcount bubbles #singlebubble:nth-child(" + realcountbefore + ")").removeClass("bubble-active");
          rightclickcount += 1;
          var realcountafter = rightclickcount + 1;
          $("#currentcount bubbles #singlebubble:nth-child(" + realcountafter + ")").addClass("bubble-active");
          if (leftclickcount > 0) {
            leftclickcount -= 1;
          }
        }
      });

      $('#left').click(function() {
        if (rightclickcount > 0) {
          $('#sliderinner').animate({
            left: '+=' + sliderWidth
          }, 500);
          leftclickcount += 1;
          var realcountbefore = rightclickcount + 1;
          $("#currentcount bubbles #singlebubble:nth-child(" + realcountbefore + ")").removeClass("bubble-active");
          rightclickcount -= 1;
          var realcountafter = rightclickcount + 1;
          $("#currentcount bubbles #singlebubble:nth-child(" + realcountafter + ")").addClass("bubble-active");

        }
      });
    }
