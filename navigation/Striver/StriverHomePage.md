---
permalink: /Striver/
layout: post
---
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Striver - Social Media</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <header class="header">
      <div class="logo">Striver</div>
      <div class="header-links">
        <a href="#">Settings</a>
        <a href="#">Your Profile</a>
      </div>
    </header>
    <div class="main-content">
      <aside class="sidebar">
        <button class="btn">Achievements</button>
        <button class="btn">Challenges</button>
        <button class="btn">About</button>
        <button class="btn">Terms</button>
      </aside>
      <main class="content">
        <div class="post-section">
          <input type="text" class="post-title" placeholder="Title">
          <textarea class="post-text" placeholder="Post here"></textarea>
        </div>
        <div class="posts">
          <div class="post">
            <h3>Promotion</h3>
            <p>Lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum...</p>
            <button class="comment-btn">Click to Comment</button>
          </div>
          <div class="post">
            <h3>Get a Dog</h3>
            <p>Lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum...</p>
            <button class="comment-btn">Click to Comment</button>
          </div>
          <div class="post">
            <h3>Start Co.</h3>
            <img src="https://via.placeholder.com/150" alt="Building Image">
            <p>Lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum...</p>
            <button class="comment-btn">Click to Comment</button>
          </div>
          <div class="post">
            <h3>Best Career</h3>
            <p>Lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum...</p>
            <button class="comment-btn">Click to Comment</button>
          </div>
        </div>
      </main>
      <aside class="members-section">
        <h3>Members</h3>
        <ul class="members-list">
          <li>Person</li>
          <li>Person</li>
          <li>Person</li>
          <li>Person</li>
          <li>Person</li>
        </ul>
      </aside>
    </div>
  </div>
<style>
    body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #121212;
  color: #ffffff;
}
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background-color: #1f1f1f;
  border-bottom: 1px solid #333;
}
.logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: #ff4d4d;
}
.header-links a {
  margin-left: 15px;
  color: #ffffff;
  text-decoration: none;
}
.main-content {
  display: flex;
  flex: 1;
}
.sidebar, .members-section {
  width: 15%;
  padding: 20px;
  background-color: #1f1f1f;
  border-right: 1px solid #333;
}
.sidebar {
  display: flex;
  flex-direction: column;
}
.btn {
  margin-bottom: 10px;
  padding: 10px;
  background-color: #ff4d4d;
  border: none;
  color: #fff;
  cursor: pointer;
  border-radius: 5px;
}
.btn:hover {
  background-color: #ff6666;
}
.content {
  flex: 1;
  padding: 20px;
}
.post-section {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 20px;
}
.post-title, .post-text {
  width: 100%;
  padding: 10px;
  background-color: #333;
  border: 1px solid #555;
  color: #fff;
  border-radius: 5px;
}
.posts {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}
.post {
  background-color: #333;
  padding: 15px;
  border-radius: 10px;
}
.post img {
  width: 100%;
  height: auto;
  border-radius: 5px;
  margin: 10px 0;
}
.comment-btn {
  margin-top: 10px;
  padding: 10px;
  background-color: #ff4d4d;
  border: none;
  color: #fff;
  cursor: pointer;
  border-radius: 5px;
}
.comment-btn:hover {
  background-color: #ff6666;
}
.members-section h3 {
  margin-bottom: 10px;
}
.members-list {
  list-style: none;
  padding: 0;
}
.members-list li {
  padding: 5px 0;
}
</style>
</body>
</html>