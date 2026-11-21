<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>REDRROX | Official Profile</title>
    
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        /* --- RESET & BASE STYLES --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }

        body {
            min-height: 100vh;
            background-color: #050508;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 2rem 1rem;
            overflow-x: hidden;
            position: relative;
        }

        /* --- FANCY PREMIUM ANIMATED BACKGROUND --- */
        /* 1. Subtle Cyber Grid */
        .bg-grid {
            position: fixed;
            inset: 0;
            background-image: 
                linear-gradient(to right, rgba(255, 255, 255, 0.03) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
            background-size: 40px 40px;
            z-index: 0;
            pointer-events: none;
            mask-image: radial-gradient(circle at center, black 40%, transparent 95%);
            -webkit-mask-image: radial-gradient(circle at center, black 40%, transparent 95%);
        }

        /* 2. Glowing Ambient Aurora Orbs */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(90px);
            z-index: 0;
            pointer-events: none;
            opacity: 0.45;
            animation: floatOrb 12s ease-in-out infinite alternate;
        }

        .orb-1 {
            width: 380px;
            height: 380px;
            background: radial-gradient(circle, #ef4444, #991b1b);
            top: -80px;
            left: -80px;
        }

        .orb-2 {
            width: 420px;
            height: 420px;
            background: radial-gradient(circle, #5865F2, #312e81);
            bottom: -100px;
            right: -80px;
            animation-delay: -6s;
        }

        .orb-3 {
            width: 280px;
            height: 280px;
            background: radial-gradient(circle, #e1306c, #701a75);
            top: 45%;
            left: 55%;
            opacity: 0.25;
            animation-duration: 16s;
        }

        @keyframes floatOrb {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(35px, -40px) scale(1.12); }
        }

        /* 3. Background Sliding Logos */
        .bg-slider-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
            pointer-events: none;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            opacity: 0.05;
            transform: rotate(-12deg) scale(1.2);
        }

        .bg-track {
            display: flex;
            width: max-content;
            gap: 4.5rem;
            font-size: 5rem;
            animation: slideLeft 28s linear infinite;
        }

        .bg-track.reverse {
            animation: slideRight 34s linear infinite;
        }

        @keyframes slideLeft {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        @keyframes slideRight {
            0% { transform: translateX(-50%); }
            100% { transform: translateX(0); }
        }

        /* --- MAIN GLASSMORPHISM PROFILE CARD --- */
        .profile-card {
            position: relative;
            z-index: 10;
            width: 100%;
            max-width: 480px;
            background: rgba(18, 18, 24, 0.65);
            backdrop-filter: blur(22px);
            -webkit-backdrop-filter: blur(22px);
            border: 1px solid rgba(255, 255, 255, 0.12);
            border-radius: 26px;
            padding: 2.5rem 2rem;
            box-shadow: 0 25px 60px -15px rgba(0, 0, 0, 0.85),
                        inset 0 1px 0 rgba(255, 255, 255, 0.12);
            text-align: center;
            animation: fadeInUp 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(25px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* --- PROFILE IMAGE & HEADER --- */
        .avatar-wrapper {
            position: relative;
            width: 112px;
            height: 112px;
            margin: 0 auto 1.2rem;
        }

        .avatar-wrapper::before {
            content: '';
            position: absolute;
            inset: -3.5px;
            border-radius: 50%;
            background: linear-gradient(135deg, #ef4444, #e1306c, #5865F2);
            z-index: -1;
            animation: spinBorder 6s linear infinite;
        }

        @keyframes spinBorder {
            0% { filter: hue-rotate(0deg); }
            100% { filter: hue-rotate(360deg); }
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid #0e0e13;
        }

        .name {
            font-size: 1.75rem;
            font-weight: 800;
            letter-spacing: 0.04em;
            margin-bottom: 0.35rem;
            background: linear-gradient(to right, #ffffff, #e4e4e7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .tagline {
            font-size: 0.88rem;
            color: #a1a1aa;
            font-weight: 500;
            margin-bottom: 1.3rem;
        }

        /* --- DETAILED BIO SECTION --- */
        .bio-box {
            background: rgba(255, 255, 255, 0.035);
            border: 1px solid rgba(255, 255, 255, 0.07);
            border-radius: 15px;
            padding: 1rem 1.2rem;
            margin-bottom: 1.8rem;
            text-align: left;
        }

        .bio-title {
            font-size: 0.72rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            color: #f87171;
            font-weight: 700;
            margin-bottom: 0.35rem;
        }

        .bio-text {
            font-size: 0.92rem;
            line-height: 1.6;
            color: #e4e4e7;
        }

        /* --- SOCIAL LINK CARDS --- */
        .links-container {
            display: flex;
            flex-direction: column;
            gap: 0.9rem;
        }

        .social-card {
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-decoration: none;
            color: #ffffff;
            background: rgba(255, 255, 255, 0.04);
            border: 1px solid rgba(255, 255, 255, 0.08);
            padding: 0.95rem 1.2rem;
            border-radius: 16px;
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            position: relative;
            overflow: hidden;
        }

        .social-card:hover {
            transform: translateY(-3px) scale(1.015);
            background: rgba(255, 255, 255, 0.08);
            box-shadow: 0 12px 28px -6px rgba(0, 0, 0, 0.6);
        }

        .social-left {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .icon-box {
            width: 44px;
            height: 44px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.25rem;
            transition: transform 0.3s ease;
        }

        .social-card:hover .icon-box {
            transform: scale(1.12);
        }

        .social-info {
            text-align: left;
        }

        .social-name {
            font-size: 1rem;
            font-weight: 600;
            display: block;
        }

        .social-handle {
            font-size: 0.8rem;
            color: #a1a1aa;
        }

        .arrow-icon {
            color: #71717a;
            font-size: 0.9rem;
            transition: transform 0.3s ease, color 0.3s ease;
        }

        .social-card:hover .arrow-icon {
            transform: translateX(4px);
            color: #ffffff;
        }

        /* --- BRAND SPECIFIC HOVER ACCENTS --- */
        .web .icon-box { background: rgba(16, 185, 129, 0.15); color: #34d399; }
        .web:hover { border-color: rgba(52, 211, 153, 0.45); }

        .yt .icon-box { background: rgba(239, 68, 68, 0.15); color: #ff4444; }
        .yt:hover { border-color: rgba(255, 68, 68, 0.45); }

        .ig .icon-box { background: rgba(225, 48, 108, 0.15); color: #f43f5e; }
        .ig:hover { border-color: rgba(244, 63, 94, 0.45); }

        .dc .icon-box { background: rgba(88, 101, 242, 0.18); color: #7289da; }
        .dc:hover { border-color: rgba(88, 101, 242, 0.5); }

        /* --- FOOTER --- */
        .footer {
            margin-top: 2rem;
            font-size: 0.78rem;
            color: #71717a;
            letter-spacing: 0.02em;
        }

        /* --- RESPONSIVE ADJUSTMENTS --- */
        @media (max-width: 480px) {
            .profile-card {
                padding: 2rem 1.3rem;
            }
            .name {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>

    <!-- Fancy Premium Background Layers -->
    <div class="bg-grid" aria-hidden="true"></div>
    <div class="orb orb-1" aria-hidden="true"></div>
    <div class="orb orb-2" aria-hidden="true"></div>
    <div class="orb orb-3" aria-hidden="true"></div>

    <!-- Animated Sliding Background Logos -->
    <div class="bg-slider-container" aria-hidden="true">
        <div class="bg-track">
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
            <!-- Duplicated for seamless loop -->
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
        </div>

        <div class="bg-track reverse">
            <i class="fa-brands fa-discord"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <!-- Duplicated for seamless loop -->
            <i class="fa-brands fa-discord"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
        </div>

        <div class="bg-track">
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
            <!-- Duplicated for seamless loop -->
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-discord"></i>
            <i class="fa-solid fa-globe"></i>
        </div>
    </div>

    <!-- Main Profile Card -->
    <main class="profile-card">
        
        <!-- Profile Picture (Replace src with your own photo URL or local file) -->
        <div class="avatar-wrapper">
            <img src="rrp.jpg" alt="REDRROX Profile Photo" class="avatar">
        </div>

        <!-- Name & Tagline -->
        <h1 class="name">REDRROX</h1>
        <p class="tagline">Content Creator • Tech Enthusiast • Developer</p>

        <!-- Detailed Bio -->
        <div class="bio-box">
            <div class="bio-title">About Me</div>
            <p class="bio-text">Nothing :)</p>
        </div>

        <!-- Social Media & Website Link Cards -->
        <div class="links-container">
            
            <!-- Official Website -->
            <a href="https://rrxstudios.github.io/rrxstudios/" target="_blank" rel="noopener noreferrer" class="social-card web">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-solid fa-globe"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">Official Website</span>
                        <span class="social-handle">RRXSTUDIOS • Portfolio & Projects</span>
                    </div>
                </div>
                <i class="fa-solid fa-arrow-up-right-from-square arrow-icon"></i>
            </a>

            <!-- YouTube -->
            <a href="http://www.youtube.com/@redrrox" target="_blank" rel="noopener noreferrer" class="social-card yt">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-brands fa-youtube"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">YouTube</span>
                        <span class="social-handle">@redrrox • Subscribe for videos</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-right arrow-icon"></i>
            </a>

            <!-- Instagram -->
            <a href="https://www.instagram.com/red.rrox/" target="_blank" rel="noopener noreferrer" class="social-card ig">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-brands fa-instagram"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">Instagram</span>
                        <span class="social-handle">@red.rrox • Photos & Reels</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-right arrow-icon"></i>
            </a>

            <!-- Discord -->
            <a href="https://discord.gg/cmcM6W6Gk8" target="_blank" rel="noopener noreferrer" class="social-card dc">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-brands fa-discord"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">Discord</span>
                        <span class="social-handle">Join our official community server</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-right arrow-icon"></i>
            </a>

        </div>

        <footer class="footer">
            © 2026 RRXSTUDIOS. All rights reserved.
        </footer>

    </main>

</body>
</html>
