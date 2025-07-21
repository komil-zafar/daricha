<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>دریچه - بازار آنلاین افغانستان</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800;900&display=swap');
        
        * {
            font-family: 'Vazirmatn', sans-serif;
        }
        
        /* 3D Logo Animation */
        .logo-3d {
            background: linear-gradient(45deg, #ff6b35, #f7931e, #ffcc02);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite, bounce 2s ease-in-out infinite;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            transform: perspective(500px) rotateX(15deg);
            filter: drop-shadow(0 4px 8px rgba(255, 107, 53, 0.3));
        }
        
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        @keyframes bounce {
            0%, 100% { transform: perspective(500px) rotateX(15deg) translateY(0); }
            50% { transform: perspective(500px) rotateX(15deg) translateY(-5px); }
        }
        
        /* Bell decoration for logo */
        .bell-decoration {
            display: inline-block;
            animation: swing 2s ease-in-out infinite;
            color: #ffd700;
            filter: drop-shadow(0 2px 4px rgba(255, 215, 0, 0.5));
        }
        
        @keyframes swing {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(10deg); }
            75% { transform: rotate(-10deg); }
        }
        
        /* Premium badges */
        .badge-bronze { background: linear-gradient(45deg, #cd7f32, #b8860b); }
        .badge-silver { background: linear-gradient(45deg, #c0c0c0, #a8a8a8); }
        .badge-gold { background: linear-gradient(45deg, #ffd700, #ffb347); }
        
        /* Card hover effects */
        .card-hover {
            transition: all 0.3s ease;
        }
        .card-hover:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        
        /* Afghan flag colors */
        .afghan-gradient {
            background: linear-gradient(90deg, #000000 33%, #d32f2f 33%, #d32f2f 66%, #4caf50 66%);
        }
        
        /* Notification bell */
        .notification-bell {
            animation: ring 2s ease-in-out infinite;
        }
        
        @keyframes ring {
            0%, 100% { transform: rotate(0deg); }
            10%, 30%, 50%, 70%, 90% { transform: rotate(10deg); }
            20%, 40%, 60%, 80% { transform: rotate(-10deg); }
        }
        
        /* Modal styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
        }
        
        .modal.active {
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* Page transitions */
        .page {
            display: none;
        }
        
        .page.active {
            display: block;
            animation: fadeIn 0.3s ease-in-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Category grid */
        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
        }
        
        .category-card {
            background: white;
            border-radius: 12px;
            padding: 1.5rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }
        
        .category-card:hover {
            transform: translateY(-5px);
            border-color: #f97316;
            box-shadow: 0 10px 30px rgba(249, 115, 22, 0.2);
        }
        
        .category-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }
        
        /* Video upload styles */
        .video-upload-area {
            border: 2px dashed #d1d5db;
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .video-upload-area.dragover {
            border-color: #f97316;
            background-color: #fff7ed;
        }
        
        .video-preview {
            max-width: 100%;
            max-height: 200px;
            border-radius: 8px;
            margin: 1rem 0;
        }
        
        /* Login/Register forms */
        .auth-form {
            background: white;
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        /* Dropdown menu */
        .dropdown {
            position: relative;
        }
        
        .dropdown-menu {
            position: absolute;
            top: 100%;
            right: 0;
            background: white;
            border-radius: 8px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            min-width: 200px;
            z-index: 50;
            display: none;
        }
        
        .dropdown.active .dropdown-menu {
            display: block;
        }
        
        /* Subcategory styles */
        .subcategory-list {
            display: none;
            background: #f9fafb;
            border-radius: 8px;
            padding: 1rem;
            margin-top: 1rem;
        }
        
        .subcategory-list.active {
            display: block;
        }
        
        .subcategory-item {
            padding: 0.5rem 1rem;
            border-radius: 6px;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        
        .subcategory-item:hover {
            background-color: #e5e7eb;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Header -->
    <header class="bg-white shadow-lg sticky top-0 z-50">
        <div class="container mx-auto px-4 py-3">
            <div class="flex items-center justify-between">
                <!-- Logo -->
                <div class="flex items-center space-x-4 space-x-reverse">
                    <button onclick="showPage('home')" class="text-4xl font-black logo-3d cursor-pointer">
                        <span class="bell-decoration">🔔</span>
                        دریچه
                        <span class="bell-decoration">🔔</span>
                    </button>
                    <div class="text-sm text-gray-600">بازار آنلاین افغانستان</div>
                </div>
                
                <!-- Search Bar -->
                <div class="flex-1 max-w-2xl mx-8">
                    <div class="relative">
                        <input type="text" placeholder="جستجو در میان هزاران کالا..." 
                               class="w-full px-4 py-3 pr-12 border-2 border-orange-200 rounded-full focus:border-orange-500 focus:outline-none">
                        <button class="absolute right-3 top-1/2 transform -translate-y-1/2 text-orange-500">
                            🔍
                        </button>
                    </div>
                </div>
                
                <!-- User Actions -->
                <div class="flex items-center space-x-4 space-x-reverse">
                    <!-- City Selector -->
                    <div class="relative">
                        <button onclick="toggleCityMenu()" class="flex items-center space-x-2 space-x-reverse bg-gray-100 hover:bg-gray-200 px-4 py-2 rounded-full transition">
                            <span id="selectedCityIcon">🏛️</span>
                            <span id="selectedCityName">کابل</span>
                            <span class="text-sm">📍</span>
                        </button>
                        <div id="cityDropdown" class="absolute top-full left-0 mt-2 bg-white border rounded-lg shadow-lg w-64 z-50 hidden">
                            <div class="p-4 border-b">
                                <h3 class="font-bold text-gray-800">انتخاب شهر</h3>
                            </div>
                            <div class="max-h-80 overflow-y-auto">
                                <button onclick="selectCityFromMenu('کابل', '🏛️')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse transition">
                                    <span class="text-xl">🏛️</span>
                                    <span class="font-medium">کابل</span>
                                </button>
                                <button onclick="selectCityFromMenu('هرات', '🕌')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse transition">
                                    <span class="text-xl">🕌</span>
                                    <span class="font-medium">هرات</span>
                                </button>
                                <button onclick="selectCityFromMenu('مزار شریف', '🏰')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse transition">
                                    <span class="text-xl">🏰</span>
                                    <span class="font-medium">مزار شریف</span>
                                </button>
                                <button onclick="selectCityFromMenu('قندهار', '🏜️')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse transition">
                                    <span class="text-xl">🏜️</span>
                                    <span class="font-medium">قندهار</span>
                                </button>
                                <button onclick="selectCityFromMenu('جلال آباد', '🌄')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse transition">
                                    <span class="text-xl">🌄</span>
                                    <span class="font-medium">جلال آباد</span>
                                </button>
                                <button onclick="selectCityFromMenu('کندز', '🏔️')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse transition">
                                    <span class="text-xl">🏔️</span>
                                    <span class="font-medium">کندز</span>
                                </button>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Login/Register Buttons -->
                    <div id="authButtons" class="flex items-center space-x-2 space-x-reverse">
                        <button onclick="openModal('loginModal')" class="bg-blue-500 text-white px-4 py-2 rounded-full hover:bg-blue-600 transition">
                            ورود
                        </button>
                        <button onclick="openModal('registerModal')" class="bg-green-500 text-white px-4 py-2 rounded-full hover:bg-green-600 transition">
                            ثبت نام
                        </button>
                    </div>
                    
                    <!-- User Profile (hidden by default) -->
                    <div id="userProfile" class="hidden">
                        <div class="dropdown">
                            <button onclick="toggleUserMenu()" class="flex items-center space-x-2 space-x-reverse bg-gray-100 hover:bg-gray-200 px-4 py-2 rounded-full transition">
                                <div class="w-8 h-8 bg-orange-500 rounded-full flex items-center justify-center text-white font-bold">
                                    <span id="userInitial">ا</span>
                                </div>
                                <span id="userName">احمد رضایی</span>
                            </button>
                            <div class="dropdown-menu">
                                <button onclick="showPage('profile')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse">
                                    <span>👤</span>
                                    <span>پروفایل من</span>
                                </button>
                                <button onclick="showPage('profile')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse">
                                    <span>📝</span>
                                    <span>آگهی‌های من</span>
                                </button>
                                <button onclick="openModal('walletModal')" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse">
                                    <span>💰</span>
                                    <span>کیف پول</span>
                                </button>
                                <hr class="my-2">
                                <button onclick="logout()" class="w-full text-right px-4 py-3 hover:bg-gray-50 flex items-center space-x-3 space-x-reverse text-red-600">
                                    <span>🚪</span>
                                    <span>خروج</span>
                                </button>
                            </div>
                        </div>
                    </div>
                    
                    <div class="relative">
                        <button class="text-2xl notification-bell">🔔</button>
                        <span class="absolute -top-1 -right-1 bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">3</span>
                    </div>
                    <button class="text-2xl">🛒</button>
                </div>
            </div>
            
            <!-- Navigation -->
            <nav class="mt-4 border-t pt-4">
                <div class="flex items-center justify-between">
                    <div class="flex space-x-8 space-x-reverse">
                        <button onclick="showPage('home')" class="text-gray-700 hover:text-orange-500 font-medium">خانه</button>
                        <button onclick="showPage('categories')" class="text-gray-700 hover:text-orange-500 font-medium">دسته‌بندی‌ها</button>
                        <button onclick="showCategoryPage('vehicles')" class="text-gray-700 hover:text-orange-500 font-medium">وسایل نقلیه</button>
                        <button onclick="showCategoryPage('real-estate')" class="text-gray-700 hover:text-orange-500 font-medium">املاک</button>
                        <button onclick="showCategoryPage('electronics')" class="text-gray-700 hover:text-orange-500 font-medium">الکترونیک</button>
                        <button onclick="showCategoryPage('fashion')" class="text-gray-700 hover:text-orange-500 font-medium">پوشاک</button>
                    </div>
                    <button onclick="showPage('add-listing')" class="bg-green-500 text-white px-4 py-2 rounded-full hover:bg-green-600 transition">
                        ➕ ثبت آگهی
                    </button>
                </div>
            </nav>
        </div>
    </header>

    <!-- Premium Membership Banner -->
    <div class="afghan-gradient h-2"></div>
    <div class="bg-gradient-to-r from-yellow-400 to-orange-500 text-white py-3">
        <div class="container mx-auto px-4 text-center">
            <span class="font-bold">🌟 عضویت ویژه دریچه - امکانات بیشتر، فروش بهتر! 🌟</span>
            <button onclick="openModal('premiumModal')" class="mr-4 bg-white text-orange-500 px-4 py-1 rounded-full font-bold hover:bg-gray-100 transition">
                مشاهده پکیج‌ها
            </button>
        </div>
    </div>

    <!-- HOME PAGE -->
    <div id="homePage" class="page active">
        <main class="container mx-auto px-4 py-8">
            <!-- Main Categories Grid -->
            <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                <h2 class="text-2xl font-bold mb-6 text-center">🛍️ دسته‌بندی محصولات</h2>
                <div class="category-grid">
                    <!-- Fashion & Clothing -->
                    <div class="category-card" onclick="toggleSubcategories('fashion')">
                        <span class="category-icon">👕</span>
                        <h3 class="font-bold text-lg mb-2">پوشاک و مد</h3>
                        <p class="text-gray-600 text-sm">لباس، کفش، اکسسوری</p>
                        <div id="fashion-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('mens-clothing')">👔 لباس مردانه</div>
                            <div class="subcategory-item" onclick="showCategoryPage('womens-clothing')">👗 لباس زنانه</div>
                            <div class="subcategory-item" onclick="showCategoryPage('shoes')">👟 کفش</div>
                            <div class="subcategory-item" onclick="showCategoryPage('accessories')">💍 اکسسوری</div>
                            <div class="subcategory-item" onclick="showCategoryPage('bags')">👜 کیف</div>
                        </div>
                    </div>

                    <!-- Vehicles -->
                    <div class="category-card" onclick="toggleSubcategories('vehicles')">
                        <span class="category-icon">🚗</span>
                        <h3 class="font-bold text-lg mb-2">وسایل نقلیه</h3>
                        <p class="text-gray-600 text-sm">خودرو، موتور، دوچرخه</p>
                        <div id="vehicles-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('cars')">🚗 خودرو</div>
                            <div class="subcategory-item" onclick="showCategoryPage('motorcycles')">🏍️ موتورسیکلت</div>
                            <div class="subcategory-item" onclick="showCategoryPage('bicycles')">🚲 دوچرخه</div>
                            <div class="subcategory-item" onclick="showCategoryPage('trucks')">🚛 کامیون</div>
                            <div class="subcategory-item" onclick="showCategoryPage('parts')">🔧 قطعات</div>
                        </div>
                    </div>

                    <!-- Real Estate -->
                    <div class="category-card" onclick="toggleSubcategories('real-estate')">
                        <span class="category-icon">🏠</span>
                        <h3 class="font-bold text-lg mb-2">املاک و زمین</h3>
                        <p class="text-gray-600 text-sm">خانه، آپارتمان، زمین</p>
                        <div id="real-estate-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('houses')">🏡 خانه</div>
                            <div class="subcategory-item" onclick="showCategoryPage('apartments')">🏢 آپارتمان</div>
                            <div class="subcategory-item" onclick="showCategoryPage('land')">🌾 زمین</div>
                            <div class="subcategory-item" onclick="showCategoryPage('commercial')">🏪 تجاری</div>
                            <div class="subcategory-item" onclick="showCategoryPage('rent')">🔑 اجاره</div>
                        </div>
                    </div>

                    <!-- Digital & Technology -->
                    <div class="category-card" onclick="toggleSubcategories('digital')">
                        <span class="category-icon">📱</span>
                        <h3 class="font-bold text-lg mb-2">دیجیتال و فناوری</h3>
                        <p class="text-gray-600 text-sm">موبایل، لپ تاپ، تبلت</p>
                        <div id="digital-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('mobile')">📱 موبایل</div>
                            <div class="subcategory-item" onclick="showCategoryPage('laptop')">💻 لپ تاپ</div>
                            <div class="subcategory-item" onclick="showCategoryPage('tablet')">📟 تبلت</div>
                            <div class="subcategory-item" onclick="showCategoryPage('gaming')">🎮 گیمینگ</div>
                            <div class="subcategory-item" onclick="showCategoryPage('accessories-tech')">🔌 لوازم جانبی</div>
                        </div>
                    </div>

                    <!-- Electronics -->
                    <div class="category-card" onclick="toggleSubcategories('electronics')">
                        <span class="category-icon">📺</span>
                        <h3 class="font-bold text-lg mb-2">الکترونیک</h3>
                        <p class="text-gray-600 text-sm">تلویزیون، یخچال، لوازم برقی</p>
                        <div id="electronics-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('tv')">📺 تلویزیون</div>
                            <div class="subcategory-item" onclick="showCategoryPage('refrigerator')">❄️ یخچال</div>
                            <div class="subcategory-item" onclick="showCategoryPage('washing-machine')">🌀 ماشین لباسشویی</div>
                            <div class="subcategory-item" onclick="showCategoryPage('air-conditioner')">❄️ کولر</div>
                            <div class="subcategory-item" onclick="showCategoryPage('kitchen-appliances')">🍳 لوازم آشپزخانه</div>
                        </div>
                    </div>

                    <!-- Furniture -->
                    <div class="category-card" onclick="toggleSubcategories('furniture')">
                        <span class="category-icon">🛋️</span>
                        <h3 class="font-bold text-lg mb-2">مبلمان و دکوراسیون</h3>
                        <p class="text-gray-600 text-sm">مبل، تخت، میز</p>
                        <div id="furniture-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('sofa')">🛋️ مبل</div>
                            <div class="subcategory-item" onclick="showCategoryPage('bed')">🛏️ تخت</div>
                            <div class="subcategory-item" onclick="showCategoryPage('table')">🪑 میز و صندلی</div>
                            <div class="subcategory-item" onclick="showCategoryPage('wardrobe')">🚪 کمد</div>
                            <div class="subcategory-item" onclick="showCategoryPage('decoration')">🖼️ دکوراسیون</div>
                        </div>
                    </div>

                    <!-- Home & Garden -->
                    <div class="category-card" onclick="toggleSubcategories('home')">
                        <span class="category-icon">🏡</span>
                        <h3 class="font-bold text-lg mb-2">وسایل خانه</h3>
                        <p class="text-gray-600 text-sm">آشپزخانه، حمام، نظافت</p>
                        <div id="home-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('kitchen')">🍳 آشپزخانه</div>
                            <div class="subcategory-item" onclick="showCategoryPage('bathroom')">🚿 حمام</div>
                            <div class="subcategory-item" onclick="showCategoryPage('cleaning')">🧽 نظافت</div>
                            <div class="subcategory-item" onclick="showCategoryPage('garden')">🌱 باغبانی</div>
                            <div class="subcategory-item" onclick="showCategoryPage('tools')">🔨 ابزار</div>
                        </div>
                    </div>

                    <!-- Sports & Recreation -->
                    <div class="category-card" onclick="toggleSubcategories('sports')">
                        <span class="category-icon">⚽</span>
                        <h3 class="font-bold text-lg mb-2">ورزش و تفریح</h3>
                        <p class="text-gray-600 text-sm">ورزش، بازی، سرگرمی</p>
                        <div id="sports-sub" class="subcategory-list">
                            <div class="subcategory-item" onclick="showCategoryPage('fitness')">🏋️ بدنسازی</div>
                            <div class="subcategory-item" onclick="showCategoryPage('outdoor')">🏕️ فضای باز</div>
                            <div class="subcategory-item" onclick="showCategoryPage('games')">🎲 بازی</div>
                            <div class="subcategory-item" onclick="showCategoryPage('music')">🎵 موسیقی</div>
                            <div class="subcategory-item" onclick="showCategoryPage('books')">📚 کتاب</div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Featured Products -->
            <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                <h2 class="text-2xl font-bold mb-6">🌟 محصولات ویژه</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div onclick="showProductDetail('iphone')" class="border rounded-lg p-4 card-hover cursor-pointer">
                        <div class="bg-gray-200 h-48 rounded-lg mb-4 flex items-center justify-center text-4xl">📱</div>
                        <h3 class="font-bold mb-2">آیفون 14 پرو مکس</h3>
                        <p class="text-gray-600 mb-2">کابل، افغانستان</p>
                        <p class="text-2xl font-bold text-orange-500 mb-2">85,000 افغانی</p>
                        <div class="flex items-center justify-between">
                            <span class="badge-gold text-white px-2 py-1 rounded-full text-xs">طلایی</span>
                            <div class="flex items-center text-sm text-gray-500">
                                <span class="ml-1">📹</span>
                                <span>ویدیو</span>
                            </div>
                        </div>
                    </div>
                    
                    <div onclick="showProductDetail('car')" class="border rounded-lg p-4 card-hover cursor-pointer">
                        <div class="bg-gray-200 h-48 rounded-lg mb-4 flex items-center justify-center text-4xl">🚗</div>
                        <h3 class="font-bold mb-2">تویوتا کرولا 2020</h3>
                        <p class="text-gray-600 mb-2">هرات، افغانستان</p>
                        <p class="text-2xl font-bold text-orange-500 mb-2">450,000 افغانی</p>
                        <div class="flex items-center justify-between">
                            <span class="badge-silver text-white px-2 py-1 rounded-full text-xs">نقره‌ای</span>
                            <div class="flex items-center text-sm text-gray-500">
                                <span class="ml-1">📹</span>
                                <span>ویدیو</span>
                            </div>
                        </div>
                    </div>
                    
                    <div onclick="showProductDetail('apartment')" class="border rounded-lg p-4 card-hover cursor-pointer">
                        <div class="bg-gray-200 h-48 rounded-lg mb-4 flex items-center justify-center text-4xl">🏠</div>
                        <h3 class="font-bold mb-2">آپارتمان 3 خوابه</h3>
                        <p class="text-gray-600 mb-2">مزار شریف، افغانستان</p>
                        <p class="text-2xl font-bold text-orange-500 mb-2">120,000 افغانی</p>
                        <div class="flex items-center justify-between">
                            <span class="badge-bronze text-white px-2 py-1 rounded-full text-xs">برنزی</span>
                            <div class="flex items-center text-sm text-gray-500">
                                <span class="ml-1">📸</span>
                                <span>تصاویر</span>
                            </div>
                        </div>
                    </div>
                    
                    <div onclick="showProductDetail('sofa')" class="border rounded-lg p-4 card-hover cursor-pointer">
                        <div class="bg-gray-200 h-48 rounded-lg mb-4 flex items-center justify-center text-4xl">🛋️</div>
                        <h3 class="font-bold mb-2">مبل 7 نفره</h3>
                        <p class="text-gray-600 mb-2">قندهار، افغانستان</p>
                        <p class="text-2xl font-bold text-orange-500 mb-2">25,000 افغانی</p>
                        <div class="flex items-center justify-between">
                            <span class="bg-gray-400 text-white px-2 py-1 rounded-full text-xs">عادی</span>
                            <div class="flex items-center text-sm text-gray-500">
                                <span class="ml-1">📹</span>
                                <span>ویدیو</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Quick Services -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-gradient-to-r from-pink-500 to-purple-600 text-white p-6 rounded-lg card-hover">
                    <h3 class="text-xl font-bold mb-2">📢 تبلیغات ویژه</h3>
                    <p class="mb-4">فضای تبلیغاتی برای کسب‌وکارها</p>
                    <button class="bg-white text-purple-600 px-4 py-2 rounded-full font-bold hover:bg-gray-100 transition">
                        اطلاعات بیشتر
                    </button>
                </div>
                
                <div class="bg-gradient-to-r from-blue-500 to-cyan-600 text-white p-6 rounded-lg card-hover">
                    <h3 class="text-xl font-bold mb-2">🏍️ حمل و نقل</h3>
                    <p class="mb-4">سریع‌ترین سرویس تحویل</p>
                    <button onclick="openModal('deliveryModal')" class="bg-white text-blue-600 px-4 py-2 rounded-full font-bold hover:bg-gray-100 transition">
                        ثبت موتور
                    </button>
                </div>
                
                <div class="bg-gradient-to-r from-green-500 to-teal-600 text-white p-6 rounded-lg card-hover">
                    <h3 class="text-xl font-bold mb-2">💰 کیف پول</h3>
                    <p class="mb-4">پرداخت آسان و امن</p>
                    <button onclick="openModal('walletModal')" class="bg-white text-green-600 px-4 py-2 rounded-full font-bold hover:bg-gray-100 transition">
                        شارژ کیف پول
                    </button>
                </div>
            </div>
        </main>
    </div>

    <!-- ADD LISTING PAGE (Enhanced with Video Upload) -->
    <div id="addListingPage" class="page">
        <main class="container mx-auto px-4 py-8">
            <div class="max-w-4xl mx-auto">
                <div class="bg-white rounded-lg shadow-md p-8">
                    <h1 class="text-3xl font-bold mb-8 text-center">📝 ثبت آگهی جدید</h1>
                    
                    <form class="space-y-6">
                        <!-- Category Selection -->
                        <div>
                            <label class="block text-gray-700 font-bold mb-2">دسته‌بندی *</label>
                            <select required class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500" onchange="updateSubcategories(this.value)">
                                <option value="">انتخاب کنید</option>
                                <option value="fashion">👕 پوشاک و مد</option>
                                <option value="vehicles">🚗 وسایل نقلیه</option>
                                <option value="real-estate">🏠 املاک و زمین</option>
                                <option value="digital">📱 دیجیتال و فناوری</option>
                                <option value="electronics">📺 الکترونیک</option>
                                <option value="furniture">🛋️ مبلمان و دکوراسیون</option>
                                <option value="home">🏡 وسایل خانه</option>
                                <option value="sports">⚽ ورزش و تفریح</option>
                            </select>
                        </div>

                        <!-- Subcategory -->
                        <div id="subcategoryDiv" class="hidden">
                            <label class="block text-gray-700 font-bold mb-2">زیر دسته *</label>
                            <select id="subcategorySelect" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                                <option value="">انتخاب کنید</option>
                            </select>
                        </div>

                        <!-- Title -->
                        <div>
                            <label class="block text-gray-700 font-bold mb-2">عنوان آگهی *</label>
                            <input type="text" required placeholder="مثال: آیفون 14 پرو مکس 256 گیگ" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                        </div>

                        <!-- Description -->
                        <div>
                            <label class="block text-gray-700 font-bold mb-2">توضیحات *</label>
                            <textarea required rows="5" placeholder="توضیحات کامل محصول خود را بنویسید..." class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500"></textarea>
                        </div>

                        <!-- Price -->
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">قیمت (افغانی) *</label>
                                <input type="number" required placeholder="50000" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                            </div>
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">وضعیت *</label>
                                <select required class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                                    <option value="">انتخاب کنید</option>
                                    <option value="new">نو</option>
                                    <option value="used">دست دوم</option>
                                    <option value="refurbished">بازسازی شده</option>
                                </select>
                            </div>
                        </div>

                        <!-- Location -->
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">شهر *</label>
                                <select required class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                                    <option value="">انتخاب کنید</option>
                                    <option value="kabul">کابل</option>
                                    <option value="herat">هرات</option>
                                    <option value="mazar">مزار شریف</option>
                                    <option value="kandahar">قندهار</option>
                                    <option value="jalalabad">جلال آباد</option>
                                    <option value="kunduz">کندز</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">منطقه</label>
                                <input type="text" placeholder="مثال: شهر نو" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                            </div>
                        </div>

                        <!-- Media Upload Section -->
                        <div class="space-y-6">
                            <!-- Images -->
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">تصاویر</label>
                                <div class="border-2 border-dashed border-gray-300 rounded-lg p-8 text-center video-upload-area" id="imageUploadArea">
                                    <div class="text-4xl mb-4">📷</div>
                                    <p class="text-gray-600 mb-4">تصاویر خود را اینجا بکشید یا کلیک کنید</p>
                                    <input type="file" multiple accept="image/*" class="hidden" id="imageUpload">
                                    <button type="button" onclick="document.getElementById('imageUpload').click()" class="bg-orange-500 text-white px-6 py-2 rounded-lg hover:bg-orange-600 transition">
                                        انتخاب تصاویر
                                    </button>
                                    <p class="text-sm text-gray-500 mt-2">حداکثر 10 تصویر - فرمت JPG, PNG</p>
                                </div>
                                <div id="imagePreview" class="grid grid-cols-2 md:grid-cols-4 gap-4 mt-4 hidden"></div>
                            </div>

                            <!-- Video Upload -->
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">ویدیو کوتاه (اختیاری)</label>
                                <div class="border-2 border-dashed border-gray-300 rounded-lg p-8 text-center video-upload-area" id="videoUploadArea">
                                    <div class="text-4xl mb-4">📹</div>
                                    <p class="text-gray-600 mb-4">ویدیو کوتاه محصول خود را آپلود کنید</p>
                                    <input type="file" accept="video/*" class="hidden" id="videoUpload">
                                    <button type="button" onclick="document.getElementById('videoUpload').click()" class="bg-blue-500 text-white px-6 py-2 rounded-lg hover:bg-blue-600 transition">
                                        انتخاب ویدیو
                                    </button>
                                    <p class="text-sm text-gray-500 mt-2">حداکثر 30 ثانیه - فرمت MP4, MOV</p>
                                </div>
                                <div id="videoPreview" class="mt-4 hidden">
                                    <video class="video-preview" controls></video>
                                    <div class="flex items-center justify-between mt-2">
                                        <span id="videoInfo" class="text-sm text-gray-600"></span>
                                        <button type="button" onclick="removeVideo()" class="text-red-500 hover:text-red-700">
                                            🗑️ حذف
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Contact Info -->
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">شماره تماس *</label>
                                <input type="tel" required placeholder="+93 XXX XXX XXX" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                            </div>
                            <div>
                                <label class="block text-gray-700 font-bold mb-2">نام تماس</label>
                                <input type="text" placeholder="نام شما" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                            </div>
                        </div>

                        <!-- Premium Options -->
                        <div class="bg-yellow-50 border border-yellow-200 rounded-lg p-6">
                            <h3 class="font-bold mb-4">🌟 گزینه‌های ویژه</h3>
                            <div class="space-y-3">
                                <label class="flex items-center">
                                    <input type="checkbox" class="ml-2">
                                    <span>نمایش در بالای صفحه (+500 افغانی)</span>
                                </label>
                                <label class="flex items-center">
                                    <input type="checkbox" class="ml-2">
                                    <span>برجسته کردن آگهی (+300 افغانی)</span>
                                </label>
                                <label class="flex items-center">
                                    <input type="checkbox" class="ml-2">
                                    <span>نمایش در صفحه اول (+200 افغانی)</span>
                                </label>
                                <label class="flex items-center">
                                    <input type="checkbox" class="ml-2">
                                    <span>پشتیبانی از ویدیو (+100 افغانی)</span>
                                </label>
                            </div>
                        </div>

                        <!-- Terms -->
                        <div>
                            <label class="flex items-center">
                                <input type="checkbox" required class="ml-2">
                                <span>قوانین و مقررات دریچه را می‌پذیرم *</span>
                            </label>
                        </div>

                        <!-- Submit Buttons -->
                        <div class="flex space-x-4 space-x-reverse">
                            <button type="submit" class="flex-1 bg-orange-500 text-white py-3 rounded-lg font-bold hover:bg-orange-600 transition">
                                انتشار آگهی
                            </button>
                            <button type="button" class="flex-1 bg-gray-500 text-white py-3 rounded-lg font-bold hover:bg-gray-600 transition">
                                پیش‌نمایش
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </main>
    </div>

    <!-- Login Modal -->
    <div id="loginModal" class="modal">
        <div class="auth-form max-w-md w-full mx-4">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-2xl font-bold">ورود به حساب</h2>
                <button onclick="closeModal('loginModal')" class="text-2xl">&times;</button>
            </div>
            
            <form id="loginForm" class="space-y-4">
                <div>
                    <label class="block text-gray-700 font-bold mb-2">شماره موبایل</label>
                    <input type="tel" required placeholder="+93 XXX XXX XXX" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                </div>
                
                <div>
                    <label class="block text-gray-700 font-bold mb-2">رمز عبور</label>
                    <input type="password" required placeholder="رمز عبور" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                </div>
                
                <div class="flex items-center justify-between">
                    <label class="flex items-center">
                        <input type="checkbox" class="ml-2">
                        <span class="text-sm">مرا به خاطر بسپار</span>
                    </label>
                    <button type="button" onclick="openModal('forgotPasswordModal')" class="text-sm text-orange-500 hover:text-orange-600">
                        فراموشی رمز عبور؟
                    </button>
                </div>
                
                <button type="submit" class="w-full bg-blue-500 text-white py-3 rounded-lg font-bold hover:bg-blue-600 transition">
                    ورود
                </button>
                
                <div class="text-center">
                    <span class="text-gray-600">حساب ندارید؟ </span>
                    <button type="button" onclick="switchToRegister()" class="text-orange-500 hover:text-orange-600 font-bold">
                        ثبت نام کنید
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- Register Modal -->
    <div id="registerModal" class="modal">
        <div class="auth-form max-w-md w-full mx-4">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-2xl font-bold">ثبت نام</h2>
                <button onclick="closeModal('registerModal')" class="text-2xl">&times;</button>
            </div>
            
            <form id="registerForm" class="space-y-4">
                <div>
                    <label class="block text-gray-700 font-bold mb-2">نام و نام خانوادگی</label>
                    <input type="text" required placeholder="نام کامل" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                </div>
                
                <div>
                    <label class="block text-gray-700 font-bold mb-2">شماره موبایل</label>
                    <input type="tel" required placeholder="+93 XXX XXX XXX" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                </div>
                
                <div>
                    <label class="block text-gray-700 font-bold mb-2">شهر</label>
                    <select required class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                        <option value="">انتخاب کنید</option>
                        <option value="kabul">کابل</option>
                        <option value="herat">هرات</option>
                        <option value="mazar">مزار شریف</option>
                        <option value="kandahar">قندهار</option>
                        <option value="jalalabad">جلال آباد</option>
                        <option value="kunduz">کندز</option>
                    </select>
                </div>
                
                <div>
                    <label class="block text-gray-700 font-bold mb-2">رمز عبور</label>
                    <input type="password" required placeholder="رمز عبور" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                </div>
                
                <div>
                    <label class="block text-gray-700 font-bold mb-2">تکرار رمز عبور</label>
                    <input type="password" required placeholder="تکرار رمز عبور" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:border-orange-500">
                </div>
                
                <div>
                    <label class="flex items-center">
                        <input type="checkbox" required class="ml-2">
                        <span class="text-sm">قوانین و مقررات را می‌پذیرم</span>
                    </label>
                </div>
                
                <button type="submit" class="w-full bg-green-500 text-white py-3 rounded-lg font-bold hover:bg-green-600 transition">
                    ثبت نام
                </button>
                
                <div class="text-center">
                    <span class="text-gray-600">حساب دارید؟ </span>
                    <button type="button" onclick="switchToLogin()" class="text-orange-500 hover:text-orange-600 font-bold">
                        وارد شوید
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- Other existing modals... -->
    <!-- (Premium, Wallet, Delivery modals remain the same) -->

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-12 mt-16">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <div>
                    <div class="text-2xl font-bold logo-3d mb-4">
                        <span class="bell-decoration">🔔</span>
                        دریچه
                        <span class="bell-decoration">🔔</span>
                    </div>
                    <p class="text-gray-400">بزرگترین بازار آنلاین افغانستان</p>
                </div>
                
                <div>
                    <h3 class="font-bold mb-4">دسته‌بندی‌ها</h3>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" class="hover:text-white">پوشاک و مد</a></li>
                        <li><a href="#" class="hover:text-white">وسایل نقلیه</a></li>
                        <li><a href="#" class="hover:text-white">املاک و زمین</a></li>
                        <li><a href="#" class="hover:text-white">الکترونیک</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="font-bold mb-4">خدمات</h3>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" class="hover:text-white">خرید و فروش</a></li>
                        <li><a href="#" class="hover:text-white">حمل و نقل</a></li>
                        <li><a href="#" class="hover:text-white">کیف پول</a></li>
                        <li><a href="#" class="hover:text-white">عضویت ویژه</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="font-bold mb-4">تماس</h3>
                    <div class="space-y-2 text-gray-400">
                        <div>📞 +93 XXX XXX XXX</div>
                        <div>📧 info@dariche.af</div>
                        <div>📍 کابل، افغانستان</div>
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-700 mt-8 pt-8 text-center text-gray-400">
                <p>&copy; 2024 دریچه. تمامی حقوق محفوظ است.</p>
            </div>
        </div>
    </footer>

    <script>
        // Global variables
        let currentUser = null;
        let uploadedImages = [];
        let uploadedVideo = null;

        // Subcategory data
        const subcategories = {
            fashion: [
                { value: 'mens-clothing', text: '👔 لباس مردانه' },
                { value: 'womens-clothing', text: '👗 لباس زنانه' },
                { value: 'shoes', text: '👟 کفش' },
                { value: 'accessories', text: '💍 اکسسوری' },
                { value: 'bags', text: '👜 کیف' }
            ],
            vehicles: [
                { value: 'cars', text: '🚗 خودرو' },
                { value: 'motorcycles', text: '🏍️ موتورسیکلت' },
                { value: 'bicycles', text: '🚲 دوچرخه' },
                { value: 'trucks', text: '🚛 کامیون' },
                { value: 'parts', text: '🔧 قطعات' }
            ],
            'real-estate': [
                { value: 'houses', text: '🏡 خانه' },
                { value: 'apartments', text: '🏢 آپارتمان' },
                { value: 'land', text: '🌾 زمین' },
                { value: 'commercial', text: '🏪 تجاری' },
                { value: 'rent', text: '🔑 اجاره' }
            ],
            digital: [
                { value: 'mobile', text: '📱 موبایل' },
                { value: 'laptop', text: '💻 لپ تاپ' },
                { value: 'tablet', text: '📟 تبلت' },
                { value: 'gaming', text: '🎮 گیمینگ' },
                { value: 'accessories-tech', text: '🔌 لوازم جانبی' }
            ],
            electronics: [
                { value: 'tv', text: '📺 تلویزیون' },
                { value: 'refrigerator', text: '❄️ یخچال' },
                { value: 'washing-machine', text: '🌀 ماشین لباسشویی' },
                { value: 'air-conditioner', text: '❄️ کولر' },
                { value: 'kitchen-appliances', text: '🍳 لوازم آشپزخانه' }
            ],
            furniture: [
                { value: 'sofa', text: '🛋️ مبل' },
                { value: 'bed', text: '🛏️ تخت' },
                { value: 'table', text: '🪑 میز و صندلی' },
                { value: 'wardrobe', text: '🚪 کمد' },
                { value: 'decoration', text: '🖼️ دکوراسیون' }
            ],
            home: [
                { value: 'kitchen', text: '🍳 آشپزخانه' },
                { value: 'bathroom', text: '🚿 حمام' },
                { value: 'cleaning', text: '🧽 نظافت' },
                { value: 'garden', text: '🌱 باغبانی' },
                { value: 'tools', text: '🔨 ابزار' }
            ],
            sports: [
                { value: 'fitness', text: '🏋️ بدنسازی' },
                { value: 'outdoor', text: '🏕️ فضای باز' },
                { value: 'games', text: '🎲 بازی' },
                { value: 'music', text: '🎵 موسیقی' },
                { value: 'books', text: '📚 کتاب' }
            ]
        };

        // Page navigation
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            const targetPage = pageId + 'Page';
            document.getElementById(targetPage).classList.add('active');
        }

        // Category functions
        function toggleSubcategories(categoryId) {
            const subcategoryDiv = document.getElementById(categoryId + '-sub');
            subcategoryDiv.classList.toggle('active');
            
            // Close other subcategories
            document.querySelectorAll('.subcategory-list').forEach(list => {
                if (list.id !== categoryId + '-sub') {
                    list.classList.remove('active');
                }
            });
        }

        function showCategoryPage(category) {
            showPage('categories');
        }

        function updateSubcategories(category) {
            const subcategoryDiv = document.getElementById('subcategoryDiv');
            const subcategorySelect = document.getElementById('subcategorySelect');
            
            if (category && subcategories[category]) {
                subcategoryDiv.classList.remove('hidden');
                subcategorySelect.innerHTML = '<option value="">انتخاب کنید</option>';
                
                subcategories[category].forEach(sub => {
                    const option = document.createElement('option');
                    option.value = sub.value;
                    option.textContent = sub.text;
                    subcategorySelect.appendChild(option);
                });
            } else {
                subcategoryDiv.classList.add('hidden');
            }
        }

        // Authentication functions
        function switchToRegister() {
            closeModal('loginModal');
            openModal('registerModal');
        }

        function switchToLogin() {
            closeModal('registerModal');
            openModal('loginModal');
        }

        function login(userData) {
            currentUser = userData;
            document.getElementById('authButtons').classList.add('hidden');
            document.getElementById('userProfile').classList.remove('hidden');
            document.getElementById('userName').textContent = userData.name;
            document.getElementById('userInitial').textContent = userData.name.charAt(0);
            
            showNotification(`خوش آمدید ${userData.name}!`, 'success');
        }

        function logout() {
            currentUser = null;
            document.getElementById('authButtons').classList.remove('hidden');
            document.getElementById('userProfile').classList.add('hidden');
            
            // Close user menu
            document.querySelector('.dropdown').classList.remove('active');
            
            showNotification('با موفقیت خارج شدید', 'info');
        }

        function toggleUserMenu() {
            document.querySelector('.dropdown').classList.toggle('active');
        }

        // Media upload functions
        function setupImageUpload() {
            const imageUpload = document.getElementById('imageUpload');
            const imageUploadArea = document.getElementById('imageUploadArea');
            const imagePreview = document.getElementById('imagePreview');

            imageUpload.addEventListener('change', function(e) {
                const files = Array.from(e.target.files);
                files.forEach(file => {
                    if (uploadedImages.length < 10) {
                        uploadedImages.push(file);
                        displayImagePreview(file);
                    }
                });
                updateImagePreviewVisibility();
            });

            // Drag and drop
            imageUploadArea.addEventListener('dragover', function(e) {
                e.preventDefault();
                imageUploadArea.classList.add('dragover');
            });

            imageUploadArea.addEventListener('dragleave', function(e) {
                e.preventDefault();
                imageUploadArea.classList.remove('dragover');
            });

            imageUploadArea.addEventListener('drop', function(e) {
                e.preventDefault();
                imageUploadArea.classList.remove('dragover');
                
                const files = Array.from(e.dataTransfer.files);
                files.forEach(file => {
                    if (file.type.startsWith('image/') && uploadedImages.length < 10) {
                        uploadedImages.push(file);
                        displayImagePreview(file);
                    }
                });
                updateImagePreviewVisibility();
            });
        }

        function displayImagePreview(file) {
            const imagePreview = document.getElementById('imagePreview');
            const reader = new FileReader();
            
            reader.onload = function(e) {
                const div = document.createElement('div');
                div.className = 'relative';
                div.innerHTML = `
                    <img src="${e.target.result}" class="w-full h-24 object-cover rounded-lg">
                    <button type="button" onclick="removeImage(${uploadedImages.length - 1})" 
                            class="absolute top-1 right-1 bg-red-500 text-white rounded-full w-6 h-6 flex items-center justify-center text-sm hover:bg-red-600">
                        ×
                    </button>
                `;
                imagePreview.appendChild(div);
            };
            
            reader.readAsDataURL(file);
        }

        function removeImage(index) {
            uploadedImages.splice(index, 1);
            updateImagePreview();
        }

        function updateImagePreview() {
            const imagePreview = document.getElementById('imagePreview');
            imagePreview.innerHTML = '';
            
            uploadedImages.forEach((file, index) => {
                displayImagePreview(file);
            });
            
            updateImagePreviewVisibility();
        }

        function updateImagePreviewVisibility() {
            const imagePreview = document.getElementById('imagePreview');
            if (uploadedImages.length > 0) {
                imagePreview.classList.remove('hidden');
            } else {
                imagePreview.classList.add('hidden');
            }
        }

        function setupVideoUpload() {
            const videoUpload = document.getElementById('videoUpload');
            const videoUploadArea = document.getElementById('videoUploadArea');
            const videoPreview = document.getElementById('videoPreview');

            videoUpload.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file && file.type.startsWith('video/')) {
                    // Check file size (max 50MB)
                    if (file.size > 50 * 1024 * 1024) {
                        alert('حجم ویدیو نباید بیشتر از 50 مگابایت باشد');
                        return;
                    }
                    
                    uploadedVideo = file;
                    displayVideoPreview(file);
                }
            });

            // Drag and drop for video
            videoUploadArea.addEventListener('dragover', function(e) {
                e.preventDefault();
                videoUploadArea.classList.add('dragover');
            });

            videoUploadArea.addEventListener('dragleave', function(e) {
                e.preventDefault();
                videoUploadArea.classList.remove('dragover');
            });

            videoUploadArea.addEventListener('drop', function(e) {
                e.preventDefault();
                videoUploadArea.classList.remove('dragover');
                
                const file = e.dataTransfer.files[0];
                if (file && file.type.startsWith('video/')) {
                    if (file.size > 50 * 1024 * 1024) {
                        alert('حجم ویدیو نباید بیشتر از 50 مگابایت باشد');
                        return;
                    }
                    
                    uploadedVideo = file;
                    displayVideoPreview(file);
                }
            });
        }

        function displayVideoPreview(file) {
            const videoPreview = document.getElementById('videoPreview');
            const videoElement = videoPreview.querySelector('video');
            const videoInfo = document.getElementById('videoInfo');
            
            const url = URL.createObjectURL(file);
            videoElement.src = url;
            
            // Get video duration
            videoElement.addEventListener('loadedmetadata', function() {
                const duration = Math.round(videoElement.duration);
                const size = (file.size / (1024 * 1024)).toFixed(2);
                videoInfo.textContent = `مدت: ${duration} ثانیه | حجم: ${size} مگابایت`;
                
                if (duration > 30) {
                    alert('مدت ویدیو نباید بیشتر از 30 ثانیه باشد');
                    removeVideo();
                    return;
                }
            });
            
            videoPreview.classList.remove('hidden');
        }

        function removeVideo() {
            uploadedVideo = null;
            const videoPreview = document.getElementById('videoPreview');
            const videoElement = videoPreview.querySelector('video');
            
            if (videoElement.src) {
                URL.revokeObjectURL(videoElement.src);
            }
            
            videoElement.src = '';
            videoPreview.classList.add('hidden');
            document.getElementById('videoUpload').value = '';
        }

        // Modal functions
        function openModal(modalId) {
            document.getElementById(modalId).classList.add('active');
        }
        
        function closeModal(modalId) {
            document.getElementById(modalId).classList.remove('active');
        }
        
        // City dropdown functions
        function toggleCityMenu() {
            const dropdown = document.getElementById('cityDropdown');
            dropdown.classList.toggle('hidden');
        }
        
        function selectCityFromMenu(cityName, cityIcon) {
            document.getElementById('selectedCityName').textContent = cityName;
            document.getElementById('selectedCityIcon').textContent = cityIcon;
            document.getElementById('cityDropdown').classList.add('hidden');
            
            showNotification(`شهر ${cityName} انتخاب شد!`, 'success');
        }
        
        // Form submissions
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const formData = new FormData(e.target);
            const phone = formData.get('tel');
            
            // Simulate login
            login({
                name: 'احمد رضایی',
                phone: phone,
                city: 'کابل'
            });
            
            closeModal('loginModal');
        });

        document.getElementById('registerForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const formData = new FormData(e.target);
            const name = e.target.querySelector('input[type="text"]').value;
            const phone = e.target.querySelector('input[type="tel"]').value;
            
            // Simulate registration
            login({
                name: name,
                phone: phone,
                city: 'کابل'
            });
            
            closeModal('registerModal');
        });
        
        // Close dropdowns when clicking outside
        document.addEventListener('click', function(e) {
            // Close city dropdown
            const citySelector = e.target.closest('#cityDropdown') || e.target.closest('button[onclick="toggleCityMenu()"]');
            if (!citySelector) {
                document.getElementById('cityDropdown').classList.add('hidden');
            }
            
            // Close user menu
            const userMenu = e.target.closest('.dropdown') || e.target.closest('button[onclick="toggleUserMenu()"]');
            if (!userMenu) {
                document.querySelector('.dropdown').classList.remove('active');
            }
        });
        
        // Close modals when clicking outside
        document.querySelectorAll('.modal').forEach(modal => {
            modal.addEventListener('click', function(e) {
                if (e.target === modal) {
                    modal.classList.remove('active');
                }
            });
        });
        
        // Notification system
        function showNotification(message, type = 'info') {
            const notification = document.createElement('div');
            notification.className = `fixed top-4 right-4 z-50 p-4 rounded-lg text-white ${
                type === 'success' ? 'bg-green-500' : 
                type === 'error' ? 'bg-red-500' : 'bg-blue-500'
            }`;
            notification.textContent = message;
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.remove();
            }, 3000);
        }
        
        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            setupImageUpload();
            setupVideoUpload();
            
            setTimeout(() => {
                showNotification('به دریچه خوش آمدید! بزرگترین بازار آنلاین افغانستان', 'success');
            }, 1000);
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9628e4f52275908f',t:'MTc1MzA4MTk5My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
