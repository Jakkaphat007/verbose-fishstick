<!DOCTYPE html>
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mercury Integrated Technology - Premium Building Systems & ICT Solutions</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Kanit & Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Kanit:wght@200;300;400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        navy: {
                            DEFAULT: '#152A56', // สีน้ำเงินหลักของโลโก้ Mercury (Logo Blue)
                            light: '#2C4F94',   
                            dark: '#0D1A36',    
                        },
                        yellow: { 
                            DEFAULT: '#FFC72C', // สีเหลืองทองเสื้อ Golden State Warriors (GSW Gold)
                            light: '#FFD66B',   
                            dark: '#D69E1F',    
                        },
                        neutralbg: '#FAF9F6', // พื้นหลังสีขาวครีม Alabaster สว่างสบายตา คลีนสะอาด
                    },
                    fontFamily: {
                        sans: ['Kanit', 'Inter', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #FAF9F6;
            font-family: 'Kanit', 'Inter', sans-serif;
        }
        /* ระบบควบคุมการสลับพิกัด 2 ภาษา */
        .lang-en [lang="th"] { display: none !important; }
        .lang-th [lang="en"] { display: none !important; }
        
        /* สไตล์หน้าต่างกระจกหรูหราฝ้าโปร่งแสง (Luxury Glassmorphism) */
        .luxury-glass {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 255, 255, 0.4);
        }
    </style>
