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
    <label for="timestamp1">Timestamp</label>
    <input type="text" class="form-control" value="0" id="timestamp1">
  </div>
  <button id="actionBtn1" type="button" class="btn btn-primary">Convert</button>
  <br>
  <div class="form-group">
    <label for="date1">Date</label>
    <input type="text" class="form-control" id="date1">
  </div>
</form>

<hr>

### Convert Date to Timestamp

<form>
  <div class="form-group">
    <label for="date2">Date</label>
    <input type="text" class="form-control" id="date2" placeholder="2020-12-12 12:12:12">
  </div>
  <button id="actionBtn2" type="button" class="btn btn-primary">Convert</button>
  <br>
  <div class="form-group">
    <label for="timestamp2">Timestamp</label>
    <input type="text" class="form-control" id="timestamp2">
  </div>
</form>

<script>
  document.getElementById('actionBtn1').onclick = function() {
    var inputData = document.getElementById('timestamp1').value;
    var outputData = new Date(inputData).toLocaleString();
    document.getElementById('date1').value = outputData;
  };

  document.getElementById('actionBtn2').onclick = function() {
    var inputData = document.getElementById('date2').value;
    var outputData = Date.parse(inputData)/1000;
    document.getElementById('timestamp2').value = outputData;
  };
</script>

#### Did you know?

Unix time (also known as POSIX time or Epoch time) is a system for describing instants in time, defined as the number of seconds that have elapsed since 00:00:00 Coordinated Universal Time (UTC), Thursday, 1 January 1970, not counting leap seconds.
It is used widely in Unix-like and many other operating systems and file formats. Because it does not handle leap seconds, it is neither a linear representation of time nor a true representation of UTC.
