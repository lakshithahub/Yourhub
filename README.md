<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YourHub | Professional Developer</title>
    <!-- Google Fonts භාවිතා කර ඇත -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    
    <style>
        /* --- මූලික සැකසුම් (Basic Setup) --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: #050505; /* පසුබිම් වර්ණය */
            color: #ffffff;
            overflow-x: hidden; 
            transition: background 0.5s ease;
        }

        /* --- Login Page එකේ පෙනුම --- */
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
            box-shadow: 0 10px 40px rgba(255, 0, 0, 0.2); /* රතු පැහැති shadow එක */
            width: 90%;
            max-width: 380px;
            text-align: center;
            border: 1px solid #333;
            animation: fadeIn 0.8s ease-out;
        }

        /* --- ලාංඡනය සහ නම (Brand Name) --- */
        .brand-name {
            font-size: 32px;
            font-weight: 600;
            margin-bottom: 5px;
        }

        /* YourHub හි 'Hub' කොටස රතු පෙට්ටියක් ලෙස */
        .brand-name span {
            background: #ff0000; 
            padding: 2px 10px;
            border-radius: 6px;
            margin-left: 5px;
        }

        /* --- Input Fields (User/Pass) --- */
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
            border-color: #ff0000; /* Click කළ විට රතු පැහැ වේ */
        }

        /* --- Login Button --- */
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

        /* --- Dashboard එකේ පෙනුම (Main Site) --- */
        #main-site { 
            display: none; /* මුලින් මෙය නොපෙනී පවතී */
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

        /* Dashboard එකේ ඇති Cards (Projects, Database etc) */
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
        }

        .card:hover { 
            border-color: #ff0000; 
            transform: translateY(-10px);
        }

        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <!-- 1. ලොගින් පිටුව (Login Section) -->
    <div id="login-page">
        <div class="login-card">
            <div class="brand-name">Your<span>Hub</span></div>
            <p style="color: #888; font-size: 11px; letter-spacing: 2px; margin-bottom: 30px;">POWERED BY LAKSHITHA</p>

            <div class="input-group">
                <label>Username</label>
                <!-- මෙතන id="username" වෙනස් කරන්න එපා -->
                <input type="text" id="username" placeholder="Username එක ඇතුළත් කරන්න">
            </div>
            <div class="input-group">
                <label>Password</label>
                <!-- මෙතන id="password" වෙනස් කරන්න එපා -->
                <input type="password" id="password" placeholder="Password එක ඇතුළත් කරන්න">
            </div>
            <button class="login-btn" id="loginBtn">Console එකට ඇතුල් වන්න</button>
            
            <p id="error-msg" style="color: #ff4444; font-size: 13px; margin-top: 15px; display: none;">✖ වැරදි දත්ත. නැවත උත්සාහ කරන්න.</p>
        </div>
    </div>

    <!-- 2. ප්‍රධාන ඩෑෂ්බෝඩ් එක (Dashboard Section) -->
    <div id="main-site">
        <nav>
            <div style="font-weight: 600; color: #ff0000;">YOURHUB // DASHBOARD</div>
            <div style="cursor:pointer; font-size: 13px; color: #888; border: 1px solid #333; padding: 5px 15px; border-radius: 20px;" onclick="location.reload()">Log Out 🔒</div>
        </nav>

        <header style="padding: 60px 20px; text-align: center;">
            <h1>ආයුබෝවන්, ලක්ෂිත 👋</h1>
            <p style="color: #aaa; margin-top: 10px;">ඔබේ පද්ධති පාලක පුවරුව (Control Panel) වෙත සාදරයෙන් පිළිගනිමු.</p>
        </header>

        <section class="services">
            <!-- පළමු කාඩ්පත: Projects -->
            <div class="card">
                <div style="font-size: 30px;">📂</div>
                <h3>Active Projects</h3>
                <p style="color: #888; font-size: 14px;">ඔබේ POS පද්ධති සහ මෘදුකාංග ව්‍යාපෘති මෙතැනින් පාලනය කරන්න.</p>
            </div>

            <!-- දෙවන කාඩ්පත: Database -->
            <div class="card">
                <div style="font-size: 30px;">🗄️</div>
                <h3>Database Nodes</h3>
                <p style="color: #888; font-size: 14px;">Cloud දත්ත ගබඩා සහ Backup පරීක්ෂා කරන්න.</p>
            </div>

            <!-- තෙවන කාඩ්පත: Analytics -->
            <div class="card">
                <div style="font-size: 30px;">📊</div>
                <h3>System Analytics</h3>
                <p style="color: #888; font-size: 14px;">පද්ධතියේ ක්‍රියාකාරීත්වය සහ වේගය නිරීක්ෂණය කරන්න.</p>
            </div>
        </section>

        <footer style="text-align: center; padding: 40px; color: #444; font-size: 12px; border-top: 1px solid #1a1a1a;">
            <p>&copy; 2026 YOURHUB | BY LAKSHITHA | +94 76 999 6722</p>
        </footer>
    </div>

    <!-- 3. ක්‍රියාකාරීත්වය (JavaScript) -->
    <script>
        const loginBtn = document.getElementById('loginBtn');

        function checkLogin() {
            const u = document.getElementById('username').value;
            const p = document.getElementById('password').value;
            
            // --- මෙතනින් Username සහ Password වෙනස් කළ හැක ---
            if (u === "admin" && p === "1234") {
                document.getElementById('login-page').style.display = 'none';
                document.getElementById('main-site').style.display = 'block';
                document.body.style.background = '#0a0a0a';
            } else {
                // වැරදි නම් Error Message එක පෙන්වයි
                document.getElementById('error-msg').style.display = 'block';
            }
        }

        // Button එක Click කළ විට පරීක්ෂා කිරීම
        loginBtn.addEventListener('click', checkLogin);
    </script>
</body>
</html>
