Sharebuttons
============

Quick bit of code to add self-populating share buttons to your website with minimal effort. Includes Facebook, Twitter, Google+, Pinterest and Linkedin.

Usage
-----

Include the CSS file on your page and add the following code on your page (or copy it from the included index.html):

```html
	<script>
		function getMetaContentByName(name,attrtype,content){
		   var content = (content==null)?'content':content;
		   var ret = document.querySelector("meta["+attrtype+"='"+name+"']").getAttribute(content);
		   return ret.replace(/ /gi,'%20');
		}
		window.onload = function(){
            var el = document.getElementById('sharelinks');
            var desc = getMetaContentByName('description','name');
            txt = el.innerHTML.replace(/SBDESC/gi,desc);
            var title = getMetaContentByName('og:title','property');
			txt = txt.replace(/SBTITLE/gi,title);
			var img = getMetaContentByName('og:image','property');
			txt = txt.replace(/SBIMG/gi,title);
            var link = escape(window.location.href);
            txt = txt.replace(/SBLINK/gi,link);
            el.innerHTML = txt;
		};
	</script>
	<div class="sharebuttons">
		<div class="sharingbuttons" id="sharelinks">
			<a href="https://www.facebook.com/sharer/sharer.php?u=SBLINK" class="fb" target="_blank">Share on Facebook</a>
			<a href="https://twitter.com/home?status=SBDESC%20SBLINK" class="tw" target="_blank">Share on Twitter</a>
			<a href="https://plus.google.com/share?url=SBLINK" class="gp" target="_blank">Share on Google+</a>
			<a href="https://pinterest.com/pin/create/button/?url=SBLINK&media=SBIMG&description=SBDESC" class="pin" target="_blank">Pin on Pinterest</a>
			<a href="https://www.linkedin.com/shareArticle?mini=true&url=SBLINK&title=SBTITLE&summary=SBDESC&source=" class="li" target="_blank">Share on LinkedIn</a>
		</div>
	</div>
```

Also include the images dir (you may need to update the CSS to point to the correct place).

About
-----

This code gets the URL the page is on, extracts content from the page metadata, and populates the buttons automatically on page load.

It adds social media sharing buttons as fixed elements to the right hand side of your page. On mobile they drop down to appear in their position in the markup, as a centered row of buttons.

Written as a lightweight alternative to all the massively bloated plugins that claim to do this for you. Has no external dependencies. Link code based on examples from: http://www.sharelinkgenerator.com/

