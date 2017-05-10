---
layout: default
title:  "Freebie Download"
---

<header class="post-header">
	<h1 class="post-title" itemprop="name headline">{{ page.title }}</h1>
</header>

<article class="post">
	<div class="entry-content" itemprop="articleBody">
	  <p style="display: gone;"/>
	  <p>Hello there, thanks for stopping by! You can download the link below, happy stitching! :tada::heart:</p>
    <img id="img-preview" alt="Preview"/>
    <div class="design-download"/>
	</div>
</article>

<script>
function getParameterByName(name, url) {
    if (!url) url = window.location.href;
    name = name.replace(/[\[\]]/g, "\\$&");
    var regex = new RegExp("[?&]" + name + "(=([^&#]*)|&|#|$)"),
        results = regex.exec(url);
    if (!results) return null;
    if (!results[2]) return '';
    return decodeURIComponent(results[2].replace(/\+/g, " "));
}

// set freebie links
var downloadLink = getParameterByName('download_link');
var extensions = ['csd', 'dst', 'edr', 'exp', 'hus', 'jef', 'pcs', 'pes', 'sew', 'vip', 'vp3', 'xxx']
for (var i = 0; i < extensions.length; ++i) {
  var extension = extensions[i];
  var anchor = document.createElement('a');
  anchor.setAttribute('href', downloadLink + '.' + extension);
  anchor.innerHTML = extension;
  anchor.className = 'link-freebie';
  document.getElementsByClassName('design-download')[0].appendChild(anchor);
}

// set preview img
var imgLink = getParameterByName('img_link');
document.getElementById("img-preview").src = imgLink;

// set name
var name = getParameterByName('design_name');
document.getElementsByClassName("post-title")[0].innerHTML = name;
</script>

<style>
#img-preview {
  margin-bottom: 20px;
}
.design-download {
  text-align: center;
}
.post-header:before {
  display: none;
}
</style>

