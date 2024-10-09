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
        opacity: 0;
        transform: translateY(20px);
        transition: opacity 0.6s ease-out, transform 0.6s ease-out;
    }
    .container.visible {
        opacity: 1;
        transform: translateY(0);
    }
    h1, h2 {
        font-weight: 300;
        color: var(--accent-color);
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
        border-radius: 5px;
        cursor: pointer;
        font-size: 1em;
        transition: background var(--transition-speed), color var(--transition-speed);
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
        border-radius: 50%;
        cursor: pointer;
        font-size: 1.5em;
        display: none;
        align-items: center;
        justify-content: center;
        transition: background var(--transition-speed), color var(--transition-speed);
    }
    .back-to-top.visible {
        display: flex;
    }
    /* Tooltip */
    .tooltip {
        position: relative;
        cursor: pointer;
        color: var(--accent-color);
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
    <a href="#section1" class="nav-link">Home</a>
    <a href="#section2" class="nav-link">Nature</a>
    <a href="#section3" class="nav-link">Minimalism</a>
    <a href="#section4" class="nav-link">Mindfulness</a>
    <a href="#section5" class="nav-link">Technology</a>
    <a href="#section6" class="nav-link">Everyday Life</a>
    <a href="#section7" class="nav-link">Philosophy</a>
    <a href="#section8" class="nav-link">Well-being</a>
</nav>
<div class="container" id="section1">
    <h1>The Beauty of Simplicity</h1>
    <p>The art of finding beauty in simplicity is often overlooked in our fast-paced, detail-obsessed world. Yet, there’s something profound about simplicity—whether it’s in design, nature, or life itself. Minimalism in art or architecture, for instance, strips away the excess to reveal the core essence of a piece, allowing viewers to engage with it on a deeper level. In a similar way, simplifying our daily lives can lead to greater clarity and peace. By eliminating distractions, whether physical or mental, we make room for the things that truly matter.</p>
</div>

<div class="container" id="section2">
    <h2>Nature's Simplicity</h2>
    <p>Consider nature. A single tree standing alone in a field can evoke just as much awe as a dense forest. Its branches, reaching toward the sky, don’t need companions to make a statement. Its simplicity is its strength.</p>
    <div class="collapsible">Read More</div>
    <div class="content">
        <p>Similarly, when we declutter our lives—whether it’s removing material possessions, unnecessary commitments, or even overcomplicated thoughts—we find that what remains has more impact. The essentials become clearer: relationships, passions, and purpose.</p>
    </div>
</div>

<div class="container" id="section3">
    <h2>The Minimalist Movement</h2>
    <p>There’s a reason why movements like minimalism have gained traction in recent years. In a world bombarded with stimuli, cutting down to what’s necessary can be a form of rebellion. It’s a declaration that our value doesn’t lie in the things we accumulate or the endless tasks we take on, but in who we are, how we connect with others, and the quality of experiences we choose to engage with.</p>
</div>

<div class="container" id="section4">
    <h2>Embracing Mindfulness</h2>
    <p>In a way, embracing simplicity is a call to <span class="tooltip" data-tooltip="Mindfulness is the practice of being aware and present in the moment.">mindfulness</span>. It’s about being present and appreciating the little things that might otherwise go unnoticed. When we’re no longer distracted by the noise, we can focus on the subtleties—the way the light filters through a window, the taste of a morning coffee, or the joy of an unhurried conversation.</p>
</div>

<div class="container" id="section5">
    <h2>The Role of Technology in Simplicity</h2>
    <p>In an age where technology often adds layers of complexity to our lives, it can also be a powerful tool for achieving simplicity. Thoughtfully designed tech solutions streamline tasks, reduce clutter, and help us focus on what truly matters.</p>
    <div class="collapsible">Read More</div>
    <div class="content">
        <p>From minimalist apps that encourage mindfulness to smart home devices that automate mundane chores, technology, when used intentionally, can be an ally in our pursuit of simplicity.</p>
    </div>
</div>

<div class="container" id="section6">
    <h2>Simplicity in Everyday Life</h2>
    <p>Embracing simplicity doesn't require drastic life changes. It can be as straightforward as decluttering a workspace, practicing gratitude, or setting aside time for reflection.</p>
    <div class="collapsible">Read More</div>
    <div class="content">
        <p>These small adjustments accumulate, leading to a more centered and fulfilling life. By prioritizing what's essential, we create space for joy, creativity, and meaningful connections.</p>
    </div>
</div>

<div class="container" id="section7">
    <h2>The Philosophy of Minimalism</h2>
    <p>Minimalism is more than an aesthetic; it's a mindset. Rooted in the idea that less is more, it challenges us to evaluate our relationships with possessions, habits, and even thoughts.</p>
    <div class="collapsible">Read More</div>
    <div class="content">
        <p>This philosophy encourages intentionality, prompting us to make choices that align with our values and aspirations rather than societal pressures or fleeting trends.</p>
    </div>
</div>

<div class="container" id="section8">
    <h2>The Impact of Simplicity on Well-being</h2>
    <p>Studies have shown that simplifying our environments and routines can significantly reduce stress and anxiety. A clear space often leads to a clear mind.</p>
    <div class="collapsible">Read More</div>
    <div class="content">
        <p>By eliminating excess, we not only improve our mental health but also enhance our ability to concentrate and be productive. Simplicity fosters a sense of calm and balance, which is essential in today's hectic world.</p>
    </div>
</div>

<button class="toggle-theme" id="themeButton" aria-label="Toggle Theme">Toggle Theme</button>
<button class="back-to-top" id="backToTop" aria-label="Back to Top">⬆</button>

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

    // Scroll Progress Bar and Back to Top Button
    const progressBar = document.getElementById('progressBar');
    const backToTop = document.getElementById('backToTop');
    window.addEventListener('scroll', () => {
        const totalHeight = document.body.scrollHeight - window.innerHeight;
        const progress = (window.scrollY / totalHeight) * 100;
        progressBar.style.width = progress + '%';

        // Show or hide back to top button
        if (window.scrollY > 300) {
            backToTop.classList.add('visible');
        } else {
            backToTop.classList.remove('visible');
        }

        // Update active navigation link
        const sections = document.querySelectorAll('.container');
        const navLinks = document.querySelectorAll('.nav-link');
        sections.forEach((section, index) => {
            const rect = section.getBoundingClientRect();
            if (rect.top <= 60 && rect.bottom >= 60) {
                navLinks.forEach(link => link.classList.remove('active'));
                navLinks[index].classList.add('active');
            }
        });
    });

    backToTop.addEventListener('click', () => {
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Content Load Animations
    const containers = document.querySelectorAll('.container');
    const observerOptions = {
        threshold: 0.1
    };
    const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, observerOptions);
    containers.forEach(container => {
        observer.observe(container);
    });

    // Collapsible Sections
    const collapsibles = document.querySelectorAll('.collapsible');
    collapsibles.forEach(collapsible => {
        collapsible.addEventListener('click', () => {
            collapsible.classList.toggle('active');
            const content = collapsible.nextElementSibling;
            content.classList.toggle('open');
        });
    });

    // Hide other sections when navigating
    const navLinks = document.querySelectorAll('.nav-link');
    navLinks.forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            const targetId = link.getAttribute('href').substring(1);
            const targetSection = document.getElementById(targetId);
            
            containers.forEach(container => {
                if (container !== targetSection) {
                    container.style.transition = 'opacity 0.6s ease-out';
                    container.style.opacity = '0';
                    setTimeout(() => {
                        container.style.visibility = 'hidden';
                        container.style.position = 'absolute';
                    }, 600);
                } else {
                    container.style.visibility = 'visible';
                    container.style.position = 'relative';
                    setTimeout(() => {
                        container.style.opacity = '1';
                    }, 10);
                }
            });
            
            targetSection.scrollIntoView({ behavior: 'smooth' });
        });
    });
</script>
</body>
</html>
