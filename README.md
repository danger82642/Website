<!DOCTYPE html>
<html lang="bn" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>রেশমি ক্রাফটস - সিল্ক থ্রেড চুড়ির অনলাইন শপ ও এডমিন সফটওয়্যার</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for Bengali & English -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Anek+Bangla:wght@300;400;500;600;700;800&family=Cinzel:wght@600;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        maroon: {
                            50: '#fdf2f2',
                            100: '#fde8e8',
                            600: '#9b1c1c',
                            700: '#771d1d',
                            800: '#5c1010',
                            900: '#420b0b',
                            950: '#260404',
                        },
                        gold: {
                            200: '#fef08a',
                            300: '#fde047',
                            400: '#facc15',
                            500: '#eab308',
                            600: '#ca8a04',
                            700: '#a16207',
                        },
                        cream: '#fffdf7'
                    },
                    fontFamily: {
                        bangla: ['"Anek Bangla"', 'sans-serif'],
                        cinzel: ['"Cinzel"', 'serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            font-family: 'Anek Bangla', sans-serif;
            background-color: #fffdf7;
            color: #260404;
        }
        .gold-text {
            background: linear-gradient(135deg, #d4af37 0%, #fff3a8 50%, #aa771c 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #fde8e8;
        }
        ::-webkit-scrollbar-thumb {
            background: #771d1d;
            border-radius: 4px;
        }
        .admin-badge {
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
    </style>
</head>
<body class="antialiased min-h-screen flex flex-col selection:bg-gold-500 selection:text-maroon-950">

    <!-- Top Announcement Bar -->
    <div class="bg-maroon-950 text-xs py-2 px-4 text-center text-gold-300 font-medium border-b border-maroon-800 flex justify-between items-center max-w-7xl mx-auto w-full">
        <span class="flex items-center gap-1.5">
            <i class="fas fa-bullhorn text-gold-400"></i>
            <span id="displayAnnouncement">সারা বাংলাদেশে ক্যাশ অন ডেলিভারি সার্ভিস উপলব্ধ!</span>
        </span>
        <div class="flex items-center gap-4">
            <span class="hidden sm:inline-block"><i class="fas fa-phone-alt mr-1"></i> হেল্পলাইন: <span class="displayPhone">01792457935</span></span>
            <button onclick="openAdminAuth()" class="bg-gold-500/20 hover:bg-gold-500/30 text-gold-300 px-2.5 py-1 rounded text-[11px] border border-gold-500/40 flex items-center gap-1">
                <i class="fas fa-user-shield text-gold-400"></i>
                <span id="adminNavBtnText">এডমিন লগইন</span>
            </button>
        </div>
    </div>

    <!-- Main Navigation Header -->
    <header class="sticky top-0 z-40 bg-maroon-900 text-gold-300 shadow-xl border-b border-gold-600/30 backdrop-blur-md bg-opacity-95">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                
                <!-- Brand Logo & Title -->
                <a href="#" onclick="scrollToTop()" class="flex items-center space-x-3 group">
                    <div class="w-11 h-11 rounded-full border-2 border-gold-400 p-1 flex items-center justify-center bg-maroon-950 shadow-inner">
                        <i class="fas fa-ring text-xl text-gold-400 group-hover:rotate-45 transition duration-500"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-bold font-cinzel tracking-wider gold-text" id="displayShopName">রেশমি ক্রাফটস</h1>
                        <p class="text-[10px] text-gold-400/80 tracking-widest uppercase -mt-1 font-semibold">Reshmi Crafts • Silk Thread Bangles</p>
                    </div>
                </a>

                <!-- Desktop Navigation Menu -->
                <nav class="hidden lg:flex items-center space-x-8 font-medium text-sm">
                    <a href="#" class="text-gold-300 hover:text-white transition">হোম</a>
                    <a href="#catalog" class="text-gold-300/90 hover:text-white transition">চুড়ির কালেকশন</a>
                    <a href="#customizer" class="text-gold-300/90 hover:text-white transition flex items-center gap-1">
                        <i class="fas fa-magic text-xs text-gold-400"></i> কাস্টমাইজেশন
                    </a>
                    <a href="#about" class="text-gold-300/90 hover:text-white transition">আমাদের কথা</a>
                    <a href="#contact" class="text-gold-300/90 hover:text-white transition">যোগাযোগ</a>
                </nav>

                <!-- Actions (Search, Cart & Admin Mode) -->
                <div class="flex items-center space-x-3">
                    <!-- Search Input -->
                    <div class="hidden sm:block relative w-44 lg:w-56">
                        <input type="text" id="searchInput" onkeyup="filterProducts()" placeholder="চুড়ি খুঁজুন..." 
                            class="w-full bg-maroon-950/90 text-gold-100 placeholder-gold-600/60 border border-gold-600/40 rounded-full py-1.5 pl-4 pr-9 text-xs focus:outline-none focus:border-gold-400">
                        <i class="fas fa-search absolute right-3 top-2.5 text-xs text-gold-500"></i>
                    </div>

                    <!-- Cart Trigger Button -->
                    <button onclick="toggleCartModal()" class="relative p-2 text-gold-300 hover:text-gold-100 transition focus:outline-none bg-maroon-950/60 rounded-full border border-gold-500/30 px-3 py-2 flex items-center gap-2">
                        <i class="fas fa-shopping-bag text-lg text-gold-400"></i>
                        <span class="text-xs font-bold hidden sm:inline">কার্ট</span>
                        <span id="cartBadge" class="bg-gold-500 text-maroon-950 text-xs font-bold w-5 h-5 rounded-full flex items-center justify-center shadow-md">0</span>
                    </button>

                    <!-- Mobile Menu Button -->
                    <button onclick="toggleMobileMenu()" class="lg:hidden p-2 text-gold-400 hover:text-white">
                        <i class="fas fa-bars text-xl"></i>
                    </button>
                </div>
            </div>

            <!-- Mobile Navigation Drawer -->
            <div id="mobileMenu" class="hidden lg:hidden pb-4 pt-2 border-t border-maroon-800 space-y-2">
                <a href="#" onclick="toggleMobileMenu()" class="block py-2 text-sm text-gold-200">হোম</a>
                <a href="#catalog" onclick="toggleMobileMenu()" class="block py-2 text-sm text-gold-200">চুড়ির কালেকশন</a>
                <a href="#customizer" onclick="toggleMobileMenu()" class="block py-2 text-sm text-gold-200">কাস্টমাইজেশন স্টুডিও</a>
                <a href="#about" onclick="toggleMobileMenu()" class="block py-2 text-sm text-gold-200">আমাদের কথা</a>
                <a href="#contact" onclick="toggleMobileMenu()" class="block py-2 text-sm text-gold-200">যোগাযোগ</a>
                <div class="pt-2">
                    <input type="text" id="searchInputMobile" onkeyup="filterProductsMobile()" placeholder="চুড়ি খুঁজুন..." 
                        class="w-full bg-maroon-950 text-gold-100 placeholder-gold-600/60 border border-gold-600/40 rounded-lg py-2 px-4 text-xs">
                </div>
            </div>
        </div>
    </header>

    <!-- ADMIN PANEL / MANAGEMENT SOFTWARE DRAWER (Visible when Admin Mode Active) -->
    <div id="adminPanelSection" class="hidden bg-maroon-950 border-b-4 border-gold-500 text-gold-100 py-6 px-4 sm:px-8 shadow-2xl relative">
        <div class="max-w-7xl mx-auto space-y-6">
            <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center border-b border-gold-600/40 pb-4 gap-4">
                <div>
                    <span class="bg-gold-500 text-maroon-950 text-[10px] font-bold px-2 py-0.5 rounded uppercase font-mono">Software Mode</span>
                    <h2 class="text-2xl font-bold text-gold-300 font-serif flex items-center gap-2">
                        <i class="fas fa-sliders-h"></i> রেশমি ক্রাফটস - এডমিন ড্যাশবোর্ড
                    </h2>
                    <p class="text-xs text-gold-200/70">এখান থেকে আপনি ওয়েবসাইট এডিট, নতুন প্রোডাক্ট যোগ এবং কাস্টমারের অর্ডার হ্যান্ডেল করতে পারবেন।</p>
                </div>
                <div class="flex items-center gap-3">
                    <button onclick="openProductModal()" class="bg-gold-500 hover:bg-gold-400 text-maroon-950 font-bold px-4 py-2 rounded-xl text-xs flex items-center gap-2 shadow">
                        <i class="fas fa-plus-circle"></i> নতুন চুড়ি প্রোডাক্ট যোগ করুন
                    </button>
                    <button onclick="logoutAdmin()" class="bg-red-700 hover:bg-red-800 text-white font-bold px-3 py-2 rounded-xl text-xs flex items-center gap-1">
                        <i class="fas fa-sign-out-alt"></i> লগআউট
                    </button>
                </div>
            </div>

            <!-- Admin Sub-tabs -->
            <div class="flex space-x-2 border-b border-maroon-800 text-xs font-bold">
                <button onclick="switchAdminTab('products')" id="adminTab-products" class="px-4 py-2 text-gold-300 border-b-2 border-gold-400">প্রোডাক্ট লিস্ট (<span id="adminProductCount">0</span>)</button>
                <button onclick="switchAdminTab('orders')" id="adminTab-orders" class="px-4 py-2 text-gold-400/70 hover:text-gold-300">অর্ডার সমূহ (<span id="adminOrderCount">0</span>)</button>
                <button onclick="switchAdminTab('settings')" id="adminTab-settings" class="px-4 py-2 text-gold-400/70 hover:text-gold-300">শপ সেটিংস ও এড্রেস এডিট</button>
            </div>

            <!-- TAB 1: Product List Table -->
            <div id="adminTabContent-products" class="overflow-x-auto">
                <table class="w-full text-left text-xs text-gold-100">
                    <thead class="bg-maroon-900 text-gold-300 border-b border-maroon-700">
                        <tr>
                            <th class="p-3">চুড়ির ছবি</th>
                            <th class="p-3">নাম</th>
                            <th class="p-3">ক্যাটাগরি</th>
                            <th class="p-3">মূল্য</th>
                            <th class="p-3">পিস/সেট</th>
                            <th class="p-3 text-center">একশন</th>
                        </tr>
                    </thead>
                    <tbody id="adminProductTableBody" class="divide-y divide-maroon-900">
                        <!-- Javascript Will Populate -->
                    </tbody>
                </table>
            </div>

            <!-- TAB 2: Order Management Table -->
            <div id="adminTabContent-orders" class="hidden overflow-x-auto">
                <table class="w-full text-left text-xs text-gold-100">
                    <thead class="bg-maroon-900 text-gold-300 border-b border-maroon-700">
                        <tr>
                            <th class="p-3">আইডি ও তারিখ</th>
                            <th class="p-3">গ্রাহকের নাম ও ফোন</th>
                            <th class="p-3">ঠিকানা</th>
                            <th class="p-3">অর্ডার আইটেম</th>
                            <th class="p-3">মোট টাকা ও পেমেন্ট</th>
                            <th class="p-3">স্ট্যাটাস</th>
                        </tr>
                    </thead>
                    <tbody id="adminOrderTableBody" class="divide-y divide-maroon-900">
                        <!-- Javascript Will Populate -->
                    </tbody>
                </table>
            </div>

            <!-- TAB 3: Business Settings Form -->
            <div id="adminTabContent-settings" class="hidden max-w-2xl bg-maroon-900 p-5 rounded-2xl border border-gold-500/30 space-y-4">
                <h3 class="font-bold text-sm text-gold-300">ওয়েবসাইটের নাম ও ঠিকানা আপডেট করুন</h3>
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-[11px] font-bold text-gold-200 mb-1">দোকানের নাম (Shop Name):</label>
                        <input type="text" id="editShopName" class="w-full bg-maroon-950 border border-gold-600/40 text-gold-100 p-2 rounded text-xs">
                    </div>
                    <div>
                        <label class="block text-[11px] font-bold text-gold-200 mb-1">মোবাইল নাম্বার (Mobile):</label>
                        <input type="text" id="editShopPhone" class="w-full bg-maroon-950 border border-gold-600/40 text-gold-100 p-2 rounded text-xs">
                    </div>
                </div>
                <div>
                    <label class="block text-[11px] font-bold text-gold-200 mb-1">দোকান/ব্যবসার ঠিকানা (Address):</label>
                    <input type="text" id="editShopAddress" class="w-full bg-maroon-950 border border-gold-600/40 text-gold-100 p-2 rounded text-xs">
                </div>
                <div>
                    <label class="block text-[11px] font-bold text-gold-200 mb-1">টপ নোটিশ / অফার ব্যানার বার্তা:</label>
                    <input type="text" id="editShopAnnouncement" class="w-full bg-maroon-950 border border-gold-600/40 text-gold-100 p-2 rounded text-xs">
                </div>
                <button onclick="saveShopSettings()" class="bg-gold-500 hover:bg-gold-400 text-maroon-950 font-bold px-4 py-2 rounded-xl text-xs">
                    তথ্য সেভ করুন
                </button>
            </div>
        </div>
    </div>

    <!-- Hero Banner Section -->
    <section class="relative bg-maroon-950 text-gold-100 overflow-hidden py-12 lg:py-20 border-b border-gold-600/30">
        <div class="absolute inset-0 opacity-10 bg-[radial-gradient(#d97706_1px,transparent_1px)] [background-size:20px_20px]"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 items-center">
                <!-- Text Content -->
                <div class="text-center lg:text-left space-y-5">
                    <div class="inline-flex items-center gap-2 bg-gold-500/10 border border-gold-500/30 rounded-full px-4 py-1 text-gold-300 text-xs font-semibold">
                        <i class="fas fa-crown text-gold-400"></i> ময়মনসিংহের বিশ্বস্ত রেশমি সুতার চুড়ি শপ
                    </div>
                    <h1 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold tracking-tight leading-tight">
                        আপনার সাজে আনুন রাজকীয় আভিজাত্য <br>
                        <span class="gold-text font-serif">হস্তশিল্পের রেশমি সুতার চুড়ি</span>
                    </h1>
                    <p class="text-gold-200/80 text-sm sm:text-base max-w-xl mx-auto lg:mx-0 font-light">
                        গায়ে হলুদ, বিয়ে কিংবা যেকোনো উৎসবে আপনার পোশাকের সাথে মিলিয়ে নিখুঁত হস্তশিল্পের রেশমি সুতার চুড়ি বেছে নিন।
                    </p>
                    <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4 pt-2">
                        <a href="#catalog" class="w-full sm:w-auto px-7 py-3 bg-gradient-to-r from-gold-400 to-gold-600 text-maroon-950 font-bold rounded-full shadow-lg hover:shadow-gold-500/30 transition text-center flex items-center justify-center gap-2 text-sm">
                            <span>কালেকশন দেখুন</span>
                            <i class="fas fa-arrow-right"></i>
                        </a>
                        <a href="#customizer" class="w-full sm:w-auto px-7 py-3 bg-maroon-900/80 text-gold-300 border border-gold-500/40 font-semibold rounded-full transition text-center flex items-center justify-center gap-2 text-sm">
                            <i class="fas fa-magic text-gold-400"></i>
                            <span>কাস্টম অর্ডার করুন</span>
                        </a>
                    </div>
                </div>

                <!-- Hero Bangle Visual -->
                <div class="relative flex justify-center">
                    <div class="w-64 h-64 sm:w-80 sm:h-80 rounded-full bg-gradient-to-tr from-maroon-900 via-gold-600/20 to-maroon-950 p-2 shadow-2xl relative">
                        <div class="w-full h-full rounded-full bg-maroon-950 p-4 flex flex-col items-center justify-center border border-gold-500/40 relative overflow-hidden">
                            
                            <svg class="w-48 h-48 sm:w-60 sm:h-60 drop-shadow-2xl animate-spin-slow" viewBox="0 0 200 200">
                                <circle cx="100" cy="100" r="80" fill="none" stroke="#ca8a04" stroke-width="2" stroke-dasharray="6,4"/>
                                <circle cx="100" cy="100" r="72" fill="none" stroke="#771d1d" stroke-width="20"/>
                                <circle cx="100" cy="100" r="72" fill="none" stroke="#facc15" stroke-width="2" stroke-dasharray="3 10"/>
                                <circle cx="100" cy="28" r="4" fill="#fff" stroke="#eab308" stroke-width="1.5"/>
                                <circle cx="100" cy="172" r="4" fill="#fff" stroke="#eab308" stroke-width="1.5"/>
                                <circle cx="28" cy="100" r="4" fill="#fff" stroke="#eab308" stroke-width="1.5"/>
                                <circle cx="172" cy="100" r="4" fill="#fff" stroke="#eab308" stroke-width="1.5"/>
                                <circle cx="100" cy="100" r="56" fill="none" stroke="#ca8a04" stroke-width="6"/>
                            </svg>
                            
                            <div class="absolute bottom-4 bg-maroon-900/90 border border-gold-500/50 px-3 py-1 rounded-full text-[11px] text-gold-300 font-semibold shadow-lg">
                                👑 ময়মনসিংহে ১০০% হ্যান্ডমেড গহনা
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Main Content Container -->
    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10 flex-grow w-full space-y-16">
        
        <!-- Filter & Product Catalog Section -->
        <section id="catalog" class="scroll-mt-24">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-8 pb-4 border-b border-maroon-900/10 gap-4">
                <div>
                    <span class="text-maroon-700 font-bold text-xs tracking-widest uppercase">আমাদের এক্সক্লুসিভ কালেকশন</span>
                    <h2 class="text-3xl font-bold text-maroon-950 font-serif">সেরা রেশমি সুতার চুড়ি</h2>
                </div>

                <!-- Category Filters & Sorting -->
                <div class="flex flex-wrap items-center gap-3">
                    <div class="inline-flex p-1 bg-maroon-100/70 rounded-xl text-xs font-semibold">
                        <button onclick="setCategory('all')" id="cat-all" class="cat-btn active px-3 py-1.5 rounded-lg bg-maroon-800 text-gold-300 shadow transition">সবগুলো</button>
                        <button onclick="setCategory('bridal')" id="cat-bridal" class="cat-btn px-3 py-1.5 rounded-lg text-maroon-800 hover:text-maroon-950 transition">ব্রাইডাল সেট</button>
                        <button onclick="setCategory('heavy')" id="cat-heavy" class="cat-btn px-3 py-1.5 rounded-lg text-maroon-800 hover:text-maroon-950 transition">কাস্টমাইজড সেট</button>
                        <button onclick="setCategory('simple')" id="cat-simple" class="cat-btn px-3 py-1.5 rounded-lg text-maroon-800 hover:text-maroon-950 transition">ডেইলি ওয়্যার</button>
                        <button onclick="setCategory('kids')" id="cat-kids" class="cat-btn px-3 py-1.5 rounded-lg text-maroon-800 hover:text-maroon-950 transition">কিডস স্পেশাল</button>
                    </div>

                    <select id="sortSelect" onchange="sortProducts()" class="bg-white border border-maroon-200 text-maroon-900 text-xs rounded-xl px-3 py-2 font-medium focus:outline-none">
                        <option value="popular">জনপ্রিয়তা অনুযায়ী</option>
                        <option value="low-high">দাম: কম থেকে বেশি</option>
                        <option value="high-low">দাম: বেশি থেকে কম</option>
                    </select>
                </div>
            </div>

            <!-- Dynamic Product Grid -->
            <div id="productGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
                <!-- Javascript will populate products -->
            </div>
            
            <!-- Empty Search State -->
            <div id="noProducts" class="hidden text-center py-16 bg-white rounded-2xl border border-maroon-100 my-8 shadow-sm">
                <i class="fas fa-search-minus text-4xl text-maroon-400 mb-3"></i>
                <h3 class="text-lg font-bold text-maroon-900">কোনো চুড়ি খুঁজে পাওয়া যায়নি!</h3>
                <p class="text-xs text-gray-500 mt-1">অন্য নাম বা ক্যাটাগরি দিয়ে চেষ্টা করুন।</p>
            </div>
        </section>

        <!-- Interactive Bangle Customization Studio Section -->
        <section id="customizer" class="scroll-mt-24">
            <div class="bg-gradient-to-br from-maroon-950 via-maroon-900 to-maroon-950 text-gold-100 rounded-3xl p-6 sm:p-10 shadow-2xl border border-gold-600/30 relative overflow-hidden">
                <div class="text-center space-y-2 mb-8">
                    <span class="bg-gold-500/20 text-gold-300 text-xs px-3 py-1 rounded-full font-semibold tracking-wide border border-gold-500/30 inline-block">
                        🎨 লাইভ কাস্টমাইজেশন স্টুডিও
                    </span>
                    <h2 class="text-3xl font-bold font-serif gold-text">আপনার ড্রেসের সাথে মিলিয়ে চুড়ি তৈরি করুন</h2>
                    <p class="text-gold-200/80 text-xs sm:text-sm max-w-xl mx-auto">
                        সুতার রঙ, চুড়ির সাইজ এবং পছন্দের কারুকাজ সিলেক্ট করে সরাসরি আপনার পছন্দের চুড়ি তৈরি করুন।
                    </p>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center bg-maroon-900/60 p-6 sm:p-8 rounded-2xl border border-gold-500/20 backdrop-blur-sm">
                    
                    <!-- Left Options -->
                    <div class="lg:col-span-7 space-y-5">
                        
                        <!-- 1. Color Selection -->
                        <div>
                            <label class="block text-xs font-bold text-gold-300 uppercase tracking-wider mb-2">১. সুতার রঙ বেছে নিন:</label>
                            <div class="grid grid-cols-3 sm:grid-cols-6 gap-2">
                                <button type="button" onclick="setCustomColor('#9b1c1c', 'লাল/মেরুন')" class="color-opt active flex flex-col items-center p-2 rounded-xl border-2 border-gold-400 bg-maroon-950 text-xs">
                                    <span class="w-6 h-6 rounded-full bg-red-700 shadow mb-1"></span>
                                    <span class="text-[11px]">মেরুন</span>
                                </button>
                                <button type="button" onclick="setCustomColor('#1e40af', 'রয়্যাল ব্লু')" class="color-opt flex flex-col items-center p-2 rounded-xl border border-gold-600/30 bg-maroon-950 text-xs hover:border-gold-400">
                                    <span class="w-6 h-6 rounded-full bg-blue-700 shadow mb-1"></span>
                                    <span class="text-[11px]">ব্লু</span>
                                </button>
                                <button type="button" onclick="setCustomColor('#047857', 'পান্না সবুজ')" class="color-opt flex flex-col items-center p-2 rounded-xl border border-gold-600/30 bg-maroon-950 text-xs hover:border-gold-400">
                                    <span class="w-6 h-6 rounded-full bg-emerald-700 shadow mb-1"></span>
                                    <span class="text-[11px]">সবুজ</span>
                                </button>
                                <button type="button" onclick="setCustomColor('#d97706', 'বাসন্তী হলুদ')" class="color-opt flex flex-col items-center p-2 rounded-xl border border-gold-600/30 bg-maroon-950 text-xs hover:border-gold-400">
                                    <span class="w-6 h-6 rounded-full bg-amber-500 shadow mb-1"></span>
                                    <span class="text-[11px]">হলুদ</span>
                                </button>
                                <button type="button" onclick="setCustomColor('#db2777', 'গোলাপী')" class="color-opt flex flex-col items-center p-2 rounded-xl border border-gold-600/30 bg-maroon-950 text-xs hover:border-gold-400">
                                    <span class="w-6 h-6 rounded-full bg-pink-600 shadow mb-1"></span>
                                    <span class="text-[11px]">গোলাপী</span>
                                </button>
                                <button type="button" onclick="setCustomColor('#ca8a04', 'সোনালী')" class="color-opt flex flex-col items-center p-2 rounded-xl border border-gold-600/30 bg-maroon-950 text-xs hover:border-gold-400">
                                    <span class="w-6 h-6 rounded-full bg-yellow-600 shadow mb-1"></span>
                                    <span class="text-[11px]">গোল্ডেন</span>
                                </button>
                            </div>
                        </div>

                        <!-- 2. Bangle Size Selection -->
                        <div>
                            <label class="block text-xs font-bold text-gold-300 uppercase tracking-wider mb-2">২. চুড়ির সাইজ (Size):</label>
                            <div class="grid grid-cols-4 gap-2">
                                <button type="button" onclick="setCustomSize('2.2 (Extra Small)')" class="size-opt py-2 text-center text-xs font-bold rounded-xl border border-gold-600/30 bg-maroon-950">2.2</button>
                                <button type="button" onclick="setCustomSize('2.4 (Small)')" class="size-opt py-2 text-center text-xs font-bold rounded-xl border-2 border-gold-400 bg-gold-500 text-maroon-950">2.4</button>
                                <button type="button" onclick="setCustomSize('2.6 (Medium)')" class="size-opt py-2 text-center text-xs font-bold rounded-xl border border-gold-600/30 bg-maroon-950">2.6</button>
                                <button type="button" onclick="setCustomSize('2.8 (Large)')" class="size-opt py-2 text-center text-xs font-bold rounded-xl border border-gold-600/30 bg-maroon-950">2.8</button>
                            </div>
                        </div>

                        <!-- 3. Embellishment Style -->
                        <div>
                            <label class="block text-xs font-bold text-gold-300 uppercase tracking-wider mb-2">৩. কারুকাজ ও অলংকরণ:</label>
                            <select id="customStyleSelect" onchange="updateCustomPreviewStyle()" class="w-full bg-maroon-950 border border-gold-600/40 text-gold-100 rounded-xl py-2.5 px-4 text-xs font-medium focus:outline-none">
                                <option value="mirror">মিরর ও স্টোন ওয়ার্ক (Mirror & Stone)</option>
                                <option value="kundan">প্রিমিয়াম কুন্দন স্ট্রাইপ (Kundan Accent)</option>
                                <option value="simple">সিম্পল রেশমি সুতার জরি বর্ডার</option>
                            </select>
                        </div>

                        <!-- Add Custom Bangle to Cart -->
                        <button onclick="addCustomToCart()" class="w-full py-3.5 bg-gradient-to-r from-gold-400 to-gold-600 hover:from-gold-500 hover:to-gold-700 text-maroon-950 font-bold rounded-xl shadow-lg transition flex items-center justify-center gap-2">
                            <i class="fas fa-shopping-bag"></i>
                            <span>কাস্টমাইজড চুড়ি কার্টে যোগ করুন (৳ ২০০ / জোড়া)</span>
                        </button>
                    </div>

                    <!-- Right Live Canvas -->
                    <div class="lg:col-span-5 flex flex-col items-center justify-center p-6 bg-maroon-950/80 rounded-2xl border border-gold-500/30 relative">
                        <span class="absolute top-3 left-3 text-[10px] bg-gold-500/20 text-gold-300 border border-gold-500/40 px-2 py-0.5 rounded-full">
                            লাইভ প্রিভিউ
                        </span>

                        <div class="w-44 h-44 sm:w-56 sm:h-56 flex items-center justify-center my-4">
                            <svg id="previewBangleSvg" class="w-full h-full drop-shadow-2xl transition-all duration-300" viewBox="0 0 200 200">
                                <circle cx="100" cy="100" r="75" fill="none" stroke="#9b1c1c" stroke-width="22" id="svgMainThread"/>
                                <circle cx="100" cy="100" r="75" fill="none" stroke="#facc15" stroke-width="2" stroke-dasharray="3 10"/>
                                <g id="svgDecorations">
                                    <circle cx="100" cy="25" r="5" fill="#fff" stroke="#ca8a04"/>
                                    <circle cx="100" cy="175" r="5" fill="#fff" stroke="#ca8a04"/>
                                    <circle cx="25" cy="100" r="5" fill="#fff" stroke="#ca8a04"/>
                                    <circle cx="175" cy="100" r="5" fill="#fff" stroke="#ca8a04"/>
                                </g>
                                <circle cx="100" cy="100" r="56" fill="none" stroke="#ca8a04" stroke-width="6"/>
                            </svg>
                        </div>

                        <div class="w-full text-center space-y-1 bg-maroon-900/50 p-2.5 rounded-xl border border-gold-500/20 text-xs">
                            <div class="text-gold-300 font-bold" id="summaryColor">রঙ: লাল/মেরুন</div>
                            <div class="text-gold-200/80" id="summaryDetails">সাইজ: 2.4 (Small) | মিরর ও স্টোন ওয়ার্ক</div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- About Us Section with Specific Address -->
        <section id="about" class="bg-white rounded-3xl p-8 sm:p-12 border border-maroon-900/10 shadow-sm scroll-mt-24">
            <div class="max-w-3xl mx-auto text-center space-y-4">
                <span class="text-maroon-700 font-bold text-xs uppercase tracking-wider">আমাদের পরিচিতি</span>
                <h2 class="text-3xl font-bold font-serif text-maroon-950">রেশমি ক্রাফটস - গৌরীপুর, ময়মনসিংহ</h2>
                <p class="text-gray-600 text-sm leading-relaxed">
                    ময়মনসিংহের গৌরীপুরের বিখ্যাত <b>"গিধাউষা মাস্টার বাড়ি"</b> ভিত্তিক আমাদের নিজস্ব কারখানায় আমরা অত্যন্ত যত্ন সহকারে ১০০% প্রিমিয়াম রেশমি সুতা ও স্টোন ব্যবহার করে চুড়ি তৈরি করি। গ্রাহকের পোশাকের রঙ ও সাইজের সাথে মিলিয়ে চুড়ি কাস্টমাইজ করে পৌঁছে দেওয়া আমাদের প্রধান লক্ষ্য।
                </p>
            </div>
        </section>

    </main>

    <!-- Footer with Business Info -->
    <footer id="contact" class="bg-maroon-950 text-gold-300 border-t border-gold-600/30 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <!-- Brand Info -->
                <div class="space-y-3">
                    <h3 class="text-2xl font-bold font-cinzel gold-text" id="footerShopName">রেশমি ক্রাফটস</h3>
                    <p class="text-xs text-gold-400/80 leading-relaxed">
                        প্রিমিয়াম কোয়ালিটির সিল্ক থ্রেড বা রেশমি সুতার চুড়ি তৈরির অন্যতম বিশ্বস্ত অনলাইন শপ।
                    </p>
                </div>

                <!-- Contact Information (User Requested) -->
                <div class="md:col-span-2 space-y-2">
                    <h4 class="font-bold text-gold-200 text-sm mb-3">যোগাযোগ ও ব্যবসার ঠিকানা</h4>
                    <ul class="space-y-2.5 text-xs text-gold-300">
                        <li class="flex items-start gap-2.5">
                            <i class="fas fa-map-marker-alt text-gold-400 mt-0.5"></i>
                            <span><b>ঠিকানা:</b> <span id="displayAddress">গিধাউষা মাস্টার বাড়ি, গৌরীপুর, ময়মনসিংহ</span></span>
                        </li>
                        <li class="flex items-center gap-2.5">
                            <i class="fas fa-phone-alt text-gold-400"></i>
                            <span><b>মোবাইল / ওয়াটসঅ্যাপ:</b> <span class="displayPhone">01792457935</span></span>
                        </li>
                        <li class="flex items-center gap-2.5">
                            <i class="fas fa-truck text-gold-400"></i>
                            <span>ময়মনসিংহ ও সারা বাংলাদেশে ক্যাশ অন ডেলিভারি দেওয়া হয়।</span>
                        </li>
                    </ul>
                </div>

                <!-- Payment Methods & Admin Toggle -->
                <div>
                    <h4 class="font-bold text-gold-200 text-sm mb-3">পেমেন্ট মেথড</h4>
                    <div class="flex flex-wrap gap-2 text-xs text-maroon-950 font-bold mb-4">
                        <span class="bg-pink-100 text-pink-700 px-2.5 py-1 rounded">bKash</span>
                        <span class="bg-orange-100 text-orange-700 px-2.5 py-1 rounded">Nagad</span>
                        <span class="bg-emerald-100 text-emerald-800 px-2.5 py-1 rounded">Cash on Delivery</span>
                    </div>
                    <button onclick="openAdminAuth()" class="w-full bg-gold-500/10 hover:bg-gold-500/20 text-gold-300 border border-gold-500/40 text-xs py-2 rounded-xl flex items-center justify-center gap-2">
                        <i class="fas fa-lock text-gold-400"></i>
                        <span>এডমিন সফটওয়্যার লগইন</span>
                    </button>
                </div>
            </div>

            <div class="border-t border-maroon-900 pt-6 text-center text-xs text-gold-600">
                &copy; 2026 রেশমি ক্রাফটস (Reshmi Crafts), গৌরীপুর, ময়মনসিংহ। সর্বস্বত্ব সংরক্ষিত।
            </div>
        </div>
    </footer>

    <!-- Shopping Cart Modal Drawer -->
    <div id="cartModal" class="fixed inset-0 z-50 overflow-hidden hidden" role="dialog">
        <div class="absolute inset-0 bg-maroon-950/70 backdrop-blur-sm" onclick="toggleCartModal()"></div>

        <div class="pointer-events-none fixed inset-y-0 right-0 flex max-w-full pl-10">
            <div class="pointer-events-auto w-screen max-w-md bg-white text-maroon-950 shadow-2xl flex flex-col">
                
                <div class="p-4 bg-maroon-950 text-gold-300 flex items-center justify-between border-b border-gold-600/30">
                    <h2 class="text-base font-bold font-serif flex items-center gap-2">
                        <i class="fas fa-shopping-bag text-gold-400"></i> আপনার শপিং ব্যাগ
                    </h2>
                    <button onclick="toggleCartModal()" class="text-gold-400 hover:text-white">
                        <i class="fas fa-times text-lg"></i>
                    </button>
                </div>

                <div class="flex-1 overflow-y-auto p-4 space-y-4" id="cartItemsContainer">
                    <!-- Dynamic cart list -->
                </div>

                <div class="border-t border-gray-200 p-4 bg-maroon-50 space-y-3">
                    <div class="space-y-1.5 text-xs">
                        <div class="flex justify-between text-gray-600">
                            <span>সাবটোটাল:</span>
                            <span id="subTotal" class="font-bold">৳ 0</span>
                        </div>
                        <div class="flex justify-between items-center text-gray-600">
                            <span>ডেলিভারি এলাকা:</span>
                            <select id="deliveryRegion" onchange="updateCartUI()" class="text-xs bg-white border border-gray-300 rounded p-1">
                                <option value="60">ময়মনসিংহ / ঢাকা (৳৬০)</option>
                                <option value="120">ঢাকার বাইরে অন্যান্য জেলা (৳১২০)</option>
                            </select>
                        </div>
                        <div class="flex justify-between text-sm font-extrabold text-maroon-950 pt-2 border-t border-maroon-200">
                            <span>মোট প্রদেয়:</span>
                            <span id="grandTotal" class="text-maroon-800 text-base">৳ 0</span>
                        </div>
                    </div>

                    <button onclick="openCheckoutModal()" class="w-full py-3 bg-maroon-900 hover:bg-maroon-950 text-gold-300 font-bold rounded-xl shadow text-xs flex items-center justify-center gap-2">
                        <i class="fas fa-check-circle"></i>
                        <span>অর্ডার সম্পন্ন করুন</span>
                    </button>
                </div>

            </div>
        </div>
    </div>

    <!-- Checkout Modal Form -->
    <div id="checkoutModal" class="fixed inset-0 z-50 overflow-y-auto hidden flex items-center justify-center p-4 bg-maroon-950/80 backdrop-blur-sm">
        <div class="bg-white text-maroon-950 w-full max-w-lg rounded-2xl shadow-2xl overflow-hidden relative">
            <div class="bg-maroon-950 text-gold-300 p-4 flex items-center justify-between">
                <h3 class="text-sm font-bold flex items-center gap-2">
                    <i class="fas fa-shipping-fast text-gold-400"></i> ডেলিভারি ও পেমেন্ট তথ্য
                </h3>
                <button onclick="closeCheckoutModal()" class="text-gold-400 hover:text-white">
                    <i class="fas fa-times"></i>
                </button>
            </div>

            <form onsubmit="submitOrder(event)" class="p-5 space-y-3.5">
                <div>
                    <label class="block text-xs font-bold text-gray-700 mb-1">আপনার নাম *</label>
                    <input type="text" id="custName" required placeholder="আপনার নাম লিখুন" class="w-full text-xs p-2.5 border border-gray-300 rounded-lg">
                </div>

                <div>
                    <label class="block text-xs font-bold text-gray-700 mb-1">মোবাইল নম্বর *</label>
                    <input type="tel" id="custPhone" required placeholder="017XXXXXXXX" class="w-full text-xs p-2.5 border border-gray-300 rounded-lg">
                </div>

                <div>
                    <label class="block text-xs font-bold text-gray-700 mb-1">সম্পূর্ণ ঠিকানা *</label>
                    <textarea id="custAddress" required rows="2" placeholder="গ্রাম/রোড, পোস্ট অফিস, থানা ও জেলা" class="w-full text-xs p-2.5 border border-gray-300 rounded-lg"></textarea>
                </div>

                <div>
                    <label class="block text-xs font-bold text-gray-700 mb-1">পেমেন্ট পদ্ধতি *</label>
                    <div class="grid grid-cols-3 gap-2">
                        <label class="cursor-pointer border border-gray-200 rounded-lg p-2 text-center flex flex-col items-center hover:border-maroon-700">
                            <input type="radio" name="payMethod" value="Cash on Delivery" checked class="mb-1">
                            <span class="text-[11px] font-bold">ক্যাশ অন ডেলিভারি</span>
                        </label>
                        <label class="cursor-pointer border border-gray-200 rounded-lg p-2 text-center flex flex-col items-center hover:border-maroon-700">
                            <input type="radio" name="payMethod" value="bKash" class="mb-1">
                            <span class="text-[11px] font-bold text-pink-600">bKash (01792457935)</span>
                        </label>
                        <label class="cursor-pointer border border-gray-200 rounded-lg p-2 text-center flex flex-col items-center hover:border-maroon-700">
                            <input type="radio" name="payMethod" value="Nagad" class="mb-1">
                            <span class="text-[11px] font-bold text-orange-600">Nagad (01792457935)</span>
                        </label>
                    </div>
                </div>

                <button type="submit" class="w-full py-3 bg-maroon-900 text-gold-300 font-bold rounded-xl text-xs">
                    অর্ডার কনফার্ম করুন (সর্বমোট: <span id="checkoutGrandTotal">৳ 0</span>)
                </button>
            </form>
        </div>
    </div>

    <!-- Admin Password / Auth Modal -->
    <div id="adminAuthModal" class="fixed inset-0 z-50 overflow-y-auto hidden flex items-center justify-center p-4 bg-maroon-950/80 backdrop-blur-sm">
        <div class="bg-white text-maroon-950 w-full max-w-xs rounded-2xl p-5 shadow-2xl text-center space-y-4">
            <div class="w-12 h-12 bg-maroon-100 text-maroon-900 rounded-full flex items-center justify-center mx-auto text-xl">
                <i class="fas fa-user-lock"></i>
            </div>
            <h3 class="text-sm font-bold">এডমিন সফটওয়্যার লগইন</h3>
            <p class="text-[11px] text-gray-500">এডমিন পিন কোড প্রবেশ করুন (ডিফল্ট: 1234)</p>
            <input type="password" id="adminPinInput" placeholder="PIN লিখুন" class="w-full text-center text-sm p-2 border border-gray-300 rounded-lg font-bold tracking-widest">
            <div class="flex gap-2">
                <button onclick="closeAdminAuth()" class="w-1/2 py-2 bg-gray-200 text-xs rounded-lg font-bold">বাতিল</button>
                <button onclick="verifyAdminPin()" class="w-1/2 py-2 bg-maroon-900 text-gold-300 text-xs rounded-lg font-bold">লগইন</button>
            </div>
        </div>
    </div>

    <!-- Admin Add/Edit Product Modal -->
    <div id="productModal" class="fixed inset-0 z-50 overflow-y-auto hidden flex items-center justify-center p-4 bg-maroon-950/80 backdrop-blur-sm">
        <div class="bg-white text-maroon-950 w-full max-w-md rounded-2xl shadow-2xl overflow-hidden">
            <div class="bg-maroon-950 text-gold-300 p-4 flex items-center justify-between">
                <h3 class="text-sm font-bold" id="productModalTitle">নতুন চুড়ির বিবরণ যোগ করুন</h3>
                <button onclick="closeProductModal()" class="text-gold-400 hover:text-white"><i class="fas fa-times"></i></button>
            </div>
            <form onsubmit="saveProductForm(event)" class="p-5 space-y-3">
                <input type="hidden" id="editProductId">
                <div>
                    <label class="block text-xs font-bold text-gray-700 mb-1">চুড়ির নাম *</label>
                    <input type="text" id="prodTitle" required placeholder="যেমন: ব্রাইডাল কুন্দন মেরুন সেট" class="w-full text-xs p-2 border border-gray-300 rounded-lg">
                </div>
                <div class="grid grid-cols-2 gap-2">
                    <div>
                        <label class="block text-xs font-bold text-gray-700 mb-1">দাম (টাকা) *</label>
                        <input type="number" id="prodPrice" required placeholder="350" class="w-full text-xs p-2 border border-gray-300 rounded-lg">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-700 mb-1">ক্যাটাগরি *</label>
                        <select id="prodCategory" class="w-full text-xs p-2 border border-gray-300 rounded-lg">
                            <option value="bridal">ব্রাইডাল সেট</option>
                            <option value="heavy">কাস্টমাইজড সেট</option>
                            <option value="simple">ডেইলি ওয়্যার</option>
                            <option value="kids">কিডস স্পেশাল</option>
                        </select>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-2">
                    <div>
                        <label class="block text-xs font-bold text-gray-700 mb-1">পিস / সেট বিবরণ *</label>
                        <input type="text" id="prodPieces" required placeholder="১২ পিস সেট" class="w-full text-xs p-2 border border-gray-300 rounded-lg">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-700 mb-1">রঙের নাম *</label>
                        <input type="text" id="prodColorName" required placeholder="মেরুন ও সোনালী" class="w-full text-xs p-2 border border-gray-300 rounded-lg">
                    </div>
                </div>
                <div>
                    <label class="block text-xs font-bold text-gray-700 mb-1">ছবি (Image URL - অপশনাল):</label>
                    <input type="text" id="prodImgUrl" placeholder="https://example.com/image.jpg" class="w-full text-xs p-2 border border-gray-300 rounded-lg">
                    <span class="text-[10px] text-gray-400">ফাঁকা রাখলে অটোমেটিক SVG চুড়ির ডিজাইন জেনারেট হবে।</span>
                </div>
                <button type="submit" class="w-full py-2.5 bg-maroon-900 text-gold-300 font-bold rounded-xl text-xs">সেভ করুন</button>
            </form>
        </div>
    </div>

    <!-- Notification Toast -->
    <div id="toast" class="fixed bottom-5 right-5 z-50 transform translate-y-20 opacity-0 transition-all duration-300 bg-maroon-950 text-gold-300 border border-gold-500/50 px-5 py-3 rounded-xl shadow-2xl flex items-center space-x-3 pointer-events-none">
        <i class="fas fa-check-circle text-gold-400 text-xl" id="toastIcon"></i>
        <span id="toastMsg" class="text-xs font-medium">কাজটি সফল হয়েছে!</span>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        // Initial Default Products Data
        const defaultProducts = [
            {
                id: 1,
                title: "রাজকীয় ব্রাইডাল কুন্দন ও মেরুন সেট",
                category: "bridal",
                price: 450,
                rating: 5.0,
                pieces: "২৪ পিস সেট",
                colorName: "মেরুন ও সোনালী",
                colorHex: "#771d1d"
            },
            {
                id: 2,
                title: "হলুদ সন্ধ্যা স্পেশাল গায়ে হলুদ কম্বো",
                category: "bridal",
                price: 380,
                rating: 4.9,
                pieces: "১৮ পিস সেট",
                colorName: "বাসন্তী হলুদ",
                colorHex: "#f59e0b"
            },
            {
                id: 3,
                title: "রয়্যাল ব্লু মিরর ওয়ার্ক ক্যাটালগ",
                category: "heavy",
                price: 320,
                rating: 4.8,
                pieces: "১২ পিস সেট",
                colorName: "রয়্যাল ব্লু",
                colorHex: "#1e40af"
            },
            {
                id: 4,
                title: "কিডস কিউট পিঙ্ক বেবি চুড়ি সেট",
                category: "kids",
                price: 160,
                rating: 4.9,
                pieces: "৪ পিস সেট (কিডস)",
                colorName: "বেবি পিঙ্ক",
                colorHex: "#ec4899"
            },
            {
                id: 5,
                title: "পান্না সবুজ স্টোন ও জরি ওয়ার্ক",
                category: "heavy",
                price: 390,
                rating: 4.9,
                pieces: "১৬ পিস সেট",
                colorName: "পান্না সবুজ",
                colorHex: "#047857"
            },
            {
                id: 6,
                title: "সিম্পল ডে-টু-ডে রেড সুতার চুড়ি",
                category: "simple",
                price: 150,
                rating: 4.7,
                pieces: "৬ পিস (দৈনন্দিন ব্যবহার)",
                colorName: "টকটকে লাল",
                colorHex: "#dc2626"
            }
        ];

        // Global State persistence
        let products = JSON.parse(localStorage.getItem('reshmi_products')) || defaultProducts;
        let orders = JSON.parse(localStorage.getItem('reshmi_orders')) || [];
        let shopSettings = JSON.parse(localStorage.getItem('reshmi_settings')) || {
            name: "রেশমি ক্রাফটস",
            phone: "01792457935",
            address: "গিধাউষা মাস্টার বাড়ি, গৌরীপুর, ময়মনসিংহ",
            announcement: "সারা বাংলাদেশে ক্যাশ অন ডেলিভারি সার্ভিস উপলব্ধ!"
        };

        let cart = [];
        let activeCategory = 'all';
        let isAdminLoggedIn = false;

        let customConfig = {
            colorHex: '#9b1c1c',
            colorName: 'লাল/মেরুন',
            size: '2.4 (Small)',
            style: 'mirror'
        };

        // Initialize App & UI
        window.onload = function() {
            applyShopSettings();
            renderProducts(products);
            updateCartUI();
            updateCustomPreview();
        };

        function applyShopSettings() {
            document.getElementById('displayShopName').innerText = shopSettings.name;
            document.getElementById('footerShopName').innerText = shopSettings.name;
            document.getElementById('displayAddress').innerText = shopSettings.address;
            document.getElementById('displayAnnouncement').innerText = shopSettings.announcement;
            
            document.querySelectorAll('.displayPhone').forEach(el => el.innerText = shopSettings.phone);

            // Populate Admin Settings fields
            document.getElementById('editShopName').value = shopSettings.name;
            document.getElementById('editShopPhone').value = shopSettings.phone;
            document.getElementById('editShopAddress').value = shopSettings.address;
            document.getElementById('editShopAnnouncement').value = shopSettings.announcement;
        }

        // Generate Dynamic Bangle SVG Image
        function getBangleSvg(colorHex = '#771d1d') {
            return `<svg viewBox="0 0 200 200" class="w-full h-full">
                <rect width="100%" height="100%" fill="#fffdf7"/>
                <circle cx="100" cy="100" r="72" fill="none" stroke="${colorHex}" stroke-width="22"/>
                <circle cx="100" cy="100" r="72" fill="none" stroke="#facc15" stroke-width="2" stroke-dasharray="3 10"/>
                <circle cx="100" cy="100" r="54" fill="none" stroke="#ca8a04" stroke-width="6"/>
                <circle cx="100" cy="28" r="4" fill="#fff" stroke="#ca8a04"/>
                <circle cx="100" cy="172" r="4" fill="#fff" stroke="#ca8a04"/>
                <circle cx="28" cy="100" r="4" fill="#fff" stroke="#ca8a04"/>
                <circle cx="172" cy="100" r="4" fill="#fff" stroke="#ca8a04"/>
            </svg>`;
        }

        // Render Product Cards Grid
        function renderProducts(items) {
            const grid = document.getElementById('productGrid');
            const noProductsMsg = document.getElementById('noProducts');

            if (items.length === 0) {
                grid.innerHTML = '';
                noProductsMsg.classList.remove('hidden');
                return;
            } else {
                noProductsMsg.classList.add('hidden');
            }

            grid.innerHTML = items.map(p => `
                <div class="bg-white rounded-2xl overflow-hidden border border-maroon-900/10 shadow-sm hover:shadow-xl transition flex flex-col group relative">
                    <div class="relative h-48 bg-cream flex items-center justify-center p-4 border-b border-gray-100 overflow-hidden">
                        ${p.imageUrl ? `<img src="${p.imageUrl}" alt="${p.title}" class="h-full object-contain">` : `<div class="w-36 h-36">${getBangleSvg(p.colorHex || '#9b1c1c')}</div>`}
                        <span class="absolute top-3 left-3 bg-maroon-950/80 text-gold-300 text-[10px] px-2.5 py-1 rounded-full border border-gold-500/30">
                            ${p.pieces}
                        </span>
                        ${isAdminLoggedIn ? `
                            <button onclick="editProduct(${p.id})" class="absolute top-3 right-3 bg-gold-500 text-maroon-950 p-1.5 rounded-full shadow text-xs hover:bg-gold-400">
                                <i class="fas fa-edit"></i>
                            </button>
                        ` : ''}
                    </div>

                    <div class="p-4 flex-1 flex flex-col justify-between space-y-3">
                        <div>
                            <div class="flex items-center space-x-1.5 mb-1">
                                <span class="w-2.5 h-2.5 rounded-full inline-block" style="background-color: ${p.colorHex || '#9b1c1c'}"></span>
                                <span class="text-[11px] text-gray-500 font-medium">${p.colorName}</span>
                            </div>
                            <h3 class="font-bold text-maroon-950 text-sm leading-snug">
                                ${p.title}
                            </h3>
                        </div>

                        <div class="flex items-center justify-between pt-2 border-t border-gray-100">
                            <div>
                                <span class="text-[10px] text-gray-400 block">মূল্য</span>
                                <span class="text-base font-extrabold text-maroon-800">৳ ${p.price}</span>
                            </div>

                            <button onclick="addToCart(${p.id})" class="bg-maroon-900 hover:bg-maroon-800 text-gold-300 px-3 py-2 rounded-xl text-xs font-semibold transition flex items-center space-x-1 shadow">
                                <i class="fas fa-cart-plus"></i>
                                <span>কার্ট</span>
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        // Filtering and Sorting
        function setCategory(cat) {
            activeCategory = cat;
            document.querySelectorAll('.cat-btn').forEach(btn => {
                btn.classList.remove('bg-maroon-800', 'text-gold-300', 'shadow');
                btn.classList.add('text-maroon-800');
            });
            const activeBtn = document.getElementById(`cat-${cat}`);
            if(activeBtn) activeBtn.classList.add('bg-maroon-800', 'text-gold-300', 'shadow');
            filterAndSort();
        }

        function filterProducts() { filterAndSort(); }
        function filterProductsMobile() { filterAndSort(); }

        function filterAndSort() {
            const query = (document.getElementById('searchInput').value || document.getElementById('searchInputMobile').value).toLowerCase();
            const sortVal = document.getElementById('sortSelect').value;

            let result = products.filter(p => {
                const matchesCat = activeCategory === 'all' || p.category === activeCategory;
                const matchesSearch = p.title.toLowerCase().includes(query) || (p.colorName && p.colorName.toLowerCase().includes(query));
                return matchesCat && matchesSearch;
            });

            if (sortVal === 'low-high') result.sort((a, b) => a.price - b.price);
            else if (sortVal === 'high-low') result.sort((a, b) => b.price - a.price);

            renderProducts(result);
        }

        function sortProducts() { filterAndSort(); }

        // Live Customizer Functions
        function setCustomColor(hex, name) {
            customConfig.colorHex = hex;
            customConfig.colorName = name;
            
            document.querySelectorAll('.color-opt').forEach(el => {
                el.classList.remove('border-2', 'border-gold-400');
                el.classList.add('border', 'border-gold-600/30');
            });
            event.currentTarget.classList.remove('border-gold-600/30');
            event.currentTarget.classList.add('border-2', 'border-gold-400');

            updateCustomPreview();
        }

        function setCustomSize(size) {
            customConfig.size = size;
            document.querySelectorAll('.size-opt').forEach(el => {
                el.classList.remove('bg-gold-500', 'text-maroon-950', 'border-2', 'border-gold-400');
                el.classList.add('bg-maroon-950', 'text-gold-100', 'border', 'border-gold-600/30');
            });
            event.currentTarget.classList.remove('bg-maroon-950', 'text-gold-100', 'border-gold-600/30');
            event.currentTarget.classList.add('bg-gold-500', 'text-maroon-950', 'border-2', 'border-gold-400');

            updateCustomPreview();
        }

        function updateCustomPreviewStyle() {
            customConfig.style = document.getElementById('customStyleSelect').value;
            updateCustomPreview();
        }

        function updateCustomPreview() {
            document.getElementById('svgMainThread').setAttribute('stroke', customConfig.colorHex);

            const decorGroup = document.getElementById('svgDecorations');
            if (customConfig.style === 'mirror') {
                decorGroup.innerHTML = `
                    <circle cx="100" cy="25" r="5" fill="#fff" stroke="#ca8a04"/>
                    <circle cx="100" cy="175" r="5" fill="#fff" stroke="#ca8a04"/>
                    <circle cx="25" cy="100" r="5" fill="#fff" stroke="#ca8a04"/>
                    <circle cx="175" cy="100" r="5" fill="#fff" stroke="#ca8a04"/>
                `;
            } else if (customConfig.style === 'kundan') {
                decorGroup.innerHTML = `
                    <polygon points="100,20 106,28 100,34 94,28" fill="#fef08a" stroke="#ca8a04"/>
                    <polygon points="100,166 106,174 100,180 94,174" fill="#fef08a" stroke="#ca8a04"/>
                    <polygon points="20,100 28,106 34,100 28,94" fill="#fef08a" stroke="#ca8a04"/>
                `;
            } else {
                decorGroup.innerHTML = `
                    <circle cx="100" cy="100" r="75" fill="none" stroke="#fff" stroke-width="1.5" stroke-dasharray="2 14"/>
                `;
            }

            document.getElementById('summaryColor').innerText = `রঙ: ${customConfig.colorName}`;
            document.getElementById('summaryDetails').innerText = `সাইজ: ${customConfig.size}`;
        }

        function addCustomToCart() {
            const customItem = {
                id: Date.now(),
                title: `কাস্টম ${customConfig.colorName} সুতার চুড়ি`,
                price: 200,
                qty: 1,
                selectedSize: customConfig.size,
                colorHex: customConfig.colorHex
            };

            cart.push(customItem);
            updateCartUI();
            showToast("কাস্টম চুড়ি কার্টে যোগ হয়েছে!");
        }

        // Cart Actions
        function addToCart(id) {
            const product = products.find(p => p.id === id);
            if (!product) return;

            const existing = cart.find(c => c.id === id);
            if (existing) {
                existing.qty += 1;
            } else {
                cart.push({ ...product, qty: 1, selectedSize: '2.4 (Small)' });
            }

            updateCartUI();
            showToast(`"${product.title.substring(0, 16)}..." কার্টে যোগ হয়েছে!`);
        }

        function updateCartUI() {
            const badge = document.getElementById('cartBadge');
            const totalItems = cart.reduce((sum, item) => sum + item.qty, 0);
            badge.innerText = totalItems;

            const container = document.getElementById('cartItemsContainer');
            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-12 text-gray-400">
                        <i class="fas fa-shopping-bag text-4xl mb-2 opacity-30"></i>
                        <p class="text-xs">আপনার ব্যাগ খালি রয়েছে</p>
                    </div>
                `;
            } else {
                container.innerHTML = cart.map(item => `
                    <div class="flex items-center space-x-3 p-3 bg-gray-50 rounded-xl border border-gray-100 text-xs">
                        <div class="w-12 h-12 bg-cream rounded border border-gray-200 shrink-0 p-1">
                            ${getBangleSvg(item.colorHex || '#9b1c1c')}
                        </div>
                        <div class="flex-1 min-w-0">
                            <h4 class="font-bold text-maroon-950 truncate">${item.title}</h4>
                            <div class="text-[10px] text-gray-500">সাইজ: ${item.selectedSize}</div>
                            <div class="font-extrabold text-maroon-800 mt-0.5">৳ ${item.price}</div>
                        </div>
                        <div class="flex items-center space-x-1 border border-gray-200 bg-white rounded-lg p-1">
                            <button onclick="changeQty(${item.id}, -1)" class="w-4 h-4 text-center font-bold text-gray-600 hover:bg-gray-100 rounded">-</button>
                            <span class="w-4 text-center font-bold">${item.qty}</span>
                            <button onclick="changeQty(${item.id}, 1)" class="w-4 h-4 text-center font-bold text-gray-600 hover:bg-gray-100 rounded">+</button>
                        </div>
                        <button onclick="removeFromCart(${item.id})" class="text-red-500 p-1">
                            <i class="fas fa-trash-alt"></i>
                        </button>
                    </div>
                `).join('');
            }

            const subtotal = cart.reduce((sum, i) => sum + (i.price * i.qty), 0);
            const delivery = cart.length > 0 ? parseInt(document.getElementById('deliveryRegion').value) : 0;
            const grand = subtotal + delivery;

            document.getElementById('subTotal').innerText = `৳ ${subtotal}`;
            document.getElementById('grandTotal').innerText = `৳ ${grand}`;
            document.getElementById('checkoutGrandTotal').innerText = `৳ ${grand}`;
        }

        function changeQty(id, delta) {
            const item = cart.find(c => c.id === id);
            if (item) {
                item.qty += delta;
                if (item.qty <= 0) cart = cart.filter(c => c.id !== id);
                updateCartUI();
            }
        }

        function removeFromCart(id) {
            cart = cart.filter(c => c.id !== id);
            updateCartUI();
        }

        function toggleCartModal() {
            document.getElementById('cartModal').classList.toggle('hidden');
        }

        function openCheckoutModal() {
            if (cart.length === 0) {
                alert('আপনার কার্ট খালি!');
                return;
            }
            toggleCartModal();
            document.getElementById('checkoutModal').classList.remove('hidden');
        }

        function closeCheckoutModal() {
            document.getElementById('checkoutModal').classList.add('hidden');
        }

        function submitOrder(e) {
            e.preventDefault();
            const name = document.getElementById('custName').value;
            const phone = document.getElementById('custPhone').value;
            const address = document.getElementById('custAddress').value;
            const payMethod = document.querySelector('input[name="payMethod"]:checked').value;
            
            const subtotal = cart.reduce((sum, i) => sum + (i.price * i.qty), 0);
            const delivery = parseInt(document.getElementById('deliveryRegion').value);
            const grandTotal = subtotal + delivery;

            const newOrder = {
                id: 'ORD-' + Math.floor(100000 + Math.random() * 900000),
                date: new Date().toLocaleDateString('bn-BD'),
                name,
                phone,
                address,
                payMethod,
                items: [...cart],
                grandTotal,
                status: 'Pending'
            };

            orders.unshift(newOrder);
            localStorage.setItem('reshmi_orders', JSON.stringify(orders));

            alert(`ধন্যবাদ ${name}!\nআপনার অর্ডারটি সফলভাবে গ্রহণ করা হয়েছে।\nঅর্ডার আইডি: ${newOrder.id}\nআমরা দ্রুত আপনার নাম্বারে কল দিয়ে কনফার্ম করব।`);

            cart = [];
            updateCartUI();
            closeCheckoutModal();
            if (isAdminLoggedIn) renderAdminOrders();
        }

        // ADMIN PANEL FUNCTIONS & CONTROL SOFTWARE
        function openAdminAuth() {
            if (isAdminLoggedIn) {
                document.getElementById('adminPanelSection').classList.toggle('hidden');
            } else {
                document.getElementById('adminAuthModal').classList.remove('hidden');
            }
        }

        function closeAdminAuth() {
            document.getElementById('adminAuthModal').classList.add('hidden');
        }

        function verifyAdminPin() {
            const pin = document.getElementById('adminPinInput').value;
            if (pin === '1234') { // Simple default PIN
                isAdminLoggedIn = true;
                closeAdminAuth();
                document.getElementById('adminNavBtnText').innerText = 'এডমিন প্যানেল';
                document.getElementById('adminPanelSection').classList.remove('hidden');
                renderAdminProducts();
                renderAdminOrders();
                renderProducts(products); // Refresh to show edit buttons
                showToast("এডমিন সফটওয়্যারে সফলভাবে লগইন করেছেন!");
            } else {
                alert('ভুল পিন নাম্বার! সঠিক পিন ব্যবহার করুন (ডিফল্ট: 1234)।');
            }
        }

        function logoutAdmin() {
            isAdminLoggedIn = false;
            document.getElementById('adminNavBtnText').innerText = 'এডমিন লগইন';
            document.getElementById('adminPanelSection').classList.add('hidden');
            renderProducts(products);
            showToast("অ্যাডমিন লগআউট সম্পূর্ণ হয়েছে।");
        }

        function switchAdminTab(tabName) {
            ['products', 'orders', 'settings'].forEach(tab => {
                document.getElementById(`adminTabContent-${tab}`).classList.add('hidden');
                document.getElementById(`adminTab-${tab}`).classList.remove('text-gold-300', 'border-b-2', 'border-gold-400');
                document.getElementById(`adminTab-${tab}`).classList.add('text-gold-400/70');
            });

            document.getElementById(`adminTabContent-${tabName}`).classList.remove('hidden');
            document.getElementById(`adminTab-${tabName}`).classList.add('text-gold-300', 'border-b-2', 'border-gold-400');
        }

        function renderAdminProducts() {
            document.getElementById('adminProductCount').innerText = products.length;
            const tbody = document.getElementById('adminProductTableBody');
            tbody.innerHTML = products.map(p => `
                <tr class="hover:bg-maroon-900/50">
                    <td class="p-3">
                        <div class="w-10 h-10 border border-gold-500/30 rounded p-1 bg-cream">
                            ${getBangleSvg(p.colorHex || '#9b1c1c')}
                        </div>
                    </td>
                    <td class="p-3 font-bold text-gold-200">${p.title}</td>
                    <td class="p-3 uppercase text-[10px] bg-maroon-950/60 rounded px-2 py-1 inline-block mt-2">${p.category}</td>
                    <td class="p-3 font-bold">৳ ${p.price}</td>
                    <td class="p-3 text-gold-300">${p.pieces}</td>
                    <td class="p-3 text-center space-x-2">
                        <button onclick="editProduct(${p.id})" class="text-gold-400 hover:text-white p-1"><i class="fas fa-edit"></i></button>
                        <button onclick="deleteProduct(${p.id})" class="text-red-400 hover:text-red-300 p-1"><i class="fas fa-trash-alt"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderAdminOrders() {
            document.getElementById('adminOrderCount').innerText = orders.length;
            const tbody = document.getElementById('adminOrderTableBody');

            if(orders.length === 0) {
                tbody.innerHTML = `<tr><td colspan="6" class="p-6 text-center text-gray-400">এখনো কোনো নতুন অর্ডার আসেনি!</td></tr>`;
                return;
            }

            tbody.innerHTML = orders.map(o => `
                <tr class="hover:bg-maroon-900/50 border-b border-maroon-800">
                    <td class="p-3 font-mono">
                        <span class="text-gold-400 font-bold">${o.id}</span>
                        <div class="text-[10px] text-gray-400">${o.date}</div>
                    </td>
                    <td class="p-3 font-bold text-gold-200">
                        ${o.name}
                        <div class="text-gray-300 font-normal">${o.phone}</div>
                    </td>
                    <td class="p-3 max-w-xs text-[11px] text-gray-300">${o.address}</td>
                    <td class="p-3 text-[11px]">
                        ${o.items.map(i => `${i.title} (${i.qty}x)`).join(', ')}
                    </td>
                    <td class="p-3 font-bold">
                        ৳ ${o.grandTotal}
                        <div class="text-[10px] text-gold-400">${o.payMethod}</div>
                    </td>
                    <td class="p-3">
                        <select onchange="updateOrderStatus('${o.id}', this.value)" class="bg-maroon-950 text-gold-200 text-[11px] p-1 border border-gold-600/40 rounded">
                            <option value="Pending" ${o.status === 'Pending' ? 'selected' : ''}>Pending</option>
                            <option value="Shipped" ${o.status === 'Shipped' ? 'selected' : ''}>Shipped</option>
                            <option value="Delivered" ${o.status === 'Delivered' ? 'selected' : ''}>Delivered</option>
                        </select>
                    </td>
                </tr>
            `).join('');
        }

        function updateOrderStatus(orderId, newStatus) {
            const order = orders.find(o => o.id === orderId);
            if(order) {
                order.status = newStatus;
                localStorage.setItem('reshmi_orders', JSON.stringify(orders));
                showToast(`অর্ডারটি ${newStatus} হিসেবে সেভ করা হয়েছে`);
            }
        }

        // Product Modal Actions
        function openProductModal() {
            document.getElementById('editProductId').value = '';
            document.getElementById('prodTitle').value = '';
            document.getElementById('prodPrice').value = '';
            document.getElementById('prodPieces').value = '';
            document.getElementById('prodColorName').value = '';
            document.getElementById('productModalTitle').innerText = 'নতুন চুড়ির বিবরণ যোগ করুন';
            document.getElementById('productModal').classList.remove('hidden');
        }

        function closeProductModal() {
            document.getElementById('productModal').classList.add('hidden');
        }

        function editProduct(id) {
            const p = products.find(prod => prod.id === id);
            if (!p) return;

            document.getElementById('editProductId').value = p.id;
            document.getElementById('prodTitle').value = p.title;
            document.getElementById('prodPrice').value = p.price;
            document.getElementById('prodCategory').value = p.category;
            document.getElementById('prodPieces').value = p.pieces;
            document.getElementById('prodColorName').value = p.colorName || '';
            document.getElementById('productModalTitle').innerText = 'চুড়ির বিবরণ এডিট করুন';
            document.getElementById('productModal').classList.remove('hidden');
        }

        function saveProductForm(e) {
            e.preventDefault();
            const id = document.getElementById('editProductId').value;
            const title = document.getElementById('prodTitle').value;
            const price = parseFloat(document.getElementById('prodPrice').value);
            const category = document.getElementById('prodCategory').value;
            const pieces = document.getElementById('prodPieces').value;
            const colorName = document.getElementById('prodColorName').value;
            const imageUrl = document.getElementById('prodImgUrl').value;

            if (id) {
                // Edit existing
                const index = products.findIndex(p => p.id == id);
                if (index !== -1) {
                    products[index] = { ...products[index], title, price, category, pieces, colorName, imageUrl };
                }
            } else {
                // Add new
                const newProd = {
                    id: Date.now(),
                    title,
                    price,
                    category,
                    pieces,
                    colorName,
                    imageUrl,
                    rating: 5.0,
                    colorHex: '#9b1c1c'
                };
                products.unshift(newProd);
            }

            localStorage.setItem('reshmi_products', JSON.stringify(products));
            renderProducts(products);
            if(isAdminLoggedIn) renderAdminProducts();
            closeProductModal();
                showToast("প্রোডাক্ট তথ্য সফলভাবে সেভ হয়েছে!");
        }

        function deleteProduct(id) {
            if (confirm('আপনি কি নিশ্চিত যে এই চুড়ি প্রোডাক্টটি মুছে ফেলতে চান?')) {
                products = products.filter(p => p.id !== id);
                localStorage.setItem('reshmi_products', JSON.stringify(products));
                renderProducts(products);
                renderAdminProducts();
                showToast("প্রোডাক্টটি মুছে ফেলা হয়েছে।");
            }
        }

        function saveShopSettings() {
            shopSettings.name = document.getElementById('editShopName').value;
            shopSettings.phone = document.getElementById('editShopPhone').value;
            shopSettings.address = document.getElementById('editShopAddress').value;
            shopSettings.announcement = document.getElementById('editShopAnnouncement').value;

            localStorage.setItem('reshmi_settings', JSON.stringify(shopSettings));
            applyShopSettings();
            showToast("দোকানের তথ্য ও ঠিকানা সেভ করা হয়েছে!");
        }

        // Helpers
        function toggleMobileMenu() {
            document.getElementById('mobileMenu').classList.toggle('hidden');
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMsg').innerText = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>
</body>
</html> Website