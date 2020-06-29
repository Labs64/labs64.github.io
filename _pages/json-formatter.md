---
layout: page
title: "JSON Formatter and Validator"
description: "JSON Formatter and Validator helps to format and validate your JSON data."
permalink: /json-formatter/
status: ready
---

JSON Formatter and Validator is very powerful online tool which helps to format and validate your JSON data.

- Pretty-Print unformatted JSON string; supports indentation levels: 2 spaces, 3 spaces, 4 spaces
- Validate JSON online with clear error messages

<form>
  <div class="form-group">
    <label for="inputContainer">JSON string</label>
    <textarea class="form-control" id="inputContainer" rows="5"></textarea>
  </div>
  <button id="actionBtn" type="button" class="btn btn-primary">Format</button>
  <br><br>
  <div class="form-group">
    <label for="outputContainer">Formatted JSON</label>
    <textarea class="form-control" id="outputContainer" rows="5"></textarea>
  </div>
</form>

<script src="{{ site.baseurl }}/assets/vendor/jsonlint/jsonlint.js"></script>
<script>
  document.getElementById('actionBtn').onclick = function() {
    var inputData = document.getElementById('inputContainer').value;
    var outputData = JSON.stringify(JSON.parse(inputData), null, 2);
    document.getElementById('outputContainer').value = outputData;
  };
</script>

#### Did you know?

JSON is a way to store, persist data in a structure which is easy to read and easy to access. JSON stands for JavaScript Object Notation, which machine can understand and generate. JSON structure provides a human-readable collection of information to explain and understand the logical representation of data.
