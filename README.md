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

        /* --- Login Page Styles --- */
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
            color: #fff;
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
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.2);
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
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .login-btn:hover { 
            background: #cc0000;
            transform: scale(1.02);
        }

        /* --- Dashboard Styles --- */
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
            box-shadow: 0 10px 30px rgba(255, 0, 0, 0.15);
        }

        .project-link {
            display: inline-block;
            margin-top: 15px;
            padding: 12px 20px;
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

        footer {
            text-align: center;
            padding: 40px;
            color: #444;
            font-size: 12px;
            border-top: 1px solid #1a1a1a;
            margin-top: 50px;
        }
    </style>
</head>
<body>

    <!-- 1. Login Section -->
    <div id="login-page">
        <div class="login-card">
            <div class="brand-name">Your<span>Hub</span></div>
            <p style="color: #888; font-size: 10px; letter-spacing: 3px; margin-bottom: 30px; text-transform: uppercase;">System Developer Node</p>

            <div class="input-group">
                <label>Access Key (Username)</label>
                <input type="text" id="username" placeholder="Username" autocomplete="off">
            </div>
            <div class="input-group">
                <label>Security Pin (Password)</label>
                <input type="password" id="password" placeholder="••••••••">
            </div>
            <button class="login-btn" id="loginBtn">Initialize Console</button>
            
            <p id="error-msg" style="color: #ff4444; font-size: 13px; margin-top: 15px; display: none;">✖ Invalid Credentials. Access Denied.</p>
        </div>
    </div>

    <!-- 2. Main Dashboard -->
    <div id="main-site">
        <nav>
            <div style="font-weight: 600; color: #ff0000; letter-spacing: 1px;">YOURHUB // CENTRAL COMMAND</div>
            <div style="cursor:pointer; font-size: 12px; color: #888; border: 1px solid #333; padding: 6px 18px; border-radius: 20px; transition: 0.3s;" onmouseover="this.style.color='#fff'" onmouseout="this.style.color='#888'" onclick="location.reload()">Terminate Session 🔒</div>
        </nav>

        <header style="padding: 80px 20px 40px; text-align: center;">
            <h1 style="font-size: 2.5rem;">Welcome, Lakshitha 👋</h1>
            <p style="color: #aaa; margin-top: 15px; max-width: 600px; margin-left: auto; margin-right: auto;">Developer console active. Managing all POS systems, database nodes, and professional deployments from one central hub.</p>
        </header>

        <section class="services">
            <!-- Project 1: Senarath Printers -->
            <div class="card" style="border: 1px solid rgba(255, 0, 0, 0.3);">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🏪</div>
                    <h3 style="color: #ff0000;">Senarath Printers</h3>
                    <p style="color: #bbb; font-size: 14px; margin-top: 10px; line-height: 1.6;">Full Inventory & Sales Management System. Designed for high-performance retail operations.</p>
                </div>
                <a href="https://lakshithahub.github.io/senarath-printers-book-shop/" target="_blank" class="project-link">
                    Launch System <i class="fas fa-external-link-alt"></i>
                </a>
            </div>

            <!-- Project 2: Current Login Deployment -->
            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🔑</div>
                    <h3>Auth Gateway</h3>
                    <p style="color: #888; font-size: 14px; margin-top: 10px; line-height: 1.6;">The secure portal managing access to all sub-directories and private projects.</p>
                </div>
                <a href="https://lakshithahub.github.io/login/" target="_blank" class="project-link" style="background: #333;">
                    View Source <i class="fas fa-code"></i>
                </a>
            </div>

            <!-- Project 3: Database Status -->
            <div class="card">
                <div>
                    <div style="font-size: 40px; margin-bottom: 15px;">🗄️</div>
                    <h3>Database Cluster</h3>
                    <p style="color: #888; font-size: 14px; margin-top: 10px;">Monitoring active JSON and SQL nodes for all deployed software systems.</p>
                </div>
                <div style="margin-top: 20px;">
                    <span style="color: #00ff00; font-size: 12px; font-weight: 600;">● SYSTEM ONLINE</span>
                </div>
            </div>
        </section>

        <footer>
            <p>&copy; 2026 YOURHUB | PROFESSIONAL SYSTEM DEVELOPER</p>
            <p style="margin-top: 10px; color: #666;">Contact: +94 76 999 6722 | Sri Lanka</p>
        </footer>
    </div>

    <script>
        const loginBtn = document.getElementById('loginBtn');
        const loginPage = document.getElementById('login-page');
        const mainSite = document.getElementById('main-site');

        function checkLogin() {
            const u = document.getElementById('username').value;
            const p = document.getElementById('password').value;
            
            // Credentials: admin / 1234
            if (u === "admin" && p === "1234") {
                // Smooth Fade Out
                loginPage.style.opacity = '0';
                
                setTimeout(() => {
                    loginPage.style.display = 'none';
                    mainSite.style.display = 'block';
                    
                    // Smooth Fade In for Dashboard
                    setTimeout(() => {
                        mainSite.style.opacity = '1';
                        document.body.style.background = '#0a0a0a';
                    }, 50);
                }, 500);
            } else {
                const error = document.getElementById('error-msg');
                error.style.display = 'block';
                // Shake effect logic can be added here
            }
        }

        loginBtn.addEventListener('click', checkLogin);

        document.addEventListener('keypress', function (e) {
            if (e.key === 'Enter') {
                checkLogin();
            }
        });
    </script>
</body>
</html>
