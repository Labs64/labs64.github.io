---
layout: page
title: "JSON Formatter and Validator"
description: "JSON Formatter and Validator helps to format and validate your JSON data."
permalink: /json-formatter/
status: ready
---

JSON Formatter and Validator is very powerful online tool which helps to format and validate your JSON data.

- Validate JSON online incl. error messages
- Pretty-print unformatted JSON string

<form>
  <div class="form-group">
    <label for="inputContainer">JSON string</label>
    <textarea class="form-control" id="inputContainer" rows="5"></textarea>
  </div>
  <button id="actionBtn" type="button" class="btn btn-primary">Validate & Format</button>
  <br><br>
  <label for="validationResult">Validation result</label>
  <pre id="validationResult"></pre>
  <br>
  <div class="form-group">
    <label for="outputContainer">Formatted JSON</label>
    <textarea class="form-control" id="outputContainer" rows="10"></textarea>
  </div>
</form>

<script src="{{ site.baseurl }}/assets/vendor/jsonlint/json2.js"></script>
<script src="{{ site.baseurl }}/assets/vendor/jsonlint/jsonlint.js"></script>
<style>
  body {font-family: sans-serif;}
  #validationResult {
    padding: 1em;
  }
  .pass {
    background-color: #efe;
    color: #393;
    border: 2px solid #393;
  }
  .fail {
    background-color: #fee;
    color: #933;
    border: 2px solid #933;
  }
</style>
<script>
  document.getElementById("actionBtn").onclick = function () {
    try {
      var inputData = document.getElementById('inputContainer').value;
      var result = jsonlint.parse(inputData);
      if (result) {
        document.getElementById("validationResult").innerHTML = "JSON is valid!";
        document.getElementById("validationResult").className = "pass";
        var outputData = JSON.stringify(result, null, 2);
        document.getElementById('outputContainer').value = outputData;
      }
    } catch(e) {
      document.getElementById("validationResult").innerHTML = e;
      document.getElementById("validationResult").className = "fail";
    }
  };
</script>

#### Did you know?

JSON is a way to store, persist data in a structure which is easy to read and easy to access. JSON stands for JavaScript Object Notation, which machine can understand and generate. JSON structure provides a human-readable collection of information to explain and understand the logical representation of data.
