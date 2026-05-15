<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YourHub | Professional Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: #050505;
            color: #ffffff;
            overflow-x: hidden; 
            transition: background 0.5s ease;
        }

        /* --- Login Page --- */
        #login-page {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: radial-gradient(circle, #1a1a1a 0%, #000 100%);
        }

        .login-card {
            background: rgba(20, 20, 20, 0.95);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(255, 0, 0, 0.2);
            width: 90%;
            max-width: 380px;
            text-align: center;
            border: 1px solid #333;
            animation: fadeIn 0.8s ease-out;
        }

        .brand-name {
            font-size: 32px;
            font-weight: 600;
            margin-bottom: 5px;
        }

        .brand-name span {
            background: #ff0000; 
            padding: 2px 10px;
            border-radius: 6px;
            margin-left: 5px;
        }

        .input-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .input-group label {
            display: block;
            font-size: 12px;
            color: #aaa;
            margin-bottom: 8px;
        }

        .input-group input {
            width: 100%;
            padding: 14px;
            border-radius: 10px;
            border: 1px solid #444;
            background: #111;
            color: #fff;
            outline: none;
            transition: 0.3s;
        }

        .input-group input:focus {
            border-color: #ff0000;
        }

        .login-btn {
            width: 100%;
            padding: 14px;
            background: #ff0000;
            border: none;
            border-radius: 10px;
            color: #fff;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
            font-size: 16px;
        }

        .login-btn:hover { 
            background: #cc0000;
            transform: scale(1.02);
        }

        /* --- Dashboard --- */
        #main-site { 
            display: none;
            min-height: 100vh;
            background: #0a0a0a;
        }

        nav {
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #111;
            border-bottom: 1px solid #222;
        }

        .services {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            padding: 40px 8%;
        }

        .card {
            background: #161616;
            padding: 40px 30px;
            border-radius: 20px;
            border: 1px solid #222;
            text-align: center;
            transition: 0.4s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .card:hover { 
            border-color: #ff0000; 
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(255, 0, 0, 0.1);
        }

        /* Portfolio Specific Style */
        .project-link {
            display: inline-block;
            margin-top: 15px;
            padding: 10px 20px;
            background: #ff0000;
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-size: 13px;
            font-weight: 600;
            transition: 0.3s;
        }

        .project-link:hover {
            background: #ffffff;
            color: #ff0000;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <!-- 1. Login Section -->
    <div id="login-page">
        <div class="login-card">
            <div class="brand-name">Your<span>Hub</span></div>
            <p style="color: #888; font-size: 11px; letter-spacing: 2px; margin-bottom: 30px;">POWERED BY LAKSHITHA</p>

            <div class="input-group">
                <label>Username</label>
                <input type="text" id="username" placeholder="Username">
            </div>
            <div class="input-group">
                <label>Password</label>
                <input type="password" id="password" placeholder="Password">
            </div>
            <button class="login-btn" id="loginBtn">Console</button>
            
            <p id="error-msg" style="color: #ff4444; font-size: 13px; margin-top: 15px; display: none;">✖ වැරදි දත්ත. නැවත උත්සාහ කරන්න.</p>
        </div>
    </div>

    <!-- 2. Main Dashboard -->
    <div id="main-site">
        <nav>
            <div style="font-weight: 600; color: #ff0000;">YOURHUB // DASHBOARD</div>
            <div style="cursor:pointer; font-size: 13px; color: #888; border: 1px solid #333; padding: 5px 15px; border-radius: 20px;" onclick="location.reload()">Log Out 🔒</div>
        </nav>

        <header style="padding: 60px 20px; text-align: center;">
            <h1>ආයුබෝවන්, ලක්ෂිත 👋</h1>
            <p style="color: #aaa; margin-top: 10px;">ඔබේ නවතම ව්‍යාපෘති සහ පද්ධති පාලක පුවරුව.</p>
        </header>

        <section class="services">
            <!-- Project 1: Senarath Printers (Added by User Request) -->
            <div class="card" style="border: 1px solid rgba(255, 0, 0, 0.4);">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🏪</div>
                    <h3 style="color: #ff0000;">Senarath Printers</h3>
                    <p style="color: #888; font-size: 14px; margin-top: 10px;">මෙය මා විසින් නිර්මාණය කරන ලද සම්පූර්ණ වෙළඳ කළමනාකරණ පද්ධතිය සහ වෙබ් අඩවියයි.</p>
                </div>
                <a href="https://lakshithahub.github.io/senarath-printers-book-shop/" target="_blank" class="project-link">
                    View Project <i class="fas fa-external-link-alt"></i>
                </a>
            </div>

            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">📂</div>
                    <h3>Other Projects</h3>
                    <p style="color: #888; font-size: 14px; margin-top: 10px;">අනෙකුත් POS පද්ධති සහ මෘදුකාංග ව්‍යාපෘති මෙතැනින් බලන්න.</p>
                </div>
                <p style="color: #444; font-size: 12px; margin-top: 15px;">STATUS: ACTIVE</p>
            </div>

            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🗄️</div>
                    <h3>Database Nodes</h3>
                    <p style="color: #888; font-size: 14px; margin-top: 10px;">Cloud දත්ත ගබඩා සහ Backup පද්ධති වල තත්ත්වය පරීක්ෂා කරන්න.</p>
                </div>
                <p style="color: #444; font-size: 12px; margin-top: 15px;">STORAGE: 85% FREE</p>
            </div>
        </section>

        <footer style="text-align: center; padding: 40px; color: #444; font-size: 12px; border-top: 1px solid #1a1a1a;">
            <p>&copy; 2026 YOURHUB | BY LAKSHITHA | +94 76 999 6722</p>
        </footer>
    </div>

    <script>
        const loginBtn = document.getElementById('loginBtn');

        function checkLogin() {
            const u = document.getElementById('username').value;
            const p = document.getElementById('password').value;
            
            if (u === "admin" && p === "1234") {
                document.getElementById('login-page').style.display = 'none';
                document.getElementById('main-site').style.display = 'block';
                document.body.style.background = '#0a0a0a';
            } else {
                document.getElementById('error-msg').style.display = 'block';
            }
        }

        loginBtn.addEventListener('click', checkLogin);

        // Enter key එකෙන් Login වීමට පහසුකම
        document.addEventListener('keypress', function (e) {
            if (e.key === 'Enter') {
                checkLogin();
            }
        });
    </script>
</body>
</html>
