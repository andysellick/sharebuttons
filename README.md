Sharebuttons
============

Quick bit of code to add share buttons to your website with minimal effort. Includes Facebook, Twitter, Google+, Pinterest and Linkedin.

Usage
-----

Include the CSS file on your page and add the following code before the closing body tag (or copy it from the included index.html)

```html
	<script>
		window.onload = function(){
			var l = escape(window.location.href);
			var el = document.getElementById('sharelinks');
			var h = el.innerHTML.replace(/linkhere/gi,l);
			el.innerHTML = h;
		};
	</script>
	<div class="sharebuttons">
		<div class="sharingbuttons" id="sharelinks">
			<a href="https://www.facebook.com/sharer/sharer.php?u=linkhere" class="fb" target="_blank">Share on Facebook</a>
			<a href="https://twitter.com/home?status=linkhere" class="tw" target="_blank">Share on Twitter</a>
			<a href="https://plus.google.com/share?url=linkhere" class="gp" target="_blank">Share on Google+</a>
			<a href="https://pinterest.com/pin/create/button/?url=linkhere&media=&description=" class="pin" target="_blank">Pin on Pinterest</a>
			<a href="https://www.linkedin.com/shareArticle?mini=true&url=linkhere&title=&summary=&source=" class="li" target="_blank">Share on LinkedIn</a>
		</div>
	</div>
```

Also include the images dir (you may need to update the CSS to point to the correct place).

About
-----

This will add some social media buttons to as fixed elements to the right hand side of your page. Figures out the URL you're on and updates the buttons automatically. If you want it to be a bit more advanced feel free to expand upon it - it's only meant as a starting point.

Written as a lightweight alternative to all the massively bloated plugins that claim to do this for you. Has no external dependencies. Link code based on examples from: http://www.sharelinkgenerator.com/

