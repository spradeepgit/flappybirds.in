<!DOCTYPE html>
<html>
<head>
    
    <link rel="shortcut icon" href="/favicons.ico" type="image/x-icon">
    <link rel="icon" href="/favicons.ico" type="image/x-icon">
    
     <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
     <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
     <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
     <link rel="icon" type="image/png" sizes="48x48" href="/favicon-48x48.png">
     <link rel="manifest" href="/site.webmanifest">
    
     <!-- Audio elements for sound effects -->
    <audio id="flySound">
        <source src="flappy_whoosh.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <audio id="hitSound">
        <source src="punch.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>


  </script>
  
  
  
    <title>Flappy Bird</title>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- Favicon -->
    <link rel="icon" href="https://i.ibb.co/0nN4v7P/flappy-favicon.png" type="image/png">
    <link href='https://fonts.googleapis.com/css?family=Pacifico' rel='stylesheet'>
    <link href='https://fonts.googleapis.com/css?family=Permanent Marker' rel='stylesheet'>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <style>
        body {
            background-color: #721bc4;
            font-family: 'Pacifico';
            margin: 0;
            padding: 0;
        }
        
        /* Navigation Menu */
        nav {
            background-color: #a666e3;
            padding: 10px 0;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }
        
        nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }
        
        nav li {
            margin: 0 15px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-size: 18px;
            padding: 5px 10px;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        
        nav a:hover {
            background-color: #8e44ad;
        }
        
        .active {
            background-color: #8e44ad;
            font-weight: bold;
        }
        
        /* Page Sections */
        .page-section {
            display: none;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
            color: white;
        }
        
        #home-section {
            display: block;
        }
        
        h1 {
            background-color: #a666e3;
            text-shadow: 5px 5px 5px #dfd2ec;
            text-align: center;
            width: 100%;
            margin: 0;
            padding: 15px 0;
        }
        
        #game-container {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            margin: 20px 0;
            flex-direction: column;
        }
        
        canvas {
            animation: mymove 5s infinite;
            border: 5px solid #0a3cda;
            border-style: dotted;
            border-radius: 15px 50px;
            background: url('http://s2js.com/img/etc/flappyback.png');
            background-size: 100%;
            height: 480px;
            width: 320px;
        }
        
        @keyframes mymove {
            50% { box-shadow: 10px 20px 30px blue; }
        }
        
        h3 {
            font-family: 'Permanent Marker';
            margin: 10px 0;
        }
        
        #div1 {
            font-size: 48px;
        }
        
        #sound-toggle {
            position: absolute;
            top: 70px;
            right: 10px;
            background: rgba(255,255,255,0.5);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
        }
        
        /* About Us and Privacy Policy styling */
        .content-box {
            background-color: rgba(166, 102, 227, 0.7);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        
        .about-content {
            font-family: Sans-serif;
            background-color: rgb(248,249,250);
            padding: 18px;
            color: black;
            border-radius: 10px;
        }
        
        .about-content h2 {
            font-family: Sans-serif;
            color: black;
        }
        
        .privacy-content {
            font-family: Arial, sans-serif;
            background-color: rgb(248,249,250);
            padding: 20px;
            color: black;
            border-radius: 10px;
        }
        
        .privacy-content h1, 
        .privacy-content h2, 
        .privacy-content h3, 
        .privacy-content h4 {
            color: #2c3e50;
        }
        
        .privacy-content ul {
            padding-left: 20px;
        }
        
        .privacy-content li {
            margin-bottom: 10px;
        }
        
        .privacy-content a {
            color: #3498db;
            text-decoration: none;
        }
        
        .privacy-content a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <!-- Navigation Menu -->
    <nav>
        <ul>
            <li><a href="#" class="active" onclick="showSection('home-section')">Home</a></li>
            <li><a href="#" onclick="showSection('blog-section')">Blog</a></li>
            <li><a href="#" onclick="showSection('about-section')">About Us</a></li>
            <li><a href="#" onclick="showSection('privacy-section')">Privacy Policy</a></li>
        </ul>
    </nav>

    <!-- Home Section (Game) -->
    <section id="home-section" class="page-section">
        <h1><b>Flappy Bird <div id="div1" class="fa"></div></b></h1>
        <div id="game-container">
            <div id="sound-toggle" onclick="toggleSound()">🔊</div>
            <canvas id="myCanvas" width=320 height=480></canvas>
        </div>
        <h3><i onclick="toggleThumbs(this)" class="fa fa-thumbs-up"></i></h3>
    </section>

    <!-- Blog Section -->
    <section id="blog-section" class="page-section">
        <div class="content-box">
            <h2>Flappy Bird Blog</h2>
            <article>
                <h3>How to Master Flappy Bird</h3>
                <p>Learn the best strategies to get high scores in Flappy Bird with our expert tips and tricks.</p>
            </article>
            <article>
                <h3>The History of Flappy Bird</h3>
                <p>Discover the fascinating story behind one of the most popular mobile games of all time.</p>
            </article>
        </div>
    </section>

    <!-- About Us Section -->
    <section id="about-section" class="page-section">
        <div class="about-content">
            <br>
            <h2 style="font-family: Sans-serif; color: black;">About Us !</h2>
            <h2 style="font-family: Sans-serif; text-align: center;">Welcome To <span id="W_Name1">Flappybirds.in</span></h2>
            <p><span id="W_Name2">Flappybirds.in</span> is a Professional <span id="W_Type1">online game</span> Platform. Here we will only provide you with interesting content that you will enjoy very much. We are committed to providing you the best of <span id="W_Type2">online game</span>, with a focus on reliability and <span id="W_Spec">online gaming</span>. we strive to turn our passion for <span id="W_Type3">online game</span> into a thriving website. We hope you enjoy our <span id="W_Type4">online game</span> as much as we enjoy giving them to you.</p>
            <p>I will keep on posting such valuable anf knowledgeable information on my Website for all of you. Your love and support matters a lot.</p>
            <p style="font-weight: bold; text-align: center;">Thank you For Visiting Our Site<br><br>
            <span style="color: blue; font-size: 16px; font-weight: bold; text-align: center;">Have a great day !</span></p>
        </div>
    </section>

    <!-- Privacy Policy Section -->
    <section id="privacy-section" class="page-section">
        <div class="privacy-content">
            <h1>Privacy Policy</h1>
            <p>Last updated: August 11, 2025</p>
            <p>This Privacy Policy describes Our policies and procedures on the collection, use and disclosure of Your information when You use the Service and tells You about Your privacy rights and how the law protects You.</p>
            <p>We use Your Personal data to provide and improve the Service. By using the Service, You agree to the collection and use of information in accordance with this Privacy Policy. This Privacy Policy has been created with the help of the <a href="https://www.termsfeed.com/privacy-policy-generator/" target="_blank">Privacy Policy Generator</a>.</p>
            
            <h2>Interpretation and Definitions</h2>
            <h3>Interpretation</h3>
            <p>The words of which the initial letter is capitalized have meanings defined under the following conditions. The following definitions shall have the same meaning regardless of whether they appear in singular or in plural.</p>
            <h3>Definitions</h3>
            <p>For the purposes of this Privacy Policy:</p>
            <ul>
                <li><strong>Account</strong> means a unique account created for You to access our Service or parts of our Service.</li>
                <li><strong>Affiliate</strong> means an entity that controls, is controlled by or is under common control with a party.</li>
                <li><strong>Company</strong> refers to flappybirds.in.</li>
                <li><strong>Cookies</strong> are small files placed on Your device by a website.</li>
                <li><strong>Country</strong> refers to: Madhya Pradesh, India</li>
                <li><strong>Device</strong> means any device that can access the Service.</li>
                <li><strong>Personal Data</strong> is any information that relates to an identified or identifiable individual.</li>
                <li><strong>Service</strong> refers to the Website.</li>
                <li><strong>Website</strong> refers to flappybirds.in.</li>
                <li><strong>You</strong> means the individual accessing or using the Service.</li>
            </ul>
            
            <h2>Collecting and Using Your Personal Data</h2>
            <h3>Types of Data Collected</h3>
            <h4>Personal Data</h4>
            <p>While using Our Service, We may ask You to provide Us with certain personally identifiable information that can be used to contact or identify You.</p>
            <h4>Usage Data</h4>
            <p>Usage Data is collected automatically when using the Service.</p>
            <h4>Tracking Technologies and Cookies</h4>
            <p>We use Cookies and similar tracking technologies to track activity on Our Service.</p>
            
            <h3>Use of Your Personal Data</h3>
            <p>The Company may use Personal Data for the following purposes:</p>
            <ul>
                <li>To provide and maintain our Service</li>
                <li>To manage Your Account</li>
                <li>For business transfers</li>
                <li>For other purposes</li>
            </ul>
            
            <h2>Children's Privacy</h2>
            <p>Our Service does not address anyone under the age of 13.</p>
            
            <h2>Links to Other Websites</h2>
            <p>Our Service may contain links to other websites that are not operated by Us.</p>
            
            <h2>Changes to this Privacy Policy</h2>
            <p>We may update Our Privacy Policy from time to time.</p>
            
            <h2>Contact Us</h2>
            <p>If you have any questions about this Privacy Policy, You can contact us:</p>
            <ul>
                <li>By email: spradeep@gmail.com</li>
            </ul>
        </div>
    </section>

    <!-- Audio elements for sound effects -->
    <audio id="flySound">
        <source src="https://assets.mixkit.co/sfx/preview/mixkit-quick-jump-arcade-game-239.mp3" type="audio/mpeg">
    </audio>
    
    <audio id="hitSound">
        <source src="https://assets.mixkit.co/sfx/preview/mixkit-arcade-retro-game-over-213.mp3" type="audio/mpeg">
    </audio>
    
    <audio id="scoreSound">
        <source src="https://assets.mixkit.co/sfx/preview/mixkit-winning-chimes-2015.mp3" type="audio/mpeg">
    </audio>
    
    <script>
        // Navigation function
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('.page-section').forEach(section => {
                section.style.display = 'none';
            });
            
            // Show selected section
            document.getElementById(sectionId).style.display = 'block';
            
            // Update active menu item
            document.querySelectorAll('nav a').forEach(link => {
                link.classList.remove('active');
            });
            event.target.classList.add('active');
            
            // If showing game section, reset game if needed
            if (sectionId === 'home-section' && game_mode === 'over') {
                reset_game();
            }
        }

        // Game setup
        const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');
        const FPS = 60;
        const jump_amount = -8;
        const max_fall_speed = +6;
        const acceleration = 0.5;
        const pipe_speed = -2;
        const pipe_spacing = 300;
        const pipe_gap = 280;
        let game_mode = 'prestart';
        let time_game_last_running;
        let bottom_bar_offset = 0;
        let pipes = [];
        let score = 0;
        let soundEnabled = true;
        let lastPipePassed = -1;
        
        // Sound elements
        const flySound = document.getElementById('flySound');
        const hitSound = document.getElementById('hitSound');
        const scoreSound = document.getElementById('scoreSound');
        
        // Sound control
        function toggleSound() {
            soundEnabled = !soundEnabled;
            document.getElementById('sound-toggle').textContent = soundEnabled ? '🔊' : '🔇';
        }
        
        function playSound(sound) {
            if (soundEnabled) {
                sound.currentTime = 0;
                sound.play().catch(e => console.log("Audio play failed:", e));
            }
        }
        
        // Sprite class
        class MySprite {
            constructor(img_url, width, height) {
                this.x = 0;
                this.y = 0;
                this.visible = true;
                this.velocity_x = 0;
                this.velocity_y = 0;
                this.MyImg = new Image();
                this.MyImg.crossOrigin = "Anonymous";
                this.MyImg.src = img_url || '';
                this.angle = 0;
                this.flipV = false;
                this.flipH = false;
                this.width = width || 60;
                this.height = height || 60;
            }
            Do_Frame_Things() {
                ctx.save();
                ctx.translate(this.x + this.width/2, this.y + this.height/2);
                ctx.rotate(this.angle * Math.PI / 180);
                if (this.flipV) ctx.scale(1, -1);
                if (this.flipH) ctx.scale(-1, 1);
                if (this.visible && this.MyImg.complete) {
                    ctx.drawImage(this.MyImg, -this.width/2, -this.height/2, this.width, this.height);
                }
                this.x = this.x + this.velocity_x;
                this.y = this.y + this.velocity_y;
                ctx.restore();
            }
        }
        
        // UI functions
        function smile() {
            const a = document.getElementById("div1");
            a.innerHTML = "&#xf118;";
            setTimeout(() => a.innerHTML = "&#xf11a;", 1000);
            setTimeout(() => a.innerHTML = "&#xf119;", 2000);
            setTimeout(() => a.innerHTML = "&#xf11a;", 3000);
        }
        function toggleThumbs(x) {
            x.classList.toggle("fa-thumbs-down");
        }
        
        // Game functions
        function ImagesTouching(thing1, thing2) {
            if (!thing1.visible || !thing2.visible) return false;
            if (thing1.x >= thing2.x + thing2.width || 
                thing1.x + thing1.width <= thing2.x) return false;
            if (thing1.y >= thing2.y + thing2.height || 
                thing1.y + thing1.height <= thing2.y) return false;
            return true;
        }
        
        function Got_Player_Input(MyEvent) {
            switch (game_mode) {
                case 'prestart': 
                    game_mode = 'running';
                    bird.velocity_y = jump_amount;
                    playSound(flySound);
                    break;
                case 'running': 
                    bird.velocity_y = jump_amount;
                    playSound(flySound);
                    break;
                case 'over': 
                    if (new Date() - time_game_last_running > 1000) {
                        reset_game();
                        game_mode = 'running';
                        bird.velocity_y = jump_amount;
                        playSound(flySound);
                    }
                    break;
            }
            MyEvent.preventDefault();
        }
        
        function make_bird_slow_and_fall() {
            if (bird.velocity_y < max_fall_speed) bird.velocity_y += acceleration;
            if (bird.y > canvas.height - bird.height) {
                bird.velocity_y = 0;
                bird.y = canvas.height - bird.height;
                game_mode = 'over';
                playSound(hitSound);
            }
        }
        
        function add_pipe(x_pos, top_of_gap) {
            const top_pipe = new MySprite("http://s2js.com/img/etc/flappypipe.png", 80, 400);
            top_pipe.x = x_pos;
            top_pipe.y = top_of_gap - top_pipe.height;
            top_pipe.velocity_x = pipe_speed;
            pipes.push(top_pipe);
            
            const bottom_pipe = new MySprite("http://s2js.com/img/etc/flappypipe.png", 80, 400);
            bottom_pipe.flipV = true;
            bottom_pipe.x = x_pos;
            bottom_pipe.y = top_of_gap + pipe_gap;
            bottom_pipe.velocity_x = pipe_speed;
            pipes.push(bottom_pipe);
        }
        
        function make_bird_tilt_appropriately() {
            if (bird.velocity_y < 0) bird.angle = Math.max(-20, bird.angle - 5);
            else if (bird.angle < 70) bird.angle = Math.min(70, bird.angle + 3);
        }
        
        function show_the_pipes() { 
            pipes.forEach(pipe => pipe.Do_Frame_Things()); 
        }
        
        function check_for_end_game() {
            if (bird.y + bird.height >= canvas.height - bottom_bar.height) {
                game_mode = "over";
                playSound(hitSound);
                return;
            }
            
            for (let i = 0; i < pipes.length; i++) {
                if (ImagesTouching(bird, pipes[i])) {
                    game_mode = "over";
                    playSound(hitSound);
                    break;
                }
            }
        }
        
        function check_score() {
            for (let i = 0; i < pipes.length; i += 2) {
                if (pipes[i].x + pipes[i].width < bird.x && i > lastPipePassed) {
                    score += 0.5;
                    playSound(scoreSound);
                    lastPipePassed = i;
                    break;
                }
            }
        }
        
        function display_intro_instructions() {
            ctx.font = "25px Arial";
            ctx.fillStyle = "red";
            ctx.textAlign = "center";
            ctx.fillText("Press, touch or click to start", canvas.width / 2, canvas.height / 4);
        }
        
        function display_game_over() {
            ctx.font = "30px Arial";
            ctx.fillStyle = "red";
            ctx.textAlign = "center";
            ctx.fillText("Game Over", canvas.width / 2, 100);
            ctx.fillText("Score: " + Math.floor(score), canvas.width / 2, 150);
            ctx.font = "20px Arial";
            ctx.fillText("Click, touch, or press to play again", canvas.width / 2, 300);
        }
        
        function display_score() {
            ctx.font = "30px Arial";
            ctx.fillStyle = "white";
            ctx.textAlign = "center";
            ctx.fillText(Math.floor(score), canvas.width / 2, 50);
        }
        
        function display_bar_running_along_bottom() {
            if (bottom_bar_offset < -23) bottom_bar_offset = 0;
            ctx.drawImage(bottom_bar, bottom_bar_offset, canvas.height - bottom_bar.height);
        }
        
        function reset_game() {
            bird.y = canvas.height / 2;
            bird.angle = 0;
            pipes = [];
            score = 0;
            lastPipePassed = -1;
            add_all_my_pipes();
        }
        
        function add_all_my_pipes() {
            let x_pos = 500;
            const heights = [150, 100, 200, 120, 180];
            for (let i = 0; i < 12; i++) {
                const heightIndex = i % heights.length;
                add_pipe(x_pos, heights[heightIndex]);
                x_pos += pipe_spacing;
            }
            const finish_line = new MySprite("http://s2js.com/img/etc/flappyend.png", 80, 50);
            finish_line.x = x_pos;
            finish_line.velocity_x = pipe_speed;
            pipes.push(finish_line);
        }
        
        function Do_a_Frame() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            if (bird.MyImg.complete) {
                bird.Do_Frame_Things();
            }
            display_bar_running_along_bottom();
            
            switch (game_mode) {
                case 'prestart': 
                    display_intro_instructions();
                    break;
                case 'running':
                    time_game_last_running = new Date();
                    bottom_bar_offset += pipe_speed;
                    show_the_pipes();
                    make_bird_tilt_appropriately();
                    make_bird_slow_and_fall();
                    check_for_end_game();
                    check_score();
                    display_score();
                    break;
                case 'over':
                    make_bird_slow_and_fall();
                    display_game_over();
                    break;
            }
        }
        
        // Initialize game
        const bottom_bar = new Image();
        bottom_bar.src = "http://s2js.com/img/etc/flappybottom.png";
        
        // Create bird with your GIF image
        const bird = new MySprite("https://i.ibb.co/rRF4sgvd/dgfdg-unscreen.gif", 70, 70);
        bird.x = canvas.width / 3;
        bird.y = canvas.height / 2;
        
        // Ensure game starts after images load
        let imagesLoaded = 0;
        function imageLoaded() {
            imagesLoaded++;
            if (imagesLoaded === 2) {
                add_all_my_pipes();
                smile();
                setInterval(smile, 4000);
                setInterval(Do_a_Frame, 1000/FPS);
            }
        }
        
        bird.MyImg.onload = imageLoaded;
        bottom_bar.onload = imageLoaded;
        
        // Event listeners
        canvas.addEventListener("touchstart", Got_Player_Input);
        canvas.addEventListener("mousedown", Got_Player_Input);
        document.addEventListener("keydown", Got_Player_Input);
    </script>
</body>
</html>
