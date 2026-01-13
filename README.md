<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>特别生日祝福</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial Rounded MT Bold', 'Helvetica Rounded', Arial, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }
        
        .container {
            width: 90%;
            max-width: 500px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            padding: 30px;
            text-align: center;
            position: relative;
            z-index: 10;
            transition: transform 0.5s ease;
        }
        
        .container:hover {
            transform: translateY(-5px);
        }
        
        .password-section {
            transition: all 0.5s ease;
        }
        
        .message-section {
            display: none;
            opacity: 0;
            transition: opacity 1s ease;
        }
        
        h1 {
            color: #ff6b6b;
            margin-bottom: 20px;
            font-size: 2.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        p {
            color: #555;
            margin-bottom: 25px;
            font-size: 1.1rem;
            line-height: 1.6;
        }
        
        .password-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .input-group {
            position: relative;
        }
        
        input[type="password"] {
            width: 100%;
            padding: 15px 20px;
            border: 2px solid #ffd3b6;
            border-radius: 50px;
            font-size: 1.1rem;
            outline: none;
            transition: all 0.3s ease;
        }
        
        input[type="password"]:focus {
            border-color: #ffaaa5;
            box-shadow: 0 0 10px rgba(255, 170, 165, 0.5);
        }
        
        button {
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            letter-spacing: 1px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
            background: linear-gradient(to right, #ff7b7f, #f8c0b0);
        }
        
        .error-message {
            color: #ff6b6b;
            height: 20px;
            margin-top: 10px;
            font-weight: bold;
        }
        
        .message-content {
            animation: fadeIn 1s ease forwards;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .birthday-cake {
            width: 150px;
            margin: 20px auto;
            position: relative;
        }
        
        .cake {
            width: 120px;
            height: 60px;
            background: linear-gradient(#f8c0b0, #ffaaa5);
            border-radius: 10px 10px 0 0;
            margin: 0 auto;
            position: relative;
        }
        
        .icing {
            width: 140px;
            height: 20px;
            background: #ffd3b6;
            border-radius: 50%;
            position: absolute;
            top: -10px;
            left: -10px;
        }
        
        .candle {
            width: 10px;
            height: 40px;
            background: #ff9a9e;
            position: absolute;
            top: -50px;
            left: 55px;
            border-radius: 5px 5px 0 0;
        }
        
        .flame {
            width: 15px;
            height: 25px;
            background: #ffde59;
            border-radius: 50% 50% 20% 20%;
            position: absolute;
            top: -75px;
            left: 52.5px;
            animation: flicker 1s infinite alternate;
            box-shadow: 0 0 15px #ffde59;
        }
        
        @keyframes flicker {
            0% { transform: scale(1); opacity: 0.9; }
            100% { transform: scale(1.1); opacity: 1; }
        }
        
        .balloon {
            position: absolute;
            width: 50px;
            height: 60px;
            border-radius: 50%;
            z-index: 1;
        }
        
        .balloon:before {
            content: "";
            position: absolute;
            bottom: -20px;
            left: 25px;
            height: 30px;
            width: 2px;
            background: rgba(0, 0, 0, 0.2);
        }
        
        .balloon:nth-child(1) {
            background: radial-gradient(circle at 30% 30%, #ff9a9e, #ff6b6b);
            top: 10%;
            left: 10%;
            animation: float 8s infinite ease-in-out;
        }
        
        .balloon:nth-child(2) {
            background: radial-gradient(circle at 30% 30%, #ffde59, #ffb347);
            top: 15%;
            right: 15%;
            animation: float 10s infinite ease-in-out;
        }
        
        .balloon:nth-child(3) {
            background: radial-gradient(circle at 30% 30%, #a7e9af, #66bb6a);
            bottom: 10%;
            left: 20%;
            animation: float 12s infinite ease-in-out;
        }
        
        .balloon:nth-child(4) {
            background: radial-gradient(circle at 30% 30%, #a8dadc, #457b9d);
            bottom: 15%;
            right: 10%;
            animation: float 9s infinite ease-in-out;
        }
        
        @keyframes float {
            0% { transform: translateY(0) rotate(0); }
            50% { transform: translateY(-20px) rotate(5deg); }
            100% { transform: translateY(0) rotate(0); }
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #ffde59;
            opacity: 0;
        }
        
        .heart {
            position: absolute;
            font-size: 2rem;
            color: #ff6b6b;
            opacity: 0;
            z-index: 0;
        }
        
        .footer-note {
            margin-top: 20px;
            color: #888;
            font-size: 0.9rem;
        }
        
        @media (max-width: 600px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- 背景装饰元素 -->
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    
    <div class="container">
        <div class="password-section" id="passwordSection">
            <h1>🎂 特别生日祝福 🎂</h1>
            <p>请输入密码查看专门为你准备的生日惊喜！</p>
            <p><small>提示：密码是你的生日日期（8位数字，例如：20231126）</small></p>
            
            <div class="password-form">
                <div class="input-group">
                    <input type="password" id="passwordInput" placeholder="请输入密码..." autocomplete="off">
                </div>
                <div class="error-message" id="errorMessage"></div>
                <button id="submitBtn">解锁祝福</button>
            </div>
            
            <p class="footer-note">仅限寿星本人查看</p>
        </div>
        
        <div class="message-section" id="messageSection">
            <div class="message-content">
                <h1>🎉 生日快乐呀！ 🎉</h1>
                
                <div class="birthday-cake">
                    <div class="flame"></div>
                    <div class="candle"></div>
                    <div class="icing"></div>
                    <div class="cake"></div>
                </div>
                
                <p>亲爱的！</p>
                <p>在这特别的日子里，愿你被幸福和快乐包围！</p>
                <p>愿你的每一天都如阳光般灿烂，</p>
                <p>愿你的每个梦想都如星辰般闪耀！</p>
                <p>新的一岁，新的开始，</p>
                <p>愿所有的美好都如期而至！</p>
                
                <div class="birthday-wish">
                    <p>🎈 永远年轻，永远热泪盈眶 🎈</p>
                    <p>✨ 愿你拥有最美好的一年！ ✨</p>
                </div>
                
                <p class="footer-note">这份祝福专属于你，再次祝你生日快乐！</p>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const passwordSection = document.getElementById('passwordSection');
            const messageSection = document.getElementById('messageSection');
            const passwordInput = document.getElementById('passwordInput');
            const submitBtn = document.getElementById('submitBtn');
            const errorMessage = document.getElementById('errorMessage');
            
            // 正确的密码 - 这里设置为20231126（可以根据需要修改）
            const correctPassword = '20070209';
            
            submitBtn.addEventListener('click', function() {
                const enteredPassword = passwordInput.value.trim();
                
                if (enteredPassword === correctPassword) {
                    // 密码正确，显示祝福
                    passwordSection.style.display = 'none';
                    messageSection.style.display = 'block';
                    
                    // 淡入效果
                    setTimeout(() => {
                        messageSection.style.opacity = '1';
                        createHearts();
                        createConfetti();
                    }, 100);
                    
                } else {
                    // 密码错误
                    errorMessage.textContent = '密码错误，请再试一次！';
                    passwordInput.value = '';
                    passwordInput.focus();
                    
                    // 添加错误动画
                    passwordInput.style.animation = 'shake 0.5s';
                    setTimeout(() => {
                        passwordInput.style.animation = '';
                    }, 500);
                }
            });
            
            // 添加键盘事件支持
            passwordInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    submitBtn.click();
                }
            });
            
            // 创建漂浮爱心效果
            function createHearts() {
                const container = document.querySelector('.container');
                for (let i = 0; i < 20; i++) {
                    const heart = document.createElement('div');
                    heart.classList.add('heart');
                    heart.innerHTML = '❤️';
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.top = Math.random() * 100 + '%';
                    heart.style.animation = `floatHeart ${5 + Math.random() * 5}s infinite`;
                    container.appendChild(heart);
                    
                    // 淡入效果
                    setTimeout(() => {
                        heart.style.opacity = '0.7';
                    }, i * 100);
                }
                
                // 添加爱心动画
                const style = document.createElement('style');
                style.innerHTML = `
                    @keyframes floatHeart {
                        0% { transform: translateY(0) translateX(0) rotate(0); opacity: 0.7; }
                        50% { transform: translateY(-30px) translateX(${Math.random() > 0.5 ? 20 : -20}px) rotate(${Math.random() > 0.5 ? 20 : -20}deg); opacity: 1; }
                        100% { transform: translateY(-60px) translateX(0) rotate(0); opacity: 0; }
                    }
                `;
                document.head.appendChild(style);
            }
            
            // 创建五彩纸屑效果
            function createConfetti() {
                const colors = ['#ff9a9e', '#ffde59', '#a7e9af', '#a8dadc', '#ffb347'];
                
                for (let i = 0; i < 150; i++) {
                    const confetti = document.createElement('div');
                    confetti.classList.add('confetti');
                    confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                    confetti.style.left = Math.random() * 100 + 'vw';
                    confetti.style.top = '-10px';
                    confetti.style.opacity = '0.8';
                    confetti.style.transform = `rotate(${Math.random() * 360}deg)`;
                    document.body.appendChild(confetti);
                    
                    // 动画设置
                    const animation = confetti.animate([
                        { transform: `translateY(0) translateX(${Math.random() * 20 - 10}px) rotate(0deg)`, opacity: 0.8 },
                        { transform: `translateY(${window.innerHeight}px) translateX(${Math.random() * 100 - 50}px) rotate(${Math.random() * 360}deg)`, opacity: 0 }
                    ], {
                        duration: 3000 + Math.random() * 3000,
                        easing: 'cubic-bezier(0.1, 0.8, 0.2, 1)'
                    });
                    
                    // 动画结束后移除元素
                    animation.onfinish = () => {
                        confetti.remove();
                    };
                }
            }
        });
    </script>
</body>
</html>
