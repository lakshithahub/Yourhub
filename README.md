<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YourHub | Professional Developer Portfolio</title>
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
            transition: background 0.8s ease;
        }

        /* --- Login Section --- */
        #login-page {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: radial-gradient(circle, #1a1a1a 0%, #000 100%);
            transition: opacity 0.5s ease;
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

        .input-group input:focus { border-color: #ff0000; }

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

        /* --- Dashboard Section --- */
        #main-site { 
            display: none;
            opacity: 0;
            min-height: 100vh;
            background: #0a0a0a;
            transition: opacity 0.8s ease;
        }

        nav {
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #111;
            border-bottom: 1px solid #222;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .section-title {
            padding: 40px 8% 0;
            font-size: 24px;
            color: #ff0000;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .services {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            padding: 20px 8% 40px;
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

        .card h3 { margin-bottom: 10px; color: #fff; }
        .card p { color: #888; font-size: 14px; line-height: 1.6; }

        .project-link {
            display: inline-block;
            margin-top: 20px;
            padding: 12px 25px;
            background: #ff0000;
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-size: 13px;
            font-weight: 600;
            transition: 0.3s;
        }

        .project-link:hover { background: #fff; color: #ff0000; }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        footer {
            text-align: center;
            padding: 40px;
            color: #444;
            font-size: 12px;
            border-top: 1px solid #1a1a1a;
        }
    </style>
</head>
<body>

    <!-- 1. Login Page -->
    <div id="login-page">
        <div class="login-card">
            <div class="brand-name">Your<span>Hub</span></div>
            <p style="color: #888; font-size: 11px; letter-spacing: 2px; margin-bottom: 30px;">DEV CONSOLE V2.0</p>
            <div class="input-group">
                <label>Username</label>
                <input type="text" id="username" placeholder="admin">
            </div>
            <div class="input-group">
                <label>Password</label>
                <input type="password" id="password" placeholder="••••">
            </div>
            <button class="login-btn" id="loginBtn">Initialize Access</button>
            <p id="error-msg" style="color: #ff4444; font-size: 13px; margin-top: 15px; display: none;">✖ Access Denied. Check Credentials.</p>
        </div>
    </div>

    <!-- 2. Main Site Dashboard -->
    <div id="main-site">
        <nav>
            <div style="font-weight: 600; color: #ff0000;">YOURHUB // DASHBOARD</div>
            <div style="cursor:pointer; font-size: 12px; color: #888; border: 1px solid #333; padding: 5px 15px; border-radius: 20px;" onclick="location.reload()">Log Out 🔒</div>
        </nav>

        <header style="padding: 60px 20px; text-align: center;">
            <h1>Welcome back, Lakshitha 👋</h1>
            <p style="color: #aaa; margin-top: 10px;">System Developer | Professional Software Solutions</p>
        </header>

        <!-- Live Projects Section -->
        <h2 class="section-title">Live Deployments</h2>
        <section class="services">
            <div class="card" style="border: 1px solid rgba(255, 0, 0, 0.4);">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🏪</div>
                    <h3>Senarath Printers</h3>
                    <p>Complete POS & Inventory management system developed for retail operations.</p>
                </div>
                <a href="https://lakshithahub.github.io/senarath-printers-book-shop/" target="_blank" class="project-link">Open System</a>
            </div>

            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🔑</div>
                    <h3>Auth Gateway</h3>
                    <p>Secure login interface used for project authentication and node management.</p>
                </div>
                <a href="https://lakshithahub.github.io/login/" target="_blank" class="project-link" style="background: #333;">View Interface</a>
            </div>
        </section>

        <!-- Portfolio Showcase Section -->
        <h2 class="section-title">My Portfolio</h2>
        <section class="services">
            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🌐</div>
                    <h3 style="color: #38bdf8;">Web Development</h3>
                    <p>Modern, responsive websites with clean code and high performance optimization.</p>
                </div>
            </div>

            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">📊</div>
                    <h3 style="color: #38bdf8;">POS Solutions</h3>
                    <p>Custom software for sales, inventory tracking, and business automation.</p>
                </div>
            </div>

            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">📱</div>
                    <h3 style="color: #38bdf8;">Mobile Dev</h3>
                    <p>Expertise in developing complex systems entirely through mobile environments.</p>
                </div>
            </div>
        </section>

        <footer>
            <p>&copy; 2026 YOURHUB | BY LAKSHITHA | +94 76 999 6722</p>
        </footer>
    </div>

    <script>
        const loginBtn = document.getElementById('loginBtn');
        const loginPage = document.getElementById('login-page');
        const mainSite = document.getElementById('main-site');

        function checkLogin() {
            const u = document.getElementById('username').value;
            const p = document.getElementById('password').value;
            
            if (u === "admin" && p === "1234") {
                loginPage.style.opacity = '0';
                setTimeout(() => {
                    loginPage.style.display = 'none';
                    mainSite.style.display = 'block';
                    setTimeout(() => { mainSite.style.opacity = '1'; }, 50);
                    document.body.style.background = '#0a0a0a';
                }, 500);
            } else {
                document.getElementById('error-msg').style.display = 'block';
            }
        }

        loginBtn.addEventListener('click', checkLogin);
        document.addEventListener('keypress', (e) => { if(e.key === 'Enter') checkLogin(); });
    </script>
</body>
</html>
