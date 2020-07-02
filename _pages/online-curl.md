---
layout: page
title: "Online cURL"
description: "Post cURL requests online directly from your browser and check server responses."
permalink: /online-curl/
status: planned
---

cURL is a popular command-line tool for transferring data to or from a server. This online cURL client supports the basic cURL commands for working with the HTTP/s protocol.

<form>
  <div class="form-group">
    <label for="inputContainer">cURL command</label>
    <textarea class="form-control" id="inputContainer" rows="5"></textarea>
  </div>
  <button id="actionBtn" type="button" class="btn btn-primary">cURL</button>
  <br><br>
  <div class="form-group">
    <label for="outputContainer">Parsed cURL</label>
    <textarea class="form-control" id="outputContainer" rows="10"></textarea>
  </div>
</form>

<script src="https://cdn.jsdelivr.net/npm/curl-parser-js@0.0.3/dist/parse-curl-js.min.js"></script>
<script>
  document.getElementById('actionBtn').onclick = function() {
    var inputData = document.getElementById('inputContainer').value;
    var outputData = JSON.stringify(parse_curl_js.parse(inputData), null, 4);
    document.getElementById('outputContainer').value = outputData;
  };
</script>

#### Did you know?

cURL (pronounced 'curl') is a computer software project providing a library (libcurl) and command-line tool (curl) for transferring data using various network protocols.
The name stands for "Client URL", which was first released in 1997.
