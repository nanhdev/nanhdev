<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Le Ngoc Anh - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: fadeIn 1s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .wave {
            display: inline-block;
            animation: wave 2s infinite;
            font-size: 3em;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-20deg); }
        }

        h1 {
            font-size: 3em;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 20px 0;
            animation: slideIn 1s ease-out;
        }

        @keyframes slideIn {
            from { transform: translateX(-100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        .subtitle {
            color: #666;
            font-size: 1.2em;
            font-style: italic;
        }

        .profile-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin: 40px 0;
        }

        .info-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .info-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }

        .info-card h2 {
            color: #667eea;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .info-item {
            margin: 15px 0;
            padding: 10px;
            background: white;
            border-radius: 8px;
            transition: background 0.3s ease;
        }

        .info-item:hover {
            background: #f0f0f0;
        }

        .info-label {
            font-weight: bold;
            color: #764ba2;
            display: inline-block;
            min-width: 120px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .social-btn {
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            color: white;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .social-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .social-btn span {
            position: relative;
            z-index: 1;
        }

        .github { background: linear-gradient(135deg, #24292e, #000); }
        .twitter { background: linear-gradient(135deg, #1DA1F2, #0d8bd9); }
        .linkedin { background: linear-gradient(135deg, #0077b5, #005582); }
        .email { background: linear-gradient(135deg, #ea4335, #c5221f); }
        .facebook { background: linear-gradient(135deg, #1877f2, #0d5dbf); }

        .social-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        .skills-section {
            margin: 40px 0;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .skill-badge {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            font-weight: bold;
            transition: all 0.3s ease;
            cursor: pointer;
            animation: fadeInUp 0.5s ease-out backwards;
        }

        .skill-badge:nth-child(1) { animation-delay: 0.1s; }
        .skill-badge:nth-child(2) { animation-delay: 0.2s; }
        .skill-badge:nth-child(3) { animation-delay: 0.3s; }
        .skill-badge:nth-child(4) { animation-delay: 0.4s; }
        .skill-badge:nth-child(5) { animation-delay: 0.5s; }
        .skill-badge:nth-child(6) { animation-delay: 0.6s; }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .skill-badge:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.5);
        }

        .stats-section {
            text-align: center;
            margin: 40px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .stat-card {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            display: block;
        }

        .stat-label {
            font-size: 1em;
            opacity: 0.9;
        }

        .interests {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin: 20px 0;
        }

        .interest-tag {
            background: white;
            padding: 10px 20px;
            border-radius: 25px;
            border: 2px solid #667eea;
            color: #667eea;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .interest-tag:hover {
            background: #667eea;
            color: white;
            transform: scale(1.1);
        }

        .quote {
            text-align: center;
            font-style: italic;
            font-size: 1.2em;
            color: #666;
            margin: 40px 0;
            padding: 20px;
            border-left: 4px solid #667eea;
            background: #f5f7fa;
            border-radius: 10px;
        }

        @media (max-width: 768px) {
            .profile-section {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2em;
            }
            
            .container {
                padding: 20px;
            }
        }

        .typing-effect {
            display: inline-block;
            border-right: 3px solid #667eea;
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 100% { border-color: transparent; }
            50% { border-color: #667eea; }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <span class="wave">👋</span>
            <h1>Xin chào! Tôi là Lê Ngọc Anh</h1>
            <p class="subtitle">💻 <span class="typing-effect">Still learning something...</span></p>
        </div>

        <div class="profile-section">
            <div class="info-card">
                <h2>📋 Thông tin cá nhân</h2>
                <div class="info-item">
                    <span class="info-label">🏷️ Tên:</span>
                    <span>Lê Ngọc Anh (Nanh)</span>
                </div>
                <div class="info-item">
                    <span class="info-label">📍 Từ:</span>
                    <span>Quy Nhơn City</span>
                </div>
                <div class="info-item">
                    <span class="info-label">👤 Đại từ:</span>
                    <span>Nanh - 男</span>
                </div>
                <div class="info-item">
                    <span class="info-label">💼 Công việc:</span>
                    <span>Still Student</span>
                </div>
                <div class="info-item">
                    <span class="info-label">🗣️ Ngôn ngữ:</span>
                    <span>Python - English</span>
                </div>
            </div>

            <div class="info-card">
                <h2>❤️ Sở thích</h2>
                <div class="interests">
                    <span class="interest-tag">💻 Coding</span>
                    <span class="interest-tag">🎌 Anime</span>
                    <span class="interest-tag">🎮 Gaming</span>
                    <span class="interest-tag">📚 Learning</span>
                </div>
                <div class="quote">
                    "The only way to do great work is to love what you do." 🚀
                </div>
            </div>
        </div>

        <div class="skills-section">
            <h2 style="text-align: center; color: #667eea; margin-bottom: 20px;">🛠️ Kỹ năng & Công nghệ</h2>
            <div class="skills-grid">
                <div class="skill-badge">🐍 Python</div>
                <div class="skill-badge">🌐 HTML/CSS</div>
                <div class="skill-badge">⚡ JavaScript</div>
                <div class="skill-badge">📱 React</div>
                <div class="skill-badge">🔥 Firebase</div>
                <div class="skill-badge">🐙 Git/GitHub</div>
            </div>
        </div>

        <div class="stats-section">
            <h2 style="color: #667eea; margin-bottom: 20px;">📊 Thống kê GitHub</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <span class="stat-number">50+</span>
                    <span class="stat-label">Repositories</span>
                </div>
                <div class="stat-card" style="background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);">
                    <span class="stat-number">100+</span>
                    <span class="stat-label">Commits</span>
                </div>
                <div class="stat-card" style="background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);">
                    <span class="stat-number">20+</span>
                    <span class="stat-label">Projects</span>
                </div>
            </div>
        </div>

        <div style="text-align: center; margin: 40px 0;">
            <h2 style="color: #667eea; margin-bottom: 30px;">🌐 Kết nối với tôi</h2>
            <div class="social-links">
                <a href="https://github.com/lenocanh" class="social-btn github" target="_blank">
                    <span>🐙 GitHub</span>
                </a>
                <a href="https://twitter.com/lenocanh" class="social-btn twitter" target="_blank">
                    <span>🐦 Twitter</span>
                </a>
                <a href="https://linkedin.com/in/lenocanh" class="social-btn linkedin" target="_blank">
                    <span>💼 LinkedIn</span>
                </a>
                <a href="https://facebook.com/lenocanh" class="social-btn facebook" target="_blank">
                    <span>📘 Facebook</span>
                </a>
                <a href="mailto:lenocanh@example.com" class="social-btn email">
                    <span>📧 Email</span>
                </a>
            </div>
        </div>

        <div style="text-align: center; padding: 30px; background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%); border-radius: 15px; margin-top: 40px;">
            <p style="font-size: 1.2em; color: #667eea; font-weight: bold;">
                ⭐ "Luôn học hỏi, luôn phát triển" ⭐
            </p>
            <p style="margin-top: 15px; color: #666;">
                Cảm ơn bạn đã ghé thăm profile của tôi! 🙏
            </p>
        </div>
    </div>
</body>
</html>
