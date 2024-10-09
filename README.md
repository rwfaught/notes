<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>The Beauty of Simplicity</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@200;400&display=swap');
    :root {
        --bg-color: #f0f0f0;
        --text-color: #121212;
        --accent-color: #6200ee;
        --container-bg: rgba(255, 255, 255, 0.85);
    }
    [data-theme="dark"] {
        --bg-color: #121212;
        --text-color: #e0e0e0;
        --accent-color: #bb86fc;
        --container-bg: rgba(30, 30, 30, 0.85);
    }
    body {
        margin: 0;
        padding: 0;
        background: var(--bg-color);
        color: var(--text-color);
        font-family: 'Inter', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        overflow: hidden;
        transition: background 0.5s, color 0.5s;
    }
    .container {
        max-width: 800px;
        padding: 40px;
        background: var(--container-bg);
        backdrop-filter: blur(10px);
        border-radius: 12px;
        animation: fadeIn 1s ease-in-out;
    }
    h1 {
        font-weight: 200;
        margin-bottom: 20px;
        font-size: 3em;
        color: var(--accent-color);
    }
    p {
        margin-bottom: 20px;
        font-size: 1.1em;
        position: relative;
        overflow: hidden;
    }
    p::before {
        content: '';
        position: absolute;
        width: 100%;
        height: 100%;
        left: -100%;
        top: 0;
        background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
        transform: skewX(-25deg);
    }
    p:hover::before {
        animation: shine 1s forwards;
    }
    .toggle-theme {
        position: absolute;
        top: 20px;
        right: 20px;
        background: var(--accent-color);
        border: none;
        color: var(--bg-color);
        padding: 10px 15px;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1em;
    }
    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }
    @keyframes shine {
        to { left: 100%; }
    }
</style>
</head>
<body>
<button class="toggle-theme" id="themeButton">Toggle Theme</button>
<div class="container">
    <h1>The Beauty of Simplicity</h1>
    <p>The art of finding beauty in simplicity is often overlooked in our fast-paced, detail-obsessed world. Yet, there’s something profound about simplicity—whether it’s in design, nature, or life itself. Minimalism in art or architecture, for instance, strips away the excess to reveal the core essence of a piece, allowing viewers to engage with it on a deeper level. In a similar way, simplifying our daily lives can lead to greater clarity and peace. By eliminating distractions, whether physical or mental, we make room for the things that truly matter.</p>

    <p>Consider nature. A single tree standing alone in a field can evoke just as much awe as a dense forest. Its branches, reaching toward the sky, don’t need companions to make a statement. Its simplicity is its strength. Similarly, when we declutter our lives—whether it’s removing material possessions, unnecessary commitments, or even overcomplicated thoughts—we find that what remains has more impact. The essentials become clearer: relationships, passions, and purpose.</p>

    <p>There’s a reason why movements like minimalism have gained traction in recent years. In a world bombarded with stimuli, cutting down to what’s necessary can be a form of rebellion. It’s a declaration that our value doesn’t lie in the things we accumulate or the endless tasks we take on, but in who we are, how we connect with others, and the quality of experiences we choose to engage with.</p>

    <p>In a way, embracing simplicity is a call to mindfulness. It’s about being present and appreciating the little things that might otherwise go unnoticed. When we’re no longer distracted by the noise, we can focus on the subtleties—the way the light filters through a window, the taste of a morning coffee, or the joy of an unhurried conversation. Life, in its most distilled form, often offers the greatest rewards.</p>
</div>
<script>
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
</script>
</body>
</html>
