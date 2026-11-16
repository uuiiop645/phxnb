<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>张锦宝宝 · 我爱你 · 彭皓轩专属</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: radial-gradient(ellipse at 30% 20%, #1a1225 0%, #0a0a18 60%, #050510 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', 'PingFang SC', 'Microsoft YaHei', system-ui, sans-serif;
            overflow-x: hidden;
            overflow-y: auto;
            position: relative;
            padding: 1rem;
        }

        /* ===== 星空背景 ===== */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .star {
            position: absolute;
            background: #fff;
            border-radius: 50%;
            animation: twinkle ease-in-out infinite;
            will-change: opacity;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.15; }
            50% { opacity: 0.9; }
        }

        /* ===== 飘浮爱心粒子 ===== */
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 1;
        }

        .heart-particle {
            position: absolute;
            bottom: -10%;
            font-size: 1.2rem;
            animation: floatUp linear infinite;
            user-select: none;
            will-change: transform, opacity;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) scale(0.8) rotate(0deg);
                opacity: 0.9;
            }
            80% { opacity: 0.6; }
            100% {
                transform: translateY(-120vh) scale(1.4) rotate(20deg);
                opacity: 0;
            }
        }

        /* ===== 主卡片 ===== */
        .love-card {
            position: relative;
            z-index: 10;
            background: rgba(25, 15, 35, 0.55);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-radius: 60px;
            padding: 2.5rem 3rem 2.8rem;
            box-shadow:
                0 30px 60px rgba(0, 0, 0, 0.8),
                0 0 0 2px rgba(255, 70, 120, 0.25),
                0 0 70px rgba(255, 20, 100, 0.45),
                inset 0 0 60px rgba(255, 50, 100, 0.06);
            text-align: center;
            border: 1px solid rgba(255, 120, 160, 0.35);
            animation: cardGlow 3s ease-in-out infinite alternate;
            max-width: 920px;
            width: 100%;
            margin: 2rem auto;
            transition: all 0.3s ease;
        }

        @keyframes cardGlow {
            0% {
                box-shadow:
                    0 30px 60px rgba(0, 0, 0, 0.8),
                    0 0 0 2px rgba(255, 70, 120, 0.25),
                    0 0 60px rgba(255, 20, 100, 0.35),
                    inset 0 0 60px rgba(255, 50, 100, 0.06);
            }
            100% {
                box-shadow:
                    0 30px 70px rgba(0, 0, 0, 0.9),
                    0 0 0 3px rgba(255, 120, 160, 0.5),
                    0 0 100px rgba(255, 50, 130, 0.7),
                    inset 0 0 80px rgba(255, 50, 100, 0.12);
            }
        }

        /* ===== 专属徽章 ===== */
        .exclusive-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 0.35rem 1.3rem;
            margin-bottom: 0.8rem;
            font-size: clamp(0.8rem, 2.6vw, 1rem);
            font-weight: 600;
            letter-spacing: 0.18em;
            color: #ffd9e6;
            background: linear-gradient(135deg, rgba(255, 30, 80, 0.35), rgba(120, 20, 60, 0.45));
            border: 1px solid rgba(255, 140, 170, 0.8);
            border-radius: 50px;
            box-shadow: 0 0 28px rgba(255, 40, 90, 0.5), inset 0 0 14px rgba(255, 80, 130, 0.2);
            backdrop-filter: blur(6px);
            animation: badgeGlow 2.2s ease-in-out infinite alternate;
            text-shadow: 0 0 12px #ff3366;
        }

        @keyframes badgeGlow {
            0% { box-shadow: 0 0 20px rgba(255, 40, 90, 0.4), inset 0 0 12px rgba(255, 80, 130, 0.15); }
            100% { box-shadow: 0 0 42px rgba(255, 50, 110, 0.85), inset 0 0 20px rgba(255, 100, 150, 0.35); }
        }

        .exclusive-badge .badge-icon {
            font-size: 1.05em;
            filter: drop-shadow(0 0 8px #ff4d6d);
        }

        /* ===== 标题 ===== */
        .name-title {
            font-size: clamp(2.4rem, 10vw, 4.8rem);
            font-weight: 800;
            letter-spacing: 0.08em;
            margin-bottom: 0.2rem;
            background: linear-gradient(135deg, #ffe6f0, #ffb3c6, #ff4d6d, #ff1a4f);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 30px rgba(255, 80, 120, 0.7), 0 0 60px rgba(255, 20, 100, 0.5);
            animation: titlePulse 2.5s infinite alternate;
            line-height: 1.15;
            filter: drop-shadow(0 0 15px #ff4d6d);
        }

        @keyframes titlePulse {
            0% { transform: scale(1); filter: drop-shadow(0 0 10px #ff4d6d); }
            100% { transform: scale(1.02); filter: drop-shadow(0 0 25px #ff1a4f); }
        }

        /* ===== 我爱你 副标题 ===== */
        .sub-message {
            font-size: clamp(1.6rem, 5vw, 2.6rem);
            font-weight: 500;
            color: #ffe6f0;
            text-shadow: 0 0 20px #ff4d6d, 0 0 35px #ff1a4f;
            margin: 0.3rem 0 0.6rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .heart-icon {
            display: inline-block;
            font-size: 2.6rem;
            color: #ff3366;
            text-shadow: 0 0 30px #ff0066, 0 0 50px #ff1a4f;
            animation: heartbeat 1.4s infinite;
            transform-origin: center;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            15% { transform: scale(1.25); }
            30% { transform: scale(1); }
            45% { transform: scale(1.15); }
            60% { transform: scale(1); }
            100% { transform: scale(1); }
        }

        /* ===== 大大的爱心 ===== */
        .big-heart-wrapper {
            margin: 0.8rem auto 0.4rem;
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            max-width: 460px;
            position: relative;
        }

        .big-heart {
            font-size: clamp(7rem, 30vw, 12.5rem);
            line-height: 1;
            color: #ff1a4f;
            text-shadow:
                0 0 30px #ff3366,
                0 0 70px #ff0066,
                0 0 120px #ff0044,
                0 0 200px #cc0033;
            animation: bigHeartbeat 1.6s ease-in-out infinite;
            transform-origin: center;
            filter: drop-shadow(0 0 35px rgba(255, 30, 80, 0.9));
            user-select: none;
            position: relative;
            z-index: 2;
        }

        @keyframes bigHeartbeat {
            0% { transform: scale(1); }
            12% { transform: scale(1.08); }
            24% { transform: scale(0.98); }
            36% { transform: scale(1.04); }
            48% { transform: scale(1); }
            60% { transform: scale(1.02); }
            72% { transform: scale(0.99); }
            100% { transform: scale(1); }
        }

        .heart-halo {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 100%;
            height: 100%;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            background: radial-gradient(circle, rgba(255, 40, 90, 0.35) 0%, transparent 70%);
            animation: haloPulse 1.6s ease-in-out infinite;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes haloPulse {
            0%, 100% { transform: translate(-50%, -50%) scale(0.9); opacity: 0.5; }
            50% { transform: translate(-50%, -50%) scale(1.25); opacity: 0.9; }
        }

        /* ===== 一生一世 ===== */
        .promise {
            font-size: clamp(1.2rem, 4vw, 1.9rem);
            font-weight: 300;
            color: #ffccdd;
            letter-spacing: 0.28em;
            padding: 0.8rem 1rem 0.6rem;
            border-top: 2px solid rgba(255, 100, 150, 0.6);
            border-bottom: 2px solid rgba(255, 100, 150, 0.6);
            margin-top: 0.2rem;
            text-shadow: 0 0 20px #ff4d6d, 0 0 30px #ff0066;
            background: linear-gradient(90deg, transparent, rgba(255, 80, 120, 0.15), transparent);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { opacity: 0.9; letter-spacing: 0.28em; }
            50% { opacity: 1; letter-spacing: 0.34em; }
            100% { opacity: 0.9; letter-spacing: 0.28em; }
        }

        /* ===== 1314 520 ===== */
        .forever {
            font-size: clamp(1.1rem, 4vw, 1.6rem);
            color: #ffd9e6;
            margin-top: 0.8rem;
            font-weight: 400;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .forever span {
            background: rgba(255, 70, 120, 0.2);
            padding: 0.3rem 1.2rem;
            border-radius: 60px;
            border: 1px solid rgba(255, 120, 160, 0.7);
            box-shadow: 0 0 25px rgba(255, 50, 130, 0.5);
            backdrop-filter: blur(5px);
        }

        /* ===== 打字机情话 ===== */
        .typewriter-box {
            margin: 1.4rem auto 0.6rem;
            min-height: 3.4rem;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 0.6rem 1.4rem;
            background: rgba(255, 80, 120, 0.12);
            border-radius: 50px;
            border: 1px solid rgba(255, 120, 160, 0.4);
            backdrop-filter: blur(6px);
            box-shadow: 0 0 30px rgba(255, 50, 130, 0.2);
            max-width: 100%;
        }

        .typewriter-text {
            font-size: clamp(1rem, 3.5vw, 1.35rem);
            font-weight: 400;
            color: #ffd9e6;
            letter-spacing: 0.05em;
            text-shadow: 0 0 15px rgba(255, 80, 120, 0.6);
            line-height: 1.5;
        }

        .cursor {
            display: inline-block;
            width: 2px;
            height: 1.2em;
            background: #ff4d6d;
            margin-left: 4px;
            vertical-align: middle;
            animation: blink 0.9s step-end infinite;
            box-shadow: 0 0 10px #ff3366;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        /* ===== 情话区域 ===== */
        .love-words {
            margin: 1.3rem 0 0.8rem;
            display: flex;
            flex-direction: column;
            gap: 0.7rem;
            color: #ffe6f0;
        }

        .love-line {
            font-size: clamp(0.95rem, 3.2vw, 1.25rem);
            font-weight: 300;
            letter-spacing: 0.04em;
            padding: 0.65rem 1.1rem;
            border-radius: 50px;
            background: rgba(255, 80, 120, 0.08);
            backdrop-filter: blur(4px);
            border: 1px solid rgba(255, 120, 160, 0.25);
            transition: all 0.3s ease;
            animation: fadeSlide 0.8s ease backwards;
            text-shadow: 0 0 12px rgba(255, 80, 120, 0.4);
            line-height: 1.5;
        }

        .love-line:nth-child(1) { animation-delay: 0.15s; }
        .love-line:nth-child(2) { animation-delay: 0.25s; }
        .love-line:nth-child(3) { animation-delay: 0.35s; }
        .love-line:nth-child(4) { animation-delay: 0.45s; }
        .love-line:nth-child(5) { animation-delay: 0.55s; }
        .love-line:nth-child(6) { animation-delay: 0.65s; }
        .love-line:nth-child(7) { animation-delay: 0.75s; }
        .love-line:nth-child(8) { animation-delay: 0.85s; }
        .love-line:nth-child(9) { animation-delay: 0.95s; }
        .love-line:nth-child(10) { animation-delay: 1.05s; }
        .love-line:nth-child(11) { animation-delay: 1.15s; }
        .love-line:nth-child(12) { animation-delay: 1.25s; }
        .love-line:nth-child(13) { animation-delay: 1.35s; }
        .love-line:nth-child(14) { animation-delay: 1.45s; }

        @keyframes fadeSlide {
            0% {
                opacity: 0;
                transform: translateY(12px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .love-line:hover {
            background: rgba(255, 70, 120, 0.18);
            border-color: rgba(255, 120, 160, 0.7);
            box-shadow: 0 0 30px rgba(255, 50, 130, 0.3);
            transform: scale(1.01);
        }

        .love-line .emoji {
            display: inline-block;
            margin-right: 6px;
            filter: drop-shadow(0 0 6px #ff4d6d);
        }

        /* 专属情话特别样式 */
        .love-line.exclusive {
            background: linear-gradient(135deg, rgba(255, 60, 110, 0.18), rgba(180, 40, 90, 0.12));
            border: 1px solid rgba(255, 150, 180, 0.65);
            box-shadow: 0 0 24px rgba(255, 50, 110, 0.28);
            font-weight: 400;
        }

        .love-line.exclusive .exclusive-tag {
            display: inline-block;
            font-size: 0.7em;
            font-weight: 700;
            letter-spacing: 0.08em;
            padding: 0.12em 0.6em;
            margin-right: 8px;
            border-radius: 40px;
            background: linear-gradient(135deg, #ff4d6d, #cc0033);
            color: #fff;
            box-shadow: 0 0 12px rgba(255, 50, 100, 0.8);
            vertical-align: middle;
        }

        /* ===== 彩蛋按钮 ===== */
        .surprise-btn {
            margin-top: 1.2rem;
            padding: 0.7rem 2.2rem;
            font-size: clamp(0.95rem, 3vw, 1.1rem);
            font-family: inherit;
            font-weight: 600;
            letter-spacing: 0.1em;
            color: #fff;
            background: linear-gradient(135deg, #ff4d6d, #ff1a4f, #cc0033);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 0 30px rgba(255, 50, 100, 0.6), 0 8px 20px rgba(0, 0, 0, 0.4);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            z-index: 20;
        }

        .surprise-btn:hover {
            transform: scale(1.06);
            box-shadow: 0 0 50px rgba(255, 60, 110, 0.9), 0 8px 24px rgba(0, 0, 0, 0.5);
        }

        .surprise-btn:active {
            transform: scale(0.97);
        }

        .surprise-btn::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.6s ease, height 0.6s ease;
        }

        .surprise-btn:active::after {
            width: 300px;
            height: 300px;
            opacity: 0;
            transition: 0s;
        }

        /* ===== 弹窗彩蛋 ===== */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(6px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
            opacity: 0;
            visibility: hidden;
            transition: all 0.4s ease;
            padding: 1rem;
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-box {
            background: linear-gradient(145deg, #2a1530, #1a0f25);
            border-radius: 40px;
            padding: 2.5rem 2.2rem;
            max-width: 540px;
            width: 100%;
            text-align: center;
            border: 2px solid rgba(255, 100, 150, 0.6);
            box-shadow: 0 0 80px rgba(255, 30, 80, 0.5);
            transform: scale(0.8);
            transition: transform 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
        }

        .modal-overlay.active .modal-box {
            transform: scale(1);
        }

        .modal-heart {
            font-size: 4rem;
            display: block;
            margin-bottom: 0.8rem;
            animation: heartbeat 1.4s infinite;
        }

        .modal-title {
            font-size: 1.7rem;
            font-weight: 700;
            color: #ffb3c6;
            margin-bottom: 0.8rem;
            text-shadow: 0 0 20px #ff3366;
        }

        .modal-exclusive-line {
            display: inline-block;
            font-size: 0.82rem;
            font-weight: 600;
            letter-spacing: 0.15em;
            color: #ffd9e6;
            padding: 0.25rem 1.1rem;
            margin-bottom: 1rem;
            border-radius: 40px;
            background: rgba(255, 60, 110, 0.25);
            border: 1px solid rgba(255, 150, 180, 0.8);
            box-shadow: 0 0 22px rgba(255, 50, 110, 0.45);
        }

        .modal-text {
            font-size: 1.1rem;
            color: #ffd9e6;
            line-height: 1.7;
            text-shadow: 0 0 12px rgba(255, 80, 120, 0.4);
        }

        .modal-close {
            margin-top: 1.4rem;
            padding: 0.5rem 1.8rem;
            font-size: 0.95rem;
            font-family: inherit;
            font-weight: 600;
            color: #fff;
            background: linear-gradient(135deg, #ff4d6d, #cc0033);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 0 25px rgba(255, 50, 100, 0.6);
            transition: all 0.3s ease;
        }

        .modal-close:hover {
            transform: scale(1.05);
            box-shadow: 0 0 40px rgba(255, 60, 110, 0.9);
        }

        /* ===== 底部装饰 ===== */
        .numbers {
            font-size: 1.3rem;
            letter-spacing: 6px;
            color: #ffb3c6;
            margin-top: 0.9rem;
            opacity: 0.9;
            text-shadow: 0 0 15px #ff3366;
        }

        .signature {
            font-size: 0.9rem;
            color: #ff9eb5;
            margin-top: 1rem;
            letter-spacing: 0.18em;
            opacity: 0.9;
            border-top: 1px dashed rgba(255, 120, 160, 0.4);
            padding-top: 0.9rem;
            line-height: 1.8;
        }

        .signature .exclusive-sign {
            display: inline-block;
            margin-top: 0.35rem;
            font-size: 0.82rem;
            font-weight: 600;
            letter-spacing: 0.2em;
            color: #ffd9e6;
            padding: 0.22rem 1.1rem;
            border-radius: 40px;
            background: rgba(255, 60, 110, 0.22);
            border: 1px solid rgba(255, 140, 170, 0.7);
            box-shadow: 0 0 20px rgba(255, 50, 110, 0.4);
            text-shadow: 0 0 12px #ff4d6d;
        }

        /* ===== 响应式 ===== */
        @media (max-width: 600px) {
            .love-card {
                padding: 1.6rem 1rem 2rem;
                border-radius: 40px;
            }
            .sub-message {
                gap: 8px;
            }
            .heart-icon {
                font-size: 2rem;
            }
            .promise {
                letter-spacing: 0.2em;
            }
            @keyframes shimmer {
                0% { letter-spacing: 0.2em; }
                50% { letter-spacing: 0.28em; }
                100% { letter-spacing: 0.2em; }
            }
            .love-line {
                font-size: 0.88rem;
                padding: 0.5rem 0.8rem;
            }
            .numbers {
                font-size: 1rem;
                letter-spacing: 4px;
            }
            .big-heart {
                font-size: clamp(6rem, 32vw, 9.5rem);
            }
            .typewriter-box {
                padding: 0.5rem 1rem;
                min-height: 3rem;
            }
            .modal-box {
                padding: 1.8rem 1.4rem;
            }
            .exclusive-badge {
                font-size: 0.75rem;
                padding: 0.28rem 1rem;
            }
        }
    </style>
</head>
<body>

    <!-- 星空背景 -->
    <div class="stars" id="starsContainer"></div>

    <!-- 漂浮爱心粒子 -->
    <div class="hearts" id="heartsContainer"></div>

    <!-- 主卡片 -->
    <div class="love-card">

        <!-- 彭皓轩专属徽章 -->
        <div class="exclusive-badge">
            <span class="badge-icon">👑</span>
            彭皓轩专属 · 宠溺张锦宝宝
            <span class="badge-icon">💍</span>
        </div>

        <div class="name-title">张锦宝宝</div>
        <div class="sub-message">
            <span>我爱你</span>
            <span class="heart-icon">❤️</span>
        </div>

        <!-- 大大的爱心 + 光环 -->
        <div class="big-heart-wrapper">
            <div class="heart-halo"></div>
            <div class="big-heart">❤️</div>
        </div>

        <div class="promise">一生一世</div>

        <div class="forever">
            <span>1314</span>
            <span>💍</span>
            <span>520</span>
        </div>

        <!-- 打字机情话 -->
        <div class="typewriter-box">
            <span class="typewriter-text" id="typewriterText"></span>
            <span class="cursor"></span>
        </div>

        <!-- 情话区域 -->
        <div class="love-words">
            <div class="love-line exclusive">
                <span class="exclusive-tag">彭皓轩专属</span>
                <span class="emoji">👑</span> 张锦宝宝，你是我彭皓轩今生唯一想守护的人。
            </div>
            <div class="love-line exclusive">
                <span class="exclusive-tag">彭皓轩专属</span>
                <span class="emoji">💍</span> 我彭皓轩对天发誓：一生一世，只爱你张锦宝宝一人。
            </div>
            <div class="love-line"><span class="emoji">💖</span> 张锦宝宝，你是我藏在心底最深的温柔。</div>
            <div class="love-line"><span class="emoji">🌙</span> 你是我睡前最后一个想的人，也是醒来第一个想到的人。</div>
            <div class="love-line"><span class="emoji">✨</span> 遇见你，是我这辈子最幸运的事。</div>
            <div class="love-line"><span class="emoji">🌹</span> 我想牵着你的手，从心动走到古稀，从此刻走到永远。</div>
            <div class="love-line"><span class="emoji">💕</span> 你笑起来的样子，是我最想珍藏的风景。</div>
            <div class="love-line"><span class="emoji">☀️</span> 有你在的每一天，都是晴天。</div>
            <div class="love-line"><span class="emoji">💌</span> 我的世界原本黑白，直到你带着颜色走来。</div>
            <div class="love-line"><span class="emoji">🔒</span> 心为你上锁，一生只等你一人。</div>
            <div class="love-line"><span class="emoji">🫶</span> 张锦宝宝，你是我所有温柔的来源，也是我唯一的偏爱。</div>
            <div class="love-line"><span class="emoji">💍</span> 往后余生，风雪是你，平淡是你，清贫也是你，荣华是你，心底温柔是你，目光所至，也是你。</div>
            <div class="love-line"><span class="emoji">🌌</span> 你是我浩瀚宇宙里唯一的星光，是我所有浪漫的归宿。</div>
            <div class="love-line"><span class="emoji">🍀</span> 如果有来生，我还是要跨越人海找到你，然后再说一次我爱你。</div>
        </div>

        <!-- 彩蛋按钮 -->
        <button class="surprise-btn" id="surpriseBtn">💝 彭皓轩专属惊喜 💝</button>

        <div class="numbers">♡ 永 ♡ 远 ♡ 爱 ♡ 你 ♡</div>
        <div class="signature">
            — 致我唯一的张锦宝宝 · 一生一世 —
            <br>
            <span class="exclusive-sign">👑 彭皓轩 · 专属宠爱 👑</span>
        </div>
    </div>

    <!-- 弹窗彩蛋 -->
    <div class="modal-overlay" id="modalOverlay">
        <div class="modal-box">
            <span class="modal-heart">❤️</span>
            <div class="modal-title">张锦宝宝，我爱你！</div>
            <div class="modal-exclusive-line">👑 彭皓轩专属情话 👑</div>
            <div class="modal-text" id="modalText">
                你是我今生最美的遇见，<br>
                也是我余生唯一的答案。<br>
                1314，一生一世，<br>
                我只想和你在一起。
            </div>
            <button class="modal-close" id="modalClose">我也爱你 💕</button>
        </div>
    </div>

    <script>
        (function() {
            // ========== 1. 星空背景 ==========
            const starsContainer = document.getElementById('starsContainer');
            const starCount = window.innerWidth < 600 ? 60 : 130;
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                const size = Math.random() * 2.5 + 0.5;
                star.style.width = size + 'px';
                star.style.height = size + 'px';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDuration = (Math.random() * 3 + 2) + 's';
                star.style.animationDelay = Math.random() * 5 + 's';
                star.style.opacity = Math.random() * 0.6 + 0.1;
                starsContainer.appendChild(star);
            }

            // ========== 2. 漂浮爱心粒子 ==========
            const heartsContainer = document.getElementById('heartsContainer');
            const heartSymbols = ['❤️', '💖', '💗', '💓', '💕', '💘', '💝', '💞', '💟', '♥️', '🌹', '💍', '🫶', '💐', '✨', '👑'];
            const particleCount = window.innerWidth < 600 ? 30 : 55;
            const rand = (min, max) => Math.random() * (max - min) + min;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'heart-particle';
                particle.textContent = heartSymbols[Math.floor(Math.random() * heartSymbols.length)];
                particle.style.fontSize = rand(0.8, 2.3) + 'rem';
                particle.style.left = rand(0, 100) + '%';
                particle.style.animationDuration = rand(8, 22) + 's';
                particle.style.animationDelay = rand(0, 18) + 's';
                particle.style.opacity = rand(0.5, 1);
                particle.style.transform = `rotate(${rand(-20, 20)}deg)`;

                const colors = ['#ff4d6d', '#ff6b8a', '#ff85a2', '#ffb3c6', '#ffccdd', '#ffd966', '#ff9e7a', '#ff3377'];
                const randomColor = colors[Math.floor(Math.random() * colors.length)];
                particle.style.color = randomColor;
                particle.style.textShadow = `0 0 15px ${randomColor}, 0 0 30px #ff1a4f`;
                heartsContainer.appendChild(particle);
            }

            // ========== 3. 打字机效果（含彭皓轩专属） ==========
            const typewriterText = document.getElementById('typewriterText');
            const phrases = [
                '张锦宝宝，彭皓轩爱你到永远 💖',
                '彭皓轩专属：一生一世只宠你 👑',
                '每一天都想对你说：我爱你 💕',
                '你是我今生最美的遇见 🌹',
                '彭皓轩的心跳，只为张锦宝宝加速 💓',
                '一生一世，只爱你一人 💍',
                '你是我藏在星星里的浪漫 ✨',
                '彭皓轩专属宠爱，永不缺席 🫶',
                '1314，520，彭皓轩永远爱你 ❤️',
                '遇见你之后，彭皓轩心里再也装不下别人 🌙',
                '张锦宝宝，你是彭皓轩的全部浪漫 👑'
            ];
            let phraseIndex = 0;
            let charIndex = 0;
            let isDeleting = false;
            let typeSpeed = 120;

            function typeLoop() {
                const currentPhrase = phrases[phraseIndex];

                if (isDeleting) {
                    typewriterText.textContent = currentPhrase.substring(0, charIndex - 1);
                    charIndex--;
                    typeSpeed = 45;
                } else {
                    typewriterText.textContent = currentPhrase.substring(0, charIndex + 1);
                    charIndex++;
                    typeSpeed = 110;
                }

                if (!isDeleting && charIndex === currentPhrase.length) {
                    isDeleting = true;
                    typeSpeed = 1600;
                } else if (isDeleting && charIndex === 0) {
                    isDeleting = false;
                    phraseIndex = (phraseIndex + 1) % phrases.length;
                    typeSpeed = 350;
                }

                setTimeout(typeLoop, typeSpeed);
            }

            setTimeout(typeLoop, 800);

            // ========== 4. 彩蛋弹窗（彭皓轩专属情话） ==========
            const surpriseBtn = document.getElementById('surpriseBtn');
            const modalOverlay = document.getElementById('modalOverlay');
            const modalClose = document.getElementById('modalClose');
            const modalText = document.getElementById('modalText');

            const surpriseMessages = [
                '你是我今生最美的遇见，<br>也是我余生唯一的答案。<br>1314，一生一世，<br>我彭皓轩只想和你在一起。👑',
                '张锦宝宝，<br>你是我彭皓轩心口的朱砂痣，<br>是我窗前的白月光，<br>是我这辈子最想珍惜的人。💖',
                '如果爱你有期限，<br>我希望是一万年；<br>如果非要在前面加个数字，<br>我希望是——1314。💍',
                '你问我爱你有多深？<br>月亮代表我的心。<br>但月亮有阴晴圆缺，<br>而彭皓轩对你的爱，永远圆满。🌕',
                '我想和你一起，<br>看春天的花，吹夏天的风，<br>赏秋天的月，踏冬天的雪。<br>四季有你，一生足矣。🍀',
                '张锦宝宝，<br>彭皓轩向你郑重承诺：<br>往后余生，<br>风雪是你，平淡是你，<br>目光所至，全部是你。👑💍',
                '彭皓轩专属情话：<br>世界那么大，能遇见你，<br>是我这辈子最大的幸运。<br>张锦宝宝，我爱你，<br>一生一世，至死不渝。❤️',
                '你是我彭皓轩的全世界，<br>是我愿意用一生去守护的宝贝。<br>张锦宝宝，<br>请让我爱你一辈子。💕'
            ];

            surpriseBtn.addEventListener('click', function() {
                const randomMsg = surpriseMessages[Math.floor(Math.random() * surpriseMessages.length)];
                modalText.innerHTML = randomMsg;
                modalOverlay.classList.add('active');

                for (let i = 0; i < 16; i++) {
                    createBurstHeart();
                }
            });

            modalClose.addEventListener('click', function() {
                modalOverlay.classList.remove('active');
            });

            modalOverlay.addEventListener('click', function(e) {
                if (e.target === modalOverlay) {
                    modalOverlay.classList.remove('active');
                }
            });

            // 点击彩蛋时额外的爱心爆发效果（含👑）
            function createBurstHeart() {
                const burst = document.createElement('div');
                burst.textContent = ['❤️', '💖', '💕', '✨', '💝', '🌹', '👑', '💍'][Math.floor(Math.random() * 8)];
                burst.style.position = 'fixed';
                burst.style.left = rand(10, 90) + '%';
                burst.style.top = rand(20, 80) + '%';
                burst.style.fontSize = rand(1.5, 3) + 'rem';
                burst.style.pointerEvents = 'none';
                burst.style.zIndex = '200';
                burst.style.opacity = '1';
                burst.style.transition = 'all 1.5s cubic-bezier(0.2, 0.8, 0.3, 1)';
                burst.style.textShadow = '0 0 20px #ff3366, 0 0 40px #ff0066';
                document.body.appendChild(burst);

                requestAnimationFrame(() => {
                    burst.style.transform = `translate(${rand(-80, 80)}px, ${rand(-160, -80)}px) scale(0.3) rotate(${rand(-40, 40)}deg)`;
                    burst.style.opacity = '0';
                });

                setTimeout(() => {
                    burst.remove();
                }, 1600);
            }

            // ========== 5. 页面标题轮换（含彭皓轩专属） ==========
            const titleMessages = [
                '张锦宝宝 · 我爱你 · 彭皓轩专属',
                '张锦宝宝 · 一生一世 · 彭皓轩专属',
                '张锦宝宝 · 彭皓轩心里只有你',
                '张锦宝宝 · 彭皓轩唯一的偏爱',
                '张锦宝宝 · 彭皓轩爱你 1314',
                '张锦宝宝 · 彭皓轩心动是你 白首也是你',
                '张锦宝宝 · 彭皓轩今天也很爱你',
                '张锦宝宝 · 彭皓轩的全部浪漫'
            ];
            let titleIndex = 0;
            setInterval(() => {
                titleIndex = (titleIndex + 1) % titleMessages.length;
                document.title = titleMessages[titleIndex];
            }, 3500);

            // ========== 6. 爱心跟随鼠标（桌面端） ==========
            if (window.innerWidth > 900) {
                let lastX = 0, lastY = 0;
                document.addEventListener('mousemove', function(e) {
                    const dx = e.clientX - lastX;
                    const dy = e.clientY - lastY;
                    if (Math.abs(dx) > 60 || Math.abs(dy) > 60) {
                        lastX = e.clientX;
                        lastY = e.clientY;

                        const trail = document.createElement('div');
                        trail.textContent = Math.random() > 0.85 ? '👑' : '❤️';
                        trail.style.position = 'fixed';
                        trail.style.left = e.clientX + 'px';
                        trail.style.top = e.clientY + 'px';
                        trail.style.fontSize = rand(0.8, 1.6) + 'rem';
                        trail.style.pointerEvents = 'none';
                        trail.style.zIndex = '50';
                        trail.style.opacity = '0.8';
                        trail.style.transition = 'all 1.2s ease-out';
                        trail.style.textShadow = '0 0 15px #ff3366';
                        document.body.appendChild(trail);

                        requestAnimationFrame(() => {
                            trail.style.transform = `translate(${rand(-50, 50)}px, ${rand(-100, -40)}px) scale(0.5)`;
                            trail.style.opacity = '0';
                        });

                        setTimeout(() => trail.remove(), 1300);
                    }
                });
            }
        })();
    </script>
</body>
</html>
