---
layout: base
title: Striver About
search_exclude: true
permalink: /Striver/striver-about
author: Hithin, Nikith, Rayhaan, Pradyun, Neil, Kush, Zaid
---

<div class="sidebar">
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-achievements" class="sidebar-btn">⭐️ Achievements</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-challenges" class="sidebar-btn">📉 Challenges</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-ai" class="sidebar-btn">🤖 AI</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-about" class="sidebar-btn">❓ About</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-terms" class="sidebar-btn">📄 Terms</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-profile" class="sidebar-btn bottom-btn">👤 Profile</a>
</div>

<style>
    body {
        background-image: url("../../images/background9674.png");
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        background-attachment: fixed;
        font-family: 'Arial', sans-serif;
        line-height: 1.6;
        color: #fff;
    }

    /* Sidebar */
    .sidebar {
        position: fixed;
        top: 0;
        left: 0;
        width: 180px;
        height: 100%;
        background-color: #121212;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 20px;
        color: white;
        border-right: 1px solid gray;
    }

    .sidebar-btn {
        background-color: #121212;
        color: white !important;
        border: 2px solid gray;
        margin: 10px 0;
        padding: 10px;
        border-radius: 8px;
        font-size: 16px;
        width: 160px;
        text-align: center;
        cursor: pointer;
        text-decoration: none;
        transition: background 0.3s, transform 0.3s;
    }

    .bottom-btn {
    margin-top: auto; /* Pushes the Terms button to the bottom */
    }

    .sidebar-btn:hover {
        background-color: #1e1e1e;
        transform: scale(1.05);
    }

    .sidebar-btn.active {
        background-color: #333;
        font-weight: bold;
    }

    /* Main Content */
    .content {
        margin-left: 200px;
        padding: 40px;
    }

    h2 {
        font-size: 36px;
        margin-bottom: 20px;
        text-align: center;
    }

    p {
        font-size: 18px;
        margin-bottom: 20px;
        text-align: justify;
    }

    .about-grid {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 20px;
    }

    .card {
        background-color: rgba(0, 0, 0, 0.7);
        padding: 20px;
        border-radius: 12px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .card h3 {
        font-size: 24px;
        margin-bottom: 10px;
    }

    .card p {
        font-size: 16px;
    }

    .join-btn {
        display: block;
        margin: 30px auto;
        background-color: #04AA6D;
        color: white;
        border: none;
        padding: 15px 30px;
        font-size: 18px;
        border-radius: 8px;
        cursor: pointer;
        text-align: center;
        transition: background-color 0.3s ease;
    }

    .join-btn:hover {
        background-color: #037a54;
    }
</style>

<div class="content">
    <h2>About Striver</h2>

    <p>
        Welcome to <strong>Striver</strong>, a platform designed to celebrate personal achievements and provide support during challenges. Whether you're aiming for growth, reflecting on milestones, or seeking a community, Striver is here for you.
    </p>

    <div class="about-grid">
        <div class="card">
            <h3>🌟 Empowerment</h3>
            <p>We help individuals share their milestones, connect with others, and celebrate every step forward, no matter how small.</p>
        </div>

        <div class="card">
            <h3>💬 Connection</h3>
            <p>Engage in open and supportive conversations through our anonymous chat system, fostering empathy and understanding.</p>
        </div>

        <div class="card">
            <h3>🤖 AI Companion</h3>
            <p>Meet Gemini, our AI-powered assistant, offering personalized guidance and encouragement throughout your journey.</p>
        </div>

        <div class="card">
            <h3>📈 Growth</h3>
            <p>Explore stories of triumph and progress on the home page, inspiring growth in yourself and others.</p>
        </div>
    </div>

    <p>
        Striver isn't just a platform; it's a community where achievements are celebrated, challenges are met with encouragement, and every story inspires growth. Together, let's create a world where progress is shared and celebrated.
    </p>

    <a href="/join" class="join-btn">Join Us Today</a>
</div>