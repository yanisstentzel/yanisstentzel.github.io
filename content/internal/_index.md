---
title: "Internal Portfolio"
description: "Preview area for restricted portfolio content"
url: /internal/
---

## Prototype access (test only)

This page is protected with a **front-end password gate for testing only**.
It is not secure and should be replaced by server/proxy authentication for production use.

<div id="internal-gate" class="internal-gate">
  <p class="internal-gate-text">Enter the test password to view internal portfolio drafts.</p>
  <form id="internal-gate-form" class="internal-gate-form" autocomplete="off">
    <label for="internal-password">Password</label>
    <input id="internal-password" name="internal-password" type="password" required />
    <button type="submit">Unlock</button>
  </form>
  <p id="internal-gate-error" class="internal-gate-error" hidden>Incorrect password. Try again.</p>
</div>

<script>
  (function () {
    if (!window.location.pathname.startsWith('/internal')) {
      return;
    }

    const gate = document.getElementById('internal-gate');
    const form = document.getElementById('internal-gate-form');
    const passwordInput = document.getElementById('internal-password');
    const errorMessage = document.getElementById('internal-gate-error');
    const protectedEntries = document.querySelectorAll('.post-entry, .first-entry');
    const storageKey = 'internal-portfolio-unlocked';
    const expectedToken = 'dGVzdC1pbnRlcm5hbA==';

    function lock() {
      protectedEntries.forEach((entry) => {
        entry.style.display = 'none';
      });
      gate.removeAttribute('hidden');
      errorMessage.hidden = true;
    }

    function unlock() {
      protectedEntries.forEach((entry) => {
        entry.style.display = '';
      });
      gate.setAttribute('hidden', 'hidden');
      errorMessage.hidden = true;
    }

    if (sessionStorage.getItem(storageKey) === expectedToken) {
      unlock();
      return;
    }

    lock();

    form.addEventListener('submit', function (event) {
      event.preventDefault();
      const candidate = btoa(passwordInput.value.trim());

      if (candidate === expectedToken) {
        sessionStorage.setItem(storageKey, expectedToken);
        unlock();
        return;
      }

      errorMessage.hidden = false;
      passwordInput.value = '';
      passwordInput.focus();
    });
  })();
</script>

> Test password for this branch: `test-internal`
