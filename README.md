<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>People for People - Community Support Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Variables */
        :root {
            --primary-color: #2575fc;
            --secondary-color: #6a11cb;
            --accent-color: #ff4757;
            --text-color: #333;
            --light-gray: #f5f5f5;
            --medium-gray: #ddd;
            --dark-gray: #777;
            --white: #fff;
            --box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--secondary-color) 0%, var(--primary-color) 100%);
            color: var(--text-color);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            width: 100%;
        }
        
        /* Header Styles */
        header {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--primary-color);
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
        }
        
        .nav-icons {
            display: flex;
            gap: 20px;
        }
        
        .icon-btn {
            background: none;
            border: none;
            font-size: 20px;
            color: var(--primary-color);
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            padding: 8px;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .icon-btn:hover {
            background-color: #f0f5ff;
            color: var(--secondary-color);
        }
        
        .icon-btn.active {
            background-color: var(--primary-color);
            color: var(--white);
        }
        
        /* Welcome Section */
        .welcome-section {
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            padding: 40px;
            text-align: center;
            margin: 40px 0;
            box-shadow: var(--box-shadow);
            animation: fadeIn 1s ease;
        }
        
        .welcome-section h1 {
            color: var(--primary-color);
            margin-bottom: 20px;
            font-size: 2.5rem;
        }
        
        .welcome-section p {
            color: #555;
            font-size: 1.2rem;
            line-height: 1.6;
            margin-bottom: 30px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .auth-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }
        
        .btn {
            padding: 12px 25px;
            border-radius: 50px;
            border: none;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .btn-primary {
            background-color: var(--primary-color);
            color: var(--white);
        }
        
        .btn-primary:hover {
            background-color: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(37, 117, 252, 0.4);
        }
        
        .btn-outline {
            background-color: transparent;
            color: var(--primary-color);
            border: 2px solid var(--primary-color);
        }
        
        .btn-outline:hover {
            background-color: var(--primary-color);
            color: var(--white);
            transform: translateY(-2px);
        }
        
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.3s ease;
        }
        
        .modal-content {
            background-color: var(--white);
            padding: 30px;
            border-radius: 15px;
            width: 90%;
            max-width: 450px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
            animation: slideIn 0.3s ease;
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .close-btn {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--dark-gray);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #444;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--medium-gray);
            border-radius: 8px;
            font-size: 16px;
        }
        
        .form-group input:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 2px rgba(37, 117, 252, 0.2);
        }
        
        .submit-btn {
            width: 100%;
            padding: 12px;
            background-color: var(--primary-color);
            color: var(--white);
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .submit-btn:hover {
            background-color: var(--secondary-color);
        }
        
        .form-footer {
            text-align: center;
            margin-top: 20px;
            color: var(--dark-gray);
        }
        
        .form-footer a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
        }
        
        /* Posts Section */
        .posts-section {
            display: none;
            margin-top: 40px;
            animation: fadeIn 0.5s ease;
        }
        
        .post-form {
            background-color: var(--white);
            padding: 20px;
            border-radius: 15px;
            box-shadow: var(--box-shadow);
            margin-bottom: 30px;
        }
        
        .post-form textarea {
            width: 100%;
            padding: 15px;
            border: 1px solid var(--medium-gray);
            border-radius: 10px;
            resize: vertical;
            min-height: 100px;
            margin-bottom: 15px;
            font-size: 16px;
        }
        
        .post-form textarea:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 2px rgba(37, 117, 252, 0.2);
        }
        
        .post-form-actions {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .file-upload {
            display: flex;
            align-items: center;
            color: var(--dark-gray);
            cursor: pointer;
            padding: 8px 15px;
            border-radius: 50px;
            transition: var(--transition);
        }
        
        .file-upload:hover {
            background-color: var(--light-gray);
        }
        
        .file-upload input {
            display: none;
        }
        
        .post-btn {
            padding: 10px 20px;
            background-color: var(--primary-color);
            color: var(--white);
            border: none;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .post-btn:hover {
            background-color: var(--secondary-color);
        }
        
        /* Post Styles */
        .post {
            background-color: var(--white);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: var(--box-shadow);
            animation: slideIn 0.3s ease;
        }
        
        .post-header {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary-color);
            color: var(--white);
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            margin-right: 10px;
        }
        
        .post-content {
            margin-bottom: 15px;
            line-height: 1.6;
        }
        
        .post-image {
            width: 100%;
            border-radius: 10px;
            margin-bottom: 15px;
            max-height: 300px;
            object-fit: cover;
        }
        
        .post-actions {
            display: flex;
            gap: 15px;
            border-top: 1px solid var(--medium-gray);
            padding-top: 15px;
        }
        
        .action-btn {
            display: flex;
            align-items: center;
            gap: 5px;
            background: none;
            border: none;
            color: var(--dark-gray);
            cursor: pointer;
            font-size: 14px;
            padding: 5px 10px;
            border-radius: 20px;
            transition: var(--transition);
        }
        
        .action-btn:hover {
            color: var(--primary-color);
            background-color: #f0f5ff;
        }
        
        .action-btn.active {
            color: var(--primary-color);
            background-color: #e6f0ff;
        }
        
        .action-btn.liked {
            color: var(--accent-color);
        }
        
        .action-btn.disliked {
            color: var(--accent-color);
        }
        
        .comments-section {
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid var(--medium-gray);
        }
        
        .comment {
            display: flex;
            margin-bottom: 15px;
        }
        
        .comment-content {
            background-color: var(--light-gray);
            padding: 10px 15px;
            border-radius: 18px;
            flex-grow: 1;
        }
        
        .comment-input {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }
        
        .comment-input input {
            flex-grow: 1;
            padding: 10px 15px;
            border: 1px solid var(--medium-gray);
            border-radius: 50px;
        }
        
        .comment-input input:focus {
            outline: none;
            border-color: var(--primary-color);
        }
        
        .user-status {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 10px;
            color: var(--dark-gray);
            font-size: 14px;
        }
        
        /* Profile Page Styles */
        .profile-section {
            display: none;
            margin-top: 40px;
            animation: fadeIn 0.5s ease;
        }

        .profile-header {
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            color: var(--white);
            padding: 30px;
            border-radius: 15px 15px 0 0;
            text-align: center;
            position: relative;
        }

        .profile-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background-color: var(--white);
            color: var(--primary-color);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 40px;
            font-weight: bold;
            margin: 0 auto 15px;
            border: 4px solid var(--white);
        }

        .profile-edit-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: var(--white);
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .profile-edit-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .profile-info {
            background-color: var(--white);
            padding: 25px;
            border-radius: 0 0 15px 15px;
            box-shadow: var(--box-shadow);
            margin-bottom: 20px;
        }

        .profile-details {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 25px;
        }

        .detail-item {
            display: flex;
            flex-direction: column;
        }

        .detail-label {
            font-weight: 600;
            color: var(--dark-gray);
            margin-bottom: 5px;
            font-size: 14px;
        }

        .detail-value {
            font-size: 16px;
        }

        .profile-bio {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid var(--medium-gray);
        }

        .profile-posts {
            margin-top: 20px;
        }

        .profile-posts h3 {
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        /* Edit Profile Form */
        .edit-profile-form {
            background-color: var(--white);
            padding: 25px;
            border-radius: 15px;
            box-shadow: var(--box-shadow);
            margin-bottom: 20px;
            display: none;
        }

        .form-actions {
            display: flex;
            gap: 10px;
            justify-content: flex-end;
            margin-top: 20px;
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes slideIn {
            from { transform: translateY(-20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .welcome-section {
                padding: 20px;
            }
            
            .welcome-section h1 {
                font-size: 2rem;
            }
            
            .auth-buttons {
                flex-direction: column;
                gap: 10px;
            }
            
            .btn {
                width: 100%;
                justify-content: center;
            }
            
            .post-actions {
                flex-wrap: wrap;
            }
            
            .modal-content {
                padding: 20px;
            }

            .profile-details {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container nav-container">
            <div class="logo">
                <i class="fas fa-hands-helping"></i>
                <span>People for People</span>
            </div>
            <div class="nav-icons">
                <button class="icon-btn active" id="homeBtn" title="Home">
                    <i class="fas fa-home"></i>
                </button>
                <button class="icon-btn" id="authBtn" title="Account">
                    <i class="fas fa-user"></i>
                </button>
                <button class="icon-btn" id="postBtn" title="New Post" style="display: none;">
                    <i class="fas fa-plus"></i>
                </button>
                <button class="icon-btn" id="profileBtn" title="Profile" style="display: none;">
                    <i class="fas fa-user-circle"></i>
                </button>
            </div>
        </div>
    </header>

    <div class="container">
        <!-- Welcome Section -->
        <section class="welcome-section" id="welcomeSection">
            <h1>Welcome to People for People</h1>
            <p>A community platform that allows people to share their problems and get support and advice from others. Post your issue and help others by commenting and providing solutions.</p>
            
            <div class="auth-buttons">
                <button class="btn btn-primary" id="loginBtn">
                    <i class="fas fa-sign-in-alt"></i>
                    Log In
                </button>
                <button class="btn btn-outline" id="registerBtn">
                    <i class="fas fa-user-plus"></i>
                    Create Account
                </button>
            </div>
        </section>

        <!-- Posts Section (will appear after login) -->
        <section class="posts-section" id="postsSection">
            <!-- New post form -->
            <div class="post-form">
                <textarea placeholder="What would you like to share?"></textarea>
                <div class="post-form-actions">
                    <label class="file-upload">
                        <input type="file" accept="image/*" id="postImage">
                        <i class="fas fa-image"></i>
                        Add Image
                    </label>
                    <button class="post-btn" id="submitPost">Post</button>
                </div>
            </div>

            <!-- Posts will be dynamically added here -->
            <div id="postsContainer"></div>
        </section>

        <!-- Profile Section -->
        <section class="profile-section" id="profileSection">
            <div class="profile-header">
                <button class="profile-edit-btn" id="editProfileBtn">
                    <i class="fas fa-edit"></i> Edit Profile
                </button>
                <div class="profile-avatar" id="profileAvatar">U</div>
                <h2 id="profileName">User Name</h2>
                <p>Member since: <span id="memberSince">Jan 2023</span></p>
            </div>
            
            <div class="profile-info">
                <div class="profile-details">
                    <div class="detail-item">
                        <span class="detail-label">Full Name</span>
                        <span class="detail-value" id="profileFullName">User Full Name</span>
                    </div>
                    <div class="detail-item">
                        <span class="detail-label">Gender</span>
                        <span class="detail-value" id="profileGender">Not specified</span>
                    </div>
                    <div class="detail-item">
                        <span class="detail-label">Age</span>
                        <span class="detail-value" id="profileAge">Not specified</span>
                    </div>
                    <div class="detail-item">
                        <span class="detail-label">Email</span>
                        <span class="detail-value" id="profileEmail">user@example.com</span>
                    </div>
                </div>
                
                <div class="profile-bio">
                    <h3>About Me</h3>
                    <p id="profileBio">This user hasn't written a bio yet.</p>
                </div>
            </div>
            
            <div class="edit-profile-form" id="editProfileForm">
                <h3>Edit Profile</h3>
                <div class="form-group">
                    <label for="editFullName">Full Name</label>
                    <input type="text" id="editFullName" placeholder="Enter your full name">
                </div>
                <div class="form-group">
                    <label for="editGender">Gender</label>
                    <select id="editGender">
                        <option value="">Select gender</option>
                        <option value="male">Male</option>
                        <option value="female">Female</option>
                        <option value="other">Other</option>
                        <option value="prefer-not-to-say">Prefer not to say</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="editAge">Age</label>
                    <input type="number" id="editAge" placeholder="Enter your age" min="13" max="120">
                </div>
                <div class="form-group">
                    <label for="editBio">Bio</label>
                    <textarea id="editBio" placeholder="Tell us about yourself" rows="4"></textarea>
                </div>
                <div class="form-actions">
                    <button class="btn btn-outline" id="cancelEditBtn">Cancel</button>
                    <button class="btn btn-primary" id="saveProfileBtn">Save Changes</button>
                </div>
            </div>
            
            <div class="profile-posts">
                <h3>Recent Posts</h3>
                <div id="userPostsContainer">
                    <!-- User posts will be added here dynamically -->
                </div>
            </div>
        </section>
    </div>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Log In</h2>
                <button class="close-btn">&times;</button>
            </div>
            <form id="loginForm">
                <div class="form-group">
                    <label for="login-email">Email</label>
                    <input type="email" id="login-email" required>
                </div>
                <div class="form-group">
                    <label for="login-password">Password</label>
                    <input type="password" id="login-password" required>
                </div>
                <button type="submit" class="submit-btn">Log In</button>
            </form>
            <div class="form-footer">
                <p>Don't have an account? <a href="#" id="goToRegister">Create Account</a></p>
            </div>
        </div>
    </div>

    <!-- Register Modal -->
    <div class="modal" id="registerModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Create Account</h2>
                <button class="close-btn">&times;</button>
            </div>
            <form id="registerForm">
                <div class="form-group">
                    <label for="register-name">Full Name</label>
                    <input type="text" id="register-name" required>
                </div>
                <div class="form-group">
                    <label for="register-email">Email</label>
                    <input type="email" id="register-email" required>
                </div>
                <div class="form-group">
                    <label for="register-password">Password</label>
                    <input type="password" id="register-password" required>
                </div>
                <button type="submit" class="submit-btn">Create Account</button>
            </form>
            <div class="form-footer">
                <p>Already have an account? <a href="#" id="goToLogin">Log In</a></p>
            </div>
        </div>
    </div>

    <script>
        // Main UI elements
        const welcomeSection = document.getElementById('welcomeSection');
        const postsSection = document.getElementById('postsSection');
        const profileSection = document.getElementById('profileSection');
        const loginModal = document.getElementById('loginModal');
        const registerModal = document.getElementById('registerModal');
        const loginBtn = document.getElementById('loginBtn');
        const registerBtn = document.getElementById('registerBtn');
        const postBtn = document.getElementById('postBtn');
        const authBtn = document.getElementById('authBtn');
        const homeBtn = document.getElementById('homeBtn');
        const profileBtn = document.getElementById('profileBtn');
        const closeButtons = document.querySelectorAll('.close-btn');
        const goToRegister = document.getElementById('goToRegister');
        const goToLogin = document.getElementById('goToLogin');
        const loginForm = document.getElementById('loginForm');
        const registerForm = document.getElementById('registerForm');
        const submitPostBtn = document.getElementById('submitPost');
        const postTextarea = document.querySelector('.post-form textarea');
        const postImageInput = document.getElementById('postImage');
        const postsContainer = document.getElementById('postsContainer');
        const editProfileBtn = document.getElementById('editProfileBtn');
        const editProfileForm = document.getElementById('editProfileForm');
        const cancelEditBtn = document.getElementById('cancelEditBtn');
        const saveProfileBtn = document.getElementById('saveProfileBtn');

        // Sample data for demonstration
        const samplePosts = [
            {
                id: 1,
                user: { name: "Mohammed Ahmed", avatar: "M", verified: true },
                content: "I'm having trouble learning programming, specifically with understanding complex algorithms. Are there any tips or learning resources that could help me improve my understanding?",
                image: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&q=80",
                time: "2 hours ago",
                likes: 24,
                dislikes: 3,
                comments: [
                    { user: { name: "Sara", avatar: "S" }, content: "I recommend watching tutorials on YouTube from the Programming with Mosh channel, they're excellent for beginners." },
                    { user: { name: "Ali", avatar: "A" }, content: "Try the freeCodeCamp website, it provides excellent hands-on training for learning programming step by step." }
                ]
            },
            {
                id: 2,
                user: { name: "Jessica Wilson", avatar: "J", verified: false },
                content: "I'm looking for advice on dealing with stress at work. Lately, my workload has been overwhelming and it's affecting my productivity and mental health. Any suggestions would be appreciated!",
                image: null,
                time: "5 hours ago",
                likes: 42,
                dislikes: 2,
                comments: []
            }
        ];

        // Current user state
        let currentUser = null;
        let posts = [...samplePosts];
        
        // User profile data
        let userProfile = {
            name: "User Name",
            fullName: "User Full Name",
            email: "user@example.com",
            gender: "",
            age: "",
            bio: "This user hasn't written a bio yet.",
            memberSince: "Jan 2023",
            avatar: "U"
        };

        // Initialize the app
        function initApp() {
            loadPosts();
            setupEventListeners();
        }

        // Load posts into the UI
        function loadPosts() {
            postsContainer.innerHTML = '';
            
            posts.forEach(post => {
                const postElement = createPostElement(post);
                postsContainer.appendChild(postElement);
                addPostInteractivity(postElement);
            });
        }

        // Create a post element
        function createPostElement(post) {
            const postEl = document.createElement('div');
            postEl.className = 'post';
            postEl.dataset.id = post.id;
            
            let verifiedBadge = '';
            if (post.user.verified) {
                verifiedBadge = `<div class="user-status">
                    <i class="fas fa-shield-alt"></i>
                    Verified Member
                </div>`;
            }
            
            let postImage = '';
            if (post.image) {
                postImage = `<img src="${post.image}" class="post-image" alt="Post image">`;
            }
            
            postEl.innerHTML = `
                <div class="post-header">
                    <div class="user-avatar">${post.user.avatar}</div>
                    <div>
                        <div class="user-name">${post.user.name}</div>
                        <div class="post-time">${post.time}</div>
                        ${verifiedBadge}
                    </div>
                </div>
                <div class="post-content">
                    <p>${post.content}</p>
                </div>
                ${postImage}
                <div class="post-actions">
                    <button class="action-btn like-btn">
                        <i class="far fa-thumbs-up"></i>
                        <span>Like (${post.likes})</span>
                    </button>
                    <button class="action-btn dislike-btn">
                        <i class="far fa-thumbs-down"></i>
                        <span>Dislike (${post.dislikes})</span>
                    </button>
                    <button class="action-btn comment-btn">
                        <i class="far fa-comment"></i>
                        <span>Comment (${post.comments.length})</span>
                    </button>
                    <button class="action-btn save-btn">
                        <i class="far fa-bookmark"></i>
                        <span>Save</span>
                    </button>
                </div>
                
                <div class="comments-section">
                    ${post.comments.map(comment => `
                        <div class="comment">
                            <div class="user-avatar">${comment.user.avatar}</div>
                            <div class="comment-content">
                                <strong>${comment.user.name}</strong>
                                <p>${comment.comment}</p>
                            </div>
                        </div>
                    `).join('')}
                    <div class="comment-input">
                        <input type="text" placeholder="Write a comment...">
                        <button class="btn btn-primary">Send</button>
                    </div>
                </div>
            `;
            
            return postEl;
        }

        // Add interactivity to post buttons
        function addPostInteractivity(postElement) {
            const likeBtn = postElement.querySelector('.like-btn');
            const dislikeBtn = postElement.querySelector('.dislike-btn');
            const saveBtn = postElement.querySelector('.save-btn');
            const commentBtn = postElement.querySelector('.comment-btn');
            const commentInput = postElement.querySelector('.comment-input input');
            const commentSubmit = postElement.querySelector('.comment-input .btn');
            
            likeBtn.addEventListener('click', function() {
                this.classList.toggle('liked');
                const icon = this.querySelector('i');
                const count = this.querySelector('span');
                const postId = postElement.dataset.id;
                const post = posts.find(p => p.id == postId);
                
                if (this.classList.contains('liked')) {
                    icon.classList.remove('far');
                    icon.classList.add('fas');
                    post.likes++;
                    count.textContent = `Like (${post.likes})`;
                    
                    // If previously disliked, remove dislike
                    if (dislikeBtn.classList.contains('disliked')) {
                        dislikeBtn.classList.remove('disliked');
                        const dislikeIcon = dislikeBtn.querySelector('i');
                        dislikeIcon.classList.remove('fas');
                        dislikeIcon.classList.add('far');
                        post.dislikes--;
                        dislikeBtn.querySelector('span').textContent = `Dislike (${post.dislikes})`;
                    }
                } else {
                    icon.classList.remove('fas');
                    icon.classList.add('far');
                    post.likes--;
                    count.textContent = `Like (${post.likes})`;
                }
            });
            
            dislikeBtn.addEventListener('click', function() {
                this.classList.toggle('disliked');
                const icon = this.querySelector('i');
                const count = this.querySelector('span');
                const postId = postElement.dataset.id;
                const post = posts.find(p => p.id == postId);
                
                if (this.classList.contains('disliked')) {
                    icon.classList.remove('far');
                    icon.classList.add('fas');
                    post.dislikes++;
                    count.textContent = `Dislike (${post.dislikes})`;
                    
                    // If previously liked, remove like
                    if (likeBtn.classList.contains('liked')) {
                        likeBtn.classList.remove('liked');
                        const likeIcon = likeBtn.querySelector('i');
                        likeIcon.classList.remove('fas');
                        likeIcon.classList.add('far');
                        post.likes--;
                        likeBtn.querySelector('span').textContent = `Like (${post.likes})`;
                    }
                } else {
                    icon.classList.remove('fas');
                    icon.classList.add('far');
                    post.dislikes--;
                    count.textContent = `Dislike (${post.dislikes})`;
                }
            });
            
            saveBtn.addEventListener('click', function() {
                this.classList.toggle('active');
                const icon = this.querySelector('i');
                
                if (this.classList.contains('active')) {
                    icon.classList.remove('far');
                    icon.classList.add('fas');
                    showNotification('Post saved to your bookmarks');
                } else {
                    icon.classList.remove('fas');
                    icon.classList.add('far');
                    showNotification('Post removed from your bookmarks');
                }
            });
            
            commentSubmit.addEventListener('click', function() {
                const commentText = commentInput.value.trim();
                
                if (!commentText) {
                    showNotification('Please write a comment', 'error');
                    return;
                }
                
                const postId = postElement.dataset.id;
                const post = posts.find(p => p.id == postId);
                
                const newComment = {
                    user: currentUser,
                    comment: commentText
                };
                
                post.comments.push(newComment);
                
                const commentElement = document.createElement('div');
                commentElement.className = 'comment';
                commentElement.innerHTML = `
                    <div class="user-avatar">${currentUser.avatar}</div>
                    <div class="comment-content">
                        <strong>${currentUser.name}</strong>
                        <p>${commentText}</p>
                    </div>
                `;
                
                const commentsSection = postElement.querySelector('.comments-section');
                commentsSection.insertBefore(commentElement, commentsSection.lastElementChild);
                
                // Update comment count
                const commentCount = postElement.querySelector('.comment-btn span');
                commentCount.textContent = `Comment (${post.comments.length})`;
                
                commentInput.value = '';
                showNotification('Comment added successfully!');
            });
        }

        // Set up event listeners
        function setupEventListeners() {
            // Show login modal
            loginBtn.addEventListener('click', () => {
                loginModal.style.display = 'flex';
            });

            // Show register modal
            registerBtn.addEventListener('click', () => {
                registerModal.style.display = 'flex';
            });

            // Switch from login to register
            goToRegister.addEventListener('click', (e) => {
                e.preventDefault();
                loginModal.style.display = 'none';
                registerModal.style.display = 'flex';
            });

            // Switch from register to login
            goToLogin.addEventListener('click', (e) => {
                e.preventDefault();
                registerModal.style.display = 'none';
                loginModal.style.display = 'flex';
            });

            // Close modals
            closeButtons.forEach(button => {
                button.addEventListener('click', closeModals);
            });

            // Close modals when clicking outside
            window.addEventListener('click', (e) => {
                if (e.target === loginModal || e.target === registerModal) {
                    closeModals();
                }
            });

            // Simulate login process
            loginForm.addEventListener('submit', (e) => {
                e.preventDefault();
                handleLogin();
            });

            // Simulate registration process
            registerForm.addEventListener('submit', (e) => {
                e.preventDefault();
                handleRegister();
            });

            // Create new post
            submitPostBtn.addEventListener('click', (e) => {
                e.preventDefault();
                createNewPost();
            });

            // Home button functionality
            homeBtn.addEventListener('click', goToHome);

            // Focus on post textarea when plus icon is clicked
            postBtn.addEventListener('click', () => {
                postTextarea.focus();
                postTextarea.scrollIntoView({ behavior: 'smooth' });
            });
            
            // Profile button functionality
            profileBtn.addEventListener('click', showProfilePage);
            
            // Edit profile button
            editProfileBtn.addEventListener('click', showEditProfileForm);
            
            // Cancel edit button
            cancelEditBtn.addEventListener('click', () => {
                editProfileForm.style.display = 'none';
            });
            
            // Save profile button
            saveProfileBtn.addEventListener('click', saveProfileChanges);
        }

        // Handle login
        function handleLogin() {
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            // Simple validation
            if (!email || !password) {
                showNotification('Please fill in all fields', 'error');
                return;
            }
            
            // Simulate login process
            currentUser = {
                name: email.split('@')[0],
                email: email,
                avatar: email.charAt(0).toUpperCase()
            };
            
            // Update user profile
            userProfile.name = currentUser.name;
            userProfile.email = currentUser.email;
            userProfile.avatar = currentUser.avatar;
            
            closeModals();
            showPostsSection();
            showNotification('Successfully logged in!');
            
            // Show profile button
            profileBtn.style.display = 'flex';
        }

        // Handle registration
        function handleRegister() {
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            
            // Simple validation
            if (!name || !email || !password) {
                showNotification('Please fill in all fields', 'error');
                return;
            }
            
            if (password.length < 6) {
                showNotification('Password must be at least 6 characters', 'error');
                return;
            }
            
            // Simulate registration process
            currentUser = {
                name: name,
                email: email,
                avatar: name.charAt(0).toUpperCase()
            };
            
            // Update user profile
            userProfile.name = currentUser.name;
            userProfile.fullName = currentUser.name;
            userProfile.email = currentUser.email;
            userProfile.avatar = currentUser.avatar;
            
            closeModals();
            showPostsSection();
            showNotification('Account created successfully!');
            
            // Show profile button
            profileBtn.style.display = 'flex';
        }

        // Create a new post
        function createNewPost() {
            const content = postTextarea.value.trim();
            
            if (!content) {
                showNotification('Please write something to post', 'error');
                return;
            }
            
            const newPost = {
                id: Date.now(),
                user: currentUser,
                content: content,
                image: null,
                time: 'Just now',
                likes: 0,
                dislikes: 0,
                comments: []
            };
            
            // Handle image if selected
            if (postImageInput.files && postImageInput.files[0]) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    newPost.image = e.target.result;
                    addPostToUI(newPost);
                };
                reader.readAsDataURL(postImageInput.files[0]);
            } else {
                addPostToUI(newPost);
            }
            
            // Reset form
            postTextarea.value = '';
            postImageInput.value = '';
        }

        // Add post to UI
        function addPostToUI(post) {
            posts.unshift(post);
            const postElement = createPostElement(post);
            postsContainer.insertBefore(postElement, postsContainer.firstChild);
            addPostInteractivity(postElement);
            showNotification('Post published successfully!');
        }

        // Show posts section
        function showPostsSection() {
            welcomeSection.style.display = 'none';
            postsSection.style.display = 'block';
            profileSection.style.display = 'none';
            postBtn.style.display = 'flex';
            homeBtn.classList.add('active');
            
            // Change user icon to profile after login
            authBtn.innerHTML = '<i class="fas fa-user-circle"></i>';
            authBtn.setAttribute('title', 'My Profile');
        }

        // Show profile section
        function showProfilePage() {
            welcomeSection.style.display = 'none';
            postsSection.style.display = 'none';
            profileSection.style.display = 'block';
            homeBtn.classList.remove('active');
            
            // Load profile data
            loadProfileData();
        }
        
        // Load profile data
        function loadProfileData() {
            document.getElementById('profileAvatar').textContent = userProfile.avatar;
            document.getElementById('profileName').textContent = userProfile.name;
            document.getElementById('profileFullName').textContent = userProfile.fullName;
            document.getElementById('profileEmail').textContent = userProfile.email;
            document.getElementById('profileGender').textContent = userProfile.gender || "Not specified";
            document.getElementById('profileAge').textContent = userProfile.age || "Not specified";
            document.getElementById('profileBio').textContent = userProfile.bio;
            document.getElementById('memberSince').textContent = userProfile.memberSince;
            
            // Load user posts
            loadUserPosts();
        }
        
        // Load user posts
        function loadUserPosts() {
            const postsContainer = document.getElementById('userPostsContainer');
            postsContainer.innerHTML = '';
            
            // Filter posts by this user
            const userPosts = posts.filter(post => post.user.name === userProfile.name);
            
            if (userPosts.length === 0) {
                postsContainer.innerHTML = '<p class="no-posts">This user hasn\'t posted anything yet.</p>';
                return;
            }
            
            userPosts.forEach(post => {
                const postElement = createPostElement(post);
                postsContainer.appendChild(postElement);
                addPostInteractivity(postElement);
            });
        }
        
        // Show edit profile form
        function showEditProfileForm() {
            editProfileForm.style.display = 'block';
            
            // Fill form with current user data
            document.getElementById('editFullName').value = userProfile.fullName;
            document.getElementById('editGender').value = userProfile.gender;
            document.getElementById('editAge').value = userProfile.age;
            document.getElementById('editBio').value = userProfile.bio;
        }
        
        // Save profile changes
        function saveProfileChanges() {
            userProfile.fullName = document.getElementById('editFullName').value;
            userProfile.gender = document.getElementById('editGender').value;
            userProfile.age = document.getElementById('editAge').value;
            userProfile.bio = document.getElementById('editBio').value;
            
            // Hide edit form
            editProfileForm.style.display = 'none';
            
            // Reload profile data
            loadProfileData();
            
            showNotification('Profile updated successfully!');
        }

        // Go to home
        function goToHome() {
            welcomeSection.style.display = 'block';
            postsSection.style.display = 'none';
            profileSection.style.display = 'none';
            homeBtn.classList.add('active');
        }

        // Close all modals
        function closeModals() {
            loginModal.style.display = 'none';
            registerModal.style.display = 'none';
        }

        // Show notification
        function showNotification(message, type = 'success') {
            const notification = document.createElement('div');
            notification.style.position = 'fixed';
            notification.style.bottom = '20px';
            notification.style.right = '20px';
            notification.style.backgroundColor = type === 'success' ? '#2575fc' : '#ff4757';
            notification.style.color = 'white';
            notification.style.padding = '10px 20px';
            notification.style.borderRadius = '5px';
            notification.style.boxShadow = '0 3px 10px rgba(0, 0, 0, 0.2)';
            notification.style.zIndex = '1000';
            notification.textContent = message;
            
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.style.opacity = '0';
                notification.style.transition = 'opacity 0.5s';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 500);
            }, 3000);
        }

        // Initialize the app when the DOM is loaded
        document.addEventListener('DOMContentLoaded', initApp);
    </script>
</body>
</html>
