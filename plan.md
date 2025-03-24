FRONT END (Thịnh, Hưng, Nhật, Thư)
Làm web 
Hiển thị bản đồ 
Cập nhật  vị trí của người theo dõi 
Thêm tính năng cho bản đồ (zoom, di chuyển bản đồ , chọn một điểm trên bản đồ, hiển thị quãng đường,...)
Thêm tính năng đăng nhập và đăng ký 
Cho phép web hiển thị thông báo 
Giao diện người dùng thân thiện dễ sử dụng 
Debug



BACK END (Nhân, Lan, Khang, Khả)
Cung cấp API cho front end
Định vị và thông báo
Tích hơp, phân tích bản đồ
Thu thập vị trí tọa độ của người bị theo dõi
Xử lý dữ liệu tọa độ
Quản lý hệ thống
Debug






first take
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Help Center & Registration</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #121212;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        /* Header Section */
        header {
            background-color: #333;
            width: 100%;
            padding: 20px;
            text-align: center;
        }

        header h1 {
            color: #ffffff;
            font-size: 2.5rem;
            margin: 0;
        }

        /* Main Container */
        .main-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            width: 100%;
            max-width: 1200px;
            padding: 20px;
            gap: 40px;
            background-color: #121212;
        }

        /* Registration Section */
        .container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            width: 320px;
            text-align: center;
            animation: fadeIn 1s ease-in-out;
        }

        h2 {
            margin-bottom: 15px;
            color: #333;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 8px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            transition: 0.3s ease-in-out;
            display: block;
        }

        input:focus {
            border-color: #FFC0CB;
            outline: none;
            box-shadow: 0 0 8px rgba(76, 175, 80, 0.5);
        }

        button {
            width: 100%;
            padding: 10px;
            border: none;
            background: linear-gradient(115deg, #FFC0CB, #2196F3);
            color: white;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
            margin-top: 10px;
        }

        button:hover {
            background: linear-gradient(115deg, #45A049, #1E88E5);
            transform: scale(1.05);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Help Center Section */
        .categories {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }

        .category {
            background: #1e1e1e;
            padding: 15px 20px;
            border-radius: 10px;
            transition: 0.3s;
            width: 150px;
            text-align: center;
        }

        .category:hover {
            background: #292929;
        }

        .category img {
            width: 40px;
            height: auto;
        }

        .category h3 {
            margin-top: 10px;
            font-size: 1rem;
            font-weight: bold;
        }

        .category p {
            font-size: 0.8rem;
            color: #bbbbbb;
        }

        footer {
            padding: 20px;
            background: #1e1e1e;
            margin-top: 20px;
            font-size: 0.9rem;
            color: #bbbbbb;
        }

        /* Mobile Responsive Fix */
        @media (max-width: 600px) {
            .categories {
                flex-direction: column;
                align-items: center;
            }
            .category {
                width: 80%;
            }
        }
    </style>
</head>
<body>

    <!-- Welcome Banner -->
    <header>
        <h1>Welcome to Geo-Guard Help Center</h1>
    </header>

    <div class="main-container">
        <!-- Registration Section -->
        <div class="container">
            <h2>Register in Geo-Guard</h2>
            <form onsubmit="return validateForm()">
                <input type="text" id="handle" name="handle" required placeholder="Username">
                
                <input type="password" id="password" name="password" required minlength="5" placeholder="Password">
                
                <input type="password" id="confirm-password" name="confirm-password" required placeholder="Confirm Password">
                
                <p id="password-error" style="font-size: 0.8rem; color: red;"></p>

                <button type="submit">Register</button>
            </form>
        </div>

        <!-- Help Center Section -->
        <section class="categories">
            <div class="category">
                <img src="https://cdn-icons-png.flaticon.com/512/2972/2972498.png" alt="Account">
                <h3>Account & Security</h3>
                <p>Manage your account, passwords, and privacy settings.</p>
            </div>

            <div class="category">
                <img src="https://cdn-icons-png.flaticon.com/512/3474/3474001.png" alt="Orders">
                <h3>Orders & Billing</h3>
                <p>Track orders, request refunds, and update payment info.</p>
            </div>

            <div class="category">
                <img src="https://cdn-icons-png.flaticon.com/512/2919/2919592.png" alt="Devices">
                <h3>Devices & Services</h3>
                <p>Get help with your products and subscriptions.</p>
            </div>

            <div class="category">
                <img src="https://cdn-icons-png.flaticon.com/512/2331/2331942.png" alt="Support">
                <h3>Contact Support</h3>
                <p>Chat with our team or get in touch via email.</p>
            </div>
        </section>
    </div>

    <footer>
        &copy; 2025 Geo-guard. All rights reserved.
    </footer>

    <script>
        function validateForm() {
            let password = document.getElementById("password").value;
            let confirmPassword = document.getElementById("confirm-password").value;
            let errorText = document.getElementById("password-error");

            if (password !== confirmPassword) {
                errorText.textContent = "Passwords do not match!";
                errorText.style.color = "red";
                return false;
            }
            return true;
        }

        document.getElementById("confirm-password").addEventListener("input", function () {
            let password = document.getElementById("password").value;
            let confirmPassword = this.value;
            let errorText = document.getElementById("password-error");

            if (password !== confirmPassword) {
                errorText.textContent = "Passwords do not match!";
                errorText.style.color = "red";
            } else {
                errorText.textContent = "";
            }
        });
    </script>

</body>
</html>
