<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="css/rwd.css">
    
    <title>Daniel Whitwell | Personal Profile</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    
    <style>
        /* CSS to match the specific colors from the screenshot */
        :root {
            --header-purple: #960086; /* Deep Purple */
            --nav-blue: #2abae9;      /* Bright Blue */
            --facts-bg: #f5f4dc;      /* Light Beige/Yellow */
            --facts-border: #2abae9;  /* Matches nav blue */
        }

        body {
            font-family: Arial, sans-serif;
            background-color: white;
            color: #000;
            margin: 0;
            padding: 0;
        }

        /* Header Styling */
        .profile-header {
            background-color: var(--header-purple);
            color: white;
            text-align: center;
            padding: 20px;
            font-size: 2rem;
            font-weight: bold;
        }

        /* Navigation Buttons Styling */
        .nav-button {
            background-color: var(--nav-blue);
            color: white;
            padding: 10px 15px;
            margin-bottom: 5px;
            font-weight: 500;
            cursor: pointer;
            transition: opacity 0.2s;
        }
        .nav-button:hover {
            opacity: 0.9;
        }

        /* Facts Box Styling */
        .facts-container {
            background-color: var(--facts-bg);
            border: 1px solid var(--facts-border);
            padding: 15px;
            height: 100%; /* Fills height of column */
        }

        /* Footer Styling (Optional to keep structure) */
        .footer-bar {
            background-color: var(--nav-blue);
            color: white;
            text-align: center;
            padding: 10px;
            margin-top: 20px;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <div class="profile-header">
        Personal Profile Web Page - Daniel Whitwell
    </div>

    <div class="container mx-auto p-4">
        <div class="flex flex-col md:flex-row gap-6">

            <div class="w-full md:w-1/5 flex flex-col">
                <div class="nav-button">About me</div>
                <div class="nav-button">Education/Achievements</div>
                <div class="nav-button">Course</div>
                <div class="nav-button">Hobbies & Interests</div>
                <div class="nav-button">Goals in Life</div>
                <div class="nav-button">IT Experience</div>
            </div>

            <div class="w-full md:w-3/5">
                <h2 class="text-3xl font-bold mb-4">About me</h2>
                
                <div class="mb-6">
                    <img 
                        src="https://i.pinimg.com/1200x/21/7c/94/217c941f96d0457074411d1896d3625a.jpg" 
                        alt="Profile Picture" 
                        class="w-64 h-auto object-cover border border-gray-300 shadow-sm"
                        onerror="this.onerror=null; this.src='https://placehold.co/300x300/png?text=Profile+Pic';"
                    >
                </div>

                <div class="space-y-4 text-gray-900">
                    <p>
                        <strong>About Me:</strong> Hello! My name is Daniel Whitwell, and I'm excited to be starting this course. I am currently studying a Bachelor of Science in Computer Science Specializing in Cybersecurity & Forensics.
                    </p>

                    <p>
                        <strong>Education / Achievements:</strong> Graduated from GE in Senior High School (General Education track).
                    </p>

                    <p>
                        <strong>IT Experience:</strong> Basic skills in Java, Python, HTML, CSS and KALI.
                    </p>

                    <p>
                        <strong>Hobbies & Interests:</strong> Watching anime, Playing all sorts of video games, and Listening to music.
                    </p>

                    <p>
                        <strong>Goals In Life / Dream:</strong> Make money and make the love of my life the happiest girl in the world.
                    </p>
                </div>
            </div>

            <div class="w-full md:w-1/5">
                <div class="facts-container">
                    <h3 class="font-bold text-lg mb-2">Facts:</h3>
                    <ul class="list-disc pl-5 space-y-1">
                        <li>I love Anime</li>
                        <li>Cybersecurity Student</li>
                        <li>Gamer</li>
                    </ul>
                </div>
            </div>

        </div>
    </div>

    <div class="footer-bar">
        <p>Resize the browser window to see the responsive effect.</p>
    </div>

</body>
</html>