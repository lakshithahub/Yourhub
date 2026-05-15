
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
        }

        /* --- Advanced Splash Loading Screen --- */
        #loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: radial-gradient(circle at center, #111 0%, #000 100%);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.6s cubic-bezier(0.4, 0, 0.2, 1), visibility 0.6s;
        }

        .loader-logo {
            font-size: 42px;
            font-weight: 600;
            letter-spacing: 2px;
            color: #ffffff;
            margin-bottom: 20px;
            animation: logoPulse 2s infinite ease-in-out;
            display: flex;
            align-items: center;
        }

        .loader-logo span {
            background: #ff0000;
            padding: 2px 12px;
            border-radius: 6px;
            margin-left: 8px;
            font-size: 32px;
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.6);
            animation: glowPulse 2s infinite ease-in-out;
        }

        .loader-bar-container {
            width: 200px;
            height: 3px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }

        .loader-bar {
            width: 0%;
            height: 100%;
            background: linear-gradient(90deg, #ff0000, #ff5555);
            box-shadow: 0 0 10px #ff0000;
            border-radius: 10px;
            animation: fillProgress 2.2s cubic-bezier(0.1, 0.8, 0.3, 1) forwards;
        }

        .loader-text {
            margin-top: 12px;
            font-size: 11px;
            color: #555;
            letter-spacing: 3px;
            text-transform: uppercase;
            animation: textFade 1.5s infinite alternate;
        }

        /* --- Main Site Dashboard --- */
        #main-site { 
            opacity: 0;
            display: none;
            min-height: 100vh;
            background: #0a0a0a;
            transition: opacity 0.8s ease-out;
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

        .brand-name {
            font-size: 20px;
            font-weight: 600;
            letter-spacing: 1px;
        }

        .brand-name span {
            background: #ff0000; 
            padding: 2px 8px;
            border-radius: 4px;
            margin-left: 5px;
            font-size: 14px;
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
            padding: 30px;
            border-radius: 20px;
            border: 1px solid #222;
            text-align: center;
            transition: 0.4s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
        }

        .card:hover { 
            border-color: #ff0000; 
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 0, 0, 0.1);
        }

        .card h3 { margin-bottom: 10px; color: #fff; }
        .card p { color: #888; font-size: 14px; line-height: 1.6; margin-bottom: 15px;}

        .media-container {
            width: 100%;
            height: 150px;
            background: #222;
            border-radius: 10px;
            margin-bottom: 15px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .media-container img, .media-container video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .project-link {
            display: inline-block;
            margin-top: auto;
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

        .delete-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(255,0,0,0.2);
            color: #ff4444;
            border: none;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 12px;
            transition: 0.3s;
        }
        .delete-btn:hover { background: #ff0000; color: #fff; }

        /* --- Form Container --- */
        .form-container {
            background: #111;
            margin: 30px 8%;
            padding: 30px;
            border-radius: 20px;
            border: 1px solid #222;
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

        .input-group input, .input-group textarea {
            width: 100%;
            padding: 14px;
            border-radius: 10px;
            border: 1px solid #444;
            background: #111;
            color: #fff;
            outline: none;
            transition: 0.3s;
        }

        .input-group input:focus, .input-group textarea:focus { border-color: #ff0000; }

        .action-btn {
            padding: 12px 30px;
            background: #ff0000;
            border: none;
            border-radius: 10px;
            color: #fff;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
            font-size: 14px;
        }
        .action-btn:hover { background: #cc0000; }

        /* --- Keyframe Animations --- */
        @keyframes fillProgress {
            0% { width: 0%; }
            50% { width: 70%; }
            100% { width: 100%; }
        }

        @keyframes logoPulse {
            0%, 100% { transform: scale(1); filter: drop-shadow(0 0 2px rgba(255,255,255,0)); }
            50% { transform: scale(1.03); filter: drop-shadow(0 0 8px rgba(255,255,255,0.2)); }
        }

        @keyframes glowPulse {
            0%, 100% { box-shadow: 0 0 15px rgba(255, 0, 0, 0.4); }
            50% { box-shadow: 0 0 30px rgba(255, 0, 0, 0.8); }
        }

        @keyframes textFade {
            from { opacity: 0.3; }
            to { opacity: 1; }
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

    <!-- 1. Dynamic Loading Screen -->
    <div id="loading-screen">
        <div class="loader-logo">YOUR<span>HUB</span></div>
        <div class="loader-bar-container">
            <div class="loader-bar"></div>
        </div>
        <div class="loader-text">Initializing Console</div>
    </div>

    <!-- 2. Main Site Dashboard -->
    <div id="main-site">
        <nav>
            <div class="brand-name">YOURHUB<span>CONSOLE</span></div>
            <div style="font-size: 12px; color: #888; border: 1px solid #333; padding: 5px 15px; border-radius: 20px;">
                <i class="fa-solid fa-circle" style="color: #00ff00; font-size: 9px; margin-right: 5px;"></i> Live
            </div>
        </nav>

        <header style="padding: 60px 20px; text-align: center;">
            <h1 style="font-weight: 600;">Welcome back, Lakshitha 👋</h1>
            <p style="color: #aaa; margin-top: 10px; letter-spacing: 1px;">System Developer | Professional Software Solutions</p>
        </header>

        <!-- Dynamic Add Project Form -->
        <div class="form-container">
            <h3 style="color: #ff0000; margin-bottom: 20px;"><i class="fa-solid fa-plus"></i> Add New Deployment / Project</h3>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px;">
                <div class="input-group">
                    <label>Project Title</label>
                    <input type="text" id="projTitle" placeholder="e.g., My New App">
                </div>
                <div class="input-group">
                    <label>Media URL (Image or Video Link)</label>
                    <input type="text" id="projMedia" placeholder="https://example.com/image.jpg">
                </div>
                <div class="input-group">
                    <label>Live Project URL</label>
                    <input type="text" id="projLink" placeholder="https://lakshithahub.github.io/...">
                </div>
            </div>
            <div class="input-group">
                <label>Description</label>
                <textarea id="projDesc" rows="3" placeholder="Briefly explain the project functionalities..."></textarea>
            </div>
            <button class="action-btn" onclick="saveProject()">Save Project</button>
        </div>

        <!-- Live Projects Section -->
        <h2 class="section-title">Live Deployments</h2>
        <section class="services" id="project-list">
            <!-- Static Items -->
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
        // Page එක සම්පූර්ණයෙන්ම load වූ පසු ක්‍රියාත්මක වන කොටස
        window.addEventListener('load', () => {
            loadProjects(); // Projects load කිරීම

            // තත්පර 2.2 කට පසු Loading Screen එක ඉවත් කර Dashboard එක පෙන්වීම
            setTimeout(() => {
                const loader = document.getElementById('loading-screen');
                const mainSite = document.getElementById('main-site');
                
                loader.style.opacity = '0';
                loader.style.visibility = 'hidden';
                
                mainSite.style.display = 'block';
                // සිනිඳු ලෙස Dashboard එක මතු වීමට (Fade-in effect)
                setTimeout(() => {
                    mainSite.style.opacity = '1';
                }, 50);
                
            }, 2200); 
        });

        // --- Custom Project Dynamic Logic ---
        function saveProject() {
            const title = document.getElementById('projTitle').value;
            const media = document.getElementById('projMedia').value;
            const link = document.getElementById('projLink').value;
            const desc = document.getElementById('projDesc').value;

            if(!title || !desc) {
                alert("Please fill out at least Title and Description!");
                return;
            }

            const newProject = { id: Date.now(), title, media, link, desc };

            let projects = JSON.parse(localStorage.getItem('myProjects')) || [];
            projects.push(newProject);
            localStorage.setItem('myProjects', JSON.stringify(projects));

            document.getElementById('projTitle').value = '';
            document.getElementById('projMedia').value = '';
            document.getElementById('projLink').value = '';
            document.getElementById('projDesc').value = '';

            loadProjects();
        }

        function loadProjects() {
            const container = document.getElementById('project-list');
            document.querySelectorAll('.dynamic-card').forEach(el => el.remove());

            const projects = JSON.parse(localStorage.getItem('myProjects')) || [];

            projects.forEach(proj => {
                const card = document.createElement('div');
                card.className = 'card dynamic-card';
                
                let mediaHtml = '';
                if(proj.media) {
                    const isVideo = proj.media.match(/\.(mp4|webm|ogg)/i) || proj.media.includes('youtube') || proj.media.includes('drive.google');
                    if(isVideo) {
                        mediaHtml = `<div class="media-container"><video src="${proj.media}" controls muted></video></div>`;
                    } else {
                        mediaHtml = `<div class="media-container"><img src="${proj.media}" alt="Project Visual"></div>`;
                    }
                } else {
                    mediaHtml = `<div class="media-container" style="font-size: 40px;">🚀</div>`;
                }

                card.innerHTML = `
                    <button class="delete-btn" onclick="deleteProject(${proj.id})">Delete 🗑️</button>
                    <div>
                        ${mediaHtml}
                        <h3>${proj.title}</h3>
                        <p>${proj.desc}</p>
                    </div>
                    ${proj.link ? `<a href="${proj.link}" target="_blank" class="project-link">Open Project</a>` : ''}
                `;
                
                container.appendChild(card);
            });
        }

        function deleteProject(id) {
            let projects = JSON.parse(localStorage.getItem('myProjects')) || [];
            projects = projects.filter(p => p.id !== id);
            localStorage.setItem('myProjects', JSON.stringify(projects));
            loadProjects();
        }
    </script>
</body>
</html>
