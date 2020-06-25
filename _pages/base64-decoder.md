---
layout: page
title: "Base64 Decoder/Encoder"
description: "Encode/decode Base64-encoding; escape XML, URL's and ECMAScript; translate to UTF-8."
permalink: /base64-decoder/
status: ready
---

An online tool that does exactly what it says; decodes Base64 encoding and encodes into it quickly and easily. Base64 encode your data in a hassle-free way, or decode it into human-readable format.

<form>
  <div class="form-group">
    <label for="inputContainer">Decode/Encode from/to Base64 format</label>
    <textarea class="form-control" id="inputContainer" rows="5"></textarea>
  </div>
  <button id="decodeBtn" type="button" class="btn btn-primary">Decode</button>
  <button id="encodeBtn" type="button" class="btn btn-primary">Encode</button>
  <br><br>
  <div class="form-group">
    <label for="outputContainer">Decoded/Encoded output</label>
    <textarea class="form-control" id="outputContainer" rows="5"></textarea>
  </div>
</form>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Base64/1.1.0/base64.min.js"></script>
<script>
  document.getElementById('decodeBtn').onclick = function() {
    var inputData = document.getElementById('inputContainer').value;
    var outputData = window.atob(inputData);
    document.getElementById('outputContainer').value = outputData;
  };
  document.getElementById('encodeBtn').onclick = function() {
    var inputData = document.getElementById('inputContainer').value;
    var outputData = window.btoa(inputData);
    document.getElementById('outputContainer').value = outputData;
  };
</script>

#### Did you know?

Base64 encoding schemes are commonly used when there is a need to encode binary data that needs be stored and transferred over media that are designed to deal with textual data. This is to ensure that the data remains intact without modification during transport. Base64 is used commonly in a number of applications including email via MIME, and storing complex data in XML or JSON.
