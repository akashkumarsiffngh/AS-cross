# AS-cross

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Akash Singh's Live Content</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      text-align: center;
    }
    header {
      background-color: #007bff;
      color: white;
      padding: 20px 0;
    }
    header h1 {
      margin: 0;
    }

    /* Three dot menu styles */
    .menu {
      position: absolute;
      top: 10px;
      right: 10px;
      cursor: pointer;
      font-size: 30px;
    }
    .menu-content {
      display: none;
      position: absolute;
      right: 10px;
      top: 50px;
      background-color: #007bff;
      color: white;
      padding: 10px;
      border-radius: 5px;
      width: 200px;
      text-align: left;
    }
    .menu-content p {
      margin: 10px 0;
      font-size: 18px;
    }
    .menu-content a {
      color: white;
      text-decoration: none;
    }
    .menu-content a:hover {
      color: lightblue;
    }

    .live-link-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background-color: green;
      padding: 10px 0;
      z-index: 1000;
      display: none;
    }
    .live-link-container a {
      color: white;
      font-size: 20px;
      font-weight: bold;
      text-decoration: none;
    }
    .live-link-container a:hover {
      color: lightgreen;
    }
    .notice-container {
      background-color: yellow;
      padding: 10px;
      font-size: 18px;
      font-weight: bold;
      color: #000;
      display: none;
    }
    .password-screen {
      margin-top: 100px;
    }
    .password-input {
      padding: 10px;
      font-size: 18px;
      width: 300px;
    }
    .password-button {
      padding: 10px 20px;
      font-size: 18px;
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    .password-button:hover {
      background-color: #0056b3;
    }
    .error-message {
      color: red;
      margin-top: 10px;
      display: none;
    }
    .link-container {
      margin: 20px 0;
      display: none;
    }
    .link-container a {
      display: block;
      text-decoration: none;
      background-color: #007bff;
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      margin: 10px auto;
      width: 80%;
      max-width: 400px;
      font-size: 16px;
    }
    .link-container a:hover {
      background-color: #0056b3;
    }
    .upload-container {
      display: none;
      margin-top: 20px;
    }
    .upload-input, .upload-title {
      padding: 10px;
      font-size: 18px;
      width: 300px;
      margin-bottom: 10px;
    }
    .upload-button {
      padding: 10px 20px;
      font-size: 18px;
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    .upload-button:hover {
      background-color: #0056b3;
    }
    .watermark {
      position: fixed;
      bottom: 10px;
      right: 10px;
      font-size: 22px;
      color: red;
      opacity: 0.8;
      display: none;
      text-align: right;
    }
    .admin-button {
      display: none;
      margin-top: 20px;
    }
  </style>
  <script>
    let adminNotice = "";

    // Function to toggle menu visibility
    function toggleMenu() {
      const menuContent = document.querySelector(".menu-content");
      menuContent.style.display = (menuContent.style.display === "block") ? "none" : "block";
    }

    // Function to check password
    function checkPassword() {
      const enteredPassword = document.getElementById("password").value;
      const correctPassword = "1234"; // Static password for access
      const ownerPassword = "6202670584"; // Owner password for upload

      // Check if the entered password matches the correct one
      if (enteredPassword === correctPassword) {
        document.querySelector(".password-screen").style.display = "none";
        document.querySelector(".link-container").style.display = "block"; // Show video links
        document.querySelector(".live-link-container").style.display = "block"; // Show live link
        document.querySelector(".notice-container").style.display = "block"; // Show notice
        document.querySelector(".admin-button").style.display = "block"; // Show admin button
      } else if (enteredPassword === ownerPassword) {
        document.querySelector(".password-screen").style.display = "none";
        document.querySelector(".upload-container").style.display = "block"; // Show upload section for owner
      } else {
        document.querySelector(".error-message").style.display = "block";
      }
    }

    // Admin function to send notice
    function sendNoticeToViewer() {
      adminNotice = "Dear Students, <br> There will be no test for the 9th Abhay batch this Sunday. Instead, I have uploaded the Triangles DPP. Do that! <br> —your Shobhit bhaiya";
      document.querySelector(".notice-container").innerHTML = adminNotice;
      document.querySelector(".notice-container").style.display = "block"; // Display notice to viewers
    }
  </script>
</head>
<body>
  <header>
    <h1>Akash Singh's Live Content</h1>
    <div class="menu" onclick="toggleMenu()">&#x22EE;</div>
    <div class="menu-content">
      <p>Name: AKASH SINGH</p>
      <p>CONTACT: <a href="tel:+916202670584">+916202670584</a></p>
    </div>
  </header>

  <div class="live-link-container">
    <a href="https://d1kw75zcv4u98c.cloudfront.net/out/v1/287810d967cc428e9bd992002e55b72c/index.m3u8" target="_blank">🔴 LIVE: Class 9 (Starts at 5:05 PM)</a>
  </div>

  <div class="notice-container">
    <!-- Admin notice will be displayed here -->
  </div>

  <div class="password-screen">
    <h2>Enter Password to Access</h2>
    <input type="password" id="password" class="password-input" placeholder="Enter Password">
    <button onclick="checkPassword()" class="password-button">Submit</button>
    <div class="error-message">Incorrect Password. Try Again!</div>
  </div>

  <div class="link-container">
    <a href="https://youtu.be/rfBdnmdiCgs?si=25i6j1jKkQSplFHo" target="_blank">Force and Laws - L1</a>
    <a href="https://youtu.be/lU6Eh8AotxQ?si=PbDit29e2vv7yGsL" target="_blank">Force and Laws - L2</a>
    <a href="https://youtu.be/FhaDNzfs6Zg?si=mGsM-4J4T1d1W5y" target="_blank">Tissue - L1</a>
    <a href="https://youtu.be/XqYsXykjuZo?si=5FHebLKbxE7dTGnz" target="_blank">Tissue - L2</a>
    <a href="https://youtu.be/SQRFzrSqlxY?si=1pOoxW0KWk8tZyja" target="_blank">Gravitation - L1</a>
    <a href="https://youtu.be/VFxc26BdKQg?si=qb5qRfDpMe_L9PFt" target="_blank">French Revolution</a>
    <a href="https://youtu.be/uxjIR6Cr9DE?si=oHxzw6u9VZpvYKOb" target="_blank">India - Size and Location</a>
    <a href="https://youtu.be/DO2FBmpKeJk?si=3XYcvevrnagdPQ8N" target="_blank">Socialism in Europe - L1</a>
    <a href="https://youtu.be/MqYB6ZkRwkI?si=ZU-PXHbWDOMmyssi" target="_blank">Socialism in Europe - L2</a>
  </div>

  <div class="upload-container">
    <h2>Upload a New Video Link</h2>
    <input type="text" id="videoTitle" class="upload-title" placeholder="Enter Video Title">
    <input type="text" id="videoLink" class="upload-input" placeholder="Enter Video URL">
    <button onclick="addVideoLink()" class="upload-button">Upload</button>
  </div>

  <div class="watermark">
    <span>Name: AKASH SINGH</span>
    <span>Help Centre: +916202670584</span>
  </div>

  <div class="admin-button">
    <button onclick="sendNoticeToViewer()">Send Notice to Viewer</button>
  </div>

  </body>
  <html>
