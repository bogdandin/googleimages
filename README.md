# googleimages
button to extract images from google

This script is tested on crome windows


1 Edit one bookmark from bookmar bar


2 At url add this code

javascript: (function() { output = '<html><head><title>SEO Image SERP Extraction Tool</title></head><body>'; if (typeof jQuery == 'undefined') { var script = document.createElement('script'); script.type = "text/javascript"; script.src = "//ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"; document.getElementsByTagName('head')[0].appendChild(script); } function inlocuieste(url) { if (url.length > 200) { return; } var str = url; /* str = str.replace("https:", ""); str = str.replace("http:", ""); */ str = str + '<br />'; return str; } var imgURLList = ''; jQuery("a[jsname]").each(function(index, element) { if (jQuery(this).attr('href')) { var res = jQuery(this).attr('href'); var geoDomain = window.location.host; if (res.includes("imgres")) { var query = res; var vars = query.split('&'); var arr; var linkcount = 0; for (var t = 0; t < vars.length; t++) { var pair = vars[t].split('='); var imgurl; var sourceurl; if (pair[0] == '/imgres?imgurl') { imgURLList += inlocuieste(decodeURIComponent(decodeURIComponent(pair[1]))); imgurl = decodeURIComponent(decodeURIComponent(pair[1])); } if (pair[0] == '/imgres?imgurl') { imgURLList += inlocuieste(decodeURIComponent(decodeURIComponent(pair[1]))); imgurl = decodeURIComponent(decodeURIComponent(pair[1])); } else if (pair[0] == 'imgrefurl') { sourceurl = decodeURIComponent(decodeURIComponent(pair[1])); } } console.log(imgurl); arr = imgurl.split('/'); } } }); output += imgURLList; with(window.open()) { document.write(output); document.close(); } })();

3 At Name add "Google Image Extractor"

4 Save

5 Go to google images search results

5 Pres on that bookmark.
