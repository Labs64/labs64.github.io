---
layout: page
title: "Lorem Ipsum Generator"
description: "This lorem ipsum generator is made for all the webdesigners, designers, webmasters and others who need lorem ipsum."
permalink: /lorem-ipsum-generator/
status: planned
---

This handy tool helps you create dummy text for all your layout needs.

<form>
  <button id="actionBtn" type="button" class="btn btn-primary">Generate</button>
  <br>
  <div class="form-group">
    <label for="outputContainer">Mussum Ipsum</label>
    <textarea class="form-control" id="outputContainer" rows="5"></textarea>
  </div>
</form>

<script src="{{ site.baseurl }}/assets/vendor/mipsum/mipsum.min.js"></script>
<script>
  document.getElementById('actionBtn').onclick = function() {
    const outputData = mIpsum({ pNum: 2 });
    document.getElementById('outputContainer').value = outputData;
  };
</script>


#### Did you know?

**Lorem ipsum** is a pseudo-Latin text used in web design, typography, layout, and printing in place of English to emphasise design elements over content. It's also called placeholder (or filler) text.
