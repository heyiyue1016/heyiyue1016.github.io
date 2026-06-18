<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <!-- 响应式适配核心标签 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人主页 | 前端开发者</title>
    <!-- 引入Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 引入Font Awesome图标库 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Tailwind自定义主题配置 蓝色科技风 -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#007BFF',
                        secondary: '#0056b3',
                        lightBlue: '#E6F2FF',
                        darkGray: '#1F2937'
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <!-- 自定义工具类 -->
    <style type="text/tailwindcss">
        @layer utilities {
            .text-shadow {
                text-shadow: 0 2px 4px rgba(0,123,255,0.2);
            }
            .card-hover {
                transition: all 0.3s ease;
            }
            .card-hover:hover {
                transform: translateY(-6px);
                box-shadow: 0 12px 24px rgba(0,123,255,0.15);
            }
            .nav-link-active {
                border-bottom: 2px solid #007BFF;
            }
        }
    </style>
</head>
<body class="bg-gray-50 font-sans text-darkGray scroll-smooth">
    <!-- 1.导航栏模块 移动端折叠菜单 -->
    <nav id="navbar" class="fixed w-full top-0 z-50 bg-white/95 backdrop-blur-sm shadow-sm transition-all duration-300">
        <div class="container mx-auto px-4 md:px-8 py-4 flex justify-between items-center">
            <!-- Logo -->
            <a href="#" class="text-[clamp(1.2rem,3vw,1.6rem)] font-bold text-primary flex items-center gap-2">
                <i class="fa-solid fa-code"></i>
                <span>MyPortfolio</span>
            </a>
            <!-- 桌面端导航菜单 -->
            <div class="hidden md:flex gap-8 text-gray-700">
                <a href="#home" class="nav-link-active py-2 hover:text-primary transition-colors">首页</a>
                <a href="#about" class="py-2 hover:text-primary transition-colors">个人简介</a>
                <a href="#skill" class="py-2 hover:text-primary transition-colors">技能展示</a>
                <a href="#project" class="py-2 hover:text-primary transition-colors">项目作品</a>
                <a href="#contact" class="py-2 hover:text-primary transition-colors">联系我</a>
            </div>
            <!-- 移动端菜单按钮 -->
            <button id="menuBtn" class="md:hidden text-2xl text-darkGray">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>
        <!-- 移动端下拉菜单 -->
        <div id="mobileMenu" class="hidden md:hidden px-4 pb-4 space-y-4 bg-white border-t border-gray-100">
            <a href="#home" class="block py-2 hover:text-primary">首页</a>
            <a href="#about" class="block py-2 hover:text-primary">个人简介</a>
            <a href="#skill" class="block py-2 hover:text-primary">技能展示</a>
            <a href="#project" class="block py-2 hover:text-primary">项目作品</a>
            <a href="#contact" class="block py-2 hover:text-primary">联系我</a>
        </div>
    </nav>

    <!-- 2.首页Banner区域 -->
    <section id="home" class="pt-28 pb-20 bg-gradient-to-br from-lightBlue to-white min-h-[90vh] flex items-center">
        <div class="container mx-auto px-4 md:px-8 grid md:grid-cols-2 gap-12 items-center">
            <div class="order-2 md:order-1">
                <p class="text-primary font-medium mb-3">你好，我是</p>
                <h1 class="text-[clamp(2rem,6vw,3.5rem)] font-bold leading-tight text-darkGray mb-4">前端开发工程师</h1>
                <p class="text-gray-600 text-lg mb-8 max-w-lg">专注响应式页面开发、交互设计，擅长使用HTML/CSS/JS/Tailwind构建现代化网站，热爱简洁科技风UI。</p>
                <div class="flex flex-wrap gap-4">
                    <a href="#project" class="bg-primary text-white px-7 py-3 rounded-full hover:bg-secondary transition-colors shadow-md">
                        查看作品
                    </a>
                    <a href="#contact" class="border border-primary text-primary px-7 py-3 rounded-full hover:bg-lightBlue transition-colors">
                        联系我
                    </a>
                </div>
                <!-- 社交图标 -->
                <div class="flex gap-5 mt-10 text-xl text-gray-600">
                    <a href="#" class="hover:text-primary transition-colors"><i class="fa-brands fa-github"></i></a>
                    <a href="#" class="hover:text-primary transition-colors"><i class="fa-brands fa-gitee"></i></a>
                    <a href="#" class="hover:text-primary transition-colors"><i class="fa-brands fa-weixin"></i></a>
                    <a href="#" class="hover:text-primary transition-colors"><i class="fa-solid fa-envelope"></i></a>
                </div>
            </div>
            <!-- 装饰插画区域 -->
            <div class="order-1 md:order-2 flex justify-center">
                <div class="w-[clamp(260px,50vw,420px)] h-[clamp(260px,50vw,420px)] rounded-full bg-lightBlue flex items-center justify-center">
                    <i class="fa-solid fa-laptop-code text-[clamp(100px,20vw,180px)] text-primary/70"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- 3.个人简介模块 -->
    <section id="about" class="py-20 bg-white">
        <div class="container mx-auto px-4 md:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.6rem,4vw,2.4rem)] font-bold mb-3">个人简介</h2>
                <div class="w-20 h-1 bg-primary mx-auto"></div>
            </div>
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div class="bg-lightBlue p-8 rounded-2xl card-hover">
                    <i class="fa-solid fa-user-graduate text-6xl text-primary mb-6"></i>
                    <h3 class="text-xl font-semibold mb-4">关于我</h3>
                    <p class="text-gray-600 leading-relaxed">计算机相关专业在读学生，深耕前端页面开发，熟悉响应式布局与现代化CSS框架。擅长独立完成UI还原、单页网站搭建，具备AI辅助设计开发能力，注重页面交互体验与代码整洁规范。课余持续学习前端新技术，乐于分享项目开发经验。</p>
                </div>
                <div class="space-y-6">
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 rounded-full bg-lightBlue flex items-center justify-center text-primary text-xl">
                            <i class="fa-solid fa-calendar"></i>
                        </div>
                        <div>
                            <h4 class="font-medium">在校学习时长</h4>
                            <p class="text-gray-600">3年Web前端开发学习经验</p>
                        </div>
                    </div>
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 rounded-full bg-lightBlue flex items-center justify-center text-primary text-xl">
                            <i class="fa-solid fa-file-code"></i>
                        </div>
                        <div>
                            <h4 class="font-medium">完成项目数量</h4>
                            <p class="text-gray-600">10+完整单页网站、管理页面</p>
                        </div>
                    </div>
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 rounded-full bg-lightBlue flex items-center justify-center text-primary text-xl">
                            <i class="fa-solid fa-graduation-cap"></i>
                        </div>
                        <div>
                            <h4 class="font-medium">专业方向</h4>
                            <p class="text-gray-600">计算机应用 / 前端交互开发</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 4.技能展示模块 -->
    <section id="skill" class="py-20 bg-gray-50">
        <div class="container mx-auto px-4 md:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.6rem,4vw,2.4rem)] font-bold mb-3">技能展示</h2>
                <div class="w-20 h-1 bg-primary mx-auto"></div>
            </div>
            <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- 技能卡片1 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover">
                    <i class="fa-brands fa-html5 text-5xl text-orange-500 mb-5"></i>
                    <h3 class="text-xl font-semibold mb-3">HTML5</h3>
                    <p class="text-gray-600 mb-4">掌握语义化标签、无障碍页面、表单与多媒体标签开发</p>
                    <div class="w-full h-2 bg-gray-100 rounded-full overflow-hidden">
                        <div class="h-full bg-primary w-[95%]"></div>
                    </div>
                </div>
                <!-- 技能卡片2 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover">
                    <i class="fa-brands fa-css3-alt text-5xl text-blue-400 mb-5"></i>
                    <h3 class="text-xl font-semibold mb-3">CSS3 / Tailwind</h3>
                    <p class="text-gray-600 mb-4">Flex/Grid布局、动画过渡、Tailwind快速样式开发</p>
                    <div class="w-full h-2 bg-gray-100 rounded-full overflow-hidden">
                        <div class="h-full bg-primary w-[90%]"></div>
                    </div>
                </div>
                <!-- 技能卡片3 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover">
                    <i class="fa-brands fa-js text-5xl text-yellow-400 mb-5"></i>
                    <h3 class="text-xl font-semibold mb-3">JavaScript</h3>
                    <p class="text-gray-600 mb-4">原生DOM操作、简单交互逻辑、表单校验、滚动动画</p>
                    <div class="w-full h-2 bg-gray-100 rounded-full overflow-hidden">
                        <div class="h-full bg-primary w-[80%]"></div>
                    </div>
                </div>
                <!-- 技能卡片4 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover">
                    <i class="fa-solid fa-mobile-screen-button text-5xl text-primary mb-5"></i>
                    <h3 class="text-xl font-semibold mb-3">响应式开发</h3>
                    <p class="text-gray-600 mb-4">多设备适配、媒体查询、移动端优先布局方案</p>
                    <div class="w-full h-2 bg-gray-100 rounded-full overflow-hidden">
                        <div class="h-full bg-primary w-[92%]"></div>
                    </div>
                </div>
                <!-- 技能卡片5 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover">
                    <i class="fa-brands fa-git-alt text-5xl text-gray-700 mb-5"></i>
                    <h3 class="text-xl font-semibold mb-3">Git / Gitee/Github</h3>
                    <p class="text-gray-600 mb-4">代码版本管理、仓库搭建、Pages静态网站部署上线</p>
                    <div class="w-full h-2 bg-gray-100 rounded-full overflow-hidden">
                        <div class="h-full bg-primary w-[85%]"></div>
                    </div>
                </div>
                <!-- 技能卡片6 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover">
                    <i class="fa-solid fa-wand-magic-sparkles text-5xl text-purple-500 mb-5"></i>
                    <h3 class="text-xl font-semibold mb-3">AI辅助开发</h3>
                    <p class="text-gray-600 mb-4">使用AI生成页面代码、UI设计优化、代码注释完善</p>
                    <div class="w-full h-2 bg-gray-100 rounded-full overflow-hidden">
                        <div class="h-full bg-primary w-[88%]"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 5.项目作品模块 -->
    <section id="project" class="py-20 bg-white">
        <div class="container mx-auto px-4 md:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.6rem,4vw,2.4rem)] font-bold mb-3">项目作品</h2>
                <div class="w-20 h-1 bg-primary mx-auto"></div>
            </div>
            <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- 项目1 个人主页（当前页面） -->
                <div class="rounded-2xl overflow-hidden shadow-sm card-hover bg-gray-50">
                    <div class="h-48 bg-gradient-to-r from-primary to-blue-300 flex items-center justify-center">
                        <i class="fa-solid fa-globe text-7xl text-white/80"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-lg font-semibold mb-2">个人单页网站</h3>
                        <p class="text-gray-600 text-sm mb-4">基于Tailwind CSS开发的响应式个人作品集网站，包含完整六大模块，支持手机/电脑访问，可Gitee Pages一键上线。</p>
                        <div class="flex gap-2 flex-wrap mb-5">
                            <span class="text-xs bg-lightBlue text-primary px-3 py-1 rounded-full">HTML</span>
                            <span class="text-xs bg-lightBlue text-primary px-3 py-1 rounded-full">Tailwind CSS</span>
                            <span class="text-xs bg-lightBlue text-primary px-3 py-1 rounded-full">JS</span>
                        </div>
                        <a href="#" class="text-primary flex items-center gap-1 hover:gap-2 transition-all text-sm">
                            查看详情 <i class="fa-solid fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
                <!-- 项目2 天气预报页面 -->
                <div class="rounded-2xl overflow-hidden shadow-sm card-hover bg-gray-50">
                    <div class="h-48 bg-gradient-to-r from-sky-400 to-cyan-200 flex items-center justify-center">
                        <i class="fa-solid fa-cloud-sun text-7xl text-white/80"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-lg font-semibold mb-2">MD3风格天气预报页</h3>
                        <p class="text-gray-600 text-sm mb-4">Material Design3设计规范天气页面，可获取本地实时天气，包含温度、风力、湿度可视化卡片。</p>
                        <div class="flex gap-2 flex-wrap mb-5">
                            <span class="text-xs bg-lightBlue text-primary px-3 py-1 rounded-full">Android Compose</span>
                            <span class="text-xs bg-lightBlue text-primary px-3 py-1 rounded-full">MD3</span>
                        </div>
                        <a href="#" class="text-primary flex items-center gap-1 hover:gap-2 transition-all text-sm">
                            查看详情 <i class="fa-solid fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
                <!-- 项目3 简约企业官网 -->
                <div class="rounded-2xl overflow-hidden shadow-sm card-hover bg-gray-50">
                    <div class="h-48 bg-gradient-to-r from-indigo-500 to-blue-400 flex items-center justify-center">
                        <i class="fa-solid fa-building text-7xl text-white/80"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-lg font-semibold mb-2">科技企业官网模板</h3>
                        <p class="text-gray-600 text-sm mb-4">蓝色商务风企业单页官网，产品展示、客户案例、在线留言模块，全响应式适配移动端。</p>
                        <div class="flex gap-2 flex-wrap mb-5">
                            <span class="text-xs bg-lightBlue text-primary px-3 py-1 rounded-full">HTML</span>
                            <span class="text-xs bg-lightBlue text-primary px-3 py-1 rounded-full">Tailwind</span>
                        </div>
                        <a href="#" class="text-primary flex items-center gap-1 hover:gap-2 transition-all text-sm">
                            查看详情 <i class="fa-solid fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 6.联系方式模块 -->
    <section id="contact" class="py-20 bg-lightBlue">
        <div class="container mx-auto px-4 md:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.6rem,4vw,2.4rem)] font-bold mb-3">联系我</h2>
                <div class="w-20 h-1 bg-primary mx-auto"></div>
            </div>
            <div class="grid md:grid-cols-2 gap-12">
                <!-- 联系信息 -->
                <div class="space-y-8">
                    <p class="text-gray-700 text-lg max-w-lg">如果你有项目合作、技术交流、作业答疑需求，欢迎通过以下方式联系我，我会尽快回复！</p>
                    <div class="flex items-center gap-5">
                        <div class="w-14 h-14 rounded-full bg-white flex items-center justify-center text-primary text-xl shadow-sm">
                            <i class="fa-solid fa-envelope"></i>
                        </div>
                        <div>
                            <h4 class="font-medium mb-1">电子邮箱</h4>
                            <p class="text-gray-600">student@example.com</p>
                        </div>
                    </div>
                    <div class="flex items-center gap-5">
                        <div class="w-14 h-14 rounded-full bg-white flex items-center justify-center text-primary text-xl shadow-sm">
                            <i class="fa-brands fa-gitee"></i>
                        </div>
                        <div>
                            <h4 class="font-medium mb-1">Gitee仓库</h4>
                            <p class="text-gray-600">gitee.com/student-web</p>
                        </div>
                    </div>
                    <div class="flex items-center gap-5">
                        <div class="w-14 h-14 rounded-full bg-white flex items-center justify-center text-primary text-xl shadow-sm">
                            <i class="fa-solid fa-location-dot"></i>
                        </div>
                        <div>
                            <h4 class="font-medium mb-1">所在地</h4>
                            <p class="text-gray-600">河南省郑州市</p>
                        </div>
                    </div>
                </div>
                <!-- 留言表单 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm">
                    <form id="msgForm" class="space-y-6">
                        <div class="grid sm:grid-cols-2 gap-6">
                            <div>
                                <label class="block text-sm mb-2 text-gray-700">姓名</label>
                                <input type="text" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:outline-none focus:border-primary transition-colors" placeholder="请输入你的姓名">
                            </div>
                            <div>
                                <label class="block text-sm mb-2 text-gray-700">邮箱</label>
                                <input type="email" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:outline-none focus:border-primary transition-colors" placeholder="请输入你的邮箱">
                            </div>
                        </div>
                        <div>
                            <label class="block text-sm mb-2 text-gray-700">主题</label>
                            <input type="text" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:outline-none focus:border-primary transition-colors" placeholder="留言主题">
                        </div>
                        <div>
                            <label class="block text-sm mb-2 text-gray-700">留言内容</label>
                            <textarea rows="4" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:outline-none focus:border-primary transition-colors resize-none" placeholder="请输入你想说的内容..."></textarea>
                        </div>
                        <button type="submit" class="w-full bg-primary text-white py-4 rounded-lg hover:bg-secondary transition-colors font-medium">
                            发送留言
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- 页脚模块 -->
    <footer class="bg-darkGray text-white py-12">
        <div class="container mx-auto px-4 md:px-8">
            <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-8">
                <div>
                    <a href="#" class="text-xl font-bold flex items-center gap-2 mb-4">
                        <i class="fa-solid fa-code text-primary"></i>
                        MyPortfolio
                    </a>
                    <p class="text-gray-400 text-sm">现代化响应式个人作品集网站，使用Tailwind CSS开发，适配全终端设备。</p>
                </div>
                <div>
                    <h4 class="font-medium mb-4">快速导航</h4>
                    <div class="space-y-2 text-gray-400 text-sm">
                        <a href="#home" class="block hover:text-primary transition-colors">首页</a>
                        <a href="#about" class="block hover:text-primary transition-colors">个人简介</a>
                        <a href="#skill" class="block hover:text-primary transition-colors">技能展示</a>
                        <a href="#project" class="block hover:text-primary transition-colors">项目作品</a>
                    </div>
                </div>
                <div>
                    <h4 class="font-medium mb-4">项目资源</h4>
                    <div class="space-y-2 text-gray-400 text-sm">
                        <a href="#" class="block hover:text-primary transition-colors">Gitee源码仓库</a>
                        <a href="#" class="block hover:text-primary transition-colors">前端学习笔记</a>
                        <a href="#" class="block hover:text-primary transition-colors">免费UI素材</a>
                    </div>
                </div>
                <div>
                    <h4 class="font-medium mb-4">社交渠道</h4>
                    <div class="flex gap-4 text-xl text-gray-400">
                        <a href="#" class="hover:text-primary transition-colors"><i class="fa-brands fa-github"></i></a>
                        <a href="#" class="hover:text-primary transition-colors"><i class="fa-brands fa-gitee"></i></a>
                        <a href="#" class="hover:text-primary transition-colors"><i class="fa-brands fa-weixin"></i></a>
                        <a href="#" class="hover:text-primary transition-colors"><i class="fa-solid fa-envelope"></i></a>
                    </div>
                </div>
            </div>
            <div class="border-t border-gray-700 mt-10 pt-8 text-center text-gray-500 text-sm">
                © 2025 MyPortfolio 个人主页 | 基于AI辅助开发 保留所有版权
            </div>
        </div>
    </footer>

    <!-- 返回顶部按钮 -->
    <button id="backTop" class="fixed bottom-8 right-8 w-12 h-12 rounded-full bg-primary text-white shadow-lg hidden hover:bg-secondary transition-colors">
        <i class="fa-solid fa-arrow-up"></i>
    </button>

    <!-- 交互JS脚本 -->
    <script>
        // 1.移动端菜单切换
        const menuBtn = document.getElementById('menuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        menuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
            // 切换菜单图标
            const icon = menuBtn.querySelector('i');
            if(icon.classList.contains('fa-bars')){
                icon.classList.replace('fa-bars','fa-xmark');
            }else{
                icon.classList.replace('fa-xmark','fa-bars');
            }
        })
        // 点击导航链接关闭移动端菜单
        const mobileLinks = mobileMenu.querySelectorAll('a');
        mobileLinks.forEach(link=>{
            link.addEventListener('click',()=>{
                mobileMenu.classList.add('hidden');
                const icon = menuBtn.querySelector('i');
                icon.classList.replace('fa-xmark','fa-bars');
            })
        })

        // 2.导航栏滚动变色 + 导航激活态
        const navbar = document.getElementById('navbar');
        const sections = document.querySelectorAll('section[id]');
        const navLinks = document.querySelectorAll('.hidden.md\\:flex a');
        window.addEventListener('scroll',()=>{
            // 导航栏阴影
            if(window.scrollY > 80){
                navbar.classList.add('shadow-md');
            }else{
                navbar.classList.remove('shadow-md');
            }
            // 导航栏激活项
            let current = '';
            sections.forEach(section=>{
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if(window.scrollY >= sectionTop - 120){
                    current = section.getAttribute('id');
                }
            })
            navLinks.forEach(link=>{
                link.classList.remove('nav-link-active');
                if(link.getAttribute('href') === `#${current}`){
                    link.classList.add('nav-link-active');
                }
            })
        })

        // 3.返回顶部按钮
        const backTopBtn = document.getElementById('backTop');
        window.addEventListener('scroll',()=>{
            if(window.scrollY > 400){
                backTopBtn.classList.remove('hidden');
            }else{
                backTopBtn.classList.add('hidden');
            }
        })
        backTopBtn.addEventListener('click',()=>{
            window.scrollTo({top:0,behavior:'smooth'});
        })

        // 4.留言表单提交模拟
        const msgForm = document.getElementById('msgForm');
        msgForm.addEventListener('submit',(e)=>{
            e.preventDefault();
            alert('留言提交成功！我会尽快联系你');
            msgForm.reset();
        })
    </script>
</body>
</html>
