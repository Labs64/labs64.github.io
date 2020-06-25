---
layout: page
title: "Password Generator"
description: "Password Generator is a tool to generate password based on selected criteria."
permalink: /password-generator/
status: ready
---

Use our random password generator to create strong passwords for all your online accounts. Mix letters, numbers and symbols for the ultimate in security.

<div class="form-check">
  <input class="form-check-input" type="checkbox" value="8" id="passwordLength">
  <label class="form-check-label" for="passwordLength">Password Length</label>

  <input class="form-check-input" type="checkbox" value="" id="useUpperCase">
  <label class="form-check-label" for="useUpperCase">Use Uppercase</label>

  <input class="form-check-input" type="checkbox" value="" id="useNumbers">
  <label class="form-check-label" for="useNumbers">Use Numbers</label>

  <input class="form-check-input" type="checkbox" value="" id="useSpecialChars">
  <label class="form-check-label" for="useSpecialChars">Use Symbols</label>
</div>

<button id="actionBtn" type="button" class="btn btn-primary">Format</button>

<div class="form-group">
  <label for="generatedPassword">Generated Password</label>
  <input type="number" class="form-control" id="generatedPassword" placeholder="..." min="10" max="256">
</div>


<script>
  document.getElementById('actionBtn').onclick = function() {
    const passwordLength = document.getElementById("passwordLength").value;
    const useUpperCase = document.getElementById("useUpperCase").checked;
    const useNumbers = document.getElementById("useNumbers").checked;
    const useSpecialChars = document.getElementById("useSpecialChars").checked;

    const chars = 'abcdefghijklmnopqrstuvwxyz'
    const numberChars = '0123456789'
    const specialChars = '!"£$%^&*()'
    const usableChars = chars +
      (useUpperCase ? chars.toUpperCase() : '') +
      (useNumbers ? numberChars : '') +
      (useSpecialChars ? specialChars : '')
    let generatedPassword = ''
    for (i = 0; i <= passwordLength; i++) {
      generatedPassword += usableChars[Math.floor(Math.random() * (usableChars.length))]
    }
    document.getElementById('generatedPassword').value = generatedPassword;
  };
</script>

#### Did you know?

Passwords are a real security threat. Over 80% of hacking-related breaches are due to weak or stolen passwords.
So if you want to safeguard your personal info and assets, creating secure passwords is a big first step.
Impossible-to-crack passwords are complex with multiple types of characters (numbers, letters, and symbols).
Making your passwords different for each website or app also helps defend against hacking.
