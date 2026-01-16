<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>📄 文档之光：我们的2025高光时刻</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Microsoft YaHei', 'PingFang SC', sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            min-height: 100vh;
            color: #fff;
            overflow-x: hidden;
        }

        /* 星星背景 */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 0;
        }

        .star {
            position: absolute;
            width: 3px;
            height: 3px;
            background: #fff;
            border-radius: 50%;
            animation: twinkle 2s infinite ease-in-out;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }

        /* 主容器 */
        .container {
            position: relative;
            z-index: 1;
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* 头部区域 */
        .header {
            text-align: center;
            margin-bottom: 50px;
            animation: fadeInDown 1s ease-out;
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .header-icon {
            font-size: 80px;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
            display: inline-block;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .header h1 {
            font-size: 2.8em;
            background: linear-gradient(90deg, #ffd700, #ff6b6b, #4ecdc4, #ffd700);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientMove 3s ease infinite;
            margin-bottom: 15px;
        }

        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .header .subtitle {
            font-size: 1.3em;
            color: #a0a0a0;
            letter-spacing: 3px;
        }

        /* 卡片样式 */
        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 35px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            animation: fadeIn 0.8s ease-out forwards;
            opacity: 0;
        }

        .card:nth-child(1) { animation-delay: 0.2s; }
        .card:nth-child(2) { animation-delay: 0.4s; }
        .card:nth-child(3) { animation-delay: 0.6s; }
        .card:nth-child(4) { animation-delay: 0.8s; }
        .card:nth-child(5) { animation-delay: 1s; }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .card-title {
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.5em;
            margin-bottom: 25px;
            color: #ffd700;
        }

        .card-title .icon {
            font-size: 1.5em;
        }

        /* 活动信息卡片 */
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .info-item {
            background: rgba(255, 255, 255, 0.08);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .info-item:hover {
            background: rgba(255, 255, 255, 0.12);
            transform: scale(1.02);
        }

        .info-item .label {
            font-size: 0.9em;
            color: #888;
            margin-bottom: 8px;
        }

        .info-item .value {
            font-size: 1.2em;
            font-weight: bold;
            color: #4ecdc4;
        }

        /* 目标列表 */
        .goals-list {
            list-style: none;
        }

        .goals-list li {
            padding: 12px 0;
            padding-left: 35px;
            position: relative;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
        }

        .goals-list li:hover {
            padding-left: 40px;
            background: rgba(255, 255, 255, 0.03);
        }

        .goals-list li:last-child {
            border-bottom: none;
        }

        .goals-list li::before {
            content: '✨';
            position: absolute;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
        }

        /* 流程时间线 */
        .timeline {
            position: relative;
            padding-left: 30px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 8px;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(180deg, #ffd700, #ff6b6b, #4ecdc4);
            border-radius: 3px;
        }

        .timeline-item {
            position: relative;
            padding: 20px 25px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            margin-bottom: 20px;
            margin-left: 20px;
            transition: all 0.3s ease;
        }

        .timeline-item:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateX(10px);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -28px;
            top: 28px;
            width: 16px;
            height: 16px;
            background: #ffd700;
            border-radius: 50%;
            border: 3px solid #1a1a2e;
        }

        .timeline-item:nth-child(2)::before { background: #ff6b6b; }
        .timeline-item:nth-child(3)::before { background: #4ecdc4; }
        .timeline-item:nth-child(4)::before { background: #a855f7; }

        .timeline-time {
            display: inline-block;
            background: linear-gradient(135deg, #ffd700, #ff6b6b);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .timeline-title {
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 8px;
            color: #fff;
        }

        .timeline-desc {
            color: #aaa;
            font-size: 0.95em;
            line-height: 1.6;
        }

        /* 互动卡片 */
        .interaction-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .interaction-card {
            padding: 20px 15px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .interaction-card:hover {
            transform: translateY(-8px) scale(1.05);
        }

        .interaction-card.red { background: linear-gradient(135deg, #ff6b6b, #ee5a5a); }
        .interaction-card.blue { background: linear-gradient(135deg, #4ecdc4, #44a3aa); }
        .interaction-card.yellow { background: linear-gradient(135deg, #ffd700, #f0c000); }
        .interaction-card.green { background: linear-gradient(135deg, #95e77a, #7bc962); }

        .interaction-card .card-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .interaction-card .card-name {
            font-weight: bold;
            margin-bottom: 5px;
        }

        .interaction-card .card-desc {
            font-size: 0.85em;
            opacity: 0.9;
        }

        /* 物料准备 */
        .materials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .material-item {
            background: rgba(255, 255, 255, 0.08);
            padding: 20px 15px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .material-item:hover {
            background: rgba(255, 255, 255, 0.15);
            transform: rotate(3deg);
        }

        .material-item .emoji {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .material-item .name {
            font-size: 0.9em;
            color: #ccc;
        }

        /* CTA按钮 */
        .cta-container {
            text-align: center;
            margin-top: 40px;
            animation: fadeIn 1s ease-out 1.2s forwards;
            opacity: 0;
        }

        .cta-button {
            display: inline-block;
            padding: 18px 50px;
            font-size: 1.2em;
            font-weight: bold;
            color: #1a1a2e;
            background: linear-gradient(135deg, #ffd700, #ff6b6b);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.4);
        }

        .cta-button:active {
            transform: translateY(0) scale(0.98);
        }

        /* 底部 */
        .footer {
            text-align: center;
            margin-top: 50px;
            padding: 30px;
            color: #666;
            font-size: 0.9em;
            animation: fadeIn 1s ease-out 1.4s forwards;
            opacity: 0;
        }

        .footer .heart {
            color: #ff6b6b;
            animation: heartbeat 1.5s infinite;
            display: inline-block;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        /* 响应式 */
        @media (max-width: 600px) {
            .header h1 {
                font-size: 2em;
            }
            
            .card {
                padding: 25px 20px;
            }
            
            .timeline-item {
                margin-left: 10px;
            }
        }

        /* 闪光效果 */
        .sparkle {
            position: absolute;
            width: 10px;
            height: 10px;
            background: #ffd700;
            border-radius: 50%;
            pointer-events: none;
            animation: sparkleAnim 1s ease-out forwards;
        }

        @keyframes sparkleAnim {
            0% { transform: scale(0); opacity: 1; }
            100% { transform: scale(2); opacity: 0; }
        }
    </style>
</head>
<body>
    <!-- 星星背景 -->
    <div class="stars" id="stars"></div>

    <div class="container">
        <!-- 头部 -->
        <header class="header">
            <div class="header-icon">📄✨</div>
            <h1>文档之光</h1>
            <p class="subtitle">我们的2025高光时刻</p>
        </header>

        <!-- 活动信息 -->
        <div class="card">
            <h2 class="card-title"><span class="icon">📅</span> 活动信息</h2>
            <div class="info-grid">
                <div class="info-item">
                    <div class="label">📆 日期</div>
                    <div class="value">2026年1月31日</div>
                </div>
                <div class="info-item">
                    <div class="label">⏰ 时间</div>
                    <div class="value">9:30 - 12:00</div>
                </div>
                <div class="info-item">
                    <div class="label">📍 地点</div>
                    <div class="value">F4楼威宇斋</div>
                </div>
                <div class="info-item">
                    <div class="label">👥 参与</div>
                    <div class="value">产品信息设计组</div>
                </div>
            </div>
        </div>

        <!-- 活动目标 -->
        <div class="card">
            <h2 class="card-title"><span class="icon">🎯</span> 活动目标</h2>
            <ul class="goals-list">
                <li><strong>Showcase 成果</strong> - 集中展示各小组/业务线在2025年的技术亮点和优秀实践</li>
                <li><strong>激发灵感</strong> - 促进跨团队学习，激发对新技术的兴趣和应用热情</li>
                <li><strong>规划未来</strong> - 引导大家思考并将他人亮点转化为自己明年的具体行动计划</li>
                <li><strong>增强凝聚</strong> - 在轻松愉快的氛围中加强团队内部的交流与联系</li>
            </ul>
        </div>

        <!-- 活动流程 -->
        <div class="card">
            <h2 class="card-title"><span class="icon">🚀</span> 活动流程</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <span class="timeline-time">9:30 - 9:40</span>
                    <h3 class="timeline-title">🌟 第一环节：破冰启航 - "闪光灯准备！"</h3>
                    <p class="timeline-desc">主持人开场介绍活动主题和目标，宣布今天是一场"成果博览会"和"创意集市"，介绍"亮点卡片"和"行动计划卡"的使用方法。</p>
                </div>
                <div class="timeline-item">
                    <span class="timeline-time">9:40 - 11:00</span>
                    <h3 class="timeline-title">💎 第二环节：高光分享 - "我的闪光时刻"</h3>
                    <p class="timeline-desc">每个小组派2名代表进行8分钟闪电演讲，分享"我们做了什么？"、"为什么这么做？"、"效果如何？"以及"你最喜欢/最得意的部分是什么？"</p>
                </div>
                <div class="timeline-item">
                    <span class="timeline-time">11:00 - 11:40</span>
                    <h3 class="timeline-title">🔥 第三环节：火花碰撞 - "明年，我也要亮起来！"</h3>
                    <p class="timeline-desc">小组讨论+填写"2026我的闪光行动计划卡"，将灵感转化为具体可落地的明年计划，并在"2026愿望墙"展示。</p>
                </div>
                <div class="timeline-item">
                    <span class="timeline-time">11:40 - 12:00</span>
                    <h3 class="timeline-title">🏆 第四环节：颁奖与展望 - "我们都是追光者"</h3>
                    <p class="timeline-desc">趣味颁奖（最具技术突破奖、最佳用户体验奖、最受欢迎分享奖、降本之王），领导总结，大合影留念。</p>
                </div>
            </div>
        </div>

        <!-- 互动卡片说明 -->
        <div class="card">
            <h2 class="card-title"><span class="icon">🎨</span> 亮点卡片互动</h2>
            <p style="color: #aaa; margin-bottom: 20px;">在听分享时，如果对某个点特别感兴趣或赞赏，可以投出你的亮点卡片！</p>
            <div class="interaction-cards">
                <div class="interaction-card red">
                    <div class="card-icon">💻</div>
                    <div class="card-name">红色卡片</div>
                    <div class="card-desc">技术超赞</div>
                </div>
                <div class="interaction-card blue">
                    <div class="card-icon">🎨</div>
                    <div class="card-name">蓝色卡片</div>
                    <div class="card-desc">用户体验棒</div>
                </div>
                <div class="interaction-card yellow">
                    <div class="card-icon">🙋</div>
                    <div class="card-name">黄色卡片</div>
                    <div class="card-desc">我想试试</div>
                </div>
                <div class="interaction-card green">
                    <div class="card-icon">💰</div>
                    <div class="card-name">绿色卡片</div>
                    <div class="card-desc">省钱小能手</div>
                </div>
            </div>
        </div>

        <!-- 物料准备 -->
        <div class="card">
            <h2 class="card-title"><span class="icon">🎁</span> 会前准备与物料</h2>
            <div class="materials-grid">
                <div class="material-item">
                    <div class="emoji">📝</div>
                    <div class="name">邀请函</div>
                </div>
                <div class="material-item">
                    <div class="emoji">🖊️</div>
                    <div class="name">彩色便签纸</div>
                </div>
                <div class="material-item">
                    <div class="emoji">🖌️</div>
                    <div class="name">马克笔</div>
                </div>
                <div class="material-item">
                    <div class="emoji">📇</div>
                    <div class="name">亮点卡片</div>
                </div>
                <div class="material-item">
                    <div class="emoji">📋</div>
                    <div class="name">行动计划卡</div>
                </div>
                <div class="material-item">
                    <div class="emoji">📸</div>
                    <div class="name">拍照手举牌</div>
                </div>
                <div class="material-item">
                    <div class="emoji">🖼️</div>
                    <div class="name">星光墙</div>
                </div>
                <div class="material-item">
                    <div class="emoji">🎯</div>
                    <div class="name">2026愿望墙</div>
                </div>
            </div>
        </div>

        <!-- CTA按钮 -->
        <div class="cta-container">
            <button class="cta-button" onclick="createSparkles(event)">
                🎉 期待与您相见！
            </button>
        </div>

        <!-- 底部 -->
        <footer class="footer">
            <p>让我们一起追光而行，成为更好的自己！</p>
            <p style="margin-top: 10px;">
                用心做事，用爱发电 <span class="heart">❤️</span>
            </p>
        </footer>
    </div>

    <script>
        // 创建星星背景
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const numberOfStars = 100;

            for (let i = 0; i < numberOfStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 2 + 's';
                star.style.animationDuration = (Math.random() * 2 + 1) + 's';
                starsContainer.appendChild(star);
            }
        }

        // 闪光效果
        function createSparkles(event) {
            const button = event.target;
            const rect = button.getBoundingClientRect();
            const x = rect.left + rect.width / 2;
            const y = rect.top + rect.height / 2;

            for (let i = 0; i < 20; i++) {
                const sparkle = document.createElement('div');
                sparkle.className = 'sparkle';
                sparkle.style.left = x + 'px';
                sparkle.style.top = y + 'px';
                sparkle.style.background = ['#ffd700', '#ff6b6b', '#4ecdc4', '#a855f7'][Math.floor(Math.random() * 4)];
                document.body.appendChild(sparkle);

                const angle = (Math.PI * 2 * i) / 20;
                const velocity = 50 + Math.random() * 50;
                const tx = Math.cos(angle) * velocity;
                const ty = Math.sin(angle) * velocity;

                sparkle.animate([
                    { transform: 'translate(0, 0) scale(1)', opacity: 1 },
                    { transform: `translate(${tx}px, ${ty}px) scale(0)`, opacity: 0 }
                ], {
                    duration: 1000,
                    easing: 'ease-out'
                }).onfinish = () => sparkle.remove();
            }

            // 按钮点击反馈
            button.textContent = '✨ 已收到你的光芒！ ✨';
            button.style.background = 'linear-gradient(135deg, #4ecdc4, #44a3aa)';
            
            setTimeout(() => {
                button.textContent = '🎉 期待与您相见！';
                button.style.background = 'linear-gradient(135deg, #ffd700, #ff6b6b)';
            }, 2000);
        }

        // 初始化
        createStars();

        // 卡片点击效果
        document.querySelectorAll('.interaction-card').forEach(card => {
            card.addEventListener('click', function(e) {
                const rect = this.getBoundingClientRect();
                const x = rect.left + rect.width / 2;
                const y = rect.top + rect.height / 2;

                for (let i = 0; i < 10; i++) {
                    const sparkle = document.createElement('div');
                    sparkle.className = 'sparkle';
                    sparkle.style.left = x + 'px';
                    sparkle.style.top = y + 'px';
                    document.body.appendChild(sparkle);

                    const angle = Math.random() * Math.PI * 2;
                    const velocity = 30 + Math.random() * 30;
                    const tx = Math.cos(angle) * velocity;
                    const ty = Math.sin(angle) * velocity;

                    sparkle.animate([
                        { transform: 'translate(0, 0) scale(1)', opacity: 1 },
                        { transform: `translate(${tx}px, ${ty}px) scale(0)`, opacity: 0 }
                    ], {
                        duration: 600,
                        easing: 'ease-out'
                    }).onfinish = () => sparkle.remove();
                }
            });
        });

        // 滚动动画
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.card').forEach(card => {
            observer.observe(card);
        });
    </script>
</body>
</html>
