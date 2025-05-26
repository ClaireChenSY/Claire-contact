<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>通訊錄表單</title>
    <style>
        /* 基本樣式重設 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Helvetica Neue', Arial, sans-serif; /* 使用現代、易讀的字體 */
            background-color: #f0f2f5; /* 淺灰色背景，更柔和 */
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh; /* 確保表單在小螢幕也能垂直置中 */
            padding: 20px; /* 在小螢幕時給予邊距 */
        }

        .form-container {
            background-color: #ffffff; /* 白色表單背景 */
            padding: 30px 40px; /* 增加內邊距 */
            border-radius: 12px; /* 更大的圓角 */
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1); /* 更明顯的陰影效果 */
            width: 100%;
            max-width: 550px; /* 稍微加寬表單 */
        }

        .form-container h2 {
            text-align: center;
            color: #1c1e21; /* 深色標題，Facebook風格 */
            margin-bottom: 25px;
            font-size: 24px; /* 標題字體大小 */
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #4b4f56; /* 標籤顏色 */
            font-weight: 600; /* 標籤字體加粗 */
            font-size: 14px;
        }

        .form-group input[type="text"],
        .form-group input[type="email"],
        .form-group input[type="tel"],
        .form-group textarea {
            width: 100%;
            padding: 12px 15px; /* 調整輸入框內邊距 */
            border: 1px solid #ccd0d5; /* 輸入框邊框顏色 */
            border-radius: 6px; /* 輸入框圓角 */
            font-size: 16px;
            color: #1c1e21; /* 輸入文字顏色 */
            transition: border-color 0.2s ease-in-out, box-shadow 0.2s ease-in-out; /* 過渡效果 */
        }

        .form-group input[type="text"]::placeholder,
        .form-group input[type="email"]::placeholder,
        .form-group input[type="tel"]::placeholder,
        .form-group textarea::placeholder {
            color: #8a8d91; /* 預留位置文字顏色 */
        }

        .form-group input[type="text"]:focus,
        .form-group input[type="email"]:focus,
        .form-group input[type="tel"]:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #1877f2; /* Facebook 藍色 */
            box-shadow: 0 0 0 2px rgba(24, 119, 242, 0.2); /* 焦點時的外陰影 */
        }

        .form-group textarea {
            resize: vertical; /* 允許垂直調整大小 */
            min-height: 100px; /* 文字區域最小高度 */
        }

        .submit-button {
            background-color: #1877f2; /* Facebook 藍色 */
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 17px; /* 按鈕字體大小 */
            font-weight: 600; /* 按鈕字體加粗 */
            width: 100%;
            transition: background-color 0.2s ease-in-out;
            margin-top: 10px; /* 與上方欄位間距 */
        }

        .submit-button:hover {
            background-color: #166fe5; /* 滑鼠懸停時的顏色 */
        }

        /* 響應式調整 */
        @media (max-width: 600px) {
            .form-container {
                padding: 20px 25px;
            }
            .form-container h2 {
                font-size: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>📝 通訊錄資料</h2>
        <form id="contactForm" action="#" method="POST">
            <div class="form-group">
                <label for="name">姓名:</label>
                <input type="text" id="name" name="name" placeholder="請輸入您的全名" required>
            </div>

            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" placeholder="例如：example@email.com" required>
            </div>

            <div class="form-group">
                <label for="phone">電話:</label>
                <input type="tel" id="phone" name="phone" placeholder="例如：0912-345-678">
            </div>

            <div class="form-group">
                <label for="company">公司:</label>
                <input type="text" id="company" name="company" placeholder="請輸入公司名稱">
            </div>

            <div class="form-group">
                <label for="notes">備註:</label>
                <textarea id="notes" name="notes" rows="4" placeholder="可輸入其他相關資訊..."></textarea>
            </div>

            <button type="submit" class="submit-button">提交資料</button>
        </form>
    </div>

    <script>
        // 您可以在這裡添加 JavaScript 來處理表單提交，例如 AJAX請求或更複雜的客戶端驗證
        // 例如，在提交時顯示一個訊息：
        const contactForm = document.getElementById('contactForm');
        if (contactForm) {
            contactForm.addEventListener('submit', function(event) {
                // 阻止表單的默認提交行為，以便進行自訂處理或顯示訊息
                // event.preventDefault(); // 如果您想用 JavaScript 處理提交，請取消註解此行

                // 簡單的提交成功訊息 (實際應用中，這應該在成功將數據發送到伺服器後顯示)
                // alert('表單已提交！'); // 避免使用 alert，這裡僅為示例

                // 這裡可以添加將數據發送到後端的邏輯
                console.log('表單準備提交...');
                // const formData = new FormData(contactForm);
                // for (let [key, value] of formData.entries()) {
                //     console.log(key, value);
                // }
            });
        }
    </script>
</body>
</html>
