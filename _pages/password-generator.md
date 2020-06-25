---
layout: page
title: "Password Generator"
description: "Password Generator is a tool to generate password based on selected criteria."
permalink: /password-generator/
status: ready
---

Use our random password generator to create strong passwords for all your online accounts. Mix letters, numbers and symbols for the ultimate in security.

<form>
  <div class="form-group">
    <label class="form-check-label" for="passwordLength">Password Length</label>
    <input class="form-check-input" type="number" value="12" id="passwordLength" min="8" max="256">
  </div>

  <div class="form-group">
    <label class="form-check-label" for="useUpperCase">Use Uppercase</label>
    <input class="form-check-input" type="checkbox" value="" id="useUpperCase">
    <br>
    <label class="form-check-label" for="useNumbers">Use Numbers</label>
    <input class="form-check-input" type="checkbox" value="" id="useNumbers">
    <br>
    <label class="form-check-label" for="useSpecialChars">Use Symbols</label>
    <input class="form-check-input" type="checkbox" value="" id="useSpecialChars">
  </div>

  <button id="actionBtn" type="button" class="btn btn-primary">Generate</button>

  <div class="form-group">
    <label for="generatedPassword">Generated Password</label>
    <input type="text" class="form-control" id="generatedPassword">
  </div>
</form>

<script>
  document.getElementById('actionBtn').onclick = function() {
    var passwordLength = document.getElementById('passwordLength').value;
    var useUpperCase = document.getElementById('useUpperCase').checked;
    var useNumbers = document.getElementById('useNumbers').checked;
    var useSpecialChars = document.getElementById('useSpecialChars').checked;

    var chars = 'abcdefghijklmnopqrstuvwxyz';
    var numberChars = '0123456789';
    var specialChars = '!"£$%^&*()';

    var usableChars = chars +
      (useUpperCase ? chars.toUpperCase() : '') +
      (useNumbers ? numberChars : '') +
      (useSpecialChars ? specialChars : '');

    let generatedPassword = '';
    for (i = 0; i <= passwordLength; i++) {
      generatedPassword += usableChars[Math.floor(Math.random() * (usableChars.length))];
    }

    document.getElementById('generatedPassword').value = generatedPassword;
  };
</script>

#### Did you know?

Passwords are a real security threat. Over 80% of hacking-related breaches are due to weak or stolen passwords.
So if you want to safeguard your personal info and assets, creating secure passwords is a big first step.
Impossible-to-crack passwords are complex with multiple types of characters (numbers, letters, and symbols).
Making your passwords different for each website or app also helps defend against hacking.
