<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Profile</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <div class="sidebar">
            <div class="logo">
                <h1>Striver</h1>
            </div>
            <div class="menu">
                <button>Achievements</button>
                <button>Challenges</button>
                <button>About</button>
            </div>
            <div class="terms">
                <p>Terms</p>
            </div>
        </div>
        <div class="main-content">
            <div class="header">
                <div class="settings">
                    <button>Settings</button>
                    <button>Your Profile</button>
                </div>
            </div>
            <div class="profile">
                <div class="profile-pic">
                    <img src="https://via.placeholder.com/150" alt="User Profile Picture">
                </div>
                <h2>Ben123456</h2>
                <div class="about-me">
                    <h3>About Me</h3>
                    <p>I liked playing Brawl Stars</p>
                    <p>I enjoy coding in my free time</p>
                    <p>Trying to become CEO of Apple</p>
                </div>
            </div>
        </div>
        <div class="members">
            <h3>Members</h3>
            <ul>
                <li>Person</li>
                <li>Person</li>
                <li>Person</li>
                <li>Person</li>
                <li>Person</li>
                <li>Person</li>
                <li>Person</li>
            </ul>
        </div>
    </div>
</body>
</html>
<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #121212;
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
.container {
    display: grid;
    grid-template-columns: 1fr 3fr 1fr;
    grid-template-rows: auto;
    width: 90%;
    max-width: 1200px;
    height: 90%;
    border: 1px solid #333;
    border-radius: 10px;
    overflow: hidden;
}
.sidebar {
    background-color: #222;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 20px;
}
.sidebar .logo h1 {
    font-size: 24px;
    margin: 0;
    color: #e91e63;
}
.sidebar .menu button {
    background: none;
    border: none;
    color: #fff;
    margin: 10px 0;
    font-size: 16px;
    cursor: pointer;
    text-align: left;
}
.sidebar .menu button:hover {
    color: #e91e63;
}
.sidebar .terms p {
    margin: 0;
    font-size: 14px;
    color: #666;
}
.main-content {
    background-color: #1e1e1e;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
}
.header {
    width: 100%;
    display: flex;
    justify-content: flex-end;
    margin-bottom: 20px;
}
.header button {
    background: none;
    border: none;
    color: #fff;
    margin-left: 10px;
    font-size: 16px;
    cursor: pointer;
}
.profile {
    max-width: 400px;
}
.profile-pic img {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    border: 3px solid #e91e63;
    margin-bottom: 20px;
}
.about-me h3 {
    margin-bottom: 10px;
    font-size: 18px;
    color: #e91e63;
}
.members {
    background-color: #222;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.members h3 {
    font-size: 18px;
    margin-bottom: 10px;
    color: #e91e63;
}
.members ul {
    list-style: none;
    padding: 0;
    width: 100%;
}
.members ul li {
    padding: 10px;
    background-color: #1e1e1e;
    margin-bottom: 5px;
    text-align: center;
    border-radius: 5px;
    color: #fff;
}
.members ul li:hover {
    background-color: #333;
}
</style>