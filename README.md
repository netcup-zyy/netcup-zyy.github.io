<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>比赛暂停通知</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Microsoft YaHei', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #2a3c7c);
            color: #fff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            text-align: center;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            padding: 40px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            transform: rotate(45deg);
            animation: shine 8s infinite linear;
        }
        
        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }
        
        .content {
            position: relative;
            z-index: 1;
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            color: #ffcc00;
            text-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
            letter-spacing: 2px;
        }
        
        .message {
            font-size: 1.5rem;
            line-height: 1.6;
            margin-bottom: 30px;
            color: #e0e0ff;
        }
        
        .closed-sign {
            display: inline-block;
            background: #ff3333;
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 1.8rem;
            font-weight: bold;
            margin: 20px 0;
            transform: rotate(-5deg);
            box-shadow: 0 5px 15px rgba(255, 51, 51, 0.4);
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: rotate(-5deg) scale(1); }
            50% { transform: rotate(-5deg) scale(1.05); }
            100% { transform: rotate(-5deg) scale(1); }
        }
        
        .icon {
            font-size: 5rem;
            margin: 30px 0;
            color: #ffcc00;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        .note {
            margin-top: 30px;
            font-size: 1.2rem;
            color: #a0a0ff;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            padding-top: 20px;
        }
        
        .footer {
            margin-top: 40px;
            color: #9090cc;
            font-size: 0.9rem;
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .message {
                font-size: 1.2rem;
            }
            
            .closed-sign {
                font-size: 1.4rem;
                padding: 12px 24px;
            }
            
            .icon {
                font-size: 4rem;
            }
        }
        
        @media (max-width: 480px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .message {
                font-size: 1.1rem;
            }
            
            .closed-sign {
                font-size: 1.2rem;
                padding: 10px 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="content">
            <div class="icon">⏸️</div>
            <h1>比赛暂停通知</h1>
            <div class="message">
                本届比赛已圆满完结，感谢各位的参与和支持！<br>
                请于下届比赛开始前再次访问本页面。
            </div>
            <div class="closed-sign">暂停营业中</div>
            <div class="note">
                我们将于下届比赛开始前重新开放网站功能。<br>
                敬请期待下一届比赛的精彩内容！
            </div>
        </div>
    </div>
    <div class="footer">
        &copy; 2023 比赛组委会 版权所有
    </div>
</body>
</html>
