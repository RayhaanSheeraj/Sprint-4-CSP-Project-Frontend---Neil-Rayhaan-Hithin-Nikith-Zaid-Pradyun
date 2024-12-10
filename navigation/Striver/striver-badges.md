---
layout: base
title: Striver Badges
search_exclude: true
permalink: /Striver/striver-badges
author: Kush
---


<div class="sidebar">
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-achievements" class="sidebar-btn">⭐️ Achievements</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-challenges" class="sidebar-btn">📉 Challenges</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-ai" class="sidebar-btn">🤖 AI</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-about" class="sidebar-btn">❓ About</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-terms" class="sidebar-btn">📄 Terms</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-profile" class="sidebar-btn bottom-btn">👤 Profile</a>
    <a href="/Sprint-4-CSP-Project-Frontend---Neil-Rayhaan-Hithin-Nikith-Zaid-Pradyun/Striver/striver-badges" class="sidebar-btn bottom-btn">Badges</a>
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
        margin-top: auto; /* Pushes the Profile button to the bottom */
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

    /* Customization Styles */
    .customization-container {
        margin-top: 30px;
    }
    .customization-container label {
        font-size: 16px;
        margin-right: 10px;
    }
    .customization-container select, .customization-container input {
        padding: 8px;
        font-size: 14px;
    }
    .btn {
        margin-top: 20px;
        padding: 10px 15px;
        background-color: #00796b;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .btn:hover {
        background-color: #004d40;
    }
    .reset-btn {
        background-color: #ff5722;
        margin-left: 10px;
    }
</style>

<div class="content">
    <h2>Badges</h2>
    <p style="font-size:1.1vw;">This page is dedicated to the badges you can earn based on your achievenments!</p>

   
</div>

<script>
    // Function to customize the page's background, text color, and font size
    function customizePage() {
        let bgColor = document.getElementById('bg-color').value;
        let textColor = document.getElementById('text-color').value;
        let fontSize = document.getElementById('font-size').value;

        // Set the styles dynamically for the page elements
        document.body.style.backgroundColor = bgColor;
        document.body.style.color = textColor;
        document.body.style.fontSize = fontSize;

        // Apply custom styles to specific elements (like text in cards)
        document.querySelectorAll('.card').forEach(function(card) {
            card.style.backgroundColor = bgColor;  // Update card background color
            card.style.color = textColor;  // Update text color inside cards
        });

        document.querySelectorAll('.join-btn').forEach(function(btn) {
            btn.style.fontSize = fontSize;  // Change font size of the button
        });

        document.querySelectorAll('h2, h3, p').forEach(function(el) {
            el.style.fontSize = fontSize;  // Change font size of headings and paragraphs
        });
    }

    // Function to apply customizations
    function applyCustomizations() {
        alert('Customizations Applied!');
    }

    // Function to reset customizations to the default settings
    function resetCustomizations() {
        // Reset background and text color to default
        document.body.style.backgroundColor = '#f4f4f4';
        document.body.style.color = '#333';
        document.body.style.fontSize = '16px';

        // Reset input fields to default
        document.getElementById('bg-color').value = '#f4f4f4';
        document.getElementById('text-color').value = '#333';
        document.getElementById('font-size').value = '16px';

        // Reset other elements to default
        customizePage();  // Reapply default settings
    }
</script>