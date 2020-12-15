---
layout: page
title: "URI Decoder / Encoder"
description: "Decode / Encode URI or POST (x-www-form-urlencoded) parameters"
permalink: /uri-encode-decode/
status: ready
---

Decode / Encode URI or POST (x-www-form-urlencoded) parameters
(currently decoding only, encoding will be available soon).

<form>
  <div class="form-group">
    <label for="inputContainer">URI encoded string:</label>
    <textarea class="form-control" id="inputContainer" rows="5"></textarea>
  </div>
  <br>
  <div class="form-group">
    <label>Decoded params:</label>
    <div id="decoded">
    </div>
  </div>
</form>

<style>
  body {font-family: sans-serif;}
  input.key {width: 20%;}
  input.val {width: 75%;}
</style>
<script>
  /* Resources: */
  /* https://stackoverflow.com/questions/8486099/how-do-i-parse-a-url-query-parameters-in-javascript */
  decodeURI = (src) => {
    return decodeURIComponent(src);
  };
  decodeSpace = (src) => {
    return src.split("+").join(" ");
  };
  splitParams = (src) => {
    var result = {};
    src.split("&").forEach((part) => {
      var item = part.split("=");
      result[item[0]] = decodeSpace(decodeURI(item[1]));
    });
    return result;
  };

  makeInput = (cssClass, val) => {
    var input = document.createElement("input");
    input.type = "text";
    input.className = cssClass;
    input.value = val;
    return input;
  };

  const ic = document.getElementById('inputContainer');

  handleChange = (event) => {
    splitObj = splitParams(ic.value);
    targetNode = document.getElementById('decoded');
    targetNode.innerHTML = '';
    for (var key in splitObj) {
      targetNode.appendChild(makeInput("key", key));
      targetNode.appendChild(document.createTextNode(" = "));
      targetNode.appendChild(makeInput("val", splitObj[key]));
      targetNode.appendChild(document.createElement("br"));
    }
  };

  ic.addEventListener('input', handleChange);
</script>
