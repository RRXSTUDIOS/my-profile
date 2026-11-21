<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name | Official Profile</title>
    
    <!-- Google Fonts: Inter & Poppins -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Font Awesome Icons (For Social Logos) -->
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
            background: radial-gradient(circle at top left, #1e1b4b, #09090b 60%, #000000);
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 2rem 1rem;
            overflow-x: hidden;
            position: relative;
        }

        /* --- BACKGROUND SLIDING LOGOS ANIMATION --- */
        .bg-slider-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
            pointer-events: none;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            opacity: 0.06; /* Subtle watermark look */
            transform: rotate(-12deg) scale(1.2);
        }

        .bg-track {
            display: flex;
            width: max-content;
            gap: 4rem;
            font-size: 5rem;
            animation: slideLeft 30s linear infinite;
        }

        .bg-track.reverse {
            animation: slideRight 35s linear infinite;
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
            background: rgba(24, 24, 27, 0.65);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            padding: 2.5rem 2rem;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7),
                        0 0 30px rgba(99, 102, 241, 0.15);
            text-align: center;
            animation: fadeInUp 0.8s ease-out;
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
            width: 110px;
            height: 110px;
            margin: 0 auto 1.2rem;
        }

        .avatar-wrapper::before {
            content: '';
            position: absolute;
            inset: -3px;
            border-radius: 50%;
            background: linear-gradient(45deg, #6366f1, #ec4899, #3b82f6);
            z-index: -1;
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid #121215;
        }

        .name {
            font-size: 1.65rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            margin-bottom: 0.3rem;
        }

        .tagline {
            font-size: 0.9rem;
            color: #a1a1aa;
            font-weight: 500;
            margin-bottom: 1.2rem;
        }

        /* --- DETAILED BIO SECTION --- */
        .bio-box {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 14px;
            padding: 1rem 1.2rem;
            margin-bottom: 1.8rem;
            text-align: left;
        }

        .bio-title {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.08em;
            color: #818cf8;
            font-weight: 600;
            margin-bottom: 0.4rem;
        }

        .bio-text {
            font-size: 0.9rem;
            line-height: 1.6;
            color: #d4d4d8;
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
            transform: translateY(-3px) scale(1.01);
            background: rgba(255, 255, 255, 0.08);
            border-color: rgba(255, 255, 255, 0.2);
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.5);
        }

        .social-left {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .icon-box {
            width: 42px;
            height: 42px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.25rem;
            transition: transform 0.3s ease;
        }

        .social-card:hover .icon-box {
            transform: scale(1.1);
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
        .yt .icon-box { background: rgba(255, 0, 0, 0.15); color: #ff4444; }
        .yt:hover { border-color: rgba(255, 68, 68, 0.4); }

        .fb .icon-box { background: rgba(24, 119, 242, 0.15); color: #3b82f6; }
        .fb:hover { border-color: rgba(59, 130, 246, 0.4); }

        .ig .icon-box { background: rgba(225, 48, 108, 0.15); color: #f43f5e; }
        .ig:hover { border-color: rgba(244, 63, 94, 0.4); }

        .li .icon-box { background: rgba(10, 102, 194, 0.15); color: #38bdf8; }
        .li:hover { border-color: rgba(56, 189, 248, 0.4); }

        .web .icon-box { background: rgba(16, 185, 129, 0.15); color: #34d399; }
        .web:hover { border-color: rgba(52, 211, 153, 0.4); }

        /* --- FOOTER --- */
        .footer {
            margin-top: 2rem;
            font-size: 0.78rem;
            color: #71717a;
        }

        /* --- RESPONSIVE ADJUSTMENTS --- */
        @media (max-width: 480px) {
            .profile-card {
                padding: 2rem 1.3rem;
            }
            .name {
                font-size: 1.45rem;
            }
        }
    </style>
</head>
<body>

    <!-- Animated Sliding Background Logos -->
    <div class="bg-slider-container" aria-hidden="true">
        <div class="bg-track">
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-solid fa-globe"></i>
            <!-- Duplicated for seamless loop -->
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-solid fa-globe"></i>
        </div>

        <div class="bg-track reverse">
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
            <!-- Duplicated for seamless loop -->
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-facebook"></i>
        </div>

        <div class="bg-track">
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-solid fa-globe"></i>
            <!-- Duplicated for seamless loop -->
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-solid fa-globe"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-youtube"></i>
            <i class="fa-brands fa-linkedin"></i>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-solid fa-globe"></i>
        </div>
    </div>

    <!-- Main Profile Card -->
    <main class="profile-card">
        
        <!-- TODO: Replace with your profile picture URL -->
        <div class="avatar-wrapper">
            <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=300&q=80" alt="Profile Photo" class="avatar">
        </div>

        <!-- TODO: Replace with your Name & Tagline -->
        <h1 class="name">Your Full Name</h1>
        <p class="tagline">Digital Creator • Tech Enthusiast • Developer</p>

        <!-- TODO: Replace with your Detailed Bio -->
        <div class="bio-box">
            <div class="bio-title">About Me</div>
            <p class="bio-text">
                Hi! Welcome to my official digital hub. I create engaging content, build modern web experiences, and connect with people worldwide. Feel free to explore my platforms below and connect with me!
            </p>
        </div>

        <!-- Social Media & Website Link Cards -->
        <div class="links-container">
            
            <!-- Personal Website -->
            <!-- TODO: Replace href with your website URL -->
            <a href="https://yourwebsite.com" target="_blank" rel="noopener noreferrer" class="social-card web">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-solid fa-globe"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">Official Website</span>
                        <span class="social-handle">Visit my portfolio & projects</span>
                    </div>
                </div>
                <i class="fa-solid fa-arrow-up-right-from-square arrow-icon"></i>
            </a>

            <!-- YouTube -->
            <!-- TODO: Replace href with your YouTube URL -->
            <a href="https://youtube.com/@yourhandle" target="_blank" rel="noopener noreferrer" class="social-card yt">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-brands fa-youtube"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">YouTube</span>
                        <span class="social-handle">@yourhandle • Subscribe for videos</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-right arrow-icon"></i>
            </a>

            <!-- Facebook -->
            <!-- TODO: Replace href with your Facebook URL -->
            <a href="https://facebook.com/yourprofile" target="_blank" rel="noopener noreferrer" class="social-card fb">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-brands fa-facebook-f"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">Facebook</span>
                        <span class="social-handle">@yourprofile • Follow updates</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-right arrow-icon"></i>
            </a>

            <!-- Instagram -->
            <!-- TODO: Replace href with your Instagram URL -->
            <a href="https://instagram.com/yourhandle" target="_blank" rel="noopener noreferrer" class="social-card ig">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-brands fa-instagram"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">Instagram</span>
                        <span class="social-handle">@yourhandle • Photos & Reels</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-right arrow-icon"></i>
            </a>

            <!-- LinkedIn -->
            <!-- TODO: Replace href with your LinkedIn URL -->
            <a href="https://linkedin.com/in/yourprofile" target="_blank" rel="noopener noreferrer" class="social-card li">
                <div class="social-left">
                    <div class="icon-box">
                        <i class="fa-brands fa-linkedin-in"></i>
                    </div>
                    <div class="social-info">
                        <span class="social-name">LinkedIn</span>
                        <span class="social-handle">Connect professionally</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-right arrow-icon"></i>
            </a>

        </div>

        <footer class="footer">
            © 2026 Your Name. All rights reserved.
        </footer>

    </main>

</body>
</html>
