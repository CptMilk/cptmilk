---
layout: null
title: Donate
permalink: /donate
weight: 5
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="author" content="rwcar4">
  <title>Donate</title>

  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.15.4/css/all.css">
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f9f9f9;
      margin: 0;
    }
    .donate-container {
      text-align: center;
    }
    .donate-container h1 {
      font-size: 2.5rem;
      margin-bottom: 2rem;
    }
    .donate-container .btn {
      margin: 10px;
      padding: 15px 30px;
      font-size: 1.2rem;
      border-radius: 5px;
      font-weight: bold;
    }
    .roblox-button {
      background-color: #ff5757;
      color: white;
      border: none;
    }
    .roblox-button:hover {
      background-color: #d94444;
    }
  </style>
</head>
<body>
  <div class="donate-container">
    <h1>Support Our Work</h1>
    <a href="https://www.roblox.com/communities/5303423/The-Finest#!/store" target="_blank" class="btn roblox-button">
      Donate via Roblox Store
    </a>
    <button class="btn btn-primary" id="kofi-button">
      Donate via Ko-fi
    </button>
  </div>

  <script src="https://storage.ko-fi.com/cdn/scripts/overlay-widget.js"></script>
  <script>
    document.getElementById('kofi-button').addEventListener('click', function () {
      kofiWidgetOverlay.draw('cptmilk', {
        'type': 'floating-chat',
        'floating-chat.donateButton.text': 'Support me',
        'floating-chat.donateButton.background-color': '#00b9fe',
        'floating-chat.donateButton.text-color': '#fff'
      });
    });
  </script>
</body>
</html>
