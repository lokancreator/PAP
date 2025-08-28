<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>People for People - Community Support Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* أنماط الصفحة الحالية - لا تحذفها */
        /* أضف هذه الأنماط الجديدة في النهاية */

        /* أنماط صفحة الملف الشخصي */
        .profile-section {
            display: none;
            margin-top: 40px;
            animation: fadeIn 0.5s ease;
        }

        .profile-header {
            background: linear-gradient(to right, #2575fc, #6a11cb);
            color: white;
            padding: 30px;
            border-radius: 15px 15px 0 0;
            text-align: center;
            position: relative;
        }

        .profile-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background-color: white;
            color: #2575fc;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 40px;
            font-weight: bold;
            margin: 0 auto 15px;
            border: 4px solid white;
        }

        .profile-edit-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .profile-edit-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .profile-info {
            background-color: white;
            padding: 25px;
            border-radius: 0 0 15px 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
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
            color: #777;
            margin-bottom: 5px;
            font-size: 14px;
        }

        .detail-value {
            font-size: 16px;
        }

        .profile-bio {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }

        .profile-posts {
            margin-top: 20px;
        }

        .profile-posts h3 {
            margin-bottom: 15px;
            color: #2575fc;
        }

        /* نموذج التعديل */
        .edit-profile-form {
            background-color: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
            display: none;
        }

        .form-actions {
            display: flex;
            gap: 10px;
            justify-content: flex-end;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <!-- المحتوى الحالي لموقعك - لا تحذف أي شيء -->
    
    <!-- أضف هذا القسم في مكان مناسب، مثلاً بعد قسم المنشورات -->
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
                <!-- سيتم إضافة منشورات المستخدم هنا ديناميكيًا -->
            </div>
        </div>
    </section>

    <script>
        // أضف هذا الكود JavaScript في نهاية ملفك، بعد الكود الحالي
        
        // عناصر واجهة المستخدم الجديدة
        const profileSection = document.getElementById('profileSection');
        const authBtn = document.getElementById('authBtn');
        const profileBtn = document.createElement('button');
        
        // إنشاء زر البروفايل في شريط التنقل
        profileBtn.innerHTML = '<i class="fas fa-user"></i>';
        profileBtn.className = 'icon-btn';
        profileBtn.id = 'profileBtn';
        profileBtn.title = 'Profile';
        profileBtn.style.display = 'none';
        
        // إضافة زر البروفايل إلى واجهة المستخدم
        document.querySelector('.nav-icons').appendChild(profileBtn);
        
        // بيانات المستخدم (ستأتي من قاعدة البيانات في التطبيق الحقيقي)
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
        
        // عرض صفحة البروفايل
        function showProfilePage() {
            welcomeSection.style.display = 'none';
            postsSection.style.display = 'none';
            profileSection.style.display = 'block';
            
            // تحميل بيانات المستخدم
            loadProfileData();
        }
        
        // تحميل بيانات البروفايل
        function loadProfileData() {
            document.getElementById('profileAvatar').textContent = userProfile.avatar;
            document.getElementById('profileName').textContent = userProfile.name;
            document.getElementById('profileFullName').textContent = userProfile.fullName;
            document.getElementById('profileEmail').textContent = userProfile.email;
            document.getElementById('profileGender').textContent = userProfile.gender || "Not specified";
            document.getElementById('profileAge').textContent = userProfile.age || "Not specified";
            document.getElementById('profileBio').textContent = userProfile.bio;
            document.getElementById('memberSince').textContent = userProfile.memberSince;
            
            // تحميل منشورات المستخدم
            loadUserPosts();
        }
        
        // تحميل منشورات المستخدم
        function loadUserPosts() {
            const postsContainer = document.getElementById('userPostsContainer');
            postsContainer.innerHTML = '';
            
            // تصفية المنشورات الخاصة بهذا المستخدم فقط
            const userPosts = posts.filter(post => post.user.name === userProfile.name);
            
            if (userPosts.length === 0) {
                postsContainer.innerHTML = '<p class="no-posts">This user hasn\'t posted anything yet.</p>';
                return;
            }
            
            userPosts.forEach(post => {
                const postElement = createPostElement(post);
                postsContainer.appendChild(postElement);
            });
        }
        
        // عرض نموذج تعديل البروفايل
        function showEditProfileForm() {
            document.getElementById('editProfileForm').style.display = 'block';
            
            // تعبئة النموذج ببيانات المستخدم الحالية
            document.getElementById('editFullName').value = userProfile.fullName;
            document.getElementById('editGender').value = userProfile.gender;
            document.getElementById('editAge').value = userProfile.age;
            document.getElementById('editBio').value = userProfile.bio;
        }
        
        // حفظ changes البروفايل
        function saveProfileChanges() {
            userProfile.fullName = document.getElementById('editFullName').value;
            userProfile.gender = document.getElementById('editGender').value;
            userProfile.age = document.getElementById('editAge').value;
            userProfile.bio = document.getElementById('editBio').value;
            
            // إخفاء نموذج التعديل
            document.getElementById('editProfileForm').style.display = 'none';
            
            // إعادة تحميل بيانات البروفايل
            loadProfileData();
            
            showNotification('Profile updated successfully!');
        }
        
        // إعداد مستمعي الأحداث للوظائف الجديدة
        function setupProfileEventListeners() {
            // زر البروفايل في شريط التنقل
            document.getElementById('profileBtn').addEventListener('click', showProfilePage);
            
            // زر التعديل في صفحة البروفايل
            document.getElementById('editProfileBtn').addEventListener('click', showEditProfileForm);
            
            // زر الحفظ في نموذج التعديل
            document.getElementById('saveProfileBtn').addEventListener('click', saveProfileChanges);
            
            // زر الإلغاء في نموذج التعديل
            document.getElementById('cancelEditBtn').addEventListener('click', function() {
                document.getElementById('editProfileForm').style.display = 'none';
            });
        }
        
        // بعد تسجيل الدخول، إظهار زر البروفايل
        function afterLoginSetup() {
            // الكود الحالي الذي لديك...
            
            // إضافة هذا السطر لإظهار زر البروفايل
            document.getElementById('profileBtn').style.display = 'flex';
            
            // تهيئة بيانات المستخدم (في التطبيق الحقيقي، سيتم جلبها من الخادم)
            userProfile.name = currentUser.name;
            userProfile.email = currentUser.email;
            userProfile.avatar = currentUser.avatar;
        }
        
        // استدعاء هذه الدالة في نهاية دالة initApp
        // setupProfileEventListeners();
        
        // تعديل دالة handleLogin و handleRegister لاستدعاء afterLoginSetup
    </script>
</body>
</html>
