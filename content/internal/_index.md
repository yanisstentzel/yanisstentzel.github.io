---
title: "Internal Portfolio"
description: "Preview area for restricted portfolio content"
url: /internal/
draft: true
robots: noindex
---

## Prototype access (test only)

This page is protected with a **front-end password gate for testing only**.
It is not secure and should be replaced by server/proxy authentication for production use.

<div id="internal-gate" class="internal-gate">
  <p class="internal-gate-text">Note: la protection front-end a été retirée dans cette branche — utilisez draft/noindex ou une protection côté serveur (Basic Auth, Netlify/Cloudflare Pages, middleware) pour protéger ces pages pendant les tests.</p>
  <form id="internal-gate-form" class="internal-gate-form" autocomplete="off">
    <label for="internal-password">Password</label>
    <input id="internal-password" name="internal-password" type="password" required />
    <button type="submit">Unlock</button>
  </form>
  <p id="internal-gate-error" class="internal-gate-error" hidden>Incorrect password. Try again.</p>
</div>
