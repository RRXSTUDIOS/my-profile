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
            background: radial-gradient(circle, #38bdf8, #1d4ed8);
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
            width: 118px;
            height: 118px;
            margin: 0 auto 1.25rem;
        }

        .avatar-wrapper::before {
            content: '';
            position: absolute;
            inset: -3.5px;
            border-radius: 50%;
            background: linear-gradient(135deg, #38bdf8, #ef4444, #3b82f6);
            z-index: -
