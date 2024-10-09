<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>The Beauty of Simplicity</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
    /* Import a minimalist Google Font */
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400&display=swap');

    :root {
        --bg-color: #f0f0f0;
        --text-color: #121212;
        --accent-color: #6200ee;
        --container-bg: rgba(255, 255, 255, 0.85);
        --progress-height: 4px;
        --transition-speed: 0.3s;
    }
    [data-theme="dark"] {
        --bg-color: #121212;
        --text-color: #e0e0e0;
        --accent-color: #bb86fc;
        --container-bg: rgba(30, 30, 30, 0.85);
    }
    * {
        box-sizing: border-box;
        scroll-behavior: smooth;
    }
    body {
        margin: 0;
        background: var(--bg-color);
        color: var(--text-color);
        font-family: 'Montserrat', sans-serif;
        transition: background var(--transition-speed), color var(--transition-speed);
    }
    /* Navigation Bar */
    .navbar-container {
        position: fixed;
        top: 0;
        width: 100%;
        background: var(--container-bg);
        backdrop-filter: blur(10px);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 10px 20px;
        z-index: 1000;
    }
    .navbar {
        display: flex;
        overflow: hidden;
        scroll-behavior: smooth;
        max-width: 80%;
        white-space: nowrap;
    }
    .navbar a {
        margin: 0 15px;
        text-decoration: none;
        color: var(--text-color);
        font-weight: 400;
        position: relative;
        transition: color var(--transition-speed);
    }
    .navbar a.active {
        color: var(--accent-color);
    }
    .navbar a::after {
        content: '';
        display: block;
        width: 0;
        height: 2px;
        background: var(--accent-color);
        transition: width var(--transition-speed);
        position: absolute;
        bottom: -5px;
        left: 0;
    }
    .navbar a:hover::after,
    .navbar a.active::after {
        width: 100%;
    }
    .navbar a:hover {
        color: var(--accent-color);
    }
    .nav-arrow {
        background: none;
        border: 2px solid var(--accent-color);
        color: var(--accent-color);
        padding: 8px;
        cursor: pointer;
        font-size: 1.2em;
        border-radius: 8px;
        transition: background var(--transition-speed), color var(--transition-speed), transform var(--transition-speed);
    }
    .nav-arrow:hover {
        background: var(--accent-color);
        color: var(--bg-color);
        transform: scale(1.1);
    }
    /* Scroll Progress Bar */
    #progressBar {
        position: fixed;
        top: 0;
        left: 0;
        width: 0%;
        height: var(--progress-height);
        background: var(--accent-color);
        z-index: 999;
    }
    /* Container */
    .container {
        max-width: 800px;
        width: 90%;
        height: 80vh;
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        padding: 20px;
        background: var(--container-bg);
        backdrop-filter: blur(10px);
        border-radius: 20px;
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        opacity: 0;
        transition: opacity 0.6s ease-out;
        z-index: 10;
        display: none;
    }
    .visible {
        opacity: 1;
        display: block;
    }
    h1, h2 {
        font-weight: 300;
        color: var(--accent-color);
        background-image: linear-gradient(45deg, var(--accent-color), #ffa7c4);
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;
    }
    h1:hover, h2:hover {
        animation: shimmer 1.5s infinite;
    }
    @keyframes shimmer {
        0% { background-position: -500px; }
        100% { background-position: 500px; }
    }
    p {
        line-height: 1.6;
        margin-bottom: 20px;
    }
    /* Collapsible Sections */
    .collapsible {
        cursor: pointer;
        position: relative;
        font-weight: bold;
        color: var(--accent-color);
        transition: color var(--transition-speed);
    }
    .collapsible:hover {
        color: #ffa7c4;
    }
    .collapsible::after {
        content: '+';
        position: absolute;
        right: 0;
        font-size: 1.5em;
        transition: transform var(--transition-speed);
    }
    .collapsible.active::after {
        content: '-';
        transform: rotate(180deg);
    }
    .content {
        max-height: 0;
        overflow: hidden;
        transition: max-height var(--transition-speed) ease-in-out;
    }
    .content.open {
        max-height: 500px; /* Adjust as needed */
    }
    /* Toggle Theme Button */
    .toggle-theme {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background: var(--accent-color);
        border: none;
        color: var(--bg-color);
        padding: 10px 15px;
        border-radius: 50%;
        cursor: pointer;
        font-size: 1em;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        transition: background var(--transition-speed), color var(--transition-speed), transform var(--transition-speed);
    }
    .toggle-theme:hover {
        transform: rotate(20deg) scale(1.1);
    }
    /* Back to Top Button */
    .back-to-top {
        position: fixed;
        bottom: 80px;
        right: 20px;
        background: var(--accent-color);
        border: none;
        color: var(--bg-color);
        padding: 10px 15px;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1.5em;
        display: none;
        align-items: center;
        justify-content: center;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        transition: background var(--transition-speed), color var(--transition-speed), transform var(--transition-speed);
    }
    .back-to-top.visible {
        display: flex;
    }
    .back-to-top:hover {
        transform: scale(1.1);
    }
    /* Tooltip */
    .tooltip {
        position: relative;
        cursor: pointer;
        color: var(--accent-color);
        transition: color var(--transition-speed);
    }
    .tooltip:hover {
        color: #ffa7c4;
    }
    .tooltip::after {
        content: attr(data-tooltip);
        position: absolute;
        bottom: 125%;
        left: 50%;
        transform: translateX(-50%);
        background: var(--text-color);
        color: var(--bg-color);
        padding: 5px 10px;
        border-radius: 5px;
        opacity: 0;
        pointer-events: none;
        transition: opacity var(--transition-speed);
        white-space: nowrap;
    }
    .tooltip:hover::after {
        opacity: 1;
    }
    /* Ripple Effect on Buttons */
    .ripple {
        position: relative;
        overflow: hidden;
    }
    .ripple::after {
        content: '';
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        pointer-events: none;
        background: rgba(255, 255, 255, 0.4);
        transform: scale(0);
        opacity: 0;
        transition: transform 0.4s, opacity 0.6s;
    }
    .ripple:active::after {
        transform: scale(2);
        opacity: 1;
        transition: 0s;
    }
    /* Responsive Design */
    @media (max-width: 600px) {
        .container {
            width: 90%;
            height: auto;
            top: 10%;
            transform: translate(-50%, 0);
            position: relative;
            margin-bottom: 20px;
        }
        .navbar a {
            margin: 0 10px;
        }
    }
</style>
</head>
<body>
<div id="progressBar"></div>
<div class="navbar-container">
    <button class="nav-arrow ripple" id="navArrowLeft" aria-label="Scroll Left">&#8249;</button>
    <div class="navbar" id="navbar">
        <a href="#section1" class="nav-link">Home</a>
        <a href="#section2" class="nav-link">Nature</a>
        <a href="#section3" class="nav-link">Minimalism</a>
        <a href="#section4" class="nav-link">Mindfulness</a>
        <a href="#section5" class="nav-link">Technology</a>
        <a href="#section6" class="nav-link">Everyday Life</a>
        <a href="#section7" class="nav-link">Philosophy</a>
        <a href="#section8" class="nav-link">Well-being</a>
        <a href="#section9" class="nav-link">Growth</a>
        <a href="#section10" class="nav-link">Health</a>
        <a href="#section11" class="nav-link">Creativity</a>
        <a href="#section12" class="nav-link">Productivity</a>
        <a href="#section13" class="nav-link">Balance</a>
        <a href="#section14" class="nav-link">Resilience</a>
        <a href="#section15" class="nav-link">Sustainability</a>
        <a href="#section16" class="nav-link">Community</a>
        <a href="#section17" class="nav-link">Purpose</a>
        <a href="#section18" class="nav-link">Fulfillment</a>
        <a href="#section19" class="nav-link">Connection</a>
        <a href="#section20" class="nav-link">Joy</a>
        <a href="#section21" class="nav-link">Adventure</a>
        <a href="#section22" class="nav-link">Gratitude</a>
        <a href="#section23" class="nav-link">Empathy</a>
        <a href="#section24" class="nav-link">Love</a>
    </div>
    <button class="nav-arrow ripple" id="navArrowRight" aria-label="Scroll Right">&#8250;</button>
</div>
<button class="toggle-theme ripple" id="themeButton" aria-label="Toggle Theme">Toggle Theme</button>
<button class="back-to-top" id="backToTopButton" aria-label="Back to Top">&#8679;</button>
<div class="container visible" id="section1">
    <h1>The Beauty of Simplicity</h1>
    <p>The art of finding beauty in simplicity is often overlooked in our fast-paced, detail-obsessed world. Yet, there’s something profound about simplicity—whether it’s in design, nature, or life itself. Minimalism in art or architecture, for instance, strips away the excess to reveal the core essence of a piece, allowing viewers to engage with it on a deeper level. In a similar way, simplifying our daily lives can lead to greater clarity and peace. By eliminating distractions, whether physical or mental, we make room for the things that truly matter.</p>
</div>

<!-- Additional sections added to triple the content -->
<div class="container" id="section2">
    <h2>Nature's Simplicity</h2>
    <p>Consider nature. A single tree standing alone in a field can evoke just as much awe as a dense forest. Its branches, reaching toward the sky, don’t need companions to make a statement. Its simplicity is its strength.</p>
    <div class="collapsible">Read More</div>
    <div class="content">
        <p>Similarly, when we declutter our lives—whether it’s removing material possessions, unnecessary commitments, or even overcomplicated thoughts—we find that what remains has more impact. The essentials become clearer: relationships, passions, and purpose.</p>
    </div>
</div>

<div class="container" id="section3">
    <h2>The Minimalist Movement</h2
