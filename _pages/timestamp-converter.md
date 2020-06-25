---
layout: page
title: "Timestamp to Date Converter"
description: "Convert timestamp to date or date to timestamp easily."
permalink: /timestamp-converter/
status: planned
---

Several date to millisecond calculators, useful when coding countdown timers, cookie expiration settings or other date related scripts.

### Convert Timestamp to Date

<form>
  <div class="form-group">
    <label for="timestamp">Timestamp</label>
    <input type="text" value="999999999999" id="timestamp" min="0" max="999999999999">
  </div>
  <button id="actionBtn1" type="button" class="btn btn-primary">Convert</button>
  <br>
  <div class="form-group">
    <label for="date">Date</label>
    <input type="text" class="form-control" id="date">
  </div>
</form>

<hr>

### Convert Date to Timestamp

<form>
  <div class="form-group">
    <label for="date">Date</label>
    <input type="text" class="form-control" id="date" placeholder="2020-12-12 12:12:12">
  </div>
  <button id="actionBtn2" type="button" class="btn btn-primary">Convert</button>
  <br>
  <div class="form-group">
    <label for="timestamp">Timestamp</label>
    <input type="text" value="12" id="timestamp">
  </div>
</form>

<script>
  document.getElementById('actionBtn1').onclick = function() {
    var inputData = document.getElementById('timestamp').value;
    var outputData = new Date(inputData).toLocaleString();
    document.getElementById('date').value = outputData;
  };

  document.getElementById('actionBtn2').onclick = function() {
    var inputData = document.getElementById('date').value;
    var outputData = Date.parse(inputData)/1000;
    document.getElementById('timestamp').value = outputData;
  };
</script>

#### Did you know?

Unix time (also known as POSIX time or Epoch time) is a system for describing instants in time, defined as the number of seconds that have elapsed since 00:00:00 Coordinated Universal Time (UTC), Thursday, 1 January 1970, not counting leap seconds.
It is used widely in Unix-like and many other operating systems and file formats. Because it does not handle leap seconds, it is neither a linear representation of time nor a true representation of UTC.