</head>
<body class="lang-th text-navy min-h-screen flex flex-col selection:bg-yellow/30">

    <!-- เมนูนำทางแถบบน (Navigation Header พร้อมสัญลักษณ์แบรนด์แบบ SVG วาดขึ้นรูปเพื่อความเร็วสูงสุด) -->
    <header class="fixed top-0 w-full z-50 bg-navy/95 backdrop-blur-md border-b border-white/5 shadow-lg transition-all duration-300">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <!-- ตราสัญลักษณ์โลโก้จริงและชื่อหน่วยงานประจำแบรนด์ -->
            <a href="#homepage" class="flex items-center">
                <img src="Logo Mercury.png"
                     alt="Mercury"
                     class="h-32 w-auto">

            </a>

            <!-- รายชื่อรายการนำทางหน้ากระดานคอมพิวเตอร์ -->  
            <nav class="hidden md:flex items-center space-x-8">
                <a href="#about" class="text-gray-300 hover:text-yellow text-sm font-light tracking-wide transition-colors">
                    <span lang="th">เกี่ยวกับเรา</span>
                    <span lang="en">About us</span>
                </a>
                <a href="#products" class="text-gray-300 hover:text-yellow text-sm font-light tracking-wide transition-colors">
                    <span lang="th">สินค้าและบริการ</span>
                    <span lang="en">Products & Services</span>
                </a>
                <a href="#references" class="text-gray-300 hover:text-yellow text-sm font-light tracking-wide transition-colors">
                    <span lang="th">ผลงานอ้างอิง</span>
                    <span lang="en">Site References</span>
                </a>
                <a href="#contact" class="text-gray-300 hover:text-yellow text-sm font-light tracking-wide transition-colors">
                    <span lang="th">ติดต่อเรา</span>
                    <span lang="en">Contact us</span>
                </a>
            </nav>

            <div class="flex items-center space-x-4">
                <!-- สวิตช์ปุ่มเปลี่ยนภาษาพรีเมียม TH/EN -->
                <div class="flex items-center bg-white/5 border border-white/10 rounded-full p-1">
                    <button onclick="switchLanguage('th')" id="lang-btn-th" class="px-3 py-1 rounded-full text-xs font-medium transition-all duration-300 bg-yellow text-navy shadow-sm">TH</button>
                    <button onclick="switchLanguage('en')" id="lang-btn-en" class="px-3 py-1 rounded-full text-xs font-medium transition-all duration-300 text-gray-400 hover:text-white">EN</button>
                </div>
                <button onclick="toggleMobileMenu()" class="md:hidden text-white focus:outline-none p-2 rounded-lg hover:bg-white/5">
                    <svg id="hamburger-icon" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"/></svg>
                </button>
            </div>
        </div>

        <!-- รายการสไลด์สำหรับมือถือโทรศัพท์ -->
        <div id="mobile-menu" class="hidden md:hidden bg-navy-dark/95 border-b border-white/5 px-6 py-6 space-y-4">
            <a href="#about" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-yellow text-base font-light py-2">
                <span lang="th">เกี่ยวกับเรา</span>
                <span lang="en">About us</span>
            </a>
            <a href="#products" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-yellow text-base font-light py-2">
                <span lang="th">สินค้าและบริการ</span>
                <span lang="en">Products & Services</span>
            </a>
            <a href="#references" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-yellow text-base font-light py-2">
                <span lang="th">ผลงานอ้างอิง</span>
                <span lang="en">Site References</span>
            </a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block text-gray-300 hover:text-yellow text-base font-light py-2">
                <span lang="th">ติดต่อเรา</span>
                <span lang="en">Contact us</span>
            </a>
        </div>
    </header>

    <!-- ส่วนต้อนรับแรก (Hero Section) - ดึงภาพจำลองกระจกไร้ขอบสว่างหรูหราพาดทับข้อความคมชัดเด่นสง่างาม -->
    <section id="homepage" class="relative min-h-[90vh] md:min-h-screen flex items-center justify-center bg-white pt-20 overflow-hidden">
        <div class="absolute inset-0 z-0">
            <!-- ม่านสีขาวสว่าง Overlay เพื่อขับเน้นตรรกะดีไซน์ที่คลีนและอ่านตัวอักษรเนวี่ง่ายที่สุด -->
            <div class="absolute inset-0 bg-white/80 z-10"></div>
            <!-- ภาพกระจกไร้ขอบหรูหรา แสงอาทิตย์สว่างไสว ปลอดภัยด้านลิขสิทธิ์ 100% และโหลดเร็วเป็นพิเศษ -->
            <img src="1.png" alt="Mercury Premium Space Background" class="w-full h-full object-cover object-center scale-105">
        </div>

        <div class="max-w-7xl mx-auto px-6 relative z-20 w-full py-16">
            <div class="max-w-3xl">
                <!-- ตราสัญลักษณ์โลโก้พรีเมียมแสดงใจกลางหน้าแรกเหนือสโลแกน -->
                <div class="mb-8 inline-block rounded-2xl luxury-glass p-4 border border-navy/10 shadow-xl relative">
                    <svg class="h-16 w-16 text-navy" viewBox="0 0 100 100" fill="none">
                        <circle cx="50" cy="50" r="35" stroke="currentColor" stroke-width="5" />
                        <ellipse cx="50" cy="50" rx="42" ry="14" stroke="currentColor" stroke-width="4" transform="rotate(-30 50 50)" />
                        <circle cx="50" cy="50" r="10" fill="currentColor" />
                    </svg>
                </div>  

                <div class="inline-flex items-center space-x-2 bg-yellow/10 border border-yellow/20 text-navy px-4 py-2 rounded-full mb-6">
                    <span class="w-2 h-2 rounded-full bg-yellow animate-pulse"></span>
                    <span class="text-xs uppercase tracking-[0.2em] font-medium font-sans">
                        <span lang="th">ระบบวิศวกรรมอาคารและการบริการครบวงจร</span>
                        <span lang="en">PREMIUM BUILDING SYSTEMS & ICT SYSTEM INTEGRATION</span>
                    </span>
                </div>
                
                <h1 class="text-navy text-4xl sm:text-5xl md:text-6xl font-bold leading-none tracking-tight mb-6">
                    IT Architecting<br><span class="text-yellow-dark">the Invisible</span>
                </h1>
                
                <p class="text-gray-700 text-base sm:text-lg md:text-xl font-light mb-10 leading-relaxed font-sans max-w-2xl">
                    <span lang="th">คราฟต์ระบบโครงสร้างพื้นฐานไอที พลังงานทางเลือก และระบบควบคุมอัจฉริยะเบื้องหลังความพรีเมียม สำหรับโรงแรมและศูนย์การค้า 5 ดาวทั่วประเทศ ด้วยความประณีตเรียบร้อยสูงสุด (Neat Finish)</span>
                    <span lang="en">Designing complex, high-efficiency behind-the-scenes ICT networks and sustainable building topologies. Executed meticulously with our signature "neat finish" standard.</span>
                </p>

                <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
                    <a href="#products" class="bg-navy hover:bg-navy-light text-white font-semibold px-8 py-4 rounded-lg shadow-lg hover:shadow-navy/20 transition-all duration-300 text-center">
                        <span lang="th">ดูบริการของเรา</span>
                        <span lang="en">Explore Services</span>
                    </a>
                    <a href="#contact" class="border border-navy/20 hover:border-yellow/50 text-navy hover:text-yellow-dark px-8 py-4 rounded-lg transition-all duration-300 text-center bg-white/5 backdrop-blur-sm">
                        <span lang="th">ปรึกษาวิศวกร</span>
                        <span lang="en">Contact Our Team</span>
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- ส่วนที่ 1: เกี่ยวกับเรา (About Section) - พื้นหลัง Data Center 10% Opacity โปร่งสบายตาสไตล์โมเดิร์น -->
    <section id="about" class="py-24 bg-white relative overflow-hidden">
        <div class="absolute inset-0 z-0 pointer-events-none">
            <div class="absolute inset-0 bg-white/95 z-10"></div>
            <!-- ดึงรูปจาก Unsplash โทนห้อง Server Room สะอาดๆ สว่างและคมชัดสูงสุด -->
            <img src="2.png" alt="Data Center Background" class="w-full h-full object-cover object-center opacity-10">
        </div>

        <div class="max-w-7xl mx-auto px-6 relative z-20">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-16 items-center">
                <div class="lg:col-span-7 space-y-6">
                    <h2 class="text-yellow-dark font-light uppercase tracking-[0.25em] text-sm">
                        <span lang="th">เกี่ยวกับ เมอร์คิวรี</span>
                        <span lang="en">About Mercury</span>
                    </h2>
                    <h3 class="text-navy text-3xl sm:text-4xl font-semibold leading-tight tracking-tight">
                        <span lang="th">เราคือผู้เชี่ยวชาญวิศวกรรมระบบอาคารและไอทีครบวงจร</span>
                        <span lang="en">We are premier system integrators for smart building technology.</span>
                    </h3>
                    <p class="text-gray-600 font-light leading-relaxed text-base sm:text-lg">
                        <span lang="th">บริษัท เมอร์คิวรี อินทิเกรเต็ด เทคโนโลยี จำกัด (MIT) เป็นพันธมิตรที่ได้รับความไว้วางใจสำหรับธุรกิจโรงแรม รีสอร์ท และโครงการศูนย์การค้าขนาดใหญ่ทั่วประเทศไทย เราไม่เพียงแต่วางระบบเครือข่าย แต่เรานำวิสัยทัศน์ของผู้ประกอบการมาออกแบบทางเทคนิคเพื่อลดความผิดพลาดและงบประมาณบานปลาย</span>
                        <span lang="en">Mercury Integrated Technology (MIT) operates as a premium partner assisting hotels, resorts, and luxury commercial real estates across Thailand. We translate operational workflows into high-efficiency architectural engineering designs, ensuring low maintenance and seamless uptime.</span>
                    </p>

                    <div class="bg-neutralbg border-l-4 border-yellow p-6 rounded-r-xl space-y-2 my-4 shadow-sm">
                        <h4 class="text-navy font-semibold text-lg">
                            <span lang="th">มาตรฐานผลงานแบบ "Neat Finish" (ความประณีตระดับสูงสุด)</span>
                            <span lang="en">The Signature "Neat Finish" Standard</span>
                        </h4>
                        <p class="text-gray-600 font-light text-sm leading-relaxed">
                            <span lang="th">ไม่เพียงแต่ระบบการใช้งานที่สมบูรณ์แบบเท่านั้น แต่ทุกโครงการเราบรรจงติดตั้งอุปกรณ์ วางสายเคเบิล และเซ็ตอัประบบควบคุมให้สะอาด เป็นระเบียบ เรียบร้อยสูงสุด เพื่อป้องกันคลื่นรบกวนสัญญาณ และทำให้การบำรุงรักษาในอนาคตทำได้ง่ายและประหยัดที่สุด</span>
                            <span lang="en">Every network rack, cable runway, and control station we deliver is clean, labeled, and physically flawless. Highly organized routing prevents signal deterioration, speeds up repairs, and dramatically reduces diagnostic times.</span>
                        </p>
                    </div>

                    <div class="grid grid-cols-3 gap-6 pt-6">
                        <div class="space-y-1">
                            <span class="block text-3xl sm:text-4xl font-semibold text-navy">100%</span>
                            <span class="block text-xs uppercase tracking-wider text-gray-500">
                                <span lang="th">มาตรฐาน Neat Finish</span>
                                <span lang="en">Neat Finish Quality</span>
                            </span>
                        </div>
                        <div class="space-y-1">
                            <span class="block text-3xl sm:text-4xl font-semibold text-navy">1,000+</span>
                            <span class="block text-xs uppercase tracking-wider text-gray-500">
                                <span lang="th">กล้อง CCTV ณ สนามบินหลัก</span>
                                <span lang="en">CCTV deploy scale</span>
                            </span>
                        </div>
                        <div class="space-y-1">
                            <span class="block text-3xl sm:text-4xl font-semibold text-navy">24/7</span>
                            <span class="block text-xs uppercase tracking-wider text-gray-500">
                                <span lang="th">การสนับสนุนดูแลระบบ</span>
                                <span lang="en">Critical Support</span>
                            </span>
                        </div>
                    </div>
                </div>

                <div class="lg:col-span-5 relative">
                    <div class="aspect-square w-full rounded-3xl bg-neutralbg p-1 shadow-xl relative overflow-hidden flex items-center justify-center">
                        <img src="3.png" alt="Elegance Luxury Workspace" class="w-full h-full object-cover rounded-2xl opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-tr from-white/40 to-transparent"></div>
                        <div class="absolute bottom-6 left-6 right-6 backdrop-blur-md rounded-xl p-6 shadow-lg" style="background: rgba(255, 255, 255, 0.75); border: 1px solid rgba(255, 255, 255, 0.4);">
                            <h4 class="text-navy font-semibold text-base">
                                <span lang="th">สถาปัตยกรรมเทคโนโลยีที่โปร่งใสไร้ขอบเขต</span>
                                <span lang="en">Elegance in Engineering & Infrastructure</span>
                            </h4>
                            <p class="text-gray-600 font-light text-xs mt-1 leading-relaxed">
                                <span lang="th">เราออกแบบเพื่อสุนทรียศาสตร์ของสถานที่ที่กลมกลืนกับเทคโนโลยีล้ำสมัย</span>
                                <span lang="en">We blend advanced smart technologies into premium structures without disrupting aesthetics.</span>
                            </p>
                        </div>
                    </div>
                    <div class="absolute -bottom-4 -right-4 w-full h-full border border-yellow/25 rounded-3xl -z-10 hidden sm:block"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- ส่วนที่ 2: สินค้าและบริการ (Products Section) - แบคกราวด์ Smart City/Infrastructure คลีนเสถียร 10% Opacity -->
    <section id="products" class="py-24 bg-neutralbg relative overflow-hidden">
        <div class="absolute inset-0 z-0 pointer-events-none">
            <div class="absolute inset-0 bg-neutralbg/95 z-10"></div>
            <!-- ดึงรูปจาก Unsplash โทนตึกสถาปัตยกรรมกระจกสว่างไสว สะอาดตา -->
            <img src="ตึกสถาปัตยกรรมกระจกสว่างไสว.png" alt="Smart City Infrastructure Background" class="w-full h-full object-cover object-center opacity-10">
        </div>

        <div class="max-w-7xl mx-auto px-6 relative z-20">
            <div class="text-center max-w-3xl mx-auto mb-16 space-y-4">
                <h2 class="text-yellow-dark font-light uppercase tracking-[0.25em] text-sm">
                    <span lang="th">ขีดความสามารถทางวิศวกรรม</span>
                    <span lang="en">Engineering Scope</span>
                </h2>
                <h3 class="text-navy text-3xl sm:text-4xl font-semibold tracking-tight">
                    <span lang="th">สินค้าและบริการระบบอัจฉริยะแบบครบวงจร</span>
                    <span lang="en">9 Smart Technology Pillars for Modern Spaces</span>
                </h3>
                <p class="text-gray-500 font-light text-base leading-relaxed">
                    <span lang="th">เราพร้อมให้บริการตลอดรอบวงจรตั้งแต่การให้คำปรึกษา การออกแบบโครงสร้างเชิงตรรกะและแผนผังสาย (Design Layout) การจัดหา และการติดตั้งพร้อมสนับสนุนบำรุงรักษาอย่างมืออาชีพ</span>
                    <span lang="en">Comprehensive services from logical system architecture and budget consulting, to premium site physical implementation and long-term diagnostic support.</span>
                </p>
            </div>

            <!-- รายละเอียดตารางสินค้าหลักทั้ง 9 รายการ -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- 1. IT Network -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(1)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">โครงสร้างเครือข่ายความเร็วสูง</span>
                            <span lang="en">IT Network & Infrastructure</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">บริการออกแบบและติดตั้งระบบเครือข่ายประสิทธิภาพสูง สายใยแก้วนำแสง (Fiber Optic) และสายทองแดง สำหรับโครงการ โรงแรม สวิตช์สลับเครือข่ายความเร็วสูง และระบบบริหารจัดเก็บเงินการใช้เน็ตผู้เข้าพัก (Internet Billing)</span>
                            <span lang="en">Complete high-speed networks, robust fiber optics backbone, structured horizontal cabling, guest internet gate, and local access billing software.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 2. Security & CCTV -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(2)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">ระบบความปลอดภัยและเฝ้าระวัง</span>
                            <span lang="en">Security & CCTV Solutions</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">ระบบรักษาความปลอดภัยประสิทธิภาพสูงด้วยกล้อง IP และอนาล็อก เครื่องบันทึกข้อมูลเครือข่ายอัจฉริยะ (NVR/DVR) และระบบจำกัดสิทธิ์การเข้าออก (Access Control) เพื่อความปลอดภัยสูงสุด</span>
                            <span lang="en">Reliable high-definition security camera arrays, redundant remote recording systems, secure servers, and customizable proximity keycard access controls.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 3. People Counting & Face Recognition -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(3)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">ตรวจจับใบหน้าและนับคน</span>
                            <span lang="en">Counting & Face Recognition</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">วิเคราะห์พฤติกรรมลูกค้าด้วย AI นับจำนวนผู้ผ่านประตู (People Counting) เพื่อใช้วัดผลความหนาแน่นเชิงสถิติ และระบบจดจำใบหน้าสำหรับพื้นที่ควบคุมระดับพรีเมียม</span>
                            <span lang="en">AI-driven biometric video analytics tracking physical audience density, smart floor maps, VIP face logging, and automated occupancy reports.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 4. Communication & Wireless PA -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(4)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.536 8.464a5 5 0 010 7.072m2.828-9.9a9 9 0 010 12.728M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">ระบบสื่อสารและเสียงตามสายไร้สาย</span>
                            <span lang="en">Communication & Wireless PA</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">ระบบสารบันเทิงในโรงแรม (MATV/IPTV) และระบบโทรศัพท์ตู้สาขา (PABX) ร่วมกับระบบกระจายเสียงแบบไร้สายเพื่อช่วยโฆษณา คลอเพลงเบาๆ หรือประกาศสถานการณ์ฉุกเฉินผ่านสัญญาณ IP ไร้รอยต่อ</span>
                            <span lang="en">Unified master antenna/IPTV setups, local PABX networks, and wireless IP speakers broadcasting warnings or ambient music without massive structural piping.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 5. Digital Signage / VDO Wall -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(5)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 12l3-3 3 3 4-4M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">จอโฆษณาอัจฉริยะและวิดีโอวอลล์</span>
                            <span lang="en">Digital Signage & VDO Wall</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">การติดตั้งระบบป้ายจอประชาสัมพันธ์ดิจิทัลและจอวิดีโอวอลล์ขนาดใหญ่ความหนาแน่นสูง ไร้รอยต่อขอบบาง สำหรับห้องประชุม ล็อบบี้ และห้างสรรพสินค้า พร้อมโปรแกรมจัดการข้อมูลระยะไกลส่วนกลาง</span>
                            <span lang="en">High-end video walls with razor-thin bezels, corporate lobby presentation monitors, and customized content management software.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 6. Smart ESL -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(6)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 7h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">ป้ายราคาอิเล็กทรอนิกส์อัจฉริยะ</span>
                            <span lang="en">Electronic Shelf Label (ESL)</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">โซลูชันป้ายไร้สายอัจฉริยะปรับปรุงข้อมูลราคาและแคมเปญบนชั้นวางได้พร้อมกันเรียลไทม์ เชื่อมโยงฐานข้อมูลการคิดเงินลดต้นทุนกระดาษและพนักงานจัดโปรให้แม่นยำ 100%</span>
                            <span lang="en">Digital wireless displays dynamically syncing shelves with core inventory POS database, automating price markdowns and reducing manual labor errors.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 7. Green & Smart Energy -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(7)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">พลังงานทดแทนเพื่อความยั่งยืน (Solar / EV)</span>
                            <span lang="en">Renewable & Smart Energy</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">สำรวจ ออกแบบ วางระบบโซลาร์เซลล์บนหลังคา (Solar Rooftop) เพื่อการอนุรักษ์พลังงานในระยะยาว พร้อมงานติดตั้งเครื่องสถานีชาร์จรถยนต์ไฟฟ้า (EV Charger) มาตรฐานวิศวกรรมความปลอดภัยสูง</span>
                            <span lang="en">Professional Solar Rooftop feasibility surveys, structural loads engineering, solar array wiring setups, and smart commercial EV Charging ports.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 8. Audio Visual (AV) -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(8)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5.882V19.24a1.76 1.76 0 01-3.417.592l-2.147-6.15M18 13a3 3 0 100-6M5.436 13.683A4.001 4.001 0 017 6h1.832c4.1 0 7.625-1.234 9.168-3v14c-1.543-1.766-5.067-3-9.168-3H7a3.988 3.988 0 01-1.564-.317z"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">ระบบแสง เสียง และภาพ</span>
                            <span lang="en">Audio Visual (AV) System</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">ออกแบบและจัดหาอุปกรณ์ระบบภาพเสียงความเสถียรสูงสำหรับติดตั้งในห้องประชุมใหญ่ ห้องจัดเลี้ยง หรือพื้นที่ส่วนกลางของโรงแรมเพื่อประสบการณ์การสื่อสารที่ราบรื่น</span>
                            <span lang="en">Premium integrated Audio & Visual topologies for conference rooms, ballrooms, and public spaces, ensuring flawless AV fidelity.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

                <!-- 9. Fire Alarm System -->
                <div class="group bg-white border border-gray-100 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:border-yellow/20 transition-all duration-300 flex flex-col justify-between cursor-pointer" onclick="openProductDetail(9)">
                    <div class="space-y-4">
                        <div class="w-12 h-12 bg-yellow/10 text-yellow rounded-xl flex items-center justify-center group-hover:bg-yellow group-hover:text-white transition-all duration-300">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"/></svg>
                        </div>
                        <h4 class="text-navy font-semibold text-lg group-hover:text-yellow transition-colors">
                            <span lang="th">ระบบแจ้งเตือนอัคคีภัยอัจฉริยะ</span>
                            <span lang="en">Smart Fire Alarm Systems</span>
                        </h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed line-clamp-3">
                            <span lang="th">ออกแบบ ติดตั้ง และบำรุงรักษาระบบแจ้งเหตุเพลิงไหม้ มาตรฐานสากลเพื่อความปลอดภัยของอาคาร ชีวิต และทรัพย์สิน ควบคุมสัญญาณรวมศูนย์เชื่อมต่อรวดเร็ว</span>
                            <span lang="en">Design, installation, and maintenance of addressable fire detection systems compliant with international safety codes and central alarm panels.</span>
                        </p>
                    </div>
                    <span class="text-yellow text-xs font-medium tracking-wider group-hover:translate-x-1 transition-transform inline-flex items-center space-x-1 pt-6">
                        <span lang="th">ดูรายละเอียด</span><span lang="en">View Details</span> &rarr;
                    </span>
                </div>

            </div>
        </div>
    </section>

    <!-- Section: Site Reference (แกลเลอรีสว่างสะอาด เรียบหรู - พื้นหลังท่าอากาศยาน Suvarnabhumi / King Power ปรับความโปร่งแสงเบาบาง 10%) -->
    <section id="references" class="py-24 bg-white relative overflow-hidden">
        <!-- ภาพพื้นหลังหลักของ Reference: สนามบินสุวรรณภูมิคมชัดพรีเมียม (ปรับความเข้มเหลือ 10%) -->
        <div class="absolute inset-0 z-0 pointer-events-none">
            <div class="absolute inset-0 bg-white/95 z-10"></div>
            <!-- ดึงรูปจาก Unsplash โทนสนามบินสว่างหรูหรา และมีผลทันทีในพรีวิว -->
            <img src="สนามบินสว่างหรูหรา.png" alt="Suvarnabhumi Terminal Infrastructure Background" class="w-full h-full object-cover object-center opacity-10">
        </div>

        <div class="max-w-7xl mx-auto px-6 relative z-20">
            <!-- Title Header -->
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-16 space-y-6 md:space-y-0">
                <div class="space-y-4 max-w-xl">
                    <h2 class="text-yellow-dark font-light uppercase tracking-[0.25em] text-sm">
                        <span lang="th">ผลงานที่ไว้วางใจ</span>
                        <span lang="en">Our Projects</span>
                    </h2>
                    <h3 class="text-navy text-3xl sm:text-4xl font-semibold tracking-tight">
                        <span lang="th">สถาปัตยกรรมระบบไอทีที่ได้รับการยอมรับจากพาร์ทเนอร์ระดับสากล</span>
                        <span lang="en">Premium Project References</span>
                    </h3>
                </div>

                <!-- แถบปุ่มกรองฟิลเตอร์คัดเลือกผลงาน -->
                <div class="flex flex-wrap gap-2 border-b border-gray-100 pb-2">
                    <button onclick="filterReferences('all')" id="ref-tab-all" class="px-5 py-2 rounded-full text-sm font-medium transition-all duration-300 bg-navy text-white shadow">
                        <span lang="th">ทั้งหมด</span><span lang="en">All Projects</span>
                    </button>
                    <button onclick="filterReferences('hospitality')" id="ref-tab-hospitality" class="px-5 py-2 rounded-full text-sm font-medium transition-all duration-300 text-gray-500 hover:text-navy hover:bg-gray-100">
                        <span lang="th">โรงแรม & รีสอร์ท</span><span lang="en">Hotels & Resorts</span>
                    </button>
                    <button onclick="filterReferences('commercial')" id="ref-tab-commercial" class="px-5 py-2 rounded-full text-sm font-medium transition-all duration-300 text-gray-500 hover:text-navy hover:bg-gray-100">
                        <span lang="th">เชิงพาณิชย์ & ค้าปลีก</span><span lang="en">Retail & Offices</span>
                    </button>
                </div>
            </div>

            <!-- ตารางแสดงโครงการอ้างอิงหลัก -->
            <div id="references-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- 1. King Power Suvarnabhumi -->
                <div class="ref-card hospitality commercial group bg-neutralbg rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500 cursor-pointer"onclick="window.location.href='project-suvarnabhumi.html'">
                    <div class="h-64 overflow-hidden relative">
                        <!-- ดึงรูปจาก Unsplash โทนสนามบินสว่างพรีเมียม -->
                        <img src="Suvarnabhumi.png" alt="Suvarnabhumi Airport Terminal Concept" class="w-full h-full object-cover object-center group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute top-4 left-4 bg-navy/80 text-yellow text-xs uppercase px-3 py-1 rounded-full font-medium tracking-wide">Suvarnabhumi Airport</div>
                    </div>
                    <div class="p-8 space-y-3 bg-white">
                        <h4 class="text-navy font-semibold text-xl group-hover:text-yellow transition-colors">KING POWER - Suvarnabhumi Airport</h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed">
                            <span lang="th">งานติดตั้งวางโครงข่ายสายสัญญาณความเร็วสูง และระบบกล้องวงจรปิด CCTV ทั่วบริเวณรวมกว่า 1,000 กล้อง ทั้งในอาคารหลังเดิมและอาคารขยายใหม่</span>
                            <span lang="en">Structured network cabling, complete high-density backbone, and CCTV integration encompassing over 1,000 cameras across existing and new terminals.</span>
                        </p>
                        <span class="block text-[10px] text-gray-400 italic pt-1">*ภาพจำลองเชิงแนวคิด / Conceptual Representation</span>
                    </div>
                </div>

                <!-- 2. One Bangkok (King Power City Boutiques) -->
                <div class="ref-card hospitality commercial group bg-neutralbg rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500 cursor-pointer"onclick="window.location.href='ONE BANGKOK (KING POWER CITY BOUTIQUES).html'">
                    <div class="h-64 overflow-hidden relative">
                        <img src="One Bangkok.png" alt="Boutique Luxury Interior Glass Concept" class="w-full h-full object-cover object-center group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute top-4 left-4 bg-navy/80 text-yellow text-xs uppercase px-3 py-1 rounded-full font-medium tracking-wide">One Bangkok</div>
                    </div>
                    <div class="p-8 space-y-3 bg-white">
                        <h4 class="text-navy font-semibold text-xl group-hover:text-yellow transition-colors">ONE BANGKOK (KING POWER CITY BOUTIQUES)</h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed">
                            <span lang="th">งานออกแบบสถาปัตยกรรมเครือข่าย วางระบบสายสัญญาณสื่อสาร และการติดตั้งระบบกล้องวงจรปิด CCTV ครอบคลุมกว่า 150 กล้อง</span>
                            <span lang="en">Premium backbone physical execution, architectural low-voltage cabling, and detailed design implementation of a 150-camera surveillance system.</span>
                        </p>
                        <span class="block text-[10px] text-gray-400 italic pt-1">*ภาพจำลองเชิงแนวคิด / Conceptual Representation</span>
                    </div>
                </div>

                <!-- 3. The Standard Hotel Bangkok -->
                <div class="ref-card hospitality group bg-neutralbg rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500" data-category="hospitality">
                    <div class="h-64 overflow-hidden relative">
                        <img src="The Standard Hotel Bangkok.png" alt="Chic Modern Luxury Hotel Concept" class="w-full h-full object-cover object-center group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute top-4 left-4 bg-navy/80 text-yellow text-xs uppercase px-3 py-1 rounded-full font-medium tracking-wide">Hospitality</div>
                    </div>
                    <div class="p-8 space-y-3 bg-white">
                        <h4 class="text-navy font-semibold text-xl group-hover:text-yellow transition-colors">The Standard Hotel Bangkok</h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed">
                            <span lang="th">การวางระบบเซิร์ฟเวอร์หลัก วิศวกรรมสายเคเบิลระบบไอทีและสื่อสาร (Structured IT Cabling) และระบบเชื่อมโยงสื่อสารความเร็วสูงรองรับการทำงานของอาคารทั้งหมด</span>
                            <span lang="en">Full-scale deployment of core IT systems servers, comprehensive low-voltage structured cabling, and high-performance network topologies.</span>
                        </p>
                        <span class="block text-[10px] text-gray-400 italic pt-1">*ภาพจำลองเชิงแนวคิด / Conceptual Representation</span>
                    </div>
                </div>

                <!-- 4. Renaissance Phuket Resort & Spa -->
                <div class="ref-card hospitality group bg-neutralbg rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500" data-category="hospitality">
                    <div class="h-64 overflow-hidden relative">
                        <img src="Renaissance Phuket Resort & Spa.png" alt="Tropical Luxury Resort Concept" class="w-full h-full object-cover object-center group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute top-4 left-4 bg-navy/80 text-yellow text-xs uppercase px-3 py-1 rounded-full font-medium tracking-wide">Hospitality</div>
                    </div>
                    <div class="p-8 space-y-3 bg-white">
                        <h4 class="text-navy font-semibold text-xl group-hover:text-yellow transition-colors">Renaissance Phuket Resort & Spa</h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed">
                            <span lang="th">ออกแบบสถาปัตยกรรมโครงสร้างเชิงความปลอดภัย และดำเนินการเดินระบบรวมถึงติดตั้งระบบกล้องวงจรปิด CCTV เฝ้าระวัง</span>
                            <span lang="en">Physical security planning, site analysis, system layout blueprints, and flawless end-to-end installation of security CCTV cameras.</span>
                        </p>
                        <span class="block text-[10px] text-gray-400 italic pt-1">*ภาพจำลองเชิงแนวคิด / Conceptual Representation</span>
                    </div>
                </div>

                <!-- 5. Anantara Layan Residences -->
                <div class="ref-card hospitality group bg-neutralbg rounded-2xl overflow-hidden shadow-sm hover:shadow-xl duration-500" data-category="hospitality">
                    <div class="h-64 overflow-hidden relative">
                        <img src="Anantara Layan Residences.png" alt="Private Luxury Pool Villa Concept" class="w-full h-full object-cover object-center group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute top-4 left-4 bg-navy/80 text-yellow text-xs uppercase px-3 py-1 rounded-full font-medium tracking-wide">Hospitality</div>
                    </div>
                    <div class="p-8 space-y-3 bg-white">
                        <h4 class="text-navy font-semibold text-xl group-hover:text-yellow transition-colors">Anantara Layan Residences</h4>
                        <p class="text-gray-500 text-sm font-light leading-relaxed">
                            <span lang="th">ออกแบบ จัดทำแผนงานติดตั้งระบบกล้องเฝ้าระวังความปลอดภัยระดับพรีเมียม (IP-CCTV) และระบบบันทึกความปลอดภัยหลัก (NVR Host)</span>
                            <span lang="en">Highly detailed high-definition IP-CCTV deployment involving multi-channel recording network nodes custom-tailored for super-luxury residential estates.</span>
                        </p>
                        <span class="block text-[10px] text-gray-400 italic pt-1">*ภาพจำลองเชิงแนวคิด / Conceptual Representation</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section: Contact Us (ภาพพื้นหลังสำนักงานกระจกหรูหราพรีเมียม สบายตา 10% Opacity) -->
        <section id="contact" class="py-24 bg-neutralbg relative overflow-hidden">
            <!-- ภาพพื้นหลังสากล: Modern Office Interior (ปรับความเข้มเหลือ 10%) -->
            <div class="absolute inset-0 z-0 pointer-events-none">
                <div class="absolute inset-0 bg-neutralbg/95 z-10"></div>
                <img src="Modern Office Interior.png" alt="Modern Glass Office Tower Background" class="w-full h-full object-cover object-center opacity-10">
            </div>

            <div class="max-w-7xl mx-auto px-6 relative z-20">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-16">
                    <!-- รายละเอียดสถานที่ตั้งสำนักงาน -->
                    <div class="lg:col-span-5 space-y-8">
                        <div class="space-y-4">
                            <h2 class="text-yellow-dark font-light uppercase tracking-[0.25em] text-sm">
                                <span lang="th">ร่วมงานกับเรา</span>
                                <span lang="en">Let's Connect</span>
                            </h2>
                            <h3 class="text-navy text-3xl sm:text-4xl font-semibold tracking-tight">
                                <span lang="th">เริ่มโครงการของคุณกับเราวันนี้</span>
                                <span lang="en">Consult our engineering team for your next major project.</span>
                            </h3>
                            <p class="text-gray-500 font-light text-sm sm:text-base leading-relaxed">
                                <span lang="th">ทีมวิศวกรผู้เชี่ยวชาญพร้อมให้คำปรึกษา ออกแบบโครงสร้างแผนผัง และวางงบประมาณระบบที่ตอบโจทย์โครงสร้างธุรกิจคุณได้ถูกต้องสูงสุดเพื่อความคุ้มค่าระยะยาว</span>
                                <span lang="en">Provide us with your project blueprint or design needs, and our technical architecture experts will deliver optimized topology planning.</span>
                            </p>
                        </div>

                        <!-- Location 1: Phuket -->
                        <div class="bg-white p-6 rounded-2xl shadow-sm border border-gray-100 space-y-3">
                            <span class="inline-block px-3 py-1 bg-yellow/10 text-yellow-dark text-xs uppercase font-medium rounded-full tracking-wider">
                                <span lang="th">สำนักงานใหญ่ (ภูเก็ต)</span>
                                <span lang="en">Phuket Head Office</span>
                            </span>
                            <h4 class="text-navy font-semibold text-lg">Phuket, Ratsada</h4>
                            <p class="text-gray-500 font-light text-sm leading-relaxed">
                                <span lang="th">156/73 ถนนประชาสามัคคี ตำบลรัษฎา อำเภอเมือง จังหวัดภูเก็ต 83000</span>
                                <span lang="en">156/73 Prachasamakkee Road, Ratsada, Mueang Phuket, Phuket 83000, Thailand</span>
                            </p>
                        </div>

                        <!-- Location 2: BKK -->
                        <div class="bg-white p-6 rounded-2xl shadow-sm border border-gray-100 space-y-3">
                            <span class="inline-block px-3 py-1 bg-navy/5 text-navy text-xs uppercase font-medium rounded-full tracking-wider">
                                <span lang="th">สำนักงานกรุงเทพฯ</span>
                                <span lang="en">Bangkok Branch</span>
                            </span>
                            <h4 class="text-navy font-semibold text-lg">Wangthonglang BKK</h4>
                            <p class="text-gray-500 font-light text-sm leading-relaxed">
                                <span lang="th">404/28 โครงการ เจ ดับบลิว บูเลอวาร์ด แขวงคลองเจ้าคุณสิงห์ เขตวังทองหลาง กรุงเทพฯ 10310</span>
                                <span lang="en">404/28 JW Boulevard, Klong Chaokhunsing, Wangthonglang, Bangkok 10310, Thailand</span>
                            </p>
                        </div>

                        <!-- Direct Fast Contacts -->
                        <div class="flex flex-col sm:flex-row sm:space-x-8 space-y-4 sm:space-y-0 pt-4">
                            <div class="space-y-1">
                                <span class="block text-xs uppercase tracking-wider text-gray-400">
                                    <span lang="th">สายด่วนโทร</span><span lang="en">Phone Number</span>
                                </span>
                                <a href="tel:+66867785888" class="text-navy hover:text-yellow-dark font-medium text-lg transition-colors">086-778-5888</a>
                            </div>
                            <div class="space-y-1">
                                <span class="block text-xs uppercase tracking-wider text-gray-400">
                                    <span lang="th">อีเมลหลัก</span><span lang="en">Email Support</span>
                                </span>
                                <a href="mailto:info@mercuryth.com" class="text-navy hover:text-yellow-dark font-medium text-lg transition-colors">info@mercuryth.com</a>
                            </div>
                        </div>
                    </div>

                    
                            </form>

                            <!-- AI Response panel (Multi-turn response container) -->
                            <div id="ai-response-panel" class="hidden mt-8 border border-yellow/30 bg-yellow/5 rounded-2xl p-6 space-y-4">
                                <div class="flex items-center justify-between border-b border-yellow/20 pb-3">
                                    <div class="flex items-center space-x-2 text-navy">
                                        <span>✨</span>
                                        <h5 class="font-semibold text-sm uppercase tracking-wider">MIT AI Architect Specification</h5>
                                    </div>
                                    <button onclick="copyText('ai-response-text')" class="text-xs bg-navy/5 px-2.5 py-1.5 rounded hover:bg-navy/10 text-navy font-medium border border-navy/10">Copy</button>
                                </div>
                                <div id="ai-response-text" class="text-xs sm:text-sm text-navy/90 leading-relaxed font-sans whitespace-pre-wrap max-h-60 overflow-y-auto pr-2">
                                    <!-- AI Output goes here -->
                                </div>
                            </div>

                        </div>
                    </div>
                </div>
            </div>
        </section>

    <!-- Footer -->
    <footer class="bg-navy text-gray-400 py-16 border-t border-white/5 mt-auto">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-12 mb-12">
                <div class="space-y-4">
                    <span class="block text-white font-bold text-2xl tracking-wider">MERCURY</span>
                    <span class="block text-yellow font-light text-xs tracking-[0.2em] uppercase">Integrated Technology</span>
                    <p class="text-sm font-light leading-relaxed pt-2">
                        <span lang="th">ผู้สร้างสรรค์ออกแบบและติดตั้งระบบเทคโนโลยีสารสนเทศ พลังงานสะอาด และโซลูชันระบบควบคุมอาคารเบื้องหลังความสำเร็จอย่างประณีตเรียบร้อยสูงสุด</span>
                        <span lang="en">Meticulous architectural integration of ICT, clean energy, and building control solutions.</span>
                    </p>
                </div>
                <div class="space-y-4">
                    <h4 class="text-white font-semibold text-sm uppercase tracking-wider">
                        <span lang="th">เทคโนโลยีโซลูชัน</span>
                        <span lang="en">Technology Scope</span>
                    </h4>
                    <ul class="space-y-2 text-sm font-light">
                        <li>IT Network & Infrastructure</li>
                        <li>IP Security & Surveillance</li>
                        <li>Face Recognition & Analytics</li>
                        <li>Dynamic Digital Signage</li>
                        <li>Electronic Shelf Labels (ESL)</li>
                        <li>Solar Cell & EV Charging Ports</li>
                    </ul>
                </div>
                <div class="space-y-4">
                    <h4 class="text-white font-semibold text-sm uppercase tracking-wider">
                        <span lang="th">ลิงก์เข้าถึงข้อมูล</span>
                        <span lang="en">Explore Sites</span>
                    </h4>
                    <ul class="space-y-2 text-sm font-light">
                        <li><a href="#about" class="hover:text-yellow transition-colors"><span lang="th">เกี่ยวกับเรา</span><span lang="en">About us</span></a></li>
                        <li><a href="#products" class="hover:text-yellow transition-colors"><span lang="th">บริการและสินค้า</span><span lang="en">Products & Services</span></a></li>
                        <li><a href="#references" class="hover:text-yellow transition-colors"><span lang="th">โครงการอ้างอิง</span><span lang="en">Site References</span></a></li>
                        <li><a href="#contact" class="hover:text-yellow transition-colors"><span lang="th">ช่องทางติดต่อเรา</span><span lang="en">Contact us</span></a></li>
                    </ul>
                </div>
                <div class="space-y-4">
                    <h4 class="text-white font-semibold text-sm uppercase tracking-wider">
                        <span lang="th">การเชื่อมต่อสังคมออนไลน์</span>
                        <span lang="en">Social Network</span>
                    </h4>
                    <a href="https://www.facebook.com/MercuryIntegratedTechnology" target="_blank" rel="noopener noreferrer" class="inline-flex items-center space-x-2 text-sm font-medium text-yellow hover:text-white transition-colors">
                        <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24"><path d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.84 3.44 8.87 8 9.8V15H8v-3h2V9.5C10 7.57 11.57 6 13.5 6H16v3h-2c-.55 0-1 .45-1 1V12h3v3h-3v6.8c4.56-.93 8-4.96 8-9.8z"/></svg>
                        <span>Mercury Integrated Technology</span>
                    </a>
                </div>
            </div>

            <div class="border-t border-white/5 pt-8 text-center text-xs font-light flex flex-col sm:flex-row items-center justify-between space-y-4 sm:space-y-0 text-gray-500">
                <p>&copy; 2026 Mercury Integrated Technology Co., Ltd. All Rights Reserved.</p>
                <div class="flex space-x-6">
                    <a href="#about" class="hover:text-yellow transition-colors"><span lang="th">ข้อกำหนดความปลอดภัย</span><span lang="en">Privacy Policy</span></a>
                    <a href="#contact" class="hover:text-yellow transition-colors"><span lang="th">คำถามที่พบบ่อย</span><span lang="en">FAQs Support</span></a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Interactive Product Detail Modal (Bilingual) -->
    <div id="product-detail-modal" class="fixed inset-0 z-50 overflow-y-auto hidden" aria-labelledby="modal-title" role="dialog" aria-modal="true">
        <div class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
            <div onclick="closeProductDetail()" class="fixed inset-0 bg-navy/80 backdrop-blur-sm transition-opacity" aria-hidden="true"></div>

            <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
            <div class="inline-block align-bottom bg-white rounded-3xl text-left overflow-hidden shadow-2xl transform transition-all sm:my-8 sm:align-middle sm:max-w-3xl sm:w-full border border-gray-100">
                <div class="h-48 w-full relative overflow-hidden bg-navy-light">
                    <div class="absolute inset-0 bg-gradient-to-t from-navy to-navy/30 z-10"></div>
                    <img id="modal-banner-img" src="model banner.png" alt="Banner image" class="w-full h-full object-cover object-center opacity-70">
                    <button onclick="closeProductDetail()" class="absolute top-6 right-6 z-20 text-white hover:text-yellow bg-black/40 hover:bg-black/60 p-2 rounded-full focus:outline-none">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
                    </button>
                    <div id="modal-icon-badge" class="absolute bottom-6 left-6 z-20 w-12 h-12 bg-yellow rounded-xl flex items-center justify-center text-navy shadow-lg font-bold"></div>
                </div>

                <div class="p-8 sm:p-12 space-y-6">
                    <div class="space-y-2">
                        <span class="text-yellow-dark font-light tracking-[0.2em] text-xs uppercase">
                            <span lang="th">ขอบเขตงานและสเปกผลิตภัณฑ์</span>
                            <span lang="en">Product Scope & Architecture Specs</span>
                        </span>
                        <h3 id="modal-title" class="text-navy text-2xl sm:text-3xl font-semibold tracking-tight"></h3>
                    </div>
                    <div id="modal-description" class="text-gray-600 font-light text-base leading-relaxed space-y-4 font-sans"></div>
                    <div class="border-t border-gray-100 pt-6 space-y-4">
                        <h4 class="text-navy font-semibold text-sm uppercase tracking-wider">
                            <span lang="th">สิ่งที่คุณจะได้รับจากบริการของเรา</span>
                            <span lang="en">Key Technical Deliverables</span>
                        </h4>
                        <div id="modal-bullets" class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-sm font-light text-gray-500 font-sans"></div>
                    </div>
                    <div class="border-t border-gray-100 pt-6 flex justify-end">
                        <button onclick="closeProductDetail()" class="bg-navy hover:bg-navy-light text-white font-medium px-6 py-3 rounded-lg transition-all duration-300">
                            <span lang="th">ปิดหน้านี้</span>
                            <span lang="en">Close Window</span>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Success Message Thank You Modal -->
    <div id="success-modal" class="fixed inset-0 z-50 overflow-y-auto hidden" aria-labelledby="success-modal-title" role="dialog" aria-modal="true">
        <div class="flex items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:p-0">
            <!-- Background overlay -->
            <div onclick="closeSuccessModal()" class="fixed inset-0 bg-navy/80 backdrop-blur-sm transition-opacity" aria-hidden="true"></div>

            <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
            <div class="inline-block align-middle bg-white rounded-3xl text-left overflow-hidden shadow-2xl transform transition-all sm:my-8 sm:max-w-md sm:w-full p-8 border border-gray-100 text-center space-y-6">
                <div class="w-16 h-16 bg-yellow/15 text-yellow rounded-full flex items-center justify-center mx-auto animate-bounce">
                    <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                </div>
                
                <div class="space-y-2">
                    <h3 class="text-navy text-2xl font-semibold tracking-tight">
                        <span lang="th">ส่งข้อมูลสำเร็จ!</span>
                        <span lang="en">Inquiry Sent Successfully!</span>
                    </h3>
                    <p class="text-gray-500 font-light text-sm leading-relaxed">
                        <span lang="th">เราได้รับข้อมูลโครงร่างความต้องการของคุณเรียบร้อยแล้ว ทีมวิศวกรวิเคราะห์ระบบของเมอร์คิวรีจะติดต่อกลับหาคุณภายใน 24 ชั่วโมงทำการ</span>
                        <span lang="en">We have successfully received your structural specifications. Our architectural system engineers will get back to you within 24 hours.</span>
                    </p>
                </div>

                <button onclick="closeSuccessModal()" class="w-full bg-yellow hover:bg-yellow-light text-navy font-medium py-3 rounded-lg shadow-md transition-all duration-300">
                    <span lang="th">ตกลง</span>
                    <span lang="en">Understood</span>
                </button>
            </div>
        </div>
    </div>

    <!-- UI Custom Notification container -->
    <div id="ui-notification" class="fixed bottom-6 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 bg-navy text-white px-6 py-4 rounded-xl shadow-2xl border border-white/10 flex items-center space-x-3 max-w-md pointer-events-none">
        <span class="text-yellow text-lg">✨</span>
        <p id="ui-notification-text" class="text-sm font-light font-sans"></p>
    </div>

    <!-- Interactive Logic & State Controller Script -->
    <script>
        // Language State Management
        let currentLanguage = 'th';

        function switchLanguage(lang) {
            currentLanguage = lang;
            const body = document.body;
            const thBtn = document.getElementById('lang-btn-th');
            const enBtn = document.getElementById('lang-btn-en');

            if (lang === 'en') {
                body.classList.remove('lang-th');
                body.classList.add('lang-en');
                enBtn.className = "px-3 py-1 rounded-full text-xs font-medium transition-all duration-300 bg-yellow text-navy shadow-sm";
                thBtn.className = "px-3 py-1 rounded-full text-xs font-medium transition-all duration-300 text-gray-400 hover:text-white";
            } else {
                body.classList.remove('lang-en');
                body.classList.add('lang-th');
                thBtn.className = "px-3 py-1 rounded-full text-xs font-medium transition-all duration-300 bg-yellow text-navy shadow-sm";
                enBtn.className = "px-3 py-1 rounded-full text-xs font-medium transition-all duration-300 text-gray-400 hover:text-white";
            }
        }

        // Mobile Menu Control
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            const icon = document.getElementById('hamburger-icon');
            
            if (menu.classList.contains('hidden')) {
                menu.classList.remove('hidden');
                icon.innerHTML = '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>';
            } else {
                menu.classList.add('hidden');
                icon.innerHTML = '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"/>';
            }
        }

        // Reference / Portfolio Filtering Logic
        function filterReferences(category) {
            const cards = document.querySelectorAll('.ref-card');
            const buttons = [
                { id: 'ref-tab-all', cat: 'all' },
                { id: 'ref-tab-hospitality', cat: 'hospitality' },
                { id: 'ref-tab-commercial', cat: 'commercial' }
            ];

            buttons.forEach(btn => {
                const element = document.getElementById(btn.id);
                if (btn.cat === category) {
                    element.className = "px-5 py-2 rounded-full text-sm font-medium transition-all duration-300 bg-navy text-white shadow";
                } else {
                    element.className = "px-5 py-2 rounded-full text-sm font-medium transition-all duration-300 text-gray-500 hover:text-navy hover:bg-gray-100";
                }
            });

            cards.forEach(card => {
                const itemCategory = card.getAttribute('data-category');
                if (category === 'all' || itemCategory === category || (category === 'commercial' && card.classList.contains('commercial'))) {
                    card.style.opacity = '0';
                    card.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        card.style.display = 'block';
                        setTimeout(() => {
                            card.style.opacity = '1';
                            card.style.transform = 'scale(1)';
                        }, 50);
                    }, 300);
                } else {
                    card.style.opacity = '0';
                    card.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        card.style.display = 'none';
                    }, 300);
                }
            });
        }

        // Gemini AI Integration for Systems Architecture Blueprinting
        async function getAIAdvice() {
            const apiKey = ""; // Runtime automatically provisions the key. Keep empty.
            const companyName = document.getElementById('form-company').value || 'Mercury Project';
            const categorySelect = document.getElementById('form-category').value;
            const extraText = document.getElementById('form-details').value;
            const responsePanel = document.getElementById('ai-response-panel');
            const responseText = document.getElementById('ai-response-text');

            responsePanel.classList.remove('hidden');
            responseText.innerHTML = "✨ Mercury AI Architect is drafting your system specifications...";

            const systemPrompt = `You are the Lead Systems Architect at Mercury Integrated Technology (MIT).
You provide brief, premium, and structurally clean technical summaries (networking, low voltage routing, CCTV/AI, Solar power setups) with a signature "Neat Finish" standard.
The user is requesting brief, bulletproof advice for their project: "${companyName}".
Category: ${categorySelect}.
Custom specifications: ${extraText || 'None'}.
Reply as a professional engineer in both THAI and ENGLISH (use simple side-by-side or consecutive sections). Use bullet points and clear professional headings. Do not output raw markdown tags like ### or code snippets. Present as structured corporate proposal.`;

            const userQuery = `Draft the custom technology integration blueprint now based on my inputs.`;

            let delay = 1000;
            const maxRetries = 5;
            let success = false;
            let resultData = null;

            for (let i = 0; i < maxRetries; i++) {
                try {
                    const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json'
                        },
                        body: JSON.stringify({
                            contents: [{ parts: [{ text: userQuery }] }],
                            systemInstruction: { parts: [{ text: systemPrompt }] }
                        })
                    });

                    if (!response.ok) {
                        throw new Error(`API HTTP Error: ${response.status}`);
                    }

                    resultData = await response.json();
                    success = true;
                    break;
                } catch (err) {
                    if (i === maxRetries - 1) {
                        showNotification(
                            currentLanguage === 'en'
                            ? 'AI Proposal Generation failed. Please try again later.'
                            : 'ระบบวิเคราะห์แผนผัง AI ขัดข้องชั่วคราว กรุณาลองใหม่อีกครั้งในภายหลัง'
                        );
                        break;
                    }
                    await new Promise(resolve => setTimeout(resolve, delay));
                    delay *= 2; // Exponential backoff retry delay
                }
            }

            if (success && resultData) {
                let text = resultData.candidates?.[0]?.content?.parts?.[0]?.text || '';
                
                // Format text into structured readable blocks
                text = text.replace(/\*\*(.*?)\*\*/g, '<strong class="text-navy font-semibold">$1</strong>');
                text = text.replace(/-\s(.*?)(\n|$)/g, '<li class="ml-4 list-disc pl-1">$1</li>');
                
                responseText.innerHTML = text;
            } else {
                responseText.innerHTML = "AI Advisor failed to compile. Please check connectivity and try again.";
            }
        }

        // Helper to copy text to clipboard
        function copyText(containerId) {
            const content = document.getElementById(containerId).innerText;
            const temp = document.createElement('textarea');
            temp.value = content;
            document.body.appendChild(temp);
            temp.select();
            document.execCommand('copy');
            document.body.removeChild(temp);
            showNotification("คัดลอกร่างสเปกไปยังคลิปบอร์ดแล้ว!");
        }

        // Product database
        const productDetails = {
            1: {
                titleTh: "ระบบโครงสร้างพื้นฐานไอทีและเครือข่าย",
                titleEn: "IT Network & Infrastructure",
                icon: '1',
                bulletsTh: [
                    "ออกแบบเส้นทางการเดินสายและสายเชื่อมโยงหลัก (Fiber Optic Backbone)",
                    "เทคโนโลยีการจัดหมวดหมู่สายเชื่อมต่อสัญญาณความถี่รบกวนต่ำ",
                    "ระบบสวิตช์ความเร็วสูงสำหรับการกระจายแบนด์วิธห้องพักและอาคาร"
                ],
                bulletsEn: [
                    "Precision high-speed core fiber optic cabling design",
                    "Ultra-low noise structured cable management systems",
                    "Gigabit enterprise switching matrix implementations"
                ],
                descTh: "บริการครอบคลุมตั้งแต่การออกแบบสเปกสายเคเบิลทองแดงและใยแก้วนำแสงมาตรฐานพรีเมียม เพื่อให้รองรับปริมาณแบนด์วิธความหนาแน่นสูงได้อย่างลื่นไหลและมั่นคง 99.99%",
                descEn: "Full lifecycle network architecture consulting, optical path modeling, localized equipment staging, and stress testing."
            },
            2: {
                titleTh: "ระบบรักษาความปลอดภัยและการเฝ้าระวัง",
                titleEn: "Security & CCTV Solutions",
                icon: '2',
                bulletsTh: [
                    "กล้องความละเอียดคมชัดสูงระดับ IP-Security",
                    "ระบบกระจายข้อมูลสำรองภาพบันทึกระยะไกล (NVR / DVR Arrays)",
                    "สวิตช์ส่งกำลังไฟผ่านสายแลน (PoE) มาตรฐานเสถียรภาพ"
                ],
                bulletsEn: [
                    "Professional high-definition IP cameras",
                    "Redundant storage configurations (NVR/DVR backups)",
                    "Secure Power-over-Ethernet (PoE) design standards"
                ],
                descTh: "วางสถาปัตยกรรมการตรวจจับและเฝ้าระวังความปลอดภัยที่คมชัดสูง เพื่อลดจุดอับสายตาทั่วอาคารขนาดใหญ่ ออกแบบระบบสายเคเบิลกล้องที่มีมาตรฐานระบุป้ายและจุดเชื่อมต่อชัดเจน ทำให้ทีมควบคุมตรวจสอบปัญหาหรือซ่อมบำรุงในอนาคตได้อย่างรวดเร็ว",
                conEn: "We conceptualize full campus visual safety grids. Our organized low-voltage wiring topology minimizes interface interferences and guarantees sharp frames under any weather conditions or low-light situations."
            },
            3: {
                titleTh: "ระบบตูู้สาขาและทีวีสำหรับโรงแรม",
                titleEn: "PABX & IPTV Systems",
                icon: '3',
                bulletsTh: [
                    "ระบบตู้สาขาโทรศัพท์หลัก (Core PABX) รองรับคู่สายจำนวนมาก",
                    "ระบบทีวีสารบันเทิงความละเอียดสูงสำหรับห้องพัก (IPTV/MATV Headend)",
                    "การเชื่อมโยงระบบโทรศัพท์เข้ากับระบบบริหารจัดการโรงแรม (PMS Integration)"
                ],
                bulletsEn: [
                    "Robust Core PABX switching centers for high telephony volume",
                    "Premium high-definition IPTV/MATV headend entertainment delivery",
                    "Seamless logical integration with Property Management Systems (PMS)"
                ],
                descTh: "โครงข่ายเพื่อความพึงพอใจสูงสุดของแขกผู้เข้าพัก ด้วยระบบทีวีภาพสวยงามคมชัดไม่มีสะดุด และสัญญาณโทรศัพท์สายภายในที่พร้อมใช้งานตลอด 24 ชั่วโมง",
                descEn: "Seamless hospitality entertainment matrices and voice infrastructure ensuring perfect hotel communication uptime."
            },
            4: {
                titleTh: "ระบบวิเคราะห์ใบหน้าและนับจำนวนคนอัจฉริยะ",
                titleEn: "Counting & Face Recognition",
                icon: '4',
                bulletsTh: [
                    "เทคโนโลยีการนับจำนวนคนตรวจจับภาพ AI ความแม่นยำสูง",
                    "ระบบแดชบอร์ดสรุปยอดสถิติคนผ่านเข้า-ออกเชิงพาณิชย์",
                    "เซนเซอร์ตรวจจับลักษณะและบันทึกใบหน้าบุคคลระดับพรีเมียม"
                ],
                bulletsEn: [
                    "High-accuracy AI-driven people flow counting",
                    "Sophisticated bilingual business intelligence dashboards",
                    "Premium facial characteristic detection and matching biometrics"
                ],
                descTh: "วิเคราะห์และจัดสถิติปริมาณผู้เดินชมสินค้า ความหนาแน่น เพื่อนำข้อมูลมาวางแผนเชิงพื้นที่และการตลาดให้แก่อาคารพาณิชย์และห้างสรรพสินค้าอย่างมีตรรกะ",
                descEn: "Converting raw visual feeds into high-value operational metrics. Real-time facial analytics combined with precise footfall data tracking."
            },
            5: {
                titleTh: "ระบบจอภาพโฆษณาอัจฉริยะและวิดีโอวอลล์",
                titleEn: "Digital Signage & VDO Wall",
                icon: '5',
                bulletsTh: [
                    "ป้ายโฆณาดิจิทัลแนวตั้ง/แนวนอน สำหรับห้างและล็อบบี้โรงแรม",
                    "ระบบจอมัลติวิดีโอวอลล์ (VDO Wall) ขนาดใหญ่ ขอบเชื่อมต่อหนาแน่นต่ำสุด",
                    "ระบบโปรแกรมจัดการเนื้อหา สตอรี่บอร์ด แคมเปญ ผ่านโปรแกรมระบบคลาวด์"
                ],
                bulletsEn: [
                    "Premium vertical & horizontal commercial display installations",
                    "Seamless ultra-narrow bezel high-density multi-display Video Walls",
                    "Cloud-managed digital signage dynamic content scheduling CMS"
                ],
                descTh: "เปลี่ยนพื้นที่ล็อบบี้หรือลานโถงสูงของคุณให้ดูทันสมัย ด้วยการติดตั้งจอแสดงผลและวิดีโอวอลล์ขอบบางพิเศษที่สั่งการอัปเดตข้อมูลได้จากส่วนควบคุมกลางไปยังทุกจอภาพพร้อมกันได้เพียงปลายนิ้ว",
                descEn: "Bring wall spaces to life. Deliver synchronized promotional campaigns or digital directions dynamically in high resolution."
            },
            6: {
                titleTh: "ระบบป้ายแสดงราคาอิเล็กทรอนิกส์อัจฉริยะ",
                titleEn: "Smart ESL (Electronic Shelf Label)",
                icon: '6',
                bulletsTh: [
                    "ป้ายหมึกอิเล็กทรอนิกส์ไร้สายประหยัดพลังงานเป็นพิเศษ",
                    "การอัปเดตราคาสินค้าหรือส่วนลดอัตโนมัติพร้อมกันทั้งห้างสรรพสินค้า",
                    "เชื่อมโยงร่วมระบบจัดการสินค้าหน้าร้านและคลังสินค้าหลังบ้านโดยตรง"
                ],
                bulletsEn: [
                    "Ultra-low power wireless Electronic Paper (E-Ink) digital tags",
                    "Instant property-wide simultaneous price and coupon automation",
                    "Seamless logical integration with core POS and ERP inventory datasets"
                ],
                descTh: "นวัตกรรมเพื่อการทำห้างค้าปลีกสมัยใหม่ โดยช่วยให้การอัปเดตราคาสินค้าที่มักจะมีการจัดแคมเปญบ่อยครั้งสามารถทำได้อัตโนมัติ 100% ป้องกันราคาคลาดเคลื่อนระหว่างชั้นวางกับระบบจุดชำระเงิน และประหยัดแรงงานไปใช้ในการบริการลูกค้าได้เต็มที่",
                descEn: "Modernizing physical brick-and-mortar retail experiences. We architect the wireless gateway infrastructure connecting thousands of smart e-paper tags to central inventory databases, enabling dynamic pricing and 100% accurate markdowns."
            },
            7: {
                titleTh: "ระบบพลังงานทดแทนและรักษ์โลก (EV / Solar)",
                titleEn: "EV Charger & Solar Cell",
                icon: '7',
                bulletsTh: [
                    "สำรวจ ออกแบบ วางระบบโซลาร์เซลล์บนหลังคา (Solar Rooftop) เชิงพาณิชย์",
                    "ตู้สถานีชาร์จรถไฟฟ้าอัจฉริยะ (EV Charger) มาตรฐานความปลอดภัยสูง",
                    "ระบบบริหารการกระจายกระแสไฟฟ้าและอุปกรณ์สลับกระแสอย่างปลอดภัย"
                ],
                bulletsEn: [
                    "Commercial structural load feasibility & logical Solar Rooftop modeling",
                    "Premium high-voltage EV Charging station supply and installation",
                    "Smart electrical load balancing and premium circuit safety designs"
                ],
                descTh: "รองรับเป้าหมายการดำเนินธุรกิจสีเขียวเพื่อสิ่งแวดล้อม (ESG) เรามีวิศวกรผู้เชี่ยวชาญเข้าสำรวจโครงสร้างรับน้ำหนักของหลังคา ออกแบบแผนผังระบบสายไฟ โซลาร์เซลล์ และระบบติดตั้งเครื่องชาร์จรถยนต์ไฟฟ้า EV Charger มาตรฐานวิศวกรรมความเสถียรสูง",
                descEn: "Pioneering the corporate transition to clean power. We analyze your commercial facility, design high-performance solar array topologies, and install reliable EV chargers matching absolute civil engineering and safety guidelines."
            },
            8: {
                titleTh: "ระบบแสง เสียง และภาพ",
                titleEn: "Audio Visual (AV) System",
                icon: '8',
                bulletsTh: [
                    "ออกแบบระบบเสียงตามสายสำหรับพื้นที่สาธารณะของโรงแรมและห้าง",
                    "ระบบรวมภาพ-เสียงความเสถียรสูงสำหรับติดตั้งในห้องประชุมใหญ่องค์กร",
                    "อุปกรณ์ควบคุมการนำเสนอมัลติมีเดียแบบไร้สาย (Wireless Presentation)"
                ],
                bulletsEn: [
                    "Corporate large-scale Ballroom & Public Address (PA) logic",
                    "Integrated high-fidelity matrix Audio-Video conferencing designs",
                    "Advanced logical topology for low-latency Wireless Presentation"
                ],
                descTh: "ออกแบบระบบรวมภาพและเสียงเชิงพาณิชย์ที่มีประสิทธิภาพสูง ตั้งแต่ระบบลำโพงประชาสัมพันธ์ในทางเดินโรงแรม ไปจนถึงระบบไมโครโฟนประชุมและจอภาพในห้องจัดเลี้ยงองค์กร ด้วยการจัดการระบบสายเคเบิลที่ระเบียบเรียบร้อยสูงสุด",
                descEn: "Meticulous AV signal integrity. We engineer robust corporate environments where high-fidelity microphone matrices, automated cameras, and ultra-clear audio come together flawlessly, backed by our signature highly organized cabling structures."
            },
            9: {
                titleTh: "ระบบแจ้งเตือนอัคคีภัยอัจฉริยะ",
                titleEn: "Smart Fire Alarm Systems",
                icon: '9',
                bulletsTh: [
                    "ออกแบบระบบแจ้งเหตุเพลิงไหม้แบบระบุตำแหน่งได้ (Addressable System)",
                    "ติดตั้งอุปกรณ์ตรวจจับควันและเตือนภัยมาตรฐานสากล (NFPA / EN54)",
                    "ระบบบริหารจัดการควบคุมแผงสั่งการแจ้งเตือนภัยแบบรวมศูนย์"
                ],
                bulletsEn: [
                    "Precision-engineered Addressable System topologies",
                    "NFPA / EN54 compliant sensor placement blueprints",
                    "Integrated main control panel and graphic interface monitoring"
                ],
                descTh: "การดูแลความปลอดภัยให้กับแขกผู้เข้าพักในโรงแรม รีสอร์ท หรือลูกค้าในศูนย์การค้าเป็นสิ่งสำคัญที่สุด เราออกแบบระบบตรวจจับควันและแจ้งเตือนภัยอัคคีภัยแบบพรีเมียมที่ทนทาน วางระบบสายสัญญาณป้องกันสัญญาณรบกวนตามข้อกำหนดวิศวกรรมสากล",
                descEn: "Uncompromised security for high-density environments. Our advanced building fire networks deliver instant warning feedback, pointing out exact danger coordinates to control rooms, allowing quick actions before critical situations escalate."
            }
        };

        // UI Notification Helper
        function showNotification(text) {
            const container = document.getElementById('ui-notification');
            const textBox = document.getElementById('ui-notification-text');
            textBox.innerText = text;
            container.classList.remove('translate-y-20', 'opacity-0');
            container.classList.add('translate-y-0', 'opacity-100');
            setTimeout(() => {
                container.classList.remove('translate-y-0', 'opacity-100');
                container.classList.add('translate-y-20', 'opacity-0');
            }, 4000);
        }
    </script>
</body>
</html>
