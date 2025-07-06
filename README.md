<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>爱心互动小游戏</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }
        
.container {
            text-align: center;
        }
        
h1 {
            color: #e74c3c;
            margin-bottom: 30px;
            font-size: 28px;
        }
        
.input-box {
            padding: 12px 20px;
            font-size: 16px;
            border: 2px solid #3498db;
            border-radius: 4px;
            margin-bottom: 20px;
            width: 200px;
            text-align: center;
        }
        
.btn {
            padding: 12px 24px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
.btn:hover {
            background-color: #2980b9;
        }
        
.result {
            margin-top: 30px;
            padding: 20px;
            border-radius: 8px;
            width: 300px;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        
.default-result {
            background-color: #f9f9f9;
            border: 2px dashed #95a5a6;
        }
        
 .special-result {
            background-color: #fff8e1;
            border: 2px solid #ff9800;
        }
        
.heart-container {
            position: relative;
            width: 200px;
            height: 200px;
            margin-bottom: 20px;
            animation: rotate 6s linear infinite;
        }
        
 .heart {
            position: absolute;
            width: 100px;
            height: 90px;
            background-color: #e74c3c;
            border-radius: 100px 100px 0 0;
            transform: rotate(45deg);
            top: 55px;
        }
        
.heart:before, .heart:after {
            content: "";
            position: absolute;
            width: 100px;
            height: 140px;
            background-color: #e74c3c;
            border-radius: 100px 100px 0 0;
        }
        
 .heart:before {
            left: -50px;
            top: -70px;
        }
        
.heart:after {
            left: 0;
            top: -70px;
            transform: rotate(-90deg);
            transform-origin: 100% 100%;
        }
        
.text {
            font-size: 18px;
            color: #333;
            line-height: 1.5;
        }
        
.special-text {
            color: #e65100;
            font-weight: bold;
 }
        
 @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
</style>
</head>
<body>
    <div class="container">
        <h1>爱心互动小游戏</h1>
        <p>输入数字，看看会发生什么~</p >
        
<input type="number" id="numberInput" class="input-box" placeholder="输入数字">
        <button id="checkBtn" class="btn">确认</button>
        
 <div id="result" class="result default-result">
            <p class="text">请输入数字并点击确认</p >
        </div>
    </div>

<script>
        document.addEventListener('DOMContentLoaded', function() {
            const numberInput = document.getElementById('numberInput');
            const checkBtn = document.getElementById('checkBtn');
            const result = document.getElementById('result');
            
            checkBtn.addEventListener('click', function() {
                const number = parseInt(numberInput.value);
                
                if (isNaN(number)) {
                    showDefaultResult("请输入有效的数字哦~ (T＿T)");
                    return;
                }
                
                if (number === 1 || number === 4) {
                    showSpecialResult();
                } else {
                    showDefaultResult("未知(T＿T)");
                }
            });
            
            function showSpecialResult() {
                result.className = "result special-result";
                result.innerHTML = `
                    <div class="heart-container">
                        <div class="heart"></div>
                    </div>
                    <p class="special-text">like you is an art 🎨</p >
                    <p class="special-text">6^u 爱你永无止境 ❤️</p >
                `;
            }
            
            function showDefaultResult(text) {
                result.className = "result default-result";

result.innerHTML = `<p class="text">${text}</p >`;
             }
         });
     </script>
 </body>
 </html>
