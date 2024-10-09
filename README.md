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
        transition: background 0.5s, color 0.5s;
    }
    /* Navigation Bar */
    .navbar {
        position: fixed;
        top: 0;
        width: 100%;
        background: var(--container-bg);
        backdrop-filter: blur(10px);
        display: flex;
        justify-content: center;
        padding: 10px 0;
        z-index: 1000;
    }
    .navbar a {
        margin: 0 15px;
        text-decoration: none;
        color: var(--text-color);
        font-weight: 400;
        position: relative;
    }
    .navbar a::after {
        content: '';
        display: block;
        width: 0;
        height: 2px;
        background: var(--accent-color);
        transition: width 0.3s;
        position: absolute;
        bottom: -5px;
        left: 0;
    }
    .navbar a:hover::after {
        width: 100%;
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
        margin: 120px auto 50px auto;
        padding: 20px;
        background: var(--container-bg);
        backdrop-filter: blur(10px);
        border-radius: 12px;
    }
    h1, h2 {
        font-weight: 300;
        color: var(--accent-color);
    }
    p {
        line-height: 1.6;
        margin-bottom: 20px;
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
        border-radius: 5px;
        cursor: pointer;
        font-size: 1em;
    }
    /* Responsive Design */
    @media (max-width: 600px) {
        .container {
            margin: 100px 20px 50px 20px;
            padding: 15px;
        }
        .navbar a {
            margin: 0 10px;
        }
    }
</style>
</head>
<body>
<div id="progressBar"></div>
<nav class="navbar">
    <a href="#section1">Home</a>
    <a href="#section2">Nature</a>
    <a href="#section3">Minimalism</a>
    <a href="#section4">Mindfulness</a>
    <a href="#section5">Technology</a>
    <a href="#section6">Everyday Life</a>
    <a href="#section7">Philosophy</a>
    <a href="#section8">Well-being</a>
</nav>
<div class="container" id="section1">
    <h1>The Beauty of Simplicity</h1>
    <p>The art of finding beauty in simplicity is often overlooked in our fast-paced, detail-obsessed world. Yet, there’s something profound about simplicity—whether it’s in design, nature, or life itself. Minimalism in art or architecture, for instance, strips away the excess to reveal the core essence of a piece, allowing viewers to engage with it on a deeper level. In a similar way, simplifying our daily lives can lead to greater clarity and peace. By eliminating distractions, whether physical or mental, we make room for the things that truly matter.</p>
</div>

<div class="container" id="section2">
    <h2>Nature's Simplicity</h2>
    <p>Consider nature. A single tree standing alone in a field can evoke just as much awe as a dense forest. Its branches, reaching toward the sky, don’t need companions to make a statement. Its simplicity is its strength. Similarly, when we declutter our lives—whether it’s removing material possessions, unnecessary commitments, or even overcomplicated thoughts—we find that what remains has more impact. The essentials become clearer: relationships, passions, and purpose.</p>
</div>

<div class="container" id="section3">
    <h2>The Minimalist Movement</h2>
    <p>There’s a reason why movements like minimalism have gained traction in recent years. In a world bombarded with stimuli, cutting down to what’s necessary can be a form of rebellion. It’s a declaration that our value doesn’t lie in the things we accumulate or the endless tasks we take on, but in who we are, how we connect with others, and the quality of experiences we choose to engage with.</p>
</div>

<div class="container" id="section4">
    <h2>Embracing Mindfulness</h2>
    <p>In a way, embracing simplicity is a call to mindfulness. It’s about being present and appreciating the little things that might otherwise go unnoticed. When we’re no longer distracted by the noise, we can focus on the subtleties—the way the light filters through a window, the taste of a morning coffee, or the joy of an unhurried conversation. Life, in its most distilled form, often offers the greatest rewards.</p>
</div>

<div class="container" id="section5">
    <h2>The Role of Technology in Simplicity</h2>
    <p>In an age where technology often adds layers of complexity to our lives, it can also be a powerful tool for achieving simplicity. Thoughtfully designed tech solutions streamline tasks, reduce clutter, and help us focus on what truly matters. From minimalist apps that encourage mindfulness to smart home devices that automate mundane chores, technology, when used intentionally, can be an ally in our pursuit of simplicity.</p>
</div>

<div class="container" id="section6">
    <h2>Simplicity in Everyday Life</h2>
    <p>Embracing simplicity doesn't require drastic life changes. It can be as straightforward as decluttering a workspace, practicing gratitude, or setting aside time for reflection. These small adjustments accumulate, leading to a more centered and fulfilling life. By prioritizing what's essential, we create space for joy, creativity, and meaningful connections.</p>
</div>

<div class="container" id="section7">
    <h2>The Philosophy of Minimalism</h2>
    <p>Minimalism is more than an aesthetic; it's a mindset. Rooted in the idea that less is more, it challenges us to evaluate our relationships with possessions, habits, and even thoughts. This philosophy encourages intentionality, prompting us to make choices that align with our values and aspirations rather than societal pressures or fleeting trends.</p>
</div>

<div class="container" id="section8">
    <h2>The Impact of Simplicity on Well-being</h2>
    <p>Studies have shown that simplifying our environments and routines can significantly reduce stress and anxiety. A clear space often leads to a clear mind. By eliminating excess, we not only improve our mental health but also enhance our ability to concentrate and be productive. Simplicity fosters a sense of calm and balance, which is essential in today's hectic world.</p>
</div>

<button class="toggle-theme" id="themeButton" aria-label="Toggle Theme">Toggle Theme</button>

<script>
    // Theme Toggle
    const themeButton = document.getElementById('themeButton');
    const currentTheme = localStorage.getItem('theme') || 'light';
    document.body.setAttribute('data-theme', currentTheme);

    themeButton.addEventListener('click', () => {
        let theme = document.body.getAttribute('data-theme');
        if (theme === 'light') {
            document.body.setAttribute('data-theme', 'dark');
            localStorage.setItem('theme', 'dark');
        } else {
            document.body.setAttribute('data-theme', 'light');
            localStorage.setItem('theme', 'light');
        }
    });

    // Scroll Progress Bar
    window.addEventListener('scroll', () => {
        const progressBar = document.getElementById('progressBar');
        const totalHeight = document.body.scrollHeight - window.innerHeight;
        const progress = (window.scrollY / totalHeight) * 100;
        progressBar.style.width = progress + '%';
    });
</script>
</body>
</html>
