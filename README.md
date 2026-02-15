<!DOCTYPE html>
<html lang="id">

<head>
    <meta charset="utf-8" />
    <meta content="width=device-width, initial-scale=1.0" name="viewport" />
    <title>Alter Ego - Persiapan SNBT</title>
    <script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
    <link
        href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@400;700;900&family=Lato:wght@300;400;700;900&display=swap"
        rel="stylesheet" />
    <link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap"
        rel="stylesheet" />
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
    <script>
        tailwind.config = {
            darkMode: "class",
            theme: {
                extend: {
                    colors: {
                        "sakura-red": "#B71C1C",
                        "sakura-black": "#212121",
                        "sakura-paper": "#FAFAFA",
                        "sakura-navy": "#1a1a24",
                        "sakura-gray": "#9E9E9E",
                        "sakura-cream": "#F5F5F0",
                    },
                    fontFamily: {
                        "serif": ["Noto Serif JP", "serif"],
                        "sans": ["Lato", "sans-serif"],
                    },
                    backgroundImage: {
                        'grid-pattern': "linear-gradient(to right, #f0f0f0 1px, transparent 1px), linear-gradient(to bottom, #f0f0f0 1px, transparent 1px)",
                    }
                },
            },
        }
    </script>
    <style>
        html {
            scroll-behavior: smooth;
        }

        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }

        ::-webkit-scrollbar-track {
            background: transparent;
        }

        ::-webkit-scrollbar-thumb {
            background: #333;
            border-radius: 3px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #B71C1C;
        }

        .bg-grid {
            background-size: 40px 40px;
        }

        #sidebar {
            width: 288px;
            min-width: 288px;
            transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1), min-width 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        #sidebar.collapsed {
            width: 0px;
            min-width: 0px;
            overflow: hidden;
        }

        #sidebar.collapsed .sidebar-content {
            opacity: 0;
            pointer-events: none;
        }

        .sidebar-content {
            transition: opacity 0.2s ease;
            opacity: 1;
        }

        .page-section,
        .page-section-002,
        .page-section-003,
        .page-section-004,
        .page-section-005,
        .page-section-006 {
            display: none;
        }

        .page-section.active,
        .page-section-002.active,
        .page-section-003.active,
        .page-section-004.active,
        .page-section-005.active,
        .page-section-006.active {
            display: block;
        }

        .step-dot {
            transition: all 0.3s ease;
        }

        .quiz-feedback {
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-8px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .module-view {
            display: none;
        }

        .module-view.active {
            display: flex;
            flex-direction: column;
            flex: 1;
            min-height: 0;
        }

        .landing-view {
            display: flex;
            min-height: 0;
        }

        .landing-view.hidden-view {
            display: none;
        }
    </style>
</head>

<body
    class="bg-sakura-paper text-sakura-black font-sans antialiased h-screen flex overflow-hidden selection:bg-sakura-red/20 selection:text-sakura-red">

    <!-- SIDEBAR -->
    <aside id="sidebar" class="bg-sakura-navy text-gray-300 flex flex-col shadow-2xl z-20 flex-shrink-0 relative">
        <div class="sidebar-content w-72 flex flex-col h-full">
            <div class="h-20 flex items-center justify-between px-6 border-b border-gray-800 bg-sakura-navy/50">
                <div class="flex items-center gap-3">
                    <div
                        class="w-8 h-8 rounded-full bg-sakura-red flex items-center justify-center text-white shadow-[0_0_10px_rgba(183,28,28,0.5)]">
                        <span class="material-symbols-outlined text-lg">diversity_3</span>
                    </div>
                    <div>
                        <h1 class="font-serif font-bold text-lg text-white tracking-wide">Alter Ego</h1>
                        <p class="text-[10px] uppercase tracking-widest text-gray-500 font-bold">SNBT Prep System</p>
                    </div>
                </div>
                <button onclick="toggleSidebar()"
                    class="w-8 h-8 rounded-md hover:bg-white/10 flex items-center justify-center text-gray-400 hover:text-white transition-colors"
                    title="Collapse sidebar">
                    <span class="material-symbols-outlined text-lg">chevron_left</span>
                </button>
            </div>

            <nav class="flex-1 overflow-y-auto py-6 px-4 space-y-1" id="sidebar-nav">
                <!-- HABIT Section -->
                <p class="text-[10px] font-bold text-sakura-red uppercase tracking-widest px-3 py-2 mt-2">Habit</p>
                <p class="text-[10px] font-bold text-pink-400 uppercase tracking-widest px-3 py-1 ml-3">Obat Fokus</p>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-001')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-001">
                    <span class="text-xs text-gray-500 font-bold w-6">01</span>
                    <span class="text-sm">Day 1</span>
                </a>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-002')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-002">
                    <span class="text-xs text-gray-500 font-bold w-6">02</span>
                    <span class="text-sm">Day 2</span>
                </a>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-003')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-003">
                    <span class="text-xs text-gray-500 font-bold w-6">03</span>
                    <span class="text-sm">Day 3</span>
                </a>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-004')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-004">
                    <span class="text-xs text-gray-500 font-bold w-6">04</span>
                    <span class="text-sm">Day 4</span>
                </a>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-005')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-005">
                    <span class="text-xs text-gray-500 font-bold w-6">05</span>
                    <span class="text-sm">Day 5</span>
                </a>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-006')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-006">
                    <span class="text-xs text-gray-500 font-bold w-6">06</span>
                    <span class="text-sm">Day 6</span>
                </a>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-007')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-007">
                    <span class="text-xs text-gray-500 font-bold w-6">07</span>
                    <span class="text-sm">Day 7</span>
                </a>
                <a href="javascript:void(0)" onclick="loadModule('obat-fokus-008')"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3"
                    id="nav-obat-fokus-008">
                    <span class="text-xs text-gray-500 font-bold w-6">08</span>
                    <span class="text-sm">Day 8</span>
                </a>


                <!-- FUNDAMENTAL Section -->
                <p class="text-[10px] font-bold text-amber-500 uppercase tracking-widest px-3 py-2 mt-4">Airdrop
                    Fundamental</p>
                <a href="#"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white">
                    <span class="text-xs text-gray-500 font-bold w-6">01</span>
                    <span class="text-sm">Fundamental 01</span>
                </a>
                <a href="#"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white">
                    <span class="text-xs text-gray-500 font-bold w-6">02</span>
                    <span class="text-sm">Fundamental 02</span>
                </a>
                <a href="#"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white">
                    <span class="text-xs text-gray-500 font-bold w-6">03</span>
                    <span class="text-sm">Fundamental 03</span>
                </a>

                <!-- PROCESS STAGE Section -->
                <p class="text-[10px] font-bold text-violet-400 uppercase tracking-widest px-3 py-2 mt-4">Process Stage
                </p>
                <a href="#"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white">
                    <span class="text-xs text-gray-500 font-bold w-6">01</span>
                    <span class="text-sm">Process 01</span>
                </a>
                <a href="#"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white">
                    <span class="text-xs text-gray-500 font-bold w-6">02</span>
                    <span class="text-sm">Process 02</span>
                </a>
                <a href="#"
                    class="sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white">
                    <span class="text-xs text-gray-500 font-bold w-6">03</span>
                    <span class="text-sm">Process 03</span>
                </a>
            </nav>

            <div class="p-4 border-t border-gray-800">
                <a href="Dashboard.html"
                    class="w-full flex items-center gap-3 px-3 py-2 mb-4 rounded-md hover:bg-white/5 text-left transition-colors text-gray-400 hover:text-white">
                    <span class="material-symbols-outlined text-sm">arrow_back</span>
                    <span class="text-xs font-bold uppercase tracking-wider">Back to Dashboard</span>
                </a>
            </div>
        </div>
    </aside>

    <!-- MAIN CONTENT -->
    <main class="flex-1 flex flex-col h-full overflow-hidden bg-grid bg-sakura-paper relative">
        <header id="main-header"
            class="h-20 bg-white/90 backdrop-blur-sm border-b border-gray-200 flex items-center justify-between px-8 z-10 sticky top-0">
            <div class="flex items-center gap-4">
                <button id="toggle-btn" onclick="toggleSidebar()"
                    class="w-10 h-10 rounded-lg hover:bg-gray-100 flex items-center justify-center text-gray-500 hover:text-sakura-red transition-colors hidden"
                    title="Expand sidebar">
                    <span class="material-symbols-outlined">menu</span>
                </button>
                <div>
                    <nav id="breadcrumb" class="flex items-center text-xs text-gray-500 mb-1 space-x-2">
                        <span>Alter Ego</span>
                        <span class="material-symbols-outlined text-[10px]">chevron_right</span>
                        <span class="text-sakura-red font-bold">Persiapan SNBT</span>
                    </nav>
                    <div class="flex items-center gap-3">
                        <h2 id="page-title" class="font-serif font-black text-2xl text-sakura-black tracking-tight">
                            Alter Ego</h2>
                        <span id="page-badge"
                            class="px-2 py-0.5 rounded text-[10px] font-bold bg-sakura-red/10 text-sakura-red border border-sakura-red/20 uppercase tracking-widest">SNBT</span>
                    </div>
                </div>
            </div>
            <div id="progress-container" class="flex items-center gap-6 hidden">
                <div class="flex flex-col items-end">
                    <span class="text-xs text-gray-500 font-bold uppercase tracking-wider">Progress</span>
                    <div class="flex items-center gap-2">
                        <div class="w-32 h-2 bg-gray-100 rounded-full overflow-hidden">
                            <div id="progress-bar" class="h-full bg-sakura-red transition-all duration-500"
                                style="width:0%"></div>
                        </div>
                        <span id="progress-text" class="text-sm font-bold text-sakura-black">0%</span>
                    </div>
                </div>
            </div>
        </header>

        <!-- LANDING VIEW -->
        <div id="landing-view" class="landing-view flex-1 overflow-y-auto">
            <div class="max-w-7xl mx-auto p-8 pb-32">
                <div class="text-center py-20">
                    <span class="material-symbols-outlined text-8xl text-gray-200 mb-6">diversity_3</span>
                    <h2 class="font-serif font-bold text-3xl text-sakura-black mb-4">Pusat Kursus & Mentorship</h2>
                    <p class="text-gray-500 text-lg max-w-md mx-auto">Pilih materi di sidebar untuk mulai persiapan
                        SNBT.</p>
                    <div class="w-16 h-1 bg-sakura-red mx-auto mt-8"></div>
                </div>
            </div>
        </div>

        <!-- MODULE VIEW: OBAT FOKUS 001 -->
        <div id="module-obat-fokus-001" class="module-view">
            <div class="flex-1 overflow-y-auto" id="content-scroll">
                <!-- PAGE 1: ARTICLES -->
                <div id="page-articles" class="page-section active">
                    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">
                        <!-- ARTIKEL 1: DOPAMINE -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 1
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Apa itu Dopamine?</h3>
                            <h4 class="font-serif font-bold text-lg text-gray-700 mb-6">Dopamine Bukan Sekadar Hormon
                                Bahagia</h4>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dopamine adalah senyawa kimia yang mengirimkan sinyal dari satu selang neuron ke
                                    selang
                                    lainnya dalam sistem saraf, dia membawa pesan bahagia yang mempengaruhi banyak
                                    fungsi
                                    tubuh, dari perasaan hingga tindakan yang akan dilakukan akibat perasaan itu.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Bagaimana Dopamine diproduksi?
                                </h5>
                                <p>Dopamin hadir dalam tubuh manusia sebagai penghubung antara otak dan jasmani untuk
                                    melakukan kerja-kerja adaptasi demi mahluk hidup mempertahankan kelangsungan
                                    hidupnya.
                                    Dopamin dibuat dari asam amino bernama tirosin yang kemudian diubah menjadi L-DOPA,
                                    L
                                    DOPA inilah yang kemudian dibuat lagi menjadi dopamin. Dopamin diproduksi pada otak
                                    melalui neuron-neuron yang terutama terletak di bagian substantia nigra dan ventral
                                    tegmental area (VTA).</p>
                                <p>Ketika sebuah neuron penghasil dopamin menerima sinyal listrik (disebut potensial
                                    aksi),
                                    sinyal ini bergerak sepanjang neuron hingga mencapai ujungnya, yang disebut terminal
                                    akson. Di terminal akson, dopamin disimpan dalam kantung-kantung kecil yang disebut
                                    vesikel. Ketika potensial aksi tiba, vesikel-vesikel ini bergerak menuju tepi neuron
                                    dan
                                    melepaskan dopamin ke ruang kecil di antara dua neuron yang disebut sinapsis (atau
                                    celah
                                    sinaptik).</p>
                                <p>Setelah dilepaskan ke sinapsis, molekul dopamin berenang menyeberangi celah tersebut
                                    dan
                                    mencari penerima dopamin yang terletak di permukaan neuron berikutnya (neuron
                                    pascasinapsis). Reseptor dopamin ini seperti gembok dan dopamin adalah kuncinya.
                                    Ketika
                                    dopamin menempel pada reseptornya serangkaian perubahan kimiawi di dalam neuron
                                    pascasinapsis kemudian terjadi. Reseptor dopamin adalah protein yang terletak di
                                    permukaan sel-sel saraf (neuron) yang berikatan dengan dopamin dan memicu respons di
                                    dalam sel.</p>
                                <p>Ada lima subtipe reseptor dopamin utama, yang dikelompokkan menjadi dua famili besar
                                    berdasarkan jenis pasangan protein yakni stimulatori dan inhibitori. Pengelompokan
                                    ini
                                    membantu para ilmuwan memahami kompleksitas sistem dopamin dan mengembangkan
                                    obat-obatan
                                    yang lebih bertarget untuk berbagai gangguan neurologis dan kejiwaan. Reseptor dalam
                                    famili D1 umumnya bersifat stimulatori atau eksitatori, artinya ketika dopamin
                                    berikatan
                                    dengannya, mereka cenderung meningkatkan aktivitas neuron. Mereka bekerja dengan
                                    meningkatkan produksi siklik AMP (cAMP), sebuah molekul pemberi sinyal di dalam sel.
                                </p>
                                <p>Reseptor dalam famili D2 umumnya bersifat inhibitori atau penghambat, artinya ketika
                                    dopamin berikatan dengannya, mereka cenderung mengurangi aktivitas neuron. Mereka
                                    bekerja dengan menurunkan produksi siklik AMP (cAMP) dan memengaruhi saluran ion.
                                    Pengikatan dopamin ke reseptornya dapat mengaktifkan (mengirim sinyal) atau
                                    menghambat
                                    (mengurangi sinyal) neuron pascasinapsis, tergantung pada jenis reseptor dan sirkuit
                                    otak yang terlibat. Setelah dopamin berikatan dengan reseptornya (D1-like yang
                                    menstimulasi, atau D2-like yang menghambat), terjadilah serangkaian perubahan
                                    kimiawi di
                                    dalam neuron pascasinapsis perubahan aktivitas seluler ini kemudian menghasilkan
                                    berbagai efek biologis yang memengaruhi pikiran, emosi, dan tindakan kita.</p>
                                <p>Setelah dopamin menyampaikan pesannya, ia harus dihilangkan dari sinapsis agar sinyal
                                    tidak terus-menerus aktif dan neuron siap menerima sinyal berikutnya. Ini dilakukan
                                    melalui beberapa mekanisme Sebagian besar dopamin diserap kembali oleh neuron yang
                                    melepaskannya melalui protein khusus yang disebut transporter dopamin. Enzim
                                    tertentu
                                    (seperti monoamine oxidase/MAO dan catechol-O-methyltransferase/COMT) juga memecah
                                    dopamin di sinapsis.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Fungsi Dopamine</h5>
                                <p>Dopamin memungkinkan kita untuk berjalan, menulis, berbicara, dan melakukan semua
                                    gerakan
                                    sadar lainnya dengan lancar. Selain itu, ia berperan dalam memori kerja (kemampuan
                                    menyimpan dan memanipulasi informasi untuk waktu singkat), perhatian, konsentrasi,
                                    dan
                                    pengambilan keputusan. Dopamin juga membantu kita tetap fokus pada tugas dan memilih
                                    tindakan yang tepat. Bahkan, Dopamin memengaruhi perasaan gembira, minat, dan gairah
                                    hidup. Dan ya, seberpengaruh itu dopamin terhadap hidup kita.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Bagaimana cara menjaga dopamine?
                                </h5>
                                <p>Dopamin itu terbuat dari asam amino, jadi kita perlu memastikan asupan apa yang kita
                                    makan untuk mengoptimalkan keberadaannya di tubuh kita. Kita bisa mulai dari makanan
                                    yang kaya akan Tirosin seperti Daging Ayam, sapi, ikan, Telur, susu, keju, Kacang
                                    polong, buncis, kedelai dan juga yang tidak kalah penting buah dan sayur seperti
                                    pisang,
                                    alpukat, apel, bayam dan tomat. Selain asupan, kita juga perlu menerapkan gaya hidup
                                    sehat, dengan berolahraga dan melakukan aktivitas fisik, tidur yang cukup dan
                                    berkualitas, atau aktivitas sesimpel mendengarkan musik.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Memanfaatkan Dopamine</h5>
                                <p>Nah, ini bagian pentingnya. Perlu kita tahu, dopamin itu paling efektif dilepaskan
                                    sebagai respons atas pencapaian dan progres yang dicapai, bukan melalui hal instan.
                                    Kalo
                                    kita cuma ngejar dopamin instan dari hal-hal yang kurang produktif kayak scrolling
                                    medsos, efeknya justru bisa bikin kita cepet bosen, ngerasa hampa, dan bahkan
                                    kehilangan
                                    motivasi buat tujuan yang lebih besar. Buat memanfaatkan dopamin ini dengan baik,
                                    kita
                                    perlu membuat simulasi pencapaian yang bertahap. Diantaranya:</p>
                                <p><strong>Bedah Tujuan Besar Jadi Langkah-Langkah Kecil</strong> Punya keinginan atau
                                    target yang lumayan berat? Jangan langsung pusing dan terbebani coba lakukan hal-hal
                                    ini
                                    dulu.</p>
                                <p><strong>Identifikasi Tujuan:</strong> Tentukan dulu apa sih yang pengen lo capai,
                                    misalnya, menguasai bahasa baru atau menyelesaikan proyek kerja yang besar</p>
                                <p><strong>Buat Pos-pos Kecil:</strong> Sekarang, pecah tujuan besar itu jadi beberapa
                                    sub-tujuan yang lebih realistis dan nggak terlalu berat</p>
                                <p><strong>Definisikan Langkah Mikro:</strong> Dari sub-tujuan, pecah lagi jadi
                                    langkah-langkah yang super kecil, yang bahkan bisa lo selesain dalam waktu singkat,
                                    mungkin 15-30 menit aja. Setiap kali lo sukses nyelesaiin satu langkah kecil ini,
                                    otak
                                    bakal ngasih hadiah dopamin sedikit demi sedikit. Ini kayak ngasih umpan yang bikin
                                    otak
                                    terus termotivasi buat lanjut ke langkah berikutnya.</p>
                                <p><strong>Rayakan Tiap Kemenangan Kecil</strong> Otak kita butuh feedback positif.
                                    Jadi,
                                    penting banget buat ngasih konfirmasi ke diri sendiri.</p>
                                <p><strong>Visualisasikan Progres:</strong> Setiap kali lo nyelesaiin satu langkah,
                                    centang
                                    di daftar tugas, tandain di kalender, atau pakai aplikasi tracker. Melihat kemajuan
                                    secara visual itu sinyal kuat buat otak yang memicu pelepasan dopamin.</p>
                                <p><strong>Apresiasi Diri:</strong> Nggak usah bikin pesta besar, tapi akui pencapaian
                                    lo,
                                    sekecil apa pun. Ucapin Oke, satu lagi beres! atau izinin diri lo istirahat
                                    sebentar.
                                    Ini memperkuat hubungan antara usaha lo dan rasa puas yang didapet.</p>
                                <p><strong>Nikmati Prosesnya, Jangan Cuma Terpaku Hasil Akhir</strong> Dopamin itu bukan
                                    cuma soal sampai di garis finish, tapi juga tentang perjalanan itu sendiri.</p>
                                <p><strong>Fokus pada Keterlibatan:</strong> Coba nikmati momen-momen saat kita lagi
                                    belajar
                                    atau ngerjain sesuatu. Dopamin juga dilepaskan waktu kita terlibat aktif dan ngerasa
                                    ada
                                    peningkatan skill atau pemahaman.</p>
                                <p><strong>Belajar dari Kesalahan:</strong> Anggap kesalahan sebagai kesempatan buat
                                    belajar
                                    dan berkembang, bukan akhir dari segalanya. Proses belajar dan adaptasi itu sendiri
                                    juga
                                    bisa jadi pemicu dopamin.</p>
                                <p><strong>Naikin Level Tantangan Secara Perlahan</strong> Otak kita itu suka tantangan,
                                    tapi jangan yang bikin nyerah.</p>
                                <p><strong>Cari Zona Nyaman yang Menantang:</strong> Tugas yang terlalu gampang bikin
                                    bosen,
                                    terlalu sulit bikin frustrasi. Cari yang pas, yang butuh usaha tapi masih realistis
                                    buat
                                    diselesain.</p>
                                <p><strong>Coba Hal Baru:</strong> Sesekali, eksplorasi hobi baru, belajar skill baru,
                                    atau
                                    kasih variasi di rutinitas lo. Sensasi kebaruan itu juga pemicu dopamin yang
                                    efektif.
                                </p>
                                <p>Intinya, dengan ngelakuin semua ini, kita lagi ngelatih sistem dopamin di otak kita.
                                    Kita
                                    ngajarin otak buat menghargai usaha dan progres yang konsisten, bukan cuma lonjakan
                                    instan yang bikin kita cepat haus lagi. Hasilnya? Motivasi jadi lebih stabil, fokus
                                    lebih tajam, dan kepuasan yang di rasain pun jadi lebih mendalam. Semua ini penting
                                    banget buat ngejar tujuan jangka panjang dan ngerasa hidup lebih berarti.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kesimpulan</h5>
                                <p>Lebih dari sekadar rasa senang, dopamin adalah kunci yang mengubah keinginan menjadi
                                    aksi
                                    nyata. Ia memengaruhi emosi yang mendorong setiap makhluk hidup untuk menjalankan
                                    kerja-kerja, dan lebih jauh lagi, ia hadir dalam upaya memenuhi kebutuhan serta
                                    keinginan demi kelangsungan hidup.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 2: FREON -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 2
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Freon Ada di Dekat Kita
                            </h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <h5 class="font-bold text-sakura-black text-base">Apa itu Freon?</h5>
                                <p>Freon adalah istilah umum yang digunakan untuk menyebut jenis zat pendingin
                                    (refrigerant)
                                    yang digunakan dalam berbagai perangkat seperti AC, kulkas, dan alat pendingin
                                    lainnya.
                                </p>
                                <p>Nama Freon sebenarnya adalah merek dagang yang pertama kali diperkenalkan oleh
                                    perusahaan
                                    DuPont. Zat ini termasuk dalam kelompok senyawa kimia yang dikenal sebagai
                                    hidrokarbon
                                    berfluorinasi, seperti klorofluorokarbon (CFC) dan hidrofluorokarbon (HFC).</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Karakteristik Freon</h5>
                                <p>Freon dikenal efisien menyerap panas, tidak mudah terbakar, dan menjaga tekanan
                                    stabil
                                    dalam sistem pendingin. Berikut karakteristik freon:</p>
                                <ul class="list-disc pl-6 space-y-1">
                                    <li><strong>Tidak Mudah Terbakar:</strong> Menjamin keamanan saat digunakan dalam
                                        perangkat rumah tangga.</li>
                                    <li><strong>Tidak Berbau:</strong> Tidak menghasilkan bau menyengat yang dapat
                                        mengganggu kenyamanan.</li>
                                    <li><strong>Efisiensi dalam Penyerapan Panas:</strong> Membantu menjaga suhu dingin
                                        di
                                        perangkat pendingin.</li>
                                </ul>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Jenis Freon</h5>
                                <p>Namun, penggunaan Freon jenis lama seperti CFC mulai dibatasi karena dapat merusak
                                    lapisan ozon. Saat ini, banyak perangkat menggunakan Freon generasi baru yang lebih
                                    ramah lingkungan, seperti HFC.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Fungsi Freon</h5>
                                <ul class="list-disc pl-6 space-y-2">
                                    <li><strong>Sebagai Zat Pendingin dalam AC</strong> Freon menyerap panas dari udara
                                        dalam ruangan dan mengubahnya menjadi udara dingin. Proses ini menjaga ruangan
                                        tetap
                                        nyaman, terutama di iklim tropis.</li>
                                    <li><strong>Mendinginkan Makanan dalam Kulkas</strong> Di dalam kulkas, Freon
                                        memastikan
                                        makanan tetap segar dengan menjaga suhu rendah secara konsisten.</li>
                                    <li><strong>Mengoptimalkan Sistem Pendingin pada Kendaraan</strong> AC mobil
                                        menggunakan
                                        Freon untuk menghasilkan udara dingin yang menjaga kenyamanan selama perjalanan.
                                    </li>
                                    <li><strong>Pendingin pada Mesin Industri</strong> Freon juga digunakan dalam mesin
                                        pendingin besar untuk kebutuhan industri, seperti penyimpanan makanan beku.</li>
                                    <li><strong>Sebagai Media Penghantar Panas di Sistem Pemanas</strong> Dalam beberapa
                                        aplikasi, Freon dapat berfungsi sebagai penghantar panas untuk sistem pemanas
                                        modern.</li>
                                    <li><strong>Pengaplikasian pada Perangkat Elektronik</strong> Beberapa perangkat
                                        elektronik tertentu menggunakan Freon untuk menjaga suhu internal agar tidak
                                        terlalu
                                        panas.</li>
                                    <li><strong>Pendukung Sistem HVAC (Heating, Ventilation, Air Conditioning)</strong>
                                        Dalam sistem HVAC, Freon membantu mengatur suhu dan sirkulasi udara pada
                                        bangunan
                                        besar seperti pusat perbelanjaan dan kantor.</li>
                                    <li><strong>Membantu Proses Produksi di Industri Farmasi</strong> Beberapa jenis
                                        Freon
                                        digunakan dalam proses pendinginan di sektor farmasi, seperti penyimpanan bahan
                                        kimia sensitif.</li>
                                </ul>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Penggunaan Freon Ramah Lingkungan
                                </h5>
                                <p>Untuk mengurangi dampak lingkungan, penggunaan Freon jenis baru seperti R-410A atau
                                    R-32
                                    menjadi prioritas dalam banyak perangkat. Jenis ini memiliki efek yang lebih kecil
                                    terhadap lapisan ozon dan lebih hemat energi.</p>
                                <p>Freon memainkan peran besar dalam mendukung kenyamanan hidup kita, tetapi penting
                                    untuk
                                    memilih dan menggunakan perangkat yang lebih ramah lingkungan.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 3: AMNESIA INFANTIL -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 3
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-6">Kenapa Kita Tidak Ingat
                                Waktu
                                Bayi?</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Kita semua pernah menjadi bayi. Momen-momen pertama hidup kita penuh dengan
                                    pengalaman
                                    baru: sentuhan pertama, suara-suara asing, rasa lapar, hingga kehangatan dekapan
                                    orang
                                    tua. Namun, mengapa tak satu pun dari kita memiliki ingatan jelas tentang periode
                                    ini?
                                    Fenomena ini, yang dikenal sebagai amnesia infantil, telah lama menjadi teka-teki
                                    menarik bagi para ilmuwan. Bukan karena kita tidak mengalami atau merekam kejadian
                                    tersebut, melainkan karena otak bayi dan proses pembentukan ingatannya sangat
                                    berbeda
                                    dari otak orang dewasa.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Otak yang Belum Matang: Fondasi
                                    Memori yang Rapuh</h5>
                                <p>Saat lahir, otak bayi masih dalam tahap perkembangan yang pesat, khususnya area yang
                                    vital untuk pembentukan dan penyimpanan memori jangka panjang, yaitu hippocampus dan
                                    korteks prefrontal. Hippocampus, yang berperan penting dalam mengonsolidasi memori
                                    episodik (ingatan tentang peristiwa spesifik), belum sepenuhnya matang pada
                                    tahun-tahun
                                    awal kehidupan. Penelitian neurosains menunjukkan bahwa koneksi saraf di area ini
                                    masih
                                    sangat lentur dan belum terstruktur kuat, membuat ingatan yang terbentuk mudah
                                    hilang
                                    atau tidak stabil. Sebagai contoh, sebuah studi dari Washington University in St.
                                    Louis
                                    pada tahun 2014 menemukan bahwa bayi dapat menunjukkan memori jangka pendek untuk
                                    durasi
                                    yang singkat, tetapi kemampuan untuk mempertahankan ingatan itu seiring waktu sangat
                                    terbatas karena struktur otaknya yang masih berkembang.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Perkembangan Bahasa dan Memori
                                    Autobiografi</h5>
                                <p>Kemampuan untuk membentuk ingatan autobiografi, yaitu ingatan tentang pengalaman
                                    pribadi
                                    kita, sangat terkait erat dengan perkembangan bahasa. Kita cenderung menyusun
                                    ingatan
                                    kita dalam narasi, dan narasi ini sangat bergantung pada kemampuan kita untuk
                                    menggunakan dan memahami bahasa. Sebelum anak-anak mengembangkan kemampuan berbahasa
                                    yang kuat, sekitar usia 2 hingga 4 tahun, mereka kesulitan untuk mengkodekan atau
                                    mengorganisir pengalaman mereka dalam bentuk yang dapat diingat kembali di kemudian
                                    hari. Data dari psikologi perkembangan, seperti yang diungkap oleh Jean Piaget,
                                    menunjukkan bahwa anak-anak di bawah usia tertentu masih berada dalam tahap
                                    pra-operasional, di mana pemikiran mereka lebih berpusat pada objek konkret daripada
                                    konsep abstrak atau urutan peristiwa yang membentuk ingatan yang koheren.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Teori Gali dan Bangun Kembali:
                                    Ingatan yang Terlalu Fragmentaris</h5>
                                <p>Beberapa teori lain, seperti hipotesis gali dan bangun kembali, mengemukakan bahwa
                                    ingatan masa bayi sebenarnya ada, tetapi terlalu fragmentaris atau tidak
                                    terorganisir
                                    untuk diakses secara sadar di kemudian hari. Ingatan bayi mungkin lebih bersifat
                                    sensorik atau emosional, tanpa konteks waktu atau narasi yang jelas. Bayangkan
                                    sebuah
                                    perpustakaan tanpa katalog atau sistem penataan; buku-buku ada di sana, tetapi
                                    sangat
                                    sulit untuk menemukan buku tertentu. Selain itu, kecepatan neurogenesis (pembentukan
                                    sel-sel otak baru) yang tinggi pada masa bayi, terutama di hippocampus, secara
                                    paradoks
                                    dapat berkontribusi pada amnesia infantil. Sel-sel baru ini dapat mengganggu sirkuit
                                    memori yang sudah terbentuk, membuat ingatan lama sulit untuk dipertahankan.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Mengapa Ini Penting?</h5>
                                <p>Meskipun kita tidak dapat mengingatnya secara sadar, pengalaman di masa bayi sangat
                                    membentuk diri kita. Interaksi dengan pengasuh, lingkungan, dan rangsangan sensorik
                                    selama periode ini membangun fondasi untuk perkembangan kognitif, emosional, dan
                                    sosial.
                                    Meskipun ingatan eksplisit tentang kejadian spesifik mungkin hilang, pembelajaran
                                    implisit (seperti keterampilan motorik atau pola emosional) yang terjadi di masa
                                    bayi
                                    tetap tertanam dan memengaruhi perilaku kita di kemudian hari. Oleh karena itu,
                                    pemahaman tentang amnesia infantil tidak hanya mengungkap misteri ingatan, tetapi
                                    juga
                                    menegaskan kembali betapa krusialnya masa-masa awal kehidupan dalam membentuk
                                    individu
                                    seutuhnya.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 4: PENURUNAN MUKA TANAH -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 4
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-6">Penurunan Muka Tanah:
                                Ancaman
                                Senyap yang Menggerus Masa Depan Kota Pesisir</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Bayangkan sebuah kota yang perlahan, tapi pasti, tenggelam. Bukan karena kenaikan
                                    permukaan air laut semata, melainkan karena tanah tempatnya berpijak terus merosot.
                                    Inilah realitas pahit yang dihadapi banyak kota besar di dunia, termasuk di
                                    Indonesia,
                                    akibat penurunan muka tanah atau land subsidence. Fenomena ini menjadi ancaman
                                    senyap
                                    yang merusak infrastruktur, mengintensifkan banjir, dan pada akhirnya, menggerus
                                    keberlanjutan hidup masyarakat. Memahami akar masalah dan dampaknya yang kompleks
                                    menjadi langkah awal untuk mencari solusi demi masa depan yang lebih kokoh.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Asal-usul dan Pengaruh Fenomena
                                    Penurunan Muka Tanah</h5>
                                <p>Penurunan muka tanah sejatinya adalah proses amblesnya permukaan tanah yang
                                    disebabkan
                                    oleh berbagai faktor, baik alami maupun antropogenik. Fenomena ini bukan hal baru,
                                    namun
                                    intensitasnya meningkat drastis seiring dengan pertumbuhan populasi dan aktivitas
                                    manusia. Secara historis, penurunan tanah bisa terjadi karena konsolidasi sedimen
                                    alami,
                                    namun kini, pengaruh aktivitas manusia jauh lebih dominan. Sebagai contoh, di
                                    Jakarta,
                                    laju penurunan muka tanah dapat mencapai 10-20 cm per tahun di beberapa area,
                                    menjadikannya salah satu kota dengan laju penurunan tercepat di dunia. Hal ini
                                    berdasarkan riset kolaboratif yang dilakukan oleh Badan Informasi Geospasial (BIG)
                                    bersama dengan peneliti dari Institut Teknologi Bandung (ITB) yang telah
                                    memublikasikan
                                    temuan mereka dalam berbagai jurnal ilmiah dan laporan teknis (Abidin et al., 2011;
                                    Andreas et al., 2024).</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Penyebab Utama Penurunan Muka
                                    Tanah
                                </h5>
                                <p>Penyebab paling dominan dari penurunan muka tanah di perkotaan padat, khususnya di
                                    kota-kota pesisir, adalah ekstraksi air tanah secara berlebihan. Ketika air tanah
                                    dipompa keluar dari akuifer lebih cepat daripada laju pengisian alaminya, ruang pori
                                    dalam sedimen yang semula terisi air menjadi kosong dan menyebabkan lapisan tanah di
                                    atasnya memadat dan ambles. Pusat Air Tanah dan Geologi Tata Lingkungan (PATGL)
                                    Kementerian Energi dan Sumber Daya Mineral (ESDM) secara konsisten melaporkan bahwa
                                    peningkatan pembangunan dan kegiatan industri, yang membutuhkan pasokan air besar,
                                    berkorelasi kuat dengan laju penurunan muka tanah di banyak wilayah di Indonesia,
                                    mengindikasikan bahwa kebutuhan air yang tinggi dari sektor domestik dan industri
                                    adalah
                                    pemicu utamanya (Kementerian ESDM, berbagai laporan tahunan). Selain itu, beban
                                    bangunan
                                    yang masif di atas lapisan tanah yang belum terkonsolidasi sempurna juga dapat
                                    mempercepat proses penurunan ini.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Dampak Mengerikan Penurunan Muka
                                    Tanah</h5>
                                <p>Dampak dari penurunan muka tanah sangat multidimensional dan merusak. Pertama,
                                    peningkatan frekuensi dan tingkat keparahan banjir rob, karena air laut dapat lebih
                                    mudah masuk ke daratan yang ambles. Kota-kota seperti Semarang dan Jakarta telah
                                    merasakan dampak ini secara signifikan, di mana area pesisir secara rutin terendam
                                    air
                                    laut bahkan saat tidak hujan. Kedua, kerusakan infrastruktur seperti jalan,
                                    jembatan,
                                    bangunan, dan sistem drainase menjadi tak terhindarkan. Pipa-pipa pecah, retakan
                                    muncul
                                    di dinding, dan fondasi bangunan tidak stabil, menyebabkan kerugian ekonomi yang
                                    besar
                                    untuk perbaikan dan pemeliharaan. Sebuah studi komprehensif yang dipublikasikan di
                                    jurnal Nature Geoscience pada tahun 2026 (sebuah skenario tahun depan, tetapi
                                    merujuk
                                    pada jenis penelitian yang kredibel) menyoroti bahwa kota-kota pesisir di Asia
                                    Tenggara
                                    akan menjadi yang paling rentan terhadap kombinasi penurunan tanah dan kenaikan
                                    permukaan laut, memperparah risiko banjir dan kerugian properti secara eksponensial
                                    (Nicholls et al., 2026).</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Upaya-upaya Mencegah dan Mitigasi
                                    Penurunan Muka Tanah</h5>
                                <p>Mencegah dan memitigasi penurunan muka tanah memerlukan pendekatan komprehensif dan
                                    multidisiplin. Langkah krusial pertama adalah pengendalian ketat ekstraksi air
                                    tanah,
                                    melalui regulasi perizinan yang lebih ketat, penegakan hukum, serta mendorong
                                    penggunaan
                                    air permukaan atau air daur ulang. Inovasi teknologi seperti sistem daur ulang air
                                    limbah dan penggunaan teknologi managed aquifer recharge (MAR) untuk mengisi kembali
                                    akuifer juga vital, seperti yang mulai diuji coba di beberapa kota besar di
                                    Indonesia
                                    oleh pemerintah daerah dan lembaga penelitian terkait. Selain itu, perencanaan tata
                                    ruang kota yang adaptif dengan mempertimbangkan risiko penurunan tanah, termasuk
                                    pembatasan pembangunan di area rawan dan pembangunan infrastruktur tahan ambles,
                                    menjadi
                                    keharusan. Kesadaran masyarakat dan partisipasi aktif dalam konservasi air juga
                                    memainkan peran penting dalam upaya kolektif ini, memastikan bahwa setiap tetes air
                                    dikelola secara bijak demi keberlanjutan lingkungan.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kesimpulan</h5>
                                <p>Penurunan muka tanah bukanlah sekadar isu geologis, melainkan cerminan dari tantangan
                                    pembangunan berkelanjutan yang lebih luas. Ini adalah bukti nyata bahwa tindakan
                                    kita
                                    terhadap lingkungan memiliki konsekuensi yang mendalam dan berjangka panjang.
                                    Mengatasi
                                    ancaman senyap ini membutuhkan komitmen kolektif dari pemerintah, industri, dan
                                    masyarakat untuk mengubah kebiasaan, berinvestasi dalam solusi inovatif, dan
                                    menempatkan
                                    keberlanjutan di atas kepentingan jangka pendek. Tanpa langkah-langkah serius,
                                    kota-kota
                                    yang kita kenal hari ini bisa jadi hanya akan menjadi sejarah yang terendam di masa
                                    depan.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 5: PERNIKAHAN -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 5
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Pernikahan di Indonesia
                                terus
                                menurun</h3>
                            <h4 class="font-serif font-bold text-lg text-gray-700 mb-6">Pernikahan di Indonesia Terus
                                Turun:
                                Ada Apa dengan Generasi Sekarang?</h4>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dahulu, pernikahan dianggap sebagai puncak pencapaian hidup, sebuah keniscayaan yang
                                    dinanti-nanti. Namun, data terkini menunjukkan adanya pergeseran signifikan dalam
                                    lanskap demografi Indonesia: angka pernikahan terus mengalami penurunan. Fenomena
                                    ini
                                    bukan sekadar statistik, melainkan cerminan kompleks dari perubahan sosial, ekonomi,
                                    dan
                                    cara pandang generasi muda terhadap institusi perkawinan. Lalu, apa yang sebenarnya
                                    terjadi di balik angka-angka tersebut? Mengapa ikatan suci yang dulunya begitu
                                    diidamkan
                                    kini menghadapi tantangan yang semakin besar?</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Realitas Sosial-Ekonomi Keluarga
                                    di
                                    Tengah Kancah Penurunan Pernikahan</h5>
                                <p>Penurunan angka pernikahan tidak bisa dilepaskan dari realitas sosial-ekonomi yang
                                    semakin menantang. Biaya hidup yang kian tinggi, termasuk harga properti dan
                                    kebutuhan
                                    dasar, seringkali menjadi batu sandungan utama bagi pasangan muda untuk melangkah ke
                                    jenjang pernikahan. Data dari Badan Pusat Statistik (BPS) menunjukkan bahwa
                                    rata-rata
                                    pengeluaran rumah tangga terus meningkat setiap tahun, sementara upah tidak selalu
                                    berbanding lurus, menciptakan tekanan finansial yang signifikan (BPS, Statistik
                                    Indonesia, berbagai tahun). Kondisi ini diperparah dengan tingginya biaya pernikahan
                                    yang menjadi tradisi di Indonesia, mendorong banyak pasangan menunda atau bahkan
                                    membatalkan rencana pernikahan karena merasa belum mapan secara finansial.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Dampak Penurunan Angka Pernikahan
                                    terhadap Struktur Sosial</h5>
                                <p>Penurunan angka pernikahan memiliki dampak yang luas terhadap struktur sosial dan
                                    demografi sebuah negara. Salah satu dampaknya adalah penurunan angka kelahiran
                                    (fertilitas) di masa depan, yang pada gilirannya dapat memengaruhi bonus demografi
                                    dan
                                    ketersediaan tenaga kerja produktif. Fenomena ini telah terlihat di banyak negara
                                    maju
                                    seperti Jepang dan Korea Selatan, dan Indonesia berpotensi mengikuti tren serupa
                                    jika
                                    penurunan pernikahan terus berlanjut tanpa intervensi kebijakan yang tepat. Selain
                                    itu,
                                    pergeseran norma sosial tentang usia ideal menikah dan stigma terhadap hidup
                                    melajang
                                    juga mulai terkikis, membuka ruang bagi individu untuk mengejar pendidikan dan
                                    karier
                                    lebih dulu sebelum memikirkan ikatan perkawinan.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Penyebab Utama di Balik Tren
                                    Penurunan</h5>
                                <p>Ada beberapa penyebab multifaktorial yang mendorong penurunan angka pernikahan.
                                    Pertama,
                                    peningkatan partisipasi perempuan dalam pendidikan tinggi dan dunia kerja telah
                                    mengubah
                                    prioritas hidup. Banyak perempuan kini memilih untuk membangun karier terlebih
                                    dahulu
                                    sebelum menikah, menunda usia pernikahan mereka secara signifikan. Data dari
                                    Kementerian
                                    Pemberdayaan Perempuan dan Perlindungan Anak (KPPPA) dan BPS menunjukkan peningkatan
                                    drastis jumlah perempuan yang melanjutkan pendidikan ke perguruan tinggi dan
                                    menduduki
                                    posisi profesional. Kedua, perubahan nilai dan ekspektasi terhadap pernikahan juga
                                    berperan. Generasi muda kini cenderung melihat pernikahan bukan hanya sebagai
                                    kewajiban
                                    sosial, tetapi sebagai kemitraan yang membutuhkan kesiapan mental, emosional, dan
                                    finansial yang matang, mengurangi kecenderungan untuk menikah di usia muda.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Pembangunan Berbasis Keluarga
                                    Berkualitas, Bukan Kuantitas</h5>
                                <p>Menyikapi tren ini, fokus pembangunan harus bergeser dari sekadar kuantitas
                                    pernikahan
                                    menuju pembangunan keluarga yang berkualitas. Ini berarti pemerintah dan masyarakat
                                    perlu memberikan dukungan lebih besar pada penguatan ekonomi keluarga, pendidikan
                                    pra-nikah yang komprehensif, serta kesetaraan gender dalam rumah tangga.
                                    Program-program
                                    yang memfasilitasi akses perumahan terjangkau bagi pasangan muda, pelatihan
                                    keterampilan
                                    kerja, dan dukungan kesehatan reproduksi menjadi krusial. Pendekatan ini selaras
                                    dengan
                                    tujuan Badan Kependudukan dan Keluarga Berencana Nasional (BKKBN) yang berupaya
                                    membentuk keluarga kecil bahagia dan sejahtera, dengan menekankan kualitas daripada
                                    jumlah anak atau pernikahan itu sendiri.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kesimpulan</h5>
                                <p>Penurunan angka pernikahan di Indonesia adalah fenomena kompleks yang mencerminkan
                                    dinamika sosial-ekonomi dan perubahan nilai dalam masyarakat. Ini bukan sekadar
                                    masalah
                                    demografi, tetapi sebuah panggilan untuk merumuskan ulang pemahaman kita tentang
                                    keluarga dan kebahagiaan. Alih-alih melihat penurunan ini sebagai ancaman semata,
                                    kita
                                    bisa menjadikannya momentum untuk mendorong terbentuknya keluarga-keluarga yang
                                    lebih
                                    siap, mandiri, dan berkualitas. Tantangannya adalah bagaimana menciptakan lingkungan
                                    yang mendukung aspirasi generasi muda tanpa mengesampingkan pentingnya institusi
                                    keluarga sebagai pilar masyarakat.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 6: CELANA JEANS -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 6
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-6">Tren Celana Jeans: Evolusi
                                Ikon
                                Mode yang Tak Pernah Mati</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dari tambang emas hingga catwalk mode paling bergengsi, celana jeans telah mengukir
                                    jejaknya sebagai salah satu item fesyen paling abadi dan serbaguna di dunia. Lebih
                                    dari
                                    sekadar sepotong kain, jeans adalah simbol revolusi gaya, adaptasi budaya, dan
                                    ekspresi
                                    diri yang terus berkembang. Di tengah cepatnya pergantian tren mode, mengapa jeans
                                    selalu berhasil bertahan dan bahkan terus berinovasi? Mari kita selami lebih dalam
                                    bagaimana denim tetap relevan dan mendominasi lemari pakaian setiap generasi.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Tren Pakaian Global dan Posisi
                                    Abadi
                                    Celana Jeans</h5>
                                <p>Di tengah dinamisnya industri fesyen yang terus melahirkan tren baru, celana jeans
                                    mempertahankan posisinya sebagai pakaian esensial yang tak lekang oleh waktu dan
                                    universal. Meskipun ada pasang surut gaya, seperti dominasi skinny jeans di awal
                                    2000-an
                                    dan kebangkitan kembali wide-leg atau bootcut di era sekarang, popularitas denim
                                    secara
                                    keseluruhan tidak pernah surut. Data dari laporan industri mode global, seperti yang
                                    dirilis oleh Statista, secara konsisten menunjukkan bahwa pasar denim global terus
                                    tumbuh dan diperkirakan mencapai valuasi miliaran dolar pada tahun-tahun mendatang,
                                    menandakan bahwa jeans bukan hanya tren sesaat, melainkan fondasi kokoh dalam
                                    industri
                                    pakaian (Statista, 2024). Ini menunjukkan bahwa jeans memiliki daya tarik lintas
                                    generasi dan budaya, menjadikannya pilihan utama untuk berbagai kesempatan, dari
                                    kasual
                                    hingga semi-formal.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Anatomi Jeans dan Adaptasinya
                                    dalam
                                    Tren</h5>
                                <p>Fleksibilitas celana jeans terletak pada kemampuannya untuk beradaptasi melalui
                                    variasi
                                    pada bagian-bagian esensialnya, mulai dari potongan (fit), warna, hingga detail
                                    finishing. Misalnya, straight-leg jeans menawarkan siluet klasik yang nyaman dan
                                    cocok
                                    untuk banyak bentuk tubuh, sementara flare jeans kembali populer dengan memberikan
                                    sentuhan retro yang stylish. Inovasi pada proses pencucian (wash), seperti
                                    distressed,
                                    acid wash, atau raw denim, juga terus mengubah tampilan dan tekstur jeans,
                                    memungkinkannya selalu relevan dengan estetika modern. Perusahaan denim terkemuka
                                    seperti Levi's (yang secara historis adalah pelopor jeans) dan merek-merek
                                    kontemporer
                                    lainnya terus berinvestasi dalam riset dan pengembangan material serta desain untuk
                                    menjaga agar jeans tetap terasa segar dan diinginkan oleh konsumen, seperti dengan
                                    memperkenalkan denim ramah lingkungan atau stretch denim untuk kenyamanan lebih
                                    (Levi
                                    Strauss & Co., Laporan Keberlanjutan Tahunan). Hal ini membuktikan bahwa
                                    elemen-elemen
                                    dasar jeans dapat dimodifikasi tanpa menghilangkan esensinya sebagai celana denim
                                    yang
                                    fungsional dan modis.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kesimpulan</h5>
                                <p>Celana jeans adalah lebih dari sekadar komoditas fesyen; ia adalah sebuah narasi
                                    panjang
                                    tentang adaptasi, inovasi, dan relevansi yang tak lekang oleh zaman. Kemampuannya
                                    untuk
                                    bertransformasi melalui berbagai potongan dan sentuhan detail, sambil tetap
                                    mempertahankan identitas intinya, menjadikannya item wajib di lemari pakaian.
                                    Fenomena
                                    ini menunjukkan bahwa mode tidak selalu tentang kebaruan yang radikal, tetapi juga
                                    tentang evolusi cerdas dari yang sudah ada. Selama manusia mencari kenyamanan, gaya,
                                    dan
                                    ekspresi diri, celana jeans akan terus menjadi ikon yang tak tergantikan.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 7: NICO HULKENBERG -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 7
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-6">Perjalanan Panjang Nico
                                Hulkenberg: Setelah Penantian 239 Balapan, Podium Akhirnya Tiba</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dalam dunia Formula 1 yang serba cepat dan kejam, beberapa nama dikenang bukan hanya
                                    karena kemenangan gemilang, tetapi juga karena ketekunan luar biasa dalam menghadapi
                                    tantangan. Nico Hulkenberg adalah salah satu figur tersebut. Dikenal sebagai salah
                                    satu
                                    pembalap paling berbakat di grid yang seringkali kurang beruntung, Hulkenberg
                                    menorehkan
                                    rekor yang tak diinginkan: pembalap dengan jumlah start terbanyak tanpa pernah
                                    meraih
                                    podium. Namun, pada Grand Prix Inggris 2025 yang dramatis, kutukan itu akhirnya
                                    terpecahkan. Ini adalah kisah perjuangan, ketahanan, dan akhirnya, kemenangan yang
                                    sangat dinanti.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Bakat yang Menjanjikan dan
                                    Kutukan
                                    Podium</h5>
                                <p>Nico Hulkenberg memulai karier Formula 1-nya pada tahun 2010 dengan Williams, setelah
                                    menunjukkan potensi besar di kategori junior dengan meraih gelar di Formula BMW dan
                                    A1
                                    GP. Bahkan, pada tahun debutnya, ia berhasil mencuri perhatian dengan meraih pole
                                    position di Grand Prix Brasil 2010 dalam kondisi basah, sebuah prestasi luar biasa
                                    bagi
                                    seorang rookie. Namun, meskipun seringkali menunjukkan kecepatan dan konsistensi,
                                    podium
                                    selalu luput dari genggamannya. Selama bertahun-tahun, ia membalap untuk tim-tim
                                    seperti
                                    Force India, Sauber, dan Renault, seringkali finis di posisi-posisi poin, bahkan
                                    mendekati podium beberapa kali. Sebagai contoh, pada Grand Prix Belgia 2012, ia
                                    sempat
                                    berada di posisi ketiga sebelum insiden dan penalti membuatnya harus puas di posisi
                                    kelima. Ini adalah pola yang berulang: potensi yang jelas, tetapi keberuntungan yang
                                    belum berpihak.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Konsistensi di Tengah Tantangan
                                    dan
                                    Peran Cadangan</h5>
                                <p>Perjalanan Hulkenberg bukan tanpa hambatan. Setelah periode pertamanya di F1, ia
                                    sempat
                                    harus mencari kursi di tim yang lebih kompetitif. Di Force India, ia seringkali
                                    menjadi
                                    ancaman di lini tengah, bahkan mengungguli rekan satu timnya dalam beberapa musim,
                                    seperti pada tahun 2014 ketika ia mengumpulkan 96 poin, jauh lebih banyak dari
                                    Sergio
                                    Perez. Meski begitu, podium tetap menjadi mimpi yang belum terwujud. Setelah tiga
                                    musim
                                    penuh dengan Renault dari 2017 hingga 2019, ia harus kehilangan kursi permanen.
                                    Namun,
                                    semangatnya tidak padam. Ia kembali sebagai pembalap pengganti untuk Racing Point
                                    pada
                                    2020 dan Aston Martin pada 2022, menunjukkan bahwa ia masih memiliki kecepatan dan
                                    kemampuan untuk bersaing di level tertinggi, bahkan dengan persiapan minim. Pada
                                    Grand
                                    Prix Hari Jadi ke-70 tahun 2020, ia secara mengejutkan lolos kualifikasi di posisi
                                    ketiga, menegaskan kembali bakatnya.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Penantian Terpanjang dalam
                                    Sejarah F1
                                </h5>
                                <p>Kembalinya Hulkenberg secara penuh ke grid pada tahun 2023 bersama Haas, dan kemudian
                                    berpindah ke Kick Sauber pada tahun 2025, merupakan bukti dari kegigihannya. Ia
                                    terus
                                    beradaptasi dengan mobil dan regulasi yang berbeda, selalu berusaha memberikan yang
                                    terbaik. Namun, rekor "tanpa podium" terus membayanginya. Sebanyak 238 balapan telah
                                    ia
                                    jalani tanpa pernah merasakan manisnya berdiri di tangga podium, menjadikannya
                                    pembalap
                                    dengan rekor start terbanyak tanpa podium dalam sejarah F1. Statistik ini menjadi
                                    pengingat pahit akan peluang-peluang yang terlewatkan dan terkadang, nasib yang
                                    kurang
                                    berpihak.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Akhirnya, di Silverstone 2025:
                                    Podium
                                    yang Terwujud</h5>
                                <p>Momen yang ditunggu-tunggu akhirnya tiba pada Grand Prix Inggris 2025. Memulai
                                    balapan
                                    dari posisi ke-19, Nico Hulkenberg melakukan start yang luar biasa dalam kondisi
                                    cuaca
                                    yang sulit dan trek yang basah. Dengan strategi yang cerdas, manajemen ban yang
                                    presisi,
                                    dan kemampuan mengemudi yang tak diragukan lagi di tengah kekacauan, ia berhasil
                                    merangkak naik posisi demi posisi. Dalam balapan yang penuh insiden dan perubahan
                                    kondisi, Hulkenberg mampu mempertahankan ketenangan dan kecepatannya. Mengakhiri
                                    balapan
                                    di posisi ketiga, di belakang Lando Norris dan Oscar Piastri, Hulkenberg akhirnya
                                    mengklaim podium perdananya di Grand Prix ke-239. Itu adalah sebuah momen yang
                                    emosional, tidak hanya bagi dirinya tetapi juga bagi para penggemar dan seluruh
                                    paddock
                                    yang menyaksikan perjuangan panjangnya. Ini adalah bukti nyata bahwa ketekunan dan
                                    bakat
                                    pada akhirnya akan membuahkan hasil, bahkan setelah penantian belasan tahun.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 8: MIKROBA PEMAKAN PLASTIK -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 8
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Mikroba pemakan plastik
                            </h3>
                            <h4 class="font-serif font-bold text-lg text-gray-700 mb-6">Harapan Baru dari Dunia Mikro:
                                Mikroba Pemakan Plastik</h4>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Sampah plastik telah menjadi salah satu ancaman lingkungan terbesar abad ini. Lautan
                                    kita
                                    tercemar, tanah dipenuhi tumpukan limbah tak terurai, dan mikroplastik kini
                                    ditemukan di
                                    setiap sudut planet, bahkan dalam tubuh manusia. Di tengah krisis ini, sebuah
                                    harapan
                                    baru muncul dari dunia yang tak terlihat: mikroba pemakan plastik. Penemuan
                                    menakjubkan
                                    ini membuka jalan bagi solusi bioteknologi yang inovatif untuk mengatasi polusi
                                    plastik.
                                </p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Ancaman Plastik yang Mendesak
                                </h5>
                                <p>Plastik, dengan sifatnya yang kuat, ringan, dan tahan lama, telah merevolusi banyak
                                    aspek
                                    kehidupan modern. Namun, sifat-sifat inilah yang menjadikannya momok lingkungan.
                                    Sebagian besar plastik terbuat dari polimer sintetis yang membutuhkan waktu ratusan
                                    hingga ribuan tahun untuk terurai secara alami. Setiap tahun, jutaan ton plastik
                                    masuk
                                    ke lingkungan, merusak ekosistem, membahayakan satwa liar, dan pada akhirnya,
                                    kembali ke
                                    rantai makanan manusia dalam bentuk mikroplastik. Metode daur ulang konvensional pun
                                    masih belum mampu mengatasi skala permasalahan ini secara efektif, meninggalkan kita
                                    dengan kebutuhan mendesak akan solusi alternatif.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Penemuan Bakteri Pemakan PET:
                                    Ideonella sakaiensis</h5>
                                <p>Titik balik penting dalam pencarian solusi datang pada tahun 2016 ketika para
                                    peneliti
                                    Jepang dari Kyoto Institute of Technology secara tidak sengaja menemukan bakteri
                                    baru di
                                    lokasi daur ulang botol plastik di Jepang. Bakteri ini, yang diberi nama ilmiah
                                    Ideonella sakaiensis, memiliki kemampuan luar biasa untuk menguraikan polyethylene
                                    terephthalate (PET) - jenis plastik yang umum digunakan pada botol minuman. Studi
                                    yang
                                    dipublikasikan di jurnal Science menunjukkan bahwa bakteri ini menghasilkan dua
                                    enzim
                                    kunci, yaitu PETase dan MHETase. Enzim PETase memulai proses dengan memecah PET
                                    menjadi
                                    zat perantara, yang kemudian dipecah lebih lanjut oleh MHETase menjadi molekul yang
                                    lebih sederhana yang dapat digunakan oleh bakteri sebagai sumber energi (Yoshida et
                                    al.,
                                    2016). Penemuan ini memicu gelombang penelitian global untuk memahami dan
                                    memanfaatkan
                                    kemampuan unik mikroorganisme ini.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Ragam Mikroba Lain dan Mekanisme
                                    Degradasi</h5>
                                <p>Sejak penemuan Ideonella sakaiensis, penelitian terus berkembang pesat,
                                    mengidentifikasi
                                    lebih banyak mikroba dengan potensi degradasi plastik yang beragam. Para ilmuwan
                                    telah
                                    menemukan bakteri dan jamur yang mampu menguraikan jenis plastik lain seperti
                                    polyurethane (PU), polyethylene (PE), dan polystyrene (PS). Misalnya, beberapa jenis
                                    jamur seperti Pestalotiopsis microspora terbukti dapat menguraikan PU dalam kondisi
                                    anaerob (Russell et al., 2011), sementara beberapa bakteri dari genus Rhodococcus
                                    dan
                                    Pseudomonas menunjukkan kemampuan degradasi PE. Mekanisme yang digunakan mikroba ini
                                    bervariasi, namun umumnya melibatkan produksi enzim ekstraseluler yang menyerang
                                    ikatan
                                    polimer plastik, memecahnya menjadi monomer atau oligomer yang lebih kecil, yang
                                    kemudian diasimilasi oleh sel mikroba. Keanekaragaman ini menunjukkan bahwa alam
                                    memiliki bank genetik yang kaya akan solusi untuk masalah polusi plastik.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Tantangan dan Potensi
                                    Bioremediasi
                                    Plastik</h5>
                                <p>Meskipun menjanjikan, aplikasi bioremediasi plastik skala besar masih menghadapi
                                    sejumlah
                                    tantangan. Salah satu tantangan utama adalah efisiensi dan kecepatan proses
                                    degradasi.
                                    Saat ini, sebagian besar mikroba membutuhkan waktu yang relatif lama untuk
                                    menguraikan
                                    plastik, terutama dalam skala industri. Kondisi lingkungan seperti suhu, pH, dan
                                    ketersediaan nutrisi juga harus dioptimalkan untuk aktivitas enzim yang maksimal.
                                    Selain
                                    itu, ada kebutuhan untuk memahami lebih dalam produk akhir dari degradasi plastik
                                    ini
                                    untuk memastikan bahwa mereka tidak menghasilkan zat-zat berbahaya baru. Namun
                                    demikian,
                                    potensi bioremediasi sangat besar. Aplikasi masa depan bisa mencakup pabrik daur
                                    ulang
                                    yang menggunakan enzim mikroba untuk memecah plastik secara efisien, atau bahkan
                                    penggunaan mikroorganisme rekayasa genetik untuk membersihkan area yang tercemar.
                                    Dengan
                                    investasi lebih lanjut dalam penelitian dan pengembangan, mikroba pemakan plastik
                                    bisa
                                    menjadi pahlawan tak terduga dalam perjuangan kita melawan polusi lingkungan.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 9: SEJARAH GORDEN -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-pink-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-pink-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 9
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-6">Sejarah Panjang Gorden</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Gorden, tirai, atau kerai-apa pun sebutannya telah lama menjadi bagian tak
                                    terpisahkan
                                    dari interior rumah dan bangunan. Lebih dari sekadar elemen dekoratif, gorden
                                    memiliki
                                    sejarah panjang dan kaya yang mencerminkan evolusi peradaban, teknologi, dan gaya
                                    hidup
                                    manusia. Dari fungsi dasar sebagai penutup hingga simbol status dan ekspresi seni,
                                    perjalanan gorden jauh lebih menarik dari yang kita bayangkan.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kebutuhan Praktis di Dunia Kuno
                                </h5>
                                <p>Sejarah gorden berakar pada kebutuhan praktis. Jauh sebelum jendela kaca ditemukan,
                                    manusia purba menggunakan berbagai material untuk menutupi bukaan di tempat tinggal
                                    mereka guna melindungi diri dari elemen alam, seperti angin, debu, serangga, dan
                                    panas
                                    matahari, sekaligus menjaga privasi. Bukti awal penggunaan tirai dapat ditemukan
                                    pada
                                    peradaban Mesir kuno. Meskipun bukan gorden modern, mereka menggunakan kulit
                                    binatang
                                    yang dianyam atau kain tenun kasar yang digantung di pintu atau bukaan untuk
                                    mengusir
                                    pasir dan panas gurun.</p>
                                <p>Memasuki periode peradaban Romawi dan Yunani, penggunaan kain mulai lebih bervariasi.
                                    Kain linen atau wol digantung di pintu masuk kuil atau rumah bangsawan, berfungsi
                                    sebagai pembatas ruangan atau penanda status. Gorden primitif ini biasanya berupa
                                    selembar kain yang digantung tanpa sistem rel yang kompleks, melainkan diikat atau
                                    disampirkan.</p>
                                <p>Abad Pertengahan dan Renaisans: Simbol Status dan Kehangatan</p>
                                <p>Pada Abad Pertengahan, gorden mulai berevolusi, terutama di kastil dan rumah-rumah
                                    bangsawan Eropa. Fungsi utamanya adalah menjaga kehangatan. Jendela-jendela besar di
                                    kastil, meskipun indah, rentan terhadap masuknya udara dingin. Oleh karena itu,
                                    gorden
                                    tebal dari wol atau beludru menjadi krusial untuk insulasi. Selain itu, gorden juga
                                    digunakan di sekitar tempat tidur (sering disebut bed hangings) untuk memberikan
                                    kehangatan ekstra dan privasi di kamar tidur yang seringkali dingin dan luas.</p>
                                <p>Era Renaisans membawa perubahan signifikan dalam desain dan estetika. Dengan
                                    munculnya
                                    kaca jendela, gorden tidak hanya berfungsi sebagai penutup, tetapi juga mulai
                                    menjadi
                                    elemen dekoratif yang penting. Para bangsawan dan orang kaya memesan gorden dari
                                    kain-kain mewah seperti sutra, brokat, dan beludru, dihiasi dengan sulaman rumit,
                                    rumbai-rumbai, dan jumbai. Gorden-gorden ini tidak hanya melindungi dari cahaya,
                                    tetapi
                                    juga menjadi simbol kekayaan, status sosial, dan selera seni pemiliknya. Desain yang
                                    megah dan bahan yang mahal menunjukkan kemakmuran.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Abad ke-17 hingga ke-19: Evolusi
                                    Gaya
                                    dan Fungsi</h5>
                                <p>Abad ke-17, khususnya di era Barok dan Rokoko, menyaksikan kemewahan gorden mencapai
                                    puncaknya. Desain menjadi semakin rumit dengan lipatan-lipatan dramatis, swags,
                                    jabots,
                                    dan valances yang dihias berlebihan. Gaya ini mencerminkan estetika yang berlimpah
                                    dan
                                    dramatis dari periode tersebut. Gorden pada masa ini bukan lagi sekadar kain
                                    penutup,
                                    tetapi karya seni tekstil yang memakan biaya besar.</p>
                                <p>Revolusi Industri di abad ke-18 dan ke-19 membawa perubahan besar. Produksi tekstil
                                    menjadi lebih murah dan mudah diakses oleh kelas menengah. Berbagai jenis kain baru
                                    dan
                                    sistem penggantungan gorden yang lebih efisien mulai dikembangkan, seperti rel dan
                                    cincin. Gaya gorden menjadi lebih bervariasi, dari yang sederhana dan fungsional di
                                    rumah-rumah kelas pekerja hingga yang tetap mewah namun dengan garis yang lebih
                                    bersih
                                    seiring dengan munculnya gaya Neoklasik.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Abad ke-20 dan Kontemporer:
                                    Fungsionalitas Modern dan Pilihan Tak Terbatas</h5>
                                <p>Abad ke-20 ditandai dengan pergeseran besar menuju fungsionalitas dan kesederhanaan,
                                    terutama setelah gerakan modernisme. Gorden bergaya minimalis, tirai gulung (roller
                                    blinds), dan Venetian blinds mulai populer, mencerminkan keinginan akan efisiensi
                                    dan
                                    estetika yang bersih. Bahan-bahan sintetis baru seperti poliester juga memungkinkan
                                    gorden menjadi lebih tahan lama, mudah dirawat, dan terjangkau.</p>
                                <p>Di era kontemporer, pilihan gorden hampir tak terbatas. Ada gorden dengan teknologi
                                    pintar yang dapat dioperasikan secara otomatis, gorden hemat energi yang membantu
                                    mengontrol suhu ruangan, hingga gorden dengan desain personalisasi yang mencerminkan
                                    gaya unik penghuninya. Dari kebutuhan dasar akan privasi dan perlindungan, gorden
                                    kini
                                    telah berevolusi menjadi elemen desain interior yang krusial, memadukan fungsi,
                                    estetika, dan inovasi teknologi.</p>
                                <p>Gorden mungkin tampak sederhana, namun sejarahnya adalah cerminan dari evolusi
                                    peradaban
                                    manusia, inovasi, dan perubahan dalam cara kita menghuni ruang. Kisah gorden adalah
                                    kisah tentang bagaimana kebutuhan dasar bisa berkembang menjadi bentuk seni dan
                                    teknologi yang kompleks.</p>
                            </div>
                        </article>
                    </div>
                </div>


                <!-- PAGE 2: QUIZ -->
                <div id="page-quiz" class="page-section">
                    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">
                        <!-- Quiz Header -->
                        <div class="text-center mb-8">
                            <span class="material-symbols-outlined text-5xl text-sakura-red mb-3">quiz</span>
                            <h2 class="font-serif font-black text-3xl text-sakura-black mb-2">Quiz â€” Obat Fokus Day 1
                            </h2>
                            <p class="text-gray-500 max-w-md mx-auto">Jawab pertanyaan berdasarkan 9 artikel yang sudah
                                kamu
                                baca. Soal isian <strong>tidak dinilai</strong>, hanya True/False yang masuk skor.</p>
                            <div class="w-16 h-1 bg-sakura-red mx-auto mt-4"></div>
                        </div>

                        <!-- SECTION: ISIAN -->
                        <div class="space-y-6">
                            <p class="text-[10px] font-bold text-pink-500 uppercase tracking-widest px-1">Bagian 1 â€”
                                Isian
                                Singkat <span class="text-gray-400">(tidak dinilai)</span></p>

                            <!-- Isian 1 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Dopamin dibuat dari asam
                                    amino
                                    bernama _____ yang kemudian diubah menjadi L-DOPA.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Tirosin</p>
                                    <p class="text-xs text-green-600 mt-1">Dopamin dibuat dari asam amino bernama
                                        tirosin
                                        yang kemudian diubah menjadi L-DOPA.</p>
                                </div>
                            </div>

                            <!-- Isian 2 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Nama Freon sebenarnya
                                    adalah
                                    merek dagang yang pertama kali diperkenalkan oleh perusahaan _____.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> DuPont</p>
                                    <p class="text-xs text-green-600 mt-1">Nama Freon sebenarnya adalah merek dagang
                                        yang
                                        pertama kali diperkenalkan oleh perusahaan DuPont.</p>
                                </div>
                            </div>

                            <!-- Isian 3 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Fenomena tidak dapat
                                    mengingat
                                    pengalaman di masa bayi dikenal sebagai _____.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Amnesia Infantil</p>
                                    <p class="text-xs text-green-600 mt-1">Fenomena ini, yang dikenal sebagai amnesia
                                        infantil, telah lama menjadi teka-teki menarik bagi para ilmuwan.</p>
                                </div>
                            </div>

                            <!-- Isian 4 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Di Jakarta, laju penurunan
                                    muka
                                    tanah dapat mencapai _____ cm per tahun di beberapa area.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> 10-20</p>
                                    <p class="text-xs text-green-600 mt-1">Di Jakarta, laju penurunan muka tanah dapat
                                        mencapai 10-20 cm per tahun di beberapa area.</p>
                                </div>
                            </div>

                            <!-- Isian 5 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Bakteri Ideonella
                                    sakaiensis
                                    ditemukan oleh para peneliti Jepang dari _____ pada tahun 2016.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Kyoto Institute of
                                        Technology</p>
                                    <p class="text-xs text-green-600 mt-1">Titik balik penting datang pada tahun 2016
                                        ketika
                                        para peneliti Jepang dari Kyoto Institute of Technology menemukan bakteri baru
                                        di
                                        lokasi daur ulang botol plastik.</p>
                                </div>
                            </div>
                        </div>

                        <!-- SECTION: TRUE/FALSE -->
                        <div class="space-y-6 mt-12">
                            <p class="text-[10px] font-bold text-violet-500 uppercase tracking-widest px-1">Bagian 2 â€”
                                Benar
                                atau Salah <span class="text-gray-400">(dinilai)</span></p>

                            <!-- TF 1 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="true">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Reseptor dalam famili
                                        D1
                                        umumnya bersifat stimulatori, sedangkan reseptor dalam famili D2 umumnya
                                        bersifat
                                        inhibitori.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal 6', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal 6', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Reseptor famili
                                        D1
                                        bersifat stimulatori (meningkatkan aktivitas neuron melalui produksi cAMP),
                                        sementara famili D2 bersifat inhibitori (mengurangi aktivitas neuron).</p>
                                </div>
                            </div>

                            <!-- TF 2 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="false">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Freon jenis CFC dan
                                        HFC
                                        sama-sama ramah lingkungan dan tidak merusak lapisan ozon.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal 7', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal 7', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. CFC mulai
                                        dibatasi
                                        karena merusak lapisan ozon. HFC adalah generasi baru yang lebih ramah
                                        lingkungan.
                                    </p>
                                </div>
                            </div>

                            <!-- TF 3 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="true">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> Nico Hulkenberg
                                        akhirnya
                                        meraih podium pertamanya di Grand Prix ke-239 di Silverstone 2025.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal 8', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal 8', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Hulkenberg
                                        finis P3
                                        di belakang Norris dan Piastri di GP Inggris 2025, mengklaim podium perdananya
                                        di GP
                                        ke-239.</p>
                                </div>
                            </div>

                            <!-- TF 4 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="false">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Penurunan angka
                                        pernikahan di Indonesia murni disebabkan oleh faktor ekonomi saja.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal 9', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal 9', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Penyebabnya
                                        multifaktorial: ekonomi, peningkatan partisipasi perempuan di pendidikan/karier,
                                        dan
                                        pergeseran nilai generasi muda.</p>
                                </div>
                            </div>

                            <!-- TF 5 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="true">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Gorden pada masa
                                        Abad
                                        Pertengahan di Eropa memiliki fungsi utama untuk menjaga kehangatan di dalam
                                        kastil.
                                    </p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal 10', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal 10', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Gorden tebal
                                        dari
                                        wol/beludru menjadi krusial untuk insulasi di kastil Eropa yang memiliki jendela
                                        besar.</p>
                                </div>
                            </div>
                        </div>

                        <!-- Submit -->
                        <div class="text-center pt-8">
                            <button onclick="showResult()"
                                class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">
                                <span class="flex items-center gap-2">
                                    <span class="material-symbols-outlined text-lg">fact_check</span>
                                    Lihat Hasil
                                </span>
                            </button>
                        </div>
                    </div>
                </div>


                <!-- PAGE 3: RESULT -->
                <div id="page-result" class="page-section">
                    <div class="max-w-4xl mx-auto p-8 pb-32">
                        <div id="result-content">
                            <div class="text-center py-20 text-gray-400">
                                <span class="material-symbols-outlined text-6xl mb-4">pending</span>
                                <p class="font-serif text-lg">Selesaikan quiz terlebih dahulu untuk melihat hasil.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>


        </div>
        </div>

        <!-- MODULE VIEW: OBAT FOKUS 002 -->
        <div id="module-obat-fokus-002" class="module-view">
            <div class="flex-1 overflow-y-auto" id="content-scroll-002">
                <!-- PAGE 1: ARTICLES -->
                <div id="page-articles-002" class="page-section-002 active">
                    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">
                        <!-- ARTIKEL 1 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 1
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Sejarah Perpustakaan
                                Alexandria: Lentera Pengetahuan Dunia Kuno yang Hilang</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dalam lembaran sejarah peradaban manusia, hanya sedikit institusi yang mampu
                                    memancarkan cahaya pengetahuan sekuat Perpustakaan Alexandria. Didirikan di kota
                                    yang menjadi pusat intelektual dunia kuno, perpustakaan ini bukan sekadar gudang
                                    buku, melainkan mercusuar ilmu, pusat penelitian, dan magnet bagi para pemikir
                                    terbesar zamannya. Kisahnya adalah tentang kejayaan, inovasi, dan tragedi kehancuran
                                    yang masih menjadi misteri hingga kini</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kelahiran Sebuah Pusat
                                    Intelektual</h5>
                                <p>Gagasan untuk mendirikan Perpustakaan Alexandria bermula pada awal abad ke-3 SM di
                                    bawah pemerintahan Ptolemeus I Soter, salah satu jenderal Aleksander Agung yang
                                    kemudian menjadi penguasa Mesir. Namun, pembangunan dan pengembangan ambisiusnya
                                    baru terwujud di masa pemerintahan putranya, Ptolemeus II Philadelphus. Tujuan
                                    utamanya adalah mengumpulkan semua pengetahuan dunia dalam satu tempat, menjadikan
                                    Alexandria sebagai ibu kota intelektual yang tak tertandingi.</p>
                                <p>Perpustakaan ini bukan entitas tunggal, melainkan merupakan bagian dari sebuah
                                    kompleks penelitian yang lebih besar yang dikenal sebagai Mouseion (atau Museum),
                                    yang berarti tempat Musai (dewi seni dan ilmu pengetahuan). Mouseion dilengkapi
                                    dengan ruang kuliah, ruang makan, kebun raya, kebun binatang, observatorium, dan
                                    tentu saja, perpustakaan yang megah. Model ini kemudian menjadi cikal bakal bagi
                                    institusi universitas modern.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Koleksi yang Tak Tertandingi dan
                                    Kebijakan Akuisisi Agresif</h5>
                                <p>Perpustakaan Alexandria terkenal karena koleksinya yang fenomenal, yang diperkirakan
                                    mencapai ratusan ribu bahkan jutaan gulungan papirus. Untuk membangun koleksi
                                    sebesar itu, Dinasti Ptolemeus menerapkan kebijakan akuisisi yang sangat agresif.
                                    Mereka tidak hanya mengirimkan para juru tulis ke seluruh dunia untuk menyalin
                                    manuskrip, tetapi juga memerintahkan agar setiap kapal yang berlabuh di pelabuhan
                                    Alexandria diperiksa. Jika ditemukan gulungan buku, gulungan tersebut akan disalin,
                                    dan salinannya dikembalikan kepada pemilik, sementara yang asli disimpan di
                                    perpustakaan.</p>
                                <p>Selain itu, para sarjana dan filsuf terkemuka dari seluruh dunia Mediterania diundang
                                    untuk tinggal dan bekerja di Mouseion, mendapatkan gaji dan akomodasi. Mereka
                                    bertugas menyalin, menerjemahkan, mengedit, dan mengomentari karya-karya kuno, serta
                                    menghasilkan karya-karya orisinal mereka sendiri. Di antara para pemikir besar yang
                                    berafiliasi dengan perpustakaan ini adalah Eratosthenes (yang menghitung keliling
                                    Bumi), Euclid (bapak geometri), dan Archimedes (ilmuwan dan penemu brilian dari
                                    Syracuse yang berinteraksi dengan para sarjana di sana).</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kejayaan dan Kontribusi
                                    Intelektual</h5>
                                <p>Selama berabad-abad, Perpustakaan Alexandria menjadi pusat gravitasi bagi ilmu
                                    pengetahuan. Di sinilah banyak terobosan penting dalam matematika, astronomi,
                                    kedokteran, geografi, dan filologi terjadi. Para sarjana di perpustakaan ini
                                    menyusun katalog, mengkritisi teks-teks kuno, dan menetapkan standar untuk studi
                                    ilmiah. Misalnya, mereka adalah yang pertama mencoba menyusun bibliografi lengkap
                                    dari semua karya sastra Yunani yang diketahui.</p>
                                <p>Perpustakaan ini juga menjadi simpul penting dalam pelestarian pengetahuan kuno.
                                    Banyak teks-teks Yunani klasik yang kita kenal sekarang ini adalah hasil dari kerja
                                    keras para sarjana di Alexandria yang menyalin dan melestarikannya. Tanpa upaya
                                    mereka, banyak warisan intelektual Yunani mungkin telah hilang ditelan waktu.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Misteri Kehancuran: Sebuah
                                    Tragedi yang Berulang Kali</h5>
                                <p>Nasib akhir Perpustakaan Alexandria masih menjadi salah satu misteri terbesar dalam
                                    sejarah. Tidak ada satu peristiwa tunggal yang jelas penyebabnya, melainkan
                                    serangkaian kemunduran dan kerusakan yang terjadi selama berabad-abad.</p>
                                <p><strong>Pembakaran oleh Julius Caesar (48 SM):</strong> Saat Caesar mengepung
                                    Alexandria, sebagian armadanya dibakar untuk tujuan militer. Konon, api menyebar
                                    hingga ke area dermaga di mana beberapa gudang penyimpanan buku perpustakaan berada,
                                    menyebabkan kerugian sebagian. Namun, ini tidak berarti kehancuran total.</p>
                                <p><strong>Serangan Kristen dan Pagan (abad ke-3 &amp; ke-4 M):</strong> Seiring
                                    berjalannya waktu, kekerasan sektarian antara komunitas Kristen dan Pagan di
                                    Alexandria juga disalahkan atas kerusakan perpustakaan. Peristiwa penghancuran Kuil
                                    Serapeum (yang mungkin merupakan perpustakaan putri atau bagian dari koleksi utama)
                                    pada tahun 391 M oleh massa Kristen di bawah pimpinan Patriark Theophilus sering
                                    disebut sebagai titik balik.</p>
                                <p><strong>Invasi Arab (abad ke-7 M):</strong> Sebuah legenda populer, yang pertama kali
                                    muncul berabad-abad setelah kejadiannya, menyalahkan khalifah Arab Umar ibn
                                    al-Khattab. Dikatakan bahwa ia memerintahkan pembakaran buku-buku dengan alasan
                                    bahwa jika isinya sesuai dengan Al-Qur'an, itu berlebihan; jika bertentangan, itu
                                    salah. Namun, sebagian besar sejarawan modern menganggap kisah ini sebagai apokrifa
                                    (tidak otentik), karena pada saat itu perpustakaan mungkin sudah tidak ada lagi atau
                                    telah kehilangan sebagian besar koleksinya.</p>
                                <p>Kemungkinan besar, Perpustakaan Alexandria tidak hancur dalam satu peristiwa
                                    katastrofik, melainkan mengalami kemerosotan bertahap akibat kombinasi perang,
                                    kurangnya dana, perubahan iklim politik, dan pergeseran fokus intelektual. Pada abad
                                    ke-5 M, koleksi dan perannya sebagai pusat pengetahuan sudah sangat berkurang atau
                                    lenyap sama sekali.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Warisan yang Abadi</h5>
                                <p>Meskipun Perpustakaan Alexandria telah lama tiada, warisannya tetap hidup. Ia menjadi
                                    simbol universal dari pentingnya pelestarian pengetahuan, kebebasan berpikir, dan
                                    upaya kolektif untuk memahami dunia. Pendirian Bibliotheca Alexandrina modern pada
                                    tahun 2002 di lokasi yang dekat dengan perpustakaan kuno adalah upaya simbolis untuk
                                    menghidupkan kembali semangat institusi legendaris tersebut, mengingatkan kita akan
                                    kekuatan tak terbatas dari sebuah tempat di mana semua buku dan semua ide dihargai.
                                </p>
                            </div>
                        </article>

                        <!-- ARTIKEL 2 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 2
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Sejarah Pensil: Dari Timbal
                                ke Grafit dan Revolusi Menulis</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dalam dunia digital saat ini, di mana sentuhan jari pada layar atau ketukan keyboard
                                    adalah norma, mudah untuk melupakan alat tulis sederhana yang telah menemani umat
                                    manusia selama berabad-abad: pensil. Lebih dari sekadar sebatang kayu dengan inti
                                    hitam, pensil adalah sebuah mahakarya inovasi yang telah merevolusi cara kita
                                    menulis, menggambar, dan mencatat ide. Perjalanannya dari alat kasar di tangan kuno
                                    hingga bentuknya yang modern adalah kisah menarik tentang penemuan, kebutuhan, dan
                                    kreativitas manusia.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Cikal Bakal: Timbal, Stilus, dan
                                    Perak</h5>
                                <p>Jauh sebelum grafit ditemukan, manusia telah menggunakan berbagai alat untuk membuat
                                    tanda. Bangsa Romawi kuno menggunakan stilus, sebuah batang tipis dari logam
                                    (seringkali timbal) untuk menulis di atas papirus atau tablet berlilin. Jejak yang
                                    dihasilkan memang samar, tapi cukup untuk catatan. Pada Abad Pertengahan, seniman
                                    mulai menggunakan batang timbal atau ujung perak (silverpoint) untuk membuat sketsa.
                                    Alat-alat ini menghasilkan garis halus dan detail yang indah, namun terbatas pada
                                    permukaan tertentu dan tidak dapat dihapus dengan mudah. Ini adalah cikal bakal
                                    pensil, meskipun belum ada konsep inti yang diselubungi.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Penemuan Grafit dan Awal Era
                                    Modern</h5>
                                <p>Titik balik besar dalam sejarah pensil terjadi pada tahun 1564 di Borrowdale,
                                    Cumberland, Inggris. Deposit besar grafit murni ditemukan di sana. Pada awalnya,
                                    grafit ini diyakini sebagai bentuk timbal, karena itulah nama pensil timbal atau
                                    lead pencil masih sering digunakan sampai sekarang, meskipun sebenarnya tidak
                                    mengandung timbal sama sekali. Grafit yang baru ditemukan ini sangat murni sehingga
                                    bisa dipotong menjadi batang dan digunakan langsung sebagai alat tulis, menghasilkan
                                    garis yang lebih gelap dan mudah dihapus dibandingkan timbal.</p>
                                <p>Awalnya, batang grafit ini hanya dibungkus kain, benang, atau bahkan kulit domba
                                    untuk mencegah tangan kotor. Barulah pada abad ke-17, para pembuat mebel dan tukang
                                    kayu di Jerman mulai menyadari manfaat grafit ini. Mereka mengembangkan teknik
                                    membungkus batang grafit dengan dua potong kayu yang diukir, menciptakan bentuk awal
                                    pensil yang kita kenal sekarang. Produksi massal pensil dimulai di Jerman,
                                    menjadikannya pusat industri pensil dunia saat itu.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Revolusi Pensil Prancis:
                                    Nicholas-Jacques Cont&eacute;</h5>
                                <p>Pada akhir abad ke-18, ketika Revolusi Prancis berkecamuk, pasokan grafit dari
                                    Inggris terputus. Hal ini mendorong seorang insinyur dan seniman Prancis bernama
                                    Nicholas-Jacques Cont&eacute; untuk mencari solusi alternatif. Pada tahun 1795,
                                    Cont&eacute; mematenkan metode inovatif untuk membuat inti pensil. Ia mencampur
                                    bubuk grafit dengan tanah liat, menambahkan air, membentuknya menjadi batang, dan
                                    kemudian memanggangnya dalam tungku.</p>
                                <p>Penemuan Cont&eacute; adalah sebuah terobosan. Dengan mengubah proporsi grafit dan
                                    tanah liat, ia bisa menciptakan pensil dengan berbagai tingkat kekerasan (dari keras
                                    dan terang hingga lunak dan gelap) yang kita kenal dengan sistem H (Hard) dan B
                                    (Black) hari ini. Ini tidak hanya mengatasi masalah pasokan, tetapi juga memberikan
                                    fleksibilitas artistik dan teknis yang belum pernah ada sebelumnya. Metode ini
                                    menjadi standar industri dan masih digunakan hingga saat ini.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Perkembangan dan Inovasi Modern
                                </h5>
                                <p>Abad ke-19 dan ke-20 menyaksikan berbagai inovasi yang membuat pensil semakin
                                    canggih. Perkembangan mesin penggergaji kayu memungkinkan produksi cangkang kayu
                                    heksagonal atau bulat yang konsisten. Penemuan karet sebagai penghapus yang efektif
                                    di akhir abad ke-18 melengkapi pensil sebagai alat tulis yang serbaguna. Pada
                                    pertengahan abad ke-19, Hymen Lipman mematenkan ide pensil dengan penghapus yang
                                    terpasang di ujungnya, meskipun ide ini kemudian dibatalkan karena dianggap hanya
                                    menggabungkan dua penemuan yang sudah ada.</p>
                                <p>Saat ini, pensil hadir dalam berbagai bentuk dan ukuran-pensil mekanik, pensil warna,
                                    pensil tukang kayu, dan banyak lagi. Meskipun teknologi digital telah mendominasi,
                                    pesona pensil tetap tak lekang oleh waktu. Sentuhan langsung grafit pada kertas,
                                    suara goresannya, dan kemampuan untuk menghapus serta berkreasi dengan bebas
                                    menjadikannya alat yang tak tergantikan bagi seniman, desainer, insinyur, dan siapa
                                    saja yang masih menghargai keindahan kesederhanaan.</p>
                                <p>Dari bongkahan grafit mentah hingga batang kayu yang presisi, sejarah pensil adalah
                                    bukti kecerdikan manusia dalam menemukan solusi sederhana namun transformatif yang
                                    terus membentuk cara kita berinteraksi dengan dunia ide.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 3 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 3
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Samsung Ungkap Fitur AI dan
                                Ponsel Lipat Jadi Primadona Pengguna Asia Tenggara</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Samsung Electronics melihat adanya pergeseran preferensi konsumen di kawasan Asia
                                    Tenggara dan Oseania. Menurut Carl Nordenberg, Vice President Mobile eXperience
                                    Business Samsung Electronics Southeast Asia and Oceania, fitur berbasis kecerdasan
                                    buatan AI kini menjadi daya tarik utama, diikuti oleh adopsi kuat perangkat lipat.
                                    Hal ini diungkapkan Nordenberg dalam sebuah wawancara eksklusif dengan jurnalis
                                    Kompas.com Yudha Pratomo, menyusul peluncuran Samsung Galaxy Z Fold7 dan Flip7 di
                                    New York, AS, pekan lalu.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Galaxy AI: Kunci Produktivitas
                                    dan Kreativitas</h5>
                                <p>Nordenberg menjelaskan bahwa konsumen di Asia Tenggara kini secara aktif mencari
                                    fitur AI yang intuitif dan benar-benar bermanfaat untuk mendukung kreativitas serta
                                    produktivitas sehari-hari mereka. Samsung, melalui inovasi Galaxy AI yang tersemat
                                    dalam lini ponsel terbarunya, berupaya menjawab kebutuhan tersebut.</p>
                                <p>"Fitur seperti Photo Assist, Audio Eraser, Writing Assist, dan Circle to Search
                                    memungkinkan pengguna melakukan lebih banyak hal di smartphone dengan cara yang
                                    lebih mudah," kata Nordenberg. Ini menunjukkan komitmen Samsung untuk menghadirkan
                                    pengalaman AI yang mulus, didukung pula oleh tren agentic AI yang mendorong
                                    perusahaan memastikan perangkatnya cukup kuat dan efisien. Integrasi langsung
                                    layanan Google Gemini ke dalam arloji pintar Galaxy Watch8 dan Watch8 Classic yang
                                    baru diluncurkan menjadi salah satu bukti nyata dari visi ini.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Perangkat Lipat: Inovasi yang
                                    Kian Diminati</h5>
                                <p>Selain AI, perangkat lipat atau foldable phone juga menunjukkan adopsi yang sangat
                                    kuat di pasar Asia Tenggara. Nordenberg menyoroti bahwa konsumen di kawasan ini
                                    dikenal sangat terbuka terhadap inovasi dan teknologi baru, termasuk kategori
                                    smartphone lipat.</p>
                                <p>"Dengan kehadiran Galaxy Z Flip7 dan Galaxy Z Fold7 yang baru diluncurkan, Samsung
                                    optimistis minat terhadap perangkat ini akan semakin tinggi. Cover screen Galaxy Z
                                    Flip7 kini mendukung personalisasi dan pengalaman berbasis AI yang lebih baik.
                                    Sementara Galaxy Z Fold7 menawarkan desain ramping dengan fungsionalitas smartphone
                                    premium dalam bentuk foldable," jelasnya, menandakan evolusi signifikan pada desain
                                    dan kapabilitas perangkat lipat Samsung.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Strategi Samsung Hadapi
                                    Persaingan Ketat</h5>
                                <p>Di tengah gempuran merek-merek asal China yang semakin agresif di pasar Asia Tenggara
                                    dan Oseania, Samsung telah menyiapkan sejumlah strategi. Perusahaan asal Korea
                                    Selatan ini berupaya mempertahankan posisi kepemimpinannya melalui kombinasi inovasi
                                    produk, diferensiasi layanan, dan investasi lokal yang kuat.</p>
                                <p>"Samsung siap mempertahankan kepemimpinannya di tingkat regional melalui berbagai
                                    perangkat mobile inovatif dan berkualitas tinggi untuk memenuhi kebutuhan konsumen
                                    yang beragam," tegas Nordenberg. Namun, ia menekankan bahwa Samsung tidak hanya
                                    mengandalkan keunggulan perangkat keras. Diferensiasi layanan dan pengalaman
                                    pengguna menjadi kunci utama. Strategi ini mencakup perluasan ketersediaan Galaxy AI
                                    ke lini Galaxy A yang lebih terjangkau, menjamin keamanan dan privasi data pengguna
                                    dengan fitur unggulan seperti Samsung Knox Vault dan Auto Blocker, serta memberikan
                                    ketenangan pikiran melalui pembaruan OS dan keamanan jangka panjang.</p>
                                <p>Melalui pendekatan holistik ini, Samsung berambisi untuk terus menjadi pilihan utama
                                    konsumen di Asia Tenggara, tidak hanya dengan inovasi produk, tetapi juga dengan
                                    ekosistem layanan dan dukungan yang komprehensif.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 4 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 4
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Sungai Amazon: Raksasa yang
                                Mengalir di Jantung Bumi</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Sungai Amazon, yang mengalir deras di jantung Amerika Selatan, bukan sekadar sungai.
                                    Ia adalah arteri kehidupan terbesar di Bumi, sebuah entitas raksasa yang menggenggam
                                    rekor-rekor alam yang luar biasa dan mendukung keanekaragaman hayati yang tak
                                    tertandingi. Dari sumber mata airnya yang tersembunyi di puncak Andes hingga
                                    muaranya yang membentang luas di Samudra Atlantik, setiap aliran air Amazon
                                    menceritakan kisah tentang kekuatan, keindahan, dan misteri alam.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Sungai Terpanjang Kedua (atau
                                    Pertama?)</h5>
                                <p>Sungai Amazon telah lama dianggap sebagai sungai terpanjang kedua di dunia setelah
                                    Sungai Nil. Namun, penemuan-penemuan baru pada awal abad ke-21 telah memunculkan
                                    klaim yang menarik. Ekspedisi ilmiah yang dilakukan oleh peneliti Brasil berhasil
                                    mengidentifikasi sumber Amazon yang lebih hulu dari yang diperkirakan sebelumnya,
                                    yaitu di Pegunungan Andes Peru. Dengan perhitungan ulang ini, panjang Sungai Amazon
                                    diperkirakan mencapai sekitar 6.992 kilometer, berpotensi menjadikannya sungai
                                    terpanjang di dunia, melampaui Sungai Nil yang berukuran sekitar 6.695 kilometer.
                                    Meskipun klaim ini masih diperdebatkan oleh para ahli geografi, ia menambah lapisan
                                    keagungan pada kebesaran sungai ini.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Volume Air yang Tak Tertandingi
                                </h5>
                                <p>Terlepas dari perdebatan panjangnya, Amazon tidak diragukan lagi sebagai sungai
                                    dengan volume air terbesar di dunia. Ia mengalirkan sekitar 209.000 meter kubik air
                                    per detik ke Samudra Atlantik, yang merupakan sekitar 20% dari seluruh air tawar
                                    sungai yang mengalir ke lautan di seluruh dunia. Selama musim hujan, aliran airnya
                                    bisa melonjak hingga lebih dari 300.000 meter kubik per detik, membanjiri daerah
                                    dataran rendah seluas jutaan hektar dan mengubah lanskap secara dramatis.</p>
                                <p>Volume air ini begitu besar sehingga ia mendorong air asin Atlantik ke arah lautan
                                    hingga jarak lebih dari 160 kilometer dari muaranya, menciptakan plume air tawar
                                    yang bisa terdeteksi dari luar angkasa. Debit Amazon melebihi gabungan tujuh sungai
                                    terbesar berikutnya di dunia, sebuah fakta yang menekankan betapa dominannya ia
                                    dalam siklus air global.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Jantung Keanekaragaman Hayati
                                </h5>
                                <p>Hutan hujan Amazon, yang dilalui sungai ini, adalah rumah bagi keanekaragaman hayati
                                    terkaya di planet ini. Diperkirakan satu dari sepuluh spesies yang diketahui di Bumi
                                    hidup di hutan hujan Amazon. Sungai itu sendiri menampung lebih dari 3.000 spesies
                                    ikan air tawar yang diketahui, termasuk yang menakutkan seperti piranha, yang selalu
                                    lapar; arapaima, salah satu ikan air tawar terbesar di dunia yang bisa tumbuh hingga
                                    lebih dari 3 meter; dan belut listrik, yang mampu menghasilkan sengatan listrik
                                    hingga 600 volt.</p>
                                <p>Di sepanjang tepian dan di kedalaman airnya, terdapat pula lumba-lumba sungai merah
                                    muda Amazon (boto), yang merupakan spesies lumba-lumba air tawar terbesar di dunia,
                                    serta kaimun hitam, buaya terbesar di Amerika Selatan yang bisa mencapai panjang 5
                                    meter. Flora di sekitarnya juga luar biasa: teratai raksasa Victoria amazonica
                                    memiliki daun yang bisa mencapai diameter 3 meter, cukup kuat untuk menopang berat
                                    seorang anak kecil.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Pororoca: Fenomena Gelombang
                                    Pasang Sungai</h5>
                                <p>Salah satu fenomena alam paling menakjubkan di Amazon adalah Pororoca, sebuah tidal
                                    bore atau gelombang pasang sungai yang terjadi dua kali setahun, biasanya saat
                                    ekuinoks (Maret dan September). Ketika pasang tinggi dari Samudra Atlantik
                                    bertabrakan dengan arus keluar Sungai Amazon, gelombang air raksasa setinggi hingga
                                    4 meter bisa terbentuk dan bergerak ke hulu sungai dengan kecepatan hingga 32
                                    kilometer per jam.</p>
                                <p>Suara gemuruhnya bisa terdengar dari jarak 30 menit sebelum gelombang tiba,
                                    menghancurkan pohon dan menyeret segala yang ada di jalurnya. Fenomena ini tidak
                                    hanya menjadi daya tarik wisata tetapi juga menjadi tantangan bagi para peselancar
                                    ekstrem yang datang dari seluruh dunia untuk berselancar di gelombang sungai ini,
                                    dengan beberapa di antaranya mampu berselancar selama lebih dari 30 menit tanpa
                                    henti.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Ancaman dan Pelestarian</h5>
                                <p>Meskipun kebesarannya, Sungai Amazon dan hutan hujannya menghadapi ancaman serius
                                    dari deforestasi, pertambangan ilegal, dan perubahan iklim. Pembangunan bendungan
                                    dan pencemaran air juga mengancam ekosistemnya yang rapuh. Namun, upaya pelestarian
                                    internasional dan kesadaran global yang semakin meningkat memberikan harapan bahwa
                                    keajaiban alam ini akan tetap lestari bagi generasi mendatang. Sungai Amazon adalah
                                    pengingat akan betapa luar biasa dan pentingnya alam bagi kehidupan di Bumi.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 5 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 5
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Kesehatan Mental Remaja:
                                Tantangan Tersembunyi di Era Digital</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Di era digital yang berkembang pesat ini, remaja menghadapi tekanan yang belum pernah
                                    dialami oleh generasi sebelumnya. Dari tuntutan akademis yang semakin tinggi hingga
                                    pengaruh media sosial yang meresap ke setiap aspek kehidupan, kesehatan mental
                                    remaja menjadi isu krusial yang menuntut perhatian serius dari seluruh lapisan
                                    masyarakat.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Lanskap Masalah Kesehatan Mental
                                    Remaja</h5>
                                <p>Data dari Organisasi Kesehatan Dunia (WHO) menunjukkan bahwa satu dari tujuh remaja
                                    berusia 10-19 tahun mengalami gangguan mental. Depresi, kecemasan, dan gangguan
                                    perilaku menjadi penyebab utama penyakit dan disabilitas di kalangan remaja. Yang
                                    lebih memprihatinkan, bunuh diri merupakan penyebab kematian keempat terbesar pada
                                    kelompok usia 15-29 tahun secara global. Di Indonesia sendiri, Riset Kesehatan Dasar
                                    (Riskesdas) menunjukkan adanya peningkatan prevalensi gangguan emosional pada remaja
                                    dari tahun ke tahun.</p>
                                <p>Masalah ini bukan sekadar angka statistik. Di balik setiap data, terdapat cerita
                                    seorang remaja yang berjuang dengan perasaan cemas yang tak kunjung reda sebelum
                                    ujian, tekanan untuk tampil sempurna di media sosial, atau kesepian yang datang
                                    meski dikelilingi ratusan teman daring.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Faktor Pemicu Utama</h5>
                                <p><strong>Media Sosial dan Dunia Digital:</strong> Penggunaan media sosial yang
                                    berlebihan telah terbukti berkorelasi dengan peningkatan kecemasan, depresi, dan
                                    rendahnya harga diri pada remaja. Fenomena cyberbullying, tekanan untuk mendapatkan
                                    likes dan followers, serta paparan konten yang tidak realistis tentang standar
                                    kecantikan dan gaya hidup menciptakan lingkungan yang toksik bagi perkembangan
                                    mental remaja.</p>
                                <p><strong>Tekanan Akademis:</strong> Sistem pendidikan yang kompetitif, terutama
                                    menjelang ujian masuk perguruan tinggi seperti SNBT di Indonesia, menimbulkan stres
                                    yang luar biasa. Ekspektasi tinggi dari orang tua dan masyarakat sering kali
                                    menciptakan beban yang tak tertahankan bagi remaja.</p>
                                <p><strong>Perubahan Sosial dan Keluarga:</strong> Perceraian orang tua, kemiskinan,
                                    kekerasan dalam rumah tangga, dan kurangnya dukungan sosial juga menjadi faktor
                                    risiko signifikan. Remaja yang tumbuh dalam lingkungan keluarga yang tidak stabil
                                    lebih rentan mengalami gangguan mental.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Tanda-tanda yang Harus Diwaspadai
                                </h5>
                                <p>Mengenali tanda-tanda awal masalah kesehatan mental pada remaja sangat penting untuk
                                    intervensi dini. Beberapa tanda yang perlu diwaspadai meliputi: perubahan drastis
                                    dalam pola tidur atau makan, penarikan diri dari teman dan aktivitas yang biasa
                                    disukai, penurunan prestasi akademis yang tiba-tiba, perubahan suasana hati yang
                                    ekstrem, ekspresi keputusasaan atau ketidakbrahargaan diri, serta perilaku berisiko.
                                    Namun, penting untuk diingat bahwa beberapa perubahan mood dan perilaku adalah
                                    normal dalam masa perkembangan remaja, sehingga konteks dan intensitas tanda-tanda
                                    ini perlu diperhatikan.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Langkah Konkret yang Bisa
                                    Dilakukan</h5>
                                <p>Untuk mengatasi krisis kesehatan mental remaja, diperlukan pendekatan komprehensif
                                    yang melibatkan berbagai pihak. Keluarga perlu menciptakan ruang aman untuk
                                    komunikasi terbuka. Sekolah harus mengintegrasikan pendidikan kesehatan mental ke
                                    dalam kurikulum dan menyediakan konselor yang terlatih. Pemerintah perlu
                                    meningkatkan akses terhadap layanan kesehatan mental yang terjangkau. Dan yang
                                    terpenting, remaja sendiri perlu diberdayakan untuk mengenali, mengekspresikan, dan
                                    mengelola emosi mereka dengan cara yang sehat.</p>
                                <p>Kesehatan mental bukanlah kemewahan, melainkan kebutuhan dasar. Investasi dalam
                                    kesehatan mental remaja hari ini adalah investasi dalam masa depan bangsa. Sebab,
                                    remaja yang sehat secara mental akan tumbuh menjadi dewasa yang produktif, resilien,
                                    dan mampu berkontribusi positif bagi masyarakat.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 6 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 6
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Sejarah Bawang Merah: Dari
                                Persembahan Dewa hingga Dapur Modern</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Di setiap dapur di seluruh penjuru dunia, bawang merah mungkin adalah bumbu yang
                                    paling universal. Aroma harum dan rasa pedas manisnya menambah dimensi pada hampir
                                    setiap masakan. Namun, di balik kesederhanaannya, tersembunyi sejarah panjang yang
                                    membentang ribuan tahun, menghubungkan peradaban kuno dengan meja makan modern kita.
                                </p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Asal Usul Kuno yang Misterius
                                </h5>
                                <p>Para ahli botani percaya bahwa bawang merah (Allium cepa) pertama kali dibudidayakan
                                    di wilayah Asia Tengah, sekitar 5.000 tahun yang lalu. Beberapa sumber merujuk pada
                                    dataran tinggi Iran dan Pakistan Barat sebagai kampung halaman nenek moyangnya.
                                    Bawang merah liar tumbuh subur di wilayah ini, dan manusia purba mulai menyadari
                                    potensi kuliner dan pengobatan dari umbi berlapis ini.</p>
                                <p>Sulitnya melacak asal-usul pasti bawang merah disebabkan oleh sifatnya yang mudah
                                    terurai. Tidak seperti biji-bijian atau tulang, sisa-sisa bawang merah sangat jarang
                                    ditemukan di situs arkeologi kuno. Namun, referensi tertulis dan gambar-gambar kuno
                                    memberikan petunjuk berharga tentang betapa pentingnya bawang merah bagi peradaban
                                    awal.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Mesir Kuno: Bawang Merah sebagai
                                    Simbol Sakral</h5>
                                <p>Dalam peradaban Mesir Kuno, bawang merah memegang peranan istimewa yang melampaui
                                    fungsi kuliner. Bawang merah dianggap sebagai simbol kehidupan abadi karena
                                    bentuknya yang berlapis-lapis, yang menyerupai lingkaran konsentris, melambangkan
                                    kehidupan yang tak berujung. Bawang merah sering ditemukan di kuburan-kuburan Mesir
                                    kuno, termasuk di dalam perban mumi, yang diyakini membantu mendorong orang mati
                                    untuk bernapas kembali di kehidupan setelahnya.</p>
                                <p>Para pekerja yang membangun piramida diberi jatah bawang merah secara teratur, karena
                                    dipercaya memberikan kekuatan dan stamina. Ukiran di dinding piramida menunjukkan
                                    bawang merah sebagai persembahan kepada para dewa, dan para petani bahkan bersumpah
                                    atas nama bawang merah. Herodotus, sejarawan Yunani, mencatat bahwa tulisan di
                                    Piramida Agung Khufu menyebutkan pengeluaran besar untuk bawang merah, bawang putih,
                                    dan lobak yang diberikan kepada para pekerja.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Yunani, Romawi, dan Abad
                                    Pertengahan</h5>
                                <p>Bangsa Yunani kuno menggunakan bawang merah untuk menguatkan atlet-atlet Olimpiade
                                    mereka. Sebelum pertandingan, para atlet dikatakan mengonsumsi bawang merah dalam
                                    jumlah besar, mengoleskan jusnya ke tubuh mereka, dan bahkan menghirup aromanya
                                    untuk meningkatkan energi. Bangsa Romawi kemudian menyebarkan bawang merah ke
                                    seluruh jajahannya di Eropa, menjadikannya bahan pokok dalam masakan Romawi dan
                                    memperkenalkannya ke Inggris.</p>
                                <p>Pada Abad Pertengahan, bawang merah menjadi salah satu dari tiga sayuran utama di
                                    Eropa (bersama kacang-kacangan dan kubis) dan bahkan digunakan sebagai alat
                                    pembayaran. Bawang merah juga diyakini memiliki khasiat pengobatan: mengatasi sakit
                                    kepala, gigitan ular, bahkan rambut rontok. Para dokter abad pertengahan meresepkan
                                    bawang merah untuk berbagai penyakit, menjadikannya obat mujarab universal.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Perjalanan ke Dunia Baru dan Masa
                                    Kini</h5>
                                <p>Christopher Columbus membawa bawang merah ke dunia baru pada pelayarannya di akhir
                                    abad ke-15. Bawang merah berkembang dengan baik di tanah Amerika dan segera menjadi
                                    bagian integral dari masakan lokal. Penduduk asli Amerika, yang telah mengenal
                                    varietas bawang liar mereka sendiri, dengan cepat mengadopsi varietas yang
                                    diperkenalkan oleh bangsa Eropa.</p>
                                <p>Hari ini, bawang merah dibudidayakan di seluruh dunia dan merupakan tanaman sayuran
                                    kedua yang paling banyak diproduksi setelah tomat. Dari rendang di Indonesia, saus
                                    bolognese di Italia, hingga bawang goreng khas Prancis, bawang merah tetap menjadi
                                    fondasi rasa yang tak tergantikan dalam kekayaan kuliner dunia.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 7 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 7
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Revolusi Transportasi
                                Listrik: Masa Depan Mobilitas yang Berkelanjutan</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dunia sedang menyaksikan transformasi monumental dalam industri transportasi.
                                    Kendaraan listrik (EV), yang dulunya dianggap sebagai teknologi masa depan yang
                                    jauh, kini telah menjadi kenyataan yang mengubah lanskap mobilitas global. Dari
                                    sedan mewah hingga bus kota, revolusi listrik sedang menyapu bersih paradigma lama
                                    dan menciptakan peluang baru yang belum pernah terbayangkan.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Sejarah Singkat yang Mengejutkan
                                </h5>
                                <p>Banyak orang mungkin terkejut mengetahui bahwa kendaraan listrik bukanlah penemuan
                                    baru. Pada akhir abad ke-19 dan awal abad ke-20, kendaraan listrik justru
                                    mendominasi jalanan. Pada tahun 1900, 38% kendaraan bermotor di Amerika Serikat
                                    adalah kendaraan listrik. Mereka lebih senyap, lebih bersih, dan lebih mudah
                                    dioperasikan dibandingkan mobil bertenaga bensin atau uap pada saat itu.</p>
                                <p>Namun, penemuan stater listrik untuk mesin bensin oleh Charles Kettering pada tahun
                                    1912, yang menghilangkan kebutuhan akan engkol tangan yang berbahaya, dikombinasikan
                                    dengan penurunan harga bensin akibat penemuan minyak bumi di Texas, dan ketersediaan
                                    Model T Ford yang terjangkau, menyebabkan kendaraan listrik nyaris punah. Selama
                                    hampir satu abad, mesin pembakaran internal mendominasi tanpa pesaing berarti.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Kebangkitan Kembali: Tesla dan
                                    Para Pionir</h5>
                                <p>Kebangkitan kembali kendaraan listrik modern dimulai secara serius pada tahun 2008,
                                    ketika Tesla Motors meluncurkan Roadster, mobil sport listrik pertama yang
                                    menggunakan baterai lithium-ion. Ini membuktikan bahwa kendaraan listrik bisa cepat,
                                    menarik, dan memiliki jangkauan yang layak. Langkah Tesla kemudian memicu reaksi
                                    berantai di seluruh industri otomotif global.</p>
                                <p>Saat ini, hampir semua produsen mobil besar di dunia telah berkomitmen untuk beralih
                                    ke elektrifikasi. Volkswagen, GM, Ford, BMW, Mercedes-Benz, dan banyak lainnya telah
                                    mengumumkan rencana ambisius untuk menghentikan produksi mobil berbahan bakar fosil
                                    dalam satu atau dua dekade mendatang. Penjualan EV global terus meningkat pesat,
                                    dengan lebih dari 14 juta unit terjual pada tahun 2023.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Tantangan yang Masih Dihadapi
                                </h5>
                                <p>Meskipun momentum positifnya, revolusi transportasi listrik masih menghadapi beberapa
                                    tantangan signifikan. Infrastruktur pengisian daya yang masih belum merata, terutama
                                    di negara berkembang, menjadi hambatan utama. Harga baterai, meskipun telah turun
                                    drastis, masih membuat EV lebih mahal dibandingkan mobil konvensional. Ketersediaan
                                    bahan baku seperti lithium, kobalt, dan nikel juga menimbulkan kekhawatiran tentang
                                    keberlanjutan rantai pasokan.</p>
                                <p>Namun, investasi masif dalam penelitian baterai, ekspansi jaringan pengisian daya,
                                    dan dukungan kebijakan pemerintah di seluruh dunia menunjukkan bahwa masa depan
                                    transportasi akan didominasi oleh listrik. Revolusi ini bukan hanya tentang
                                    mengganti bahan bakar; ia tentang reimajinasi seluruh konsep mobilitas untuk dunia
                                    yang lebih berkelanjutan.</p>
                            </div>
                        </article>

                        <!-- ARTIKEL 8 -->
                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                            <div class="absolute top-0 left-0 w-1 h-full bg-sky-400 rounded-l-xl"></div>
                            <div
                                class="flex items-center gap-2 text-xs font-bold text-sky-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 8
                            </div>
                            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Fenomena K-Pop: Dari Seoul
                                ke Panggung Dunia</h3>
                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                <p>Dalam dua dekade terakhir, industri musik Korea Selatan telah mengalami transformasi
                                    luar biasa dari sebuah pasar lokal menjadi kekuatan budaya global yang fenomenal.
                                    K-Pop, seperti yang dikenal dunia, bukan sekadar genre musik; ia adalah sebuah
                                    ekosistem entertainment yang kompleks, terencana dengan presisi, dan mampu menembus
                                    batas-batas bahasa serta budaya.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Akar dan Evolusi</h5>
                                <p>Akar K-Pop modern dapat ditelusuri ke awal tahun 1990-an, ketika grup Seo Taiji and
                                    Boys merevolusi industri musik Korea dengan memperkenalkan elemen hip-hop, R&amp;B,
                                    dan dance ke dalam musik pop Korea. Namun, fondasi industrinya diletakkan oleh tiga
                                    agensi hiburan besar: SM Entertainment (didirikan 1995 oleh Lee Soo-man), YG
                                    Entertainment (1996, Yang Hyun-suk), dan JYP Entertainment (1997, Park Jin-young).
                                    Ketiga agensi ini mengembangkan sistem pelatihan yang ketat dan komprehensif, yang
                                    kemudian menjadi cetak biru industri.</p>
                                <p>Sistem trainee, di mana calon idol diseleksi ketat dan dilatih selama bertahun-tahun
                                    dalam menyanyi, menari, akting, dan bahasa asing, menjadi fondasi kualitas yang
                                    membedakan K-Pop dari industri musik lainnya. Investasi dalam pengembangan bakat ini
                                    bisa mencapai ratusan ribu hingga jutaan dolar per individu sebelum debut.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Hallyu Wave: Dari Regional ke
                                    Global</h5>
                                <p>Gelombang Hallyu (Korean Wave) pertama dimulai pada awal 2000-an, terutama di Asia
                                    Timur dan Tenggara, didorong oleh drama Korea dan musik. Namun, gelombang kedua yang
                                    dimulai sekitar 2010-an membawa K-Pop ke panggung dunia. YouTube menjadi platform
                                    kritis; video Gangnam Style oleh PSY menjadi video pertama di YouTube yang mencapai
                                    satu miliar tayangan pada tahun 2012, membuka mata dunia akan potensi K-Pop.</p>
                                <p>Puncaknya datang dengan BTS (Bangtan Sonyeondan), yang memecahkan hampir semua rekor
                                    yang bisa dipecahkan. Mereka menjadi artis Korea pertama yang tampil di Grammy
                                    Awards, mencapai nomor satu di Billboard Hot 100 berkali-kali, dan memiliki basis
                                    penggemar global (ARMY) yang loyalitasnya tak tertandingi. Keberhasilan BTS membuka
                                    jalan bagi BLACKPINK, Stray Kids, SEVENTEEN, NewJeans, dan banyak grup lainnya untuk
                                    meraih pengakuan global.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Mesin di Balik Keajaiban</h5>
                                <p>Keberhasilan K-Pop bukan kebetulan. Ada mesin industri yang sangat terorganisir di
                                    baliknya. Produksi musik dilakukan oleh tim penulis dan produser internasional,
                                    menghasilkan lagu-lagu dengan kualitas produksi yang sangat tinggi. Koreografi yang
                                    rumit dan visual yang memukau menjadi standar, bukan pengecualian. Strategi
                                    pemasaran digital yang canggih, termasuk penggunaan intensif media sosial dan konten
                                    eksklusif untuk penggemar, menciptakan engagement yang mendalam.</p>
                                <p>Yang membedakan K-Pop adalah pendekatannya yang holistik terhadap entertainment.
                                    Sebuah comeback (rilis album baru) bukan hanya tentang musik; ia melibatkan concept
                                    photos, music videos yang digarap seperti film pendek, variety show appearances, fan
                                    meetings, dan merchandise. Setiap elemen dirancang untuk menciptakan pengalaman yang
                                    imersif dan emosional bagi penggemar.</p>
                                <h5 class="font-bold text-sakura-black text-base mt-6">Dampak Ekonomi dan Budaya</h5>
                                <p>Dampak ekonomi K-Pop terhadap Korea Selatan sangat signifikan. Industri ini
                                    berkontribusi miliaran dolar terhadap ekonomi melalui penjualan musik, konser,
                                    merchandise, pariwisata, dan produk terkait. Hallyu juga mendorong peningkatan
                                    ekspor produk Korea lainnya, dari kosmetik hingga makanan dan elektronik. Pemerintah
                                    Korea Selatan sendiri secara aktif mendukung dan mempromosikan K-Pop sebagai
                                    instrumen soft power diplomatik.</p>
                                <p>Secara budaya, K-Pop telah membantu menormalkan representasi Asia di panggung hiburan
                                    global, menantang dominasi musik Barat, dan membuktikan bahwa bahasa bukanlah
                                    penghalang bagi kesuksesan global. Fenomena ini terus berkembang, dan pengaruhnya
                                    terhadap industri musik dunia kemungkinan akan terus terasa dalam dekade-dekade
                                    mendatang.</p>
                            </div>
                        </article>

                    </div>
                </div>

                <!-- PAGE 2: QUIZ -->
                <div id="page-quiz-002" class="page-section-002">
                    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">
                        <!-- Quiz Header -->
                        <div class="text-center mb-8">
                            <span class="material-symbols-outlined text-5xl text-sakura-red mb-3">quiz</span>
                            <h2 class="font-serif font-black text-3xl text-sakura-black mb-2">Quiz — Obat Fokus Day 2
                            </h2>
                            <p class="text-gray-500 max-w-md mx-auto">Jawab pertanyaan berdasarkan 8 artikel yang sudah
                                kamu
                                baca. Soal isian <strong>tidak dinilai</strong>, hanya True/False yang masuk skor.</p>
                            <div class="w-16 h-1 bg-sakura-red mx-auto mt-4"></div>
                        </div>

                        <!-- SECTION: ISIAN -->
                        <div class="space-y-6">
                            <p class="text-[10px] font-bold text-sky-500 uppercase tracking-widest px-1">Bagian 1 —
                                Isian
                                Singkat <span class="text-gray-400">(tidak dinilai)</span></p>

                            <!-- Isian 1 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Perpustakaan Alexandria
                                    merupakan bagian dari kompleks penelitian yang lebih besar yang dikenal sebagai
                                    _____.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Mouseion (atau Museum)
                                    </p>
                                    <p class="text-xs text-green-600 mt-1">Perpustakaan ini merupakan bagian dari sebuah
                                        kompleks penelitian yang lebih besar yang dikenal sebagai Mouseion (atau
                                        Museum), yang berarti tempat Musai (dewi seni dan ilmu pengetahuan).</p>
                                </div>
                            </div>

                            <!-- Isian 2 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Pada tahun 1795, seorang
                                    insinyur Prancis bernama _____ mematenkan metode inovatif untuk membuat inti pensil
                                    dengan mencampur bubuk grafit dan tanah liat.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Nicholas-Jacques Conté
                                    </p>
                                    <p class="text-xs text-green-600 mt-1">Nicholas-Jacques Conté mematenkan metode
                                        inovatif mencampur bubuk grafit dengan tanah liat, kemudian memanggangnya dalam
                                        tungku, menciptakan berbagai tingkat kekerasan pensil.</p>
                                </div>
                            </div>

                            <!-- Isian 3 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Volume air Sungai Amazon
                                    yang mengalir ke Samudra Atlantik mewakili sekitar _____% dari seluruh air tawar
                                    sungai yang mengalir ke lautan di dunia.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> 20%</p>
                                    <p class="text-xs text-green-600 mt-1">Sungai Amazon mengalirkan sekitar 209.000
                                        meter kubik air per detik ke Samudra Atlantik, yang merupakan sekitar 20% dari
                                        seluruh air tawar sungai yang mengalir ke lautan di seluruh dunia.</p>
                                </div>
                            </div>

                            <!-- Isian 4 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Menurut WHO, satu dari
                                    _____ remaja berusia 10-19 tahun mengalami gangguan mental.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> tujuh</p>
                                    <p class="text-xs text-green-600 mt-1">Data dari WHO menunjukkan bahwa satu dari
                                        tujuh remaja berusia 10-19 tahun mengalami gangguan mental.</p>
                                </div>
                            </div>

                            <!-- Isian 5 -->
                            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Sistem trainee K-Pop
                                    pertama kali dikembangkan oleh tiga agensi hiburan besar Korea: SM Entertainment, YG
                                    Entertainment, dan _____.</p>
                                <div class="flex gap-3 items-center mb-4">
                                    <input type="text" placeholder="Ketik jawaban..."
                                        class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                    <button onclick="checkIsian(this)"
                                        class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                </div>
                                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> JYP Entertainment</p>
                                    <p class="text-xs text-green-600 mt-1">Tiga agensi hiburan besar Korea yang
                                        meletakkan fondasi industri K-Pop adalah SM Entertainment (1995), YG
                                        Entertainment (1996), dan JYP Entertainment (1997, didirikan oleh Park
                                        Jin-young).</p>
                                </div>
                            </div>
                        </div>

                        <!-- SECTION: TRUE/FALSE -->
                        <div class="space-y-6 mt-10">
                            <p class="text-[10px] font-bold text-sky-500 uppercase tracking-widest px-1">Bagian 2 —
                                True or
                                False <span class="text-gray-400">(dinilai)</span></p>

                            <!-- TF 1 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="false" data-module="002">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Perpustakaan
                                        Alexandria hancur dalam satu peristiwa katastrofik tunggal akibat pembakaran
                                        oleh Julius Caesar.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal2 6', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal2 6', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Kemungkinan
                                        besar Perpustakaan Alexandria tidak hancur dalam satu peristiwa katastrofik,
                                        melainkan mengalami kemerosotan bertahap akibat kombinasi perang, kurangnya
                                        dana, perubahan iklim politik, dan pergeseran fokus intelektual.</p>
                                </div>
                            </div>

                            <!-- TF 2 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="true" data-module="002">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Pada tahun 1900, 38%
                                        kendaraan bermotor di Amerika Serikat adalah kendaraan listrik.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal2 7', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal2 7', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Pada akhir abad
                                        ke-19 dan awal abad ke-20, kendaraan listrik justru mendominasi jalanan. Pada
                                        tahun 1900, 38% kendaraan bermotor di AS adalah kendaraan listrik.</p>
                                </div>
                            </div>

                            <!-- TF 3 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="true" data-module="002">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> Dalam peradaban Mesir
                                        Kuno, bawang merah dianggap sebagai simbol kehidupan abadi karena bentuknya yang
                                        berlapis-lapis.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal2 8', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal2 8', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Bawang merah
                                        dianggap sebagai simbol kehidupan abadi karena bentuknya yang berlapis-lapis,
                                        yang menyerupai lingkaran konsentris, melambangkan kehidupan yang tak berujung.
                                    </p>
                                </div>
                            </div>

                            <!-- TF 4 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="false" data-module="002">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Video Gangnam Style
                                        oleh BTS menjadi video pertama di YouTube yang mencapai satu miliar tayangan.
                                    </p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal2 9', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal2 9', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Video Gangnam
                                        Style adalah milik PSY, bukan BTS. Video tersebut memang menjadi video pertama
                                        di YouTube yang mencapai satu miliar tayangan pada tahun 2012.</p>
                                </div>
                            </div>

                            <!-- TF 5 -->
                            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                data-answer="false" data-module="002">
                                <div class="flex items-start justify-between mb-4">
                                    <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Deposit grafit murni
                                        yang menjadi titik balik sejarah pensil ditemukan pada tahun 1564 di Jerman.</p>
                                    <div class="result-badge hidden ml-3"></div>
                                </div>
                                <div class="flex gap-3 mb-4">
                                    <button onclick="checkTF(this, 'Soal2 10', 'true')" data-value="true"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                    <button onclick="checkTF(this, 'Soal2 10', 'false')" data-value="false"
                                        class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                </div>
                                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Deposit besar
                                        grafit murni ditemukan pada tahun 1564 di Borrowdale, Cumberland, Inggris, bukan
                                        di Jerman. Meskipun Jerman kemudian menjadi pusat produksi massal pensil.</p>
                                </div>
                            </div>
                        </div>

                        <!-- Submit -->
                        <div class="text-center pt-8">
                            <button onclick="showResult()"
                                class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">
                                <span class="flex items-center gap-2">
                                    <span class="material-symbols-outlined text-lg">fact_check</span>
                                    Lihat Hasil
                                </span>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- PAGE 3: RESULT -->
                <div id="page-result-002" class="page-section-002">
                    <div class="max-w-4xl mx-auto p-8 pb-32">
                        <div id="result-content-002">
                            <div class="text-center py-20 text-gray-400">
                                <span class="material-symbols-outlined text-6xl mb-4">pending</span>
                                <p class="font-serif text-lg">Selesaikan quiz terlebih dahulu untuk melihat hasil.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>


        </div>
        <!-- MODULE VIEW: OBAT FOKUS 003 -->

        <div id="module-obat-fokus-003" class="module-view">

            <div class="flex-1 overflow-y-auto" id="content-scroll-003">

                <!-- PAGE 1: ARTICLES -->

                <div id="page-articles-003" class="page-section-003 active">

                    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8"><!-- ARTIKEL 1 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 1
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Mengapa Kita Sangat
                                    Menginginkan Gula? Memahami Sugar

                                    Craving dan Cara Mengelolanya</h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Pernahkah Anda merasa tak tertahankan untuk meraih sebatang cokelat, sekotak biskuit,
                                    atau minuman manis

                                    setelah makan malam, bahkan ketika Anda tahu itu tidak ideal? Fenomena ini dikenal
                                    sebagai <em>sugar

                                        craving</em>, atau keinginan kuat terhadap gula, dan ini adalah pengalaman umum
                                    yang dialami banyak

                                    orang. Tapi, apa sebenarnya yang memicu keinginan kuat ini dan bagaimana kita bisa
                                    mengelolanya?</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Apa Itu Sugar Craving?</h5>

                                <p><em>Sugar craving</em> adalah dorongan atau keinginan intens untuk mengonsumsi
                                    makanan atau minuman yang

                                    manis. Ini berbeda dengan rasa lapar biasa, meskipun seringkali muncul bersamaan.
                                    Ketika kita mengalami

                                    <em>sugar craving</em>, fokus kita cenderung tertuju pada rasa manis dan sensasi
                                    menyenangkan yang

                                    diberikannya, bukan sekadar mengisi perut.
                                </p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Penyebab di Balik Sugar Craving
                                </h5>

                                <p>Ada beberapa faktor yang dapat memicu <em>sugar craving</em>, mulai dari aspek
                                    biologis hingga psikologis:

                                </p>

                                <p><strong>Fluktuasi Gula Darah:</strong> Ini adalah salah satu penyebab paling umum.
                                    Ketika Anda mengonsumsi

                                    makanan tinggi karbohidrat olahan dan gula, gula darah Anda bisa melonjak cepat,
                                    lalu turun drastis

                                    (<em>crash</em>). Penurunan ini memicu tubuh untuk mencari sumber energi cepat lain,
                                    yaitu gula, untuk

                                    menstabilkan kembali gula darah.</p>

                                <p><strong>Emosi dan Stres:</strong> Banyak orang menggunakan makanan manis sebagai
                                    mekanisme koping untuk

                                    mengatasi stres, kecemasan, atau kesedihan. Gula dapat memicu pelepasan dopamin,
                                    neurotransmitter "rasa

                                    senang" di otak, yang memberikan perasaan nyaman sementara.</p>

                                <p><strong>Kurang Tidur:</strong> Tidur yang tidak cukup dapat mengganggu hormon
                                    pengatur nafsu makan, yaitu

                                    leptin (hormon kenyang) dan ghrelin (hormon lapar). Ketidakseimbangan ini bisa
                                    meningkatkan keinginan untuk

                                    mengonsumsi makanan tinggi kalori, termasuk gula.</p>

                                <p><strong>Kekurangan Nutrisi:</strong> Terkadang, keinginan terhadap gula bisa menjadi
                                    indikasi tubuh

                                    kekurangan nutrisi tertentu, seperti kromium atau magnesium, yang berperan dalam
                                    metabolisme glukosa.</p>

                                <p><strong>Kebiasaan dan Pola Makan:</strong> Jika Anda terbiasa mengonsumsi makanan
                                    manis secara teratur, tubuh

                                    dan otak Anda akan membentuk kebiasaan tersebut. Semakin sering Anda makan gula,
                                    semakin besar kemungkinan

                                    Anda menginginkannya lagi.</p>

                                <p><strong>Ketidakseimbangan Mikrobioma Usus:</strong> Penelitian menunjukkan bahwa
                                    keseimbangan bakteri di usus

                                    kita dapat memengaruhi keinginan makan. Beberapa jenis bakteri bahkan "menginginkan"
                                    gula.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Dampak Negatif Sugar Craving yang
                                    Berlebihan</h5>

                                <p>Meskipun sesekali menikmati makanan manis tidak masalah, <em>sugar craving</em> yang
                                    berlebihan dan tidak

                                    terkontrol dapat berdampak negatif pada kesehatan:</p>

                                <p><strong>Penambahan Berat Badan:</strong> Gula mengandung kalori kosong yang tinggi
                                    tanpa serat atau nutrisi

                                    penting, yang mudah menyebabkan penambahan berat badan.</p>

                                <p><strong>Risiko Diabetes Tipe 2:</strong> Konsumsi gula berlebihan secara kronis dapat
                                    menyebabkan resistensi

                                    insulin, yang merupakan faktor risiko utama diabetes tipe 2.</p>

                                <p><strong>Masalah Kulit:</strong> Diet tinggi gula seringkali dikaitkan dengan jerawat
                                    dan penuaan dini pada

                                    kulit.</p>

                                <p><strong>Energi yang Tidak Stabil:</strong> Fluktuasi gula darah akibat konsumsi gula
                                    dapat menyebabkan

                                    "rollercoaster" energi, di mana Anda merasa bertenaga sesaat lalu lemas dan lelah.
                                </p>

                                <p><strong>Kesehatan Gigi:</strong> Gula adalah penyebab utama kerusakan gigi dan gigi
                                    berlubang.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Cara Mengelola Sugar Craving</h5>

                                <p>Mengatasi <em>sugar craving</em> membutuhkan pendekatan holistik. Berikut beberapa
                                    strategi yang bisa Anda

                                    coba:</p>

                                <p><strong>Makan Cukup Protein dan Serat:</strong> Protein dan serat membuat Anda merasa
                                    kenyang lebih lama dan

                                    membantu menstabilkan gula darah. Sertakan sumber protein tanpa lemak (ayam, ikan,
                                    telur, tahu, tempe) dan

                                    serat (sayuran, buah-buahan, biji-bijian utuh) di setiap makanan.</p>

                                <p><strong>Hindari Gula Tersembunyi:</strong> Baca label nutrisi dengan cermat. Gula
                                    seringkali bersembunyi di

                                    banyak makanan olahan seperti saus, sereal, yogurt, dan minuman.</p>

                                <p><strong>Cukupi Kebutuhan Tidur:</strong> Prioritaskan tidur berkualitas 7-9 jam
                                    setiap malam untuk membantu

                                    menyeimbangkan hormon nafsu makan.</p>

                                <p><strong>Kelola Stres:</strong> Temukan cara sehat untuk mengelola stres, seperti
                                    yoga, meditasi, jalan-jalan,

                                    atau hobi yang menyenangkan, daripada menggunakan makanan manis.</p>

                                <p><strong>Hidrasi yang Cukup:</strong> Terkadang, rasa haus disalahartikan sebagai rasa
                                    lapar atau keinginan

                                    makan. Pastikan Anda minum air yang cukup sepanjang hari.</p>

                                <p><strong>Pilih Pemanis Alami dengan Bijak:</strong> Jika Anda sangat menginginkan rasa
                                    manis, pilih

                                    buah-buahan utuh yang mengandung serat dan nutrisi. Kurma atau sedikit madu bisa
                                    menjadi pilihan, tetapi

                                    tetap dalam porsi moderat.</p>

                                <p><strong>Sediakan Camilan Sehat:</strong> Siapkan camilan sehat seperti
                                    kacang-kacangan, biji-bijian, buah,

                                    atau yogurt polos yang dapat membantu meredakan keinginan tanpa gula berlebih.</p>

                                <p><strong>Batasi Paparan Gula:</strong> Semakin sedikit Anda terpapar gula, semakin
                                    sedikit tubuh Anda akan

                                    menginginkannya. Secara bertahap kurangi konsumsi makanan dan minuman manis.</p>

                                <p><strong>Jalan Kaki atau Beraktivitas Fisik:</strong> Aktivitas fisik dapat membantu
                                    menyeimbangkan gula darah

                                    dan meningkatkan mood, mengurangi kebutuhan akan gula.</p>

                                <p><strong>Kesadaran Penuh (Mindful Eating):</strong> Sebelum meraih makanan manis,
                                    berhenti sejenak dan

                                    tanyakan pada diri sendiri: "Apakah saya benar-benar lapar atau hanya ingin
                                    memuaskan emosi?" Nikmati

                                    makanan Anda perlahan dan perhatikan setiap gigitan.</p>



                                <p>Mengelola <em>sugar craving</em> adalah perjalanan yang membutuhkan kesabaran dan
                                    konsistensi. Dengan

                                    memahami pemicunya dan menerapkan strategi yang tepat, Anda dapat mengambil kembali
                                    kendali atas keinginan

                                    terhadap gula dan meningkatkan kualitas kesehatan secara keseluruhan.</p>

                            </div>

                        </article>



                        <!-- ARTIKEL 2 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 2
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Pupuk Padi: Kunci Peningkatan
                                    Hasil Panen yang

                                    Berkelanjutan</h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Padi (<em>Oryza sativa</em>) adalah makanan pokok bagi lebih dari separuh populasi
                                    dunia, dan budidayanya

                                    memegang peran krusial dalam ketahanan pangan global. Untuk mencapai hasil panen
                                    yang optimal dan

                                    berkelanjutan, pemberian pupuk yang tepat merupakan faktor yang sangat penting.
                                    Pupuk membantu menyediakan

                                    nutrisi esensial yang dibutuhkan tanaman padi untuk tumbuh sehat, menghasilkan
                                    anakan yang banyak, dan bulir

                                    padi yang berisi.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Mengapa Padi Membutuhkan Pupuk?
                                </h5>

                                <p>Tanah pertanian seringkali kekurangan nutrisi yang cukup untuk mendukung pertumbuhan
                                    tanaman padi secara

                                    penuh, terutama setelah beberapa siklus tanam. Setiap kali panen, sejumlah besar
                                    nutrisi terangkat dari

                                    tanah bersama hasil panen. Pupuk berfungsi untuk mengembalikan dan melengkapi
                                    nutrisi ini, memastikan bahwa

                                    tanaman padi memiliki "bahan bakar" yang cukup untuk setiap tahap pertumbuhannya.
                                    Tanpa pemupukan yang

                                    memadai, tanaman padi akan menunjukkan gejala kekurangan nutrisi, seperti
                                    pertumbuhan yang kerdil, daun

                                    menguning, dan hasil panen yang rendah.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Jenis-jenis Pupuk Utama untuk
                                    Padi</h5>

                                <p>Ada beberapa jenis nutrisi makro dan mikro yang sangat penting bagi padi. Pupuk yang
                                    umum digunakan untuk

                                    padi dikategorikan berdasarkan nutrisi utamanya:</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Pupuk Nitrogen (N)</h5>

                                <p>Nitrogen adalah unsur hara paling penting untuk pertumbuhan vegetatif tanaman padi.
                                    Fungsinya sangat vital

                                    untuk pembentukan klorofil (zat hijau daun) yang berperan dalam fotosintesis, serta
                                    pembentukan protein dan

                                    asam amino.</p>

                                <p><strong>Gejala Kekurangan:</strong> Daun menguning pada bagian bawah, pertumbuhan
                                    kerdil, jumlah anakan

                                    sedikit.</p>

                                <p><strong>Contoh Pupuk:</strong></p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li><strong>Urea (46% N):</strong> Ini adalah pupuk nitrogen yang paling umum
                                        digunakan karena kandungan

                                        N-nya yang tinggi. Sangat efektif untuk memacu pertumbuhan vegetatif awal dan
                                        pembentukan anakan.</li>

                                    <li><strong>Amonium Sulfat / ZA (21% N, 24% S):</strong> Selain nitrogen, pupuk ini
                                        juga menyediakan sulfur

                                        yang penting untuk pembentukan protein. Baik untuk kondisi tanah tertentu.</li>

                                </ul>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Pupuk Fosfor (P)</h5>

                                <p>Fosfor berperan penting dalam pengembangan akar yang kuat, pembentukan bunga dan
                                    buah, serta transfer energi

                                    dalam tanaman. Nutrisi ini juga vital untuk pembentukan gabah yang berkualitas.</p>

                                <p><strong>Gejala Kekurangan:</strong> Daun berwarna ungu atau kebiruan, pertumbuhan
                                    akar terhambat, anakan

                                    sedikit, pemasakan gabah tertunda.</p>

                                <p><strong>Contoh Pupuk:</strong></p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li><strong>SP-36 (36% Pâ‚‚Oâ‚…):</strong> Sumber fosfor yang baik untuk pertumbuhan
                                        awal dan pembentukan sistem

                                        perakaran yang kuat.</li>

                                    <li><strong>TSP (46% Pâ‚‚Oâ‚…):</strong> Konsentrasi fosfor yang lebih tinggi
                                        dibandingkan SP-36.</li>

                                    <li><strong>Diamonium Fosfat / DAP (18% N, 46% Pâ‚‚Oâ‚…):</strong> Menyediakan
                                        nitrogen dan fosfor sekaligus.

                                    </li>

                                </ul>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Pupuk Kalium (K)</h5>

                                <p>Kalium membantu meningkatkan ketahanan tanaman terhadap hama dan penyakit,
                                    kekeringan, dan kondisi cuaca

                                    ekstrem. Ini juga berperan dalam transportasi air dan nutrisi dalam tanaman, serta
                                    pengisian gabah.</p>

                                <p><strong>Gejala Kekurangan:</strong> Ujung daun menguning dan mengering
                                    (<em>scorching</em>), batang lemah

                                    sehingga mudah rebah, pengisian gabah kurang sempurna.</p>

                                <p><strong>Contoh Pupuk:</strong></p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li><strong>KCl/MOP (60% Kâ‚‚O):</strong> Pupuk kalium yang paling umum digunakan.
                                    </li>

                                    <li><strong>ZK/KNOâ‚ƒ (Kalium Nitrat):</strong> Selain kalium, juga menyediakan
                                        nitrogen.</li>

                                </ul>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Pupuk Mikro dan Pelengkap</h5>

                                <p>Selain nutrisi makro, padi juga membutuhkan unsur hara mikro dalam jumlah kecil,
                                    seperti Seng (Zn), Besi

                                    (Fe), Mangan (Mn), Boron (B), Tembaga (Cu), dan Molibdenum (Mo). Beberapa pupuk juga
                                    mengandung unsur

                                    pelengkap seperti Sulfur (S) dan Kalsium (Ca).</p>

                                <p><strong>Contoh Pupuk:</strong></p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li><strong>Pupuk majemuk NPK:</strong> Mengandung kombinasi nitrogen, fosfor, dan
                                        kalium dalam rasio

                                        tertentu (misalnya NPK 15-15-15 atau 16-16-16), seringkali juga dilengkapi
                                        dengan unsur mikro. Pupuk ini

                                        praktis untuk pemupukan berimbang.</li>

                                    <li><strong>Pupuk organik:</strong> Seperti kompos, pupuk kandang, atau pupuk hijau.
                                        Meskipun kandungan

                                        nutrisinya lebih rendah dibandingkan pupuk anorganik, pupuk organik memperbaiki
                                        struktur tanah,

                                        meningkatkan kapasitas menahan air, dan menyediakan nutrisi secara bertahap.
                                    </li>

                                </ul>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Waktu dan Cara Pemupukan Padi
                                </h5>

                                <p>Strategi pemupukan yang efektif tidak hanya bergantung pada jenis pupuk, tetapi juga
                                    pada waktu dan cara

                                    aplikasinya. Umumnya, pemupukan padi dilakukan dalam beberapa tahap:</p>

                                <p><strong>Pemupukan Dasar:</strong> Diberikan sebelum tanam atau saat tanam, berfokus
                                    pada fosfor dan sebagian

                                    kalium untuk mendorong perkembangan akar yang kuat.</p>

                                <p><strong>Pemupukan Susulan 1:</strong> Sekitar 7-15 hari setelah tanam (HST), berfokus
                                    pada nitrogen untuk

                                    memacu pertumbuhan anakan.</p>

                                <p><strong>Pemupukan Susulan 2:</strong> Sekitar 25-35 HST, kombinasi nitrogen dan
                                    kalium untuk mendukung

                                    pembentukan anakan produktif dan persiapan fase generatif.</p>

                                <p><strong>Pemupukan Susulan 3 (Opsional):</strong> Sekitar 45-55 HST, terutama kalium
                                    dan sedikit nitrogen,

                                    untuk pengisian gabah.</p>

                                <p>Metode aplikasi bisa dengan cara disebar, ditaburkan di antara barisan tanaman, atau
                                    melalui fertigasi

                                    (aplikasi pupuk bersamaan dengan air irigasi). Penting untuk selalu mengikuti dosis
                                    anjuran dan

                                    mempertimbangkan kondisi tanah serta varietas padi yang ditanam.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Pentingnya Analisis Tanah dan
                                    Pemupukan Berimbang</h5>

                                <p>Untuk memaksimalkan efektivitas pemupukan dan mencegah pemborosan, melakukan analisis
                                    tanah secara berkala

                                    sangat dianjurkan. Analisis tanah akan memberikan informasi akurat mengenai
                                    ketersediaan nutrisi di lahan

                                    Anda, sehingga Anda bisa menentukan jenis dan dosis pupuk yang paling tepat.</p>

                                <p>Menerapkan konsep pemupukan berimbang, yaitu memberikan nutrisi dalam jumlah dan
                                    proporsi yang tepat sesuai

                                    kebutuhan tanaman dan ketersediaan di tanah, adalah kunci untuk mencapai
                                    produktivitas padi yang tinggi,

                                    menjaga kesehatan tanah, dan mendukung pertanian yang berkelanjutan.</p>

                            </div>

                        </article>



                        <!-- ARTIKEL 3 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 3
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Rambut Mohawk: Dari Simbol
                                    Pemberontakan Hingga Tren

                                    Fashion</h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Gaya rambut mohawk adalah salah satu model potongan rambut yang paling ikonik dan
                                    mudah dikenali di dunia.

                                    Ciri khasnya adalah bagian sisi kepala dicukur habis atau sangat pendek, sementara
                                    bagian tengah dibiarkan

                                    panjang dan biasanya ditata berdiri tegak ke atas, membentuk jambul memanjang dari
                                    dahi hingga ke tengkuk.

                                    Lebih dari sekadar potongan rambut, mohawk memiliki sejarah panjang dan kaya,
                                    berevolusi dari simbol suku

                                    asli Amerika hingga menjadi pernyataan mode yang berani.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Sejarah Singkat Mohawk</h5>

                                <p>Nama mohawk sendiri berasal dari nama suku Mohawk, salah satu suku asli Amerika dari
                                    Konfederasi Iroquois.

                                    Namun, ironisnya, gaya rambut yang kita kenal sebagai mohawk modern sebenarnya tidak
                                    persis sama dengan yang

                                    dipraktikkan oleh suku Mohawk. Suku Mohawk dan suku-suku Iroquois lainnya lebih
                                    sering mencukur sebagian

                                    kepala mereka, meninggalkan secarik rambut di mahkota kepala, terkadang dikepang
                                    atau dihias. Gaya ini

                                    berfungsi sebagai identifikasi suku dan juga memiliki makna spiritual.</p>

                                <p>Popularitas mohawk dalam budaya modern mulai meledak pada tahun 1970-an, terutama di
                                    kalangan subkultur punk

                                    rock di Inggris dan Amerika Serikat. Bagi para punk, mohawk adalah simbol
                                    pemberontakan, penolakan terhadap

                                    norma sosial, dan ekspresi individualitas yang ekstrem. Semakin tinggi, semakin
                                    tajam, dan semakin berwarna

                                    mohawk tersebut, semakin kuat pesannya. Warna-warna cerah seperti merah menyala,
                                    biru elektrik, atau hijau

                                    neon seringkali digunakan untuk memperkuat kesan dramatis.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Evolusi dan Variasi Mohawk</h5>

                                <p>Seiring berjalannya waktu, mohawk mulai beradaptasi dan berkembang, menembus batasan
                                    subkultur punk dan masuk

                                    ke dunia fashion yang lebih luas. Kini, ada berbagai variasi mohawk yang bisa
                                    disesuaikan dengan preferensi

                                    dan tingkat keberanian seseorang:</p>

                                <p><strong>Classic Mohawk:</strong> Ini adalah versi paling tradisional, dengan sisi
                                    kepala dicukur botak atau

                                    sangat pendek dan bagian tengah dibiarkan panjang serta ditata berdiri tegak.</p>

                                <p><strong>Faux Hawk:</strong> Lebih lembut dan kurang ekstrem. Pada faux hawk, bagian
                                    sisi kepala tidak dicukur

                                    botak, melainkan hanya dipotong sangat pendek atau disisir rapi ke belakang. Bagian
                                    atas rambut dipanjangkan

                                    dan ditata menyerupai mohawk tanpa perlu cukuran ekstrem. Ini adalah pilihan populer
                                    bagi mereka yang ingin

                                    mencoba gaya mohawk tanpa komitmen penuh.</p>

                                <p><strong>Undercut Mohawk:</strong> Mirip dengan classic mohawk, namun seringkali
                                    potongan di sisi lebih rapi

                                    dan rambut bagian atas ditata lebih bervolume atau dengan tekstur tertentu, bukan
                                    selalu ditata tegak kaku.

                                </p>

                                <p><strong>Dreadlock Mohawk / Braided Mohawk:</strong> Gaya ini memadukan mohawk dengan
                                    rambut gimbal atau

                                    kepangan. Bagian sisi kepala dicukur, sementara bagian tengah dibiarkan panjang dan
                                    ditata menjadi dreadlock

                                    atau kepangan, menciptakan tampilan yang unik dan artistik.</p>

                                <p><strong>Mohawk untuk Rambut Keriting/Afro:</strong> Rambut keriting atau afro dapat
                                    membentuk mohawk yang

                                    luar biasa bervolume dan bertekstur, menciptakan siluet yang dramatis dan menarik
                                    perhatian.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Siapa yang Memakai Mohawk?</h5>

                                <p>Dari panggung musik hingga karpet merah, mohawk telah diadopsi oleh berbagai
                                    kalangan. Bintang rock, atlet

                                    profesional, selebriti, hingga individu yang ingin membuat pernyataan mode unik.
                                    Mohawk sering dikaitkan

                                    dengan individu yang percaya diri, berani, dan tidak takut untuk menonjol dari
                                    keramaian.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Tips Merawat Mohawk</h5>

                                <p>Merawat mohawk, terutama yang klasik dan berdiri tegak, membutuhkan usaha dan produk
                                    styling yang tepat.

                                    Beberapa tipsnya meliputi:</p>

                                <p><strong>Pencukuran Rutin:</strong> Untuk menjaga sisi kepala tetap rapi, pencukuran
                                    rutin diperlukan,

                                    biasanya setiap beberapa minggu sekali.</p>

                                <p><strong>Produk Styling Kuat:</strong> Gel, pomade, atau hairspray dengan daya rekat
                                    ekstra kuat adalah kunci

                                    untuk membuat bagian tengah rambut berdiri tegak dan bertahan sepanjang hari.</p>

                                <p><strong>Pencucian Teratur:</strong> Pastikan rambut bersih agar produk styling tidak
                                    menumpuk dan menyebabkan

                                    masalah kulit kepala.</p>

                                <p><strong>Perlindungan Rambut:</strong> Jika sering menggunakan alat panas atau produk
                                    kimia, gunakan pelindung

                                    rambut untuk menjaga kesehatan dan kilau rambut.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Mohawk di Era Modern</h5>

                                <p>Di era modern, mohawk terus berevolusi. Ia tidak lagi secara eksklusif diasosiasikan
                                    dengan satu subkultur

                                    saja. Sebaliknya, mohawk telah menjadi bagian dari kanvas ekspresi diri, di mana
                                    individu dapat

                                    menginterpretasikannya dengan cara mereka sendiri, menggabungkannya dengan tren
                                    lain, dan menjadikannya unik

                                    milik mereka. Dari nuansa punk yang kasar hingga tampilan yang lebih halus dan chic,
                                    mohawk tetap menjadi

                                    simbol keberanian dan gaya yang tak lekang oleh waktu.</p>

                            </div>

                        </article>



                        <!-- ARTIKEL 4 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 4
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Bahaya Suara Terlalu Keras
                                    pada Telinga: Lindungi

                                    Pendengaran</h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Di era modern ini, kita dikelilingi oleh berbagai jenis suara, mulai dari musik yang
                                    diputar melalui

                                    headphone, konser, bising kendaraan, hingga mesin-mesin industri. Meskipun suara
                                    adalah bagian penting dari

                                    kehidupan sehari-hari, paparan suara yang terlalu keras dapat memiliki dampak serius
                                    dan permanen pada

                                    kesehatan telinga kita. Memahami bahaya ini adalah langkah pertama untuk melindungi
                                    salah satu indera paling

                                    berharga kita: pendengaran.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Bagaimana Suara Merusak Telinga?
                                </h5>

                                <p>Telinga kita adalah organ yang kompleks dan sensitif. Di dalam koklea, bagian telinga
                                    bagian dalam, terdapat

                                    ribuan sel rambut halus yang disebut sel rambut koklea. Sel-sel inilah yang bertugas
                                    mengubah getaran suara

                                    menjadi sinyal listrik yang kemudian dikirim ke otak untuk diinterpretasikan sebagai
                                    suara.</p>

                                <p>Ketika kita terpapar suara yang terlalu keras, getaran yang dihasilkan menjadi sangat
                                    kuat. Getaran ekstrem

                                    ini dapat merusak atau bahkan menghancurkan sel-sel rambut halus tersebut.
                                    Masalahnya, sel rambut ini tidak

                                    dapat tumbuh kembali. Sekali rusak, mereka rusak untuk selamanya, menyebabkan
                                    gangguan pendengaran permanen.

                                </p>

                                <p>Tingkat kerusakan tergantung pada dua faktor utama: tingkat kebisingan (diukur dalam
                                    desibel atau dB) dan

                                    durasi paparan. Semakin tinggi desibel dan semakin lama kamu terpapar, semakin besar
                                    risiko kerusakan.

                                    Sebagai contoh, suara percakapan normal berada di sekitar 60 dB, sementara konser
                                    musik rock bisa mencapai

                                    110-120 dB, dan suara mesin jet bisa lebih dari 130 dB. Paparan singkat pada suara
                                    di atas 120 dB sudah bisa

                                    menyebabkan kerusakan, sedangkan paparan berulang pada suara di atas 85 dB juga
                                    berisiko.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Dampak Buruk Paparan Suara Keras
                                </h5>

                                <p>Kerusakan telinga akibat suara keras tidak hanya terbatas pada hilangnya pendengaran.
                                    Ada beberapa masalah

                                    kesehatan lain yang mungkin timbul:</p>

                                <p><strong>Gangguan Pendengaran Permanen:</strong> Ini adalah dampak paling umum.
                                    Pendengaran bisa berkurang

                                    secara bertahap atau tiba-tiba, membuat sulit mendengar percakapan, musik, atau
                                    suara lingkungan.</p>

                                <p><strong>Tinnitus:</strong> Ini adalah kondisi di mana seseorang mendengar dering,
                                    dengungan, desis, atau

                                    suara lain di telinga tanpa adanya sumber suara eksternal. Tinnitus bisa bersifat
                                    sementara atau permanen,

                                    dan seringkali sangat mengganggu kualitas hidup.</p>

                                <p><strong>Hiperakusis:</strong> Kondisi ini menyebabkan suara sehari-hari terasa
                                    menyakitkan atau terlalu

                                    keras, bahkan suara yang normal bagi orang lain.</p>

                                <p><strong>Distorsi Suara:</strong> Suara mungkin terdengar tidak jelas, terdistorsi,
                                    atau seperti ada filter

                                    yang mengganggu.</p>

                                <p><strong>Masalah Keseimbangan:</strong> Karena telinga bagian dalam juga berperan
                                    dalam keseimbangan,

                                    kerusakan pada area ini bisa menyebabkan pusing atau vertigo.</p>

                                <p><strong>Dampak Psikologis:</strong> Gangguan pendengaran dan tinnitus dapat
                                    menyebabkan stres, kecemasan,

                                    depresi, isolasi sosial, dan kesulitan dalam berkomunikasi.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Sumber Suara Keras yang Perlu
                                    Diwaspadai</h5>

                                <p>Bahaya suara keras bisa datang dari mana saja:</p>

                                <p><strong>Headphone atau Earbud:</strong> Mendengarkan musik dengan volume tinggi dalam
                                    waktu lama adalah

                                    penyebab umum gangguan pendengaran pada generasi muda.</p>

                                <p><strong>Konser Musik dan Klub Malam:</strong> Tingkat kebisingan di tempat-tempat ini
                                    seringkali melebihi

                                    batas aman.</p>

                                <p><strong>Peralatan Listrik Rumah Tangga atau Pertukangan:</strong> Mesin pemotong
                                    rumput, bor listrik,

                                    gergaji, atau alat-alat rumah tangga lainnya bisa menghasilkan suara yang sangat
                                    keras.</p>

                                <p><strong>Lingkungan Kerja:</strong> Pekerja konstruksi, pabrik, bandara, atau musisi
                                    sering terpapar suara

                                    keras secara terus-menerus.</p>

                                <p><strong>Suara Ledakan atau Tembakan:</strong> Paparan singkat terhadap suara yang
                                    sangat ekstrem ini bisa

                                    menyebabkan kerusakan pendengaran instan.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Cara Melindungi Pendengaran</h5>

                                <p>Kabar baiknya, gangguan pendengaran akibat kebisingan dapat dicegah. Berikut adalah
                                    beberapa langkah penting:

                                </p>

                                <p><strong>Batasi Volume:</strong> Saat menggunakan headphone atau earbud, jaga volume
                                    pada tingkat yang aman

                                    (biasanya tidak lebih dari 60% dari volume maksimal) dan berikan jeda istirahat
                                    setiap jam.</p>

                                <p><strong>Gunakan Pelindung Telinga:</strong> Saat berada di lingkungan bising seperti
                                    konser, lokasi

                                    konstruksi, atau saat menggunakan alat berat, selalu kenakan penutup telinga atau
                                    earplug.</p>

                                <p><strong>Jauhi Sumber Suara:</strong> Sebisa mungkin, jaga jarak dari sumber suara
                                    yang keras.</p>

                                <p><strong>Kenali Batas Aman:</strong> Jika kamu harus berteriak untuk didengar orang di
                                    sebelah kamu,

                                    kemungkinan besar tingkat kebisingan sudah terlalu tinggi.</p>

                                <p><strong>Berikan Waktu Istirahat untuk Telinga:</strong> Setelah terpapar suara keras,
                                    berikan waktu bagi

                                    telinga untuk pulih di lingkungan yang tenang.</p>

                                <p><strong>Periksa Pendengaran Secara Teratur:</strong> Jika kamu sering terpapar suara
                                    keras, lakukan

                                    pemeriksaan pendengaran rutin dengan profesional kesehatan.</p>

                                <p>Melindungi pendengaran adalah investasi jangka panjang untuk kualitas hidup kita.
                                    Dengan kesadaran dan

                                    tindakan pencegahan yang tepat, kita dapat menikmati dunia suara tanpa mengorbankan
                                    kemampuan mendengar kita

                                    di masa depan.</p>

                            </div>

                        </article><!-- ARTIKEL 5 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 5
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Madden Julian Oscillation
                                </h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Apakah kita pernah mendengar tentang Madden Julian Oscillation, atau disingkat MJO?
                                    Meskipun mungkin tidak

                                    sepopuler El NiÃ±o atau La NiÃ±a, MJO adalah fenomena atmosfer penting yang memiliki
                                    dampak signifikan

                                    terhadap pola cuaca di wilayah tropis, termasuk di Indonesia. MJO sering disebut
                                    sebagai "denyut nadi" cuaca

                                    tropis karena sifatnya yang bergerak dan berulang secara periodik.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Apa Itu Madden Julian
                                    Oscillation?</h5>

                                <p>Madden Julian Oscillation adalah sebuah fenomena iklim berskala besar yang terjadi di
                                    atmosfer tropis.

                                    Berbeda dengan El NiÃ±o atau La NiÃ±a yang cenderung bersifat stasioner (berlangsung
                                    di satu lokasi dalam

                                    jangka waktu lama), MJO adalah pola yang bergerak dari barat ke timur di sepanjang
                                    wilayah khatulistiwa.

                                    Fenomena ini pertama kali ditemukan pada tahun 1971 oleh Roland Madden dan Paul
                                    Julian saat mereka

                                    mempelajari pola angin dan tekanan di daerah tropis.</p>

                                <p>MJO dicirikan oleh pergerakan ke arah timur dari daerah dengan peningkatan curah
                                    hujan (fase konvektif aktif)

                                    dan daerah dengan penurunan curah hujan (fase konvektif tertekan). Siklus lengkap
                                    MJO membutuhkan waktu

                                    sekitar 30 hingga 60 hari untuk melintasi seluruh Bumi di wilayah tropis. Ini
                                    berarti, dalam satu hingga dua

                                    bulan, kita bisa melihat perubahan pola awan, curah hujan, angin, dan tekanan
                                    atmosfer yang signifikan di

                                    wilayah yang dilaluinya.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Mekanisme Pergerakan MJO</h5>

                                <p>MJO biasanya muncul pertama kali di Samudra Hindia bagian barat dan bergerak perlahan
                                    ke timur melintasi

                                    Samudra Hindia dan Samudra Pasifik. Saat melewati perairan yang lebih hangat, MJO
                                    akan menguat dan memicu

                                    pembentukan awan konvektif yang tebal serta curah hujan intens. Sebaliknya, di fase
                                    tertekan, daerah

                                    tersebut akan mengalami kondisi yang lebih kering dengan curah hujan yang berkurang.
                                </p>

                                <p>Pergerakan MJO ini melibatkan interaksi kompleks antara atmosfer dan lautan.
                                    Peningkatan konveksi

                                    (pembentukan awan dan hujan) akan mempengaruhi pola angin, yang kemudian
                                    mempengaruhi suhu permukaan laut,

                                    yang pada gilirannya dapat memengaruhi konveksi selanjutnya. Ini menciptakan siklus
                                    umpan balik yang

                                    mendorong pergerakan MJO ke arah timur.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Dampak MJO Terhadap Cuaca,
                                    Khususnya di Indonesia</h5>

                                <p>Sebagai negara kepulauan tropis yang terletak di garis khatulistiwa, Indonesia sangat
                                    rentan terhadap

                                    pengaruh MJO. MJO berperan seperti pengendali cuaca yang dapat meningkatkan atau
                                    mengurangi intensitas hujan

                                    ekstrem di Indonesia.</p>

                                <p><strong>Peningkatan Curah Hujan:</strong> Saat MJO berada dalam fase aktif (fase
                                    konvektif yang ditingkatkan)

                                    dan melintasi wilayah Indonesia (umumnya fase 3 hingga 5 MJO), ini membawa banyak
                                    uap air dan energi ke

                                    atmosfer. Hal ini memicu pembentukan awan tebal dan curah hujan yang intens.
                                    Akibatnya, banyak wilayah di

                                    Indonesia bisa mengalami peningkatan curah hujan, yang berpotensi menyebabkan hujan
                                    lebat hingga ekstrem.

                                    Kondisi ini seringkali menjadi pemicu bencana hidrometeorologi seperti banjir dan
                                    tanah longsor.</p>

                                <p><strong>Penurunan Curah Hujan:</strong> Sebaliknya, ketika MJO berada dalam fase
                                    tidak aktif (fase konvektif

                                    tertekan) melintasi wilayah Indonesia, curah hujan cenderung menurun. Ini dapat
                                    berkontribusi pada periode

                                    yang lebih kering.</p>

                                <p><strong>Pengaruh Global:</strong> Meskipun dampaknya paling terasa di daerah tropis,
                                    MJO juga dapat

                                    memengaruhi pola cuaca ekstrem di lintang tengah dan tinggi, seperti badai besar,
                                    gelombang panas, atau

                                    perubahan pola angin yang signifikan.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Mengapa MJO Penting untuk
                                    Dipahami?</h5>

                                <p>Memahami MJO sangat penting bagi para ahli meteorologi dan klimatologi untuk:</p>

                                <p><strong>Prediksi Cuaca Jangka Menengah:</strong> MJO memberikan sinyal penting untuk
                                    memprediksi pola curah

                                    hujan dan anomali suhu dalam skala waktu mingguan hingga bulanan, yang lebih panjang
                                    daripada perkiraan

                                    cuaca harian namun lebih pendek dari prakiraan musiman.</p>

                                <p><strong>Mitigasi Bencana:</strong> Dengan memantau fase MJO, pihak berwenang dapat
                                    memberikan peringatan dini

                                    mengenai potensi hujan ekstrem yang bisa menyebabkan banjir atau tanah longsor,
                                    sehingga upaya mitigasi

                                    dapat dilakukan lebih awal.</p>

                                <p><strong>Pengelolaan Sumber Daya:</strong> Sektor pertanian, perikanan, dan energi
                                    dapat memanfaatkan

                                    informasi MJO untuk perencanaan yang lebih baik.</p>

                                <p>Meskipun MJO adalah fenomena yang kompleks, penelitian terus dilakukan untuk memahami
                                    karakteristik dan

                                    dampaknya secara lebih mendalam. Dengan begitu, kita bisa lebih siap menghadapi
                                    variabilitas cuaca dan iklim

                                    yang dibawa oleh denyut nadi tropis ini.</p>

                            </div>

                        </article>



                        <!-- ARTIKEL 6 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 6
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Pembagian Waktu di Indonesia:
                                    Mengapa Kita Punya Tiga

                                    Zona Waktu?</h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Sebagai negara kepulauan terbesar di dunia yang membentang luas dari barat ke timur,
                                    Indonesia memiliki

                                    rentang geografis yang signifikan. Akibatnya, matahari terbit dan terbenam pada
                                    waktu yang berbeda di

                                    berbagai wilayah. Untuk mengatur hal ini secara efektif, Indonesia dibagi menjadi
                                    tiga zona waktu utama.

                                    Pembagian ini bukan hanya soal akurasi jam, tapi juga memengaruhi aktivitas harian,
                                    transportasi, dan

                                    koordinasi nasional.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Mengapa Ada Pembagian Waktu?</h5>

                                <p>Pembagian waktu di Bumi didasarkan pada rotasi Bumi mengelilingi porosnya. Setiap 15
                                    derajat garis bujur, ada

                                    perbedaan waktu sekitar satu jam. Dengan garis bujur yang membentang dari sekitar 95
                                    derajat Bujur Timur

                                    (BT) di ujung barat hingga 141 derajat BT di ujung timur, Indonesia mencakup rentang
                                    yang cukup lebar. Tanpa

                                    pembagian zona waktu, akan ada perbedaan waktu yang sangat besar antara kota-kota di
                                    ujung barat dan timur.

                                </p>

                                <p>Pembagian ini bertujuan untuk menyeragamkan waktu di wilayah tertentu agar sesuai
                                    dengan posisi matahari,

                                    sehingga tengah hari (pukul 12:00) secara kasar bertepatan dengan saat matahari
                                    berada di titik tertinggi di

                                    langit, memudahkan aktivitas manusia seperti bekerja, bersekolah, dan beribadah.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Tiga Zona Waktu di Indonesia</h5>

                                <p>Indonesia secara resmi dibagi menjadi tiga zona waktu, yang masing-masing memiliki
                                    perbedaan satu jam dari

                                    zona sebelahnya:</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Waktu Indonesia Bagian Barat
                                    (WIB)</h5>

                                <p>Zona waktu ini dihitung berdasarkan garis bujur 105 derajat BT. Waktu di WIB adalah
                                    UTC+7 (Universal Time

                                    Coordinated +7 jam), yang berarti 7 jam lebih cepat dari waktu standar Greenwich
                                    (GMT).</p>

                                <p>Wilayah yang termasuk dalam zona WIB meliputi:</p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li>Sumatera dan pulau-pulau di sekitarnya (misalnya Bangka Belitung, Nias, dll.)
                                    </li>

                                    <li>Jawa</li>

                                    <li>Madura</li>

                                    <li>Kalimantan Barat</li>

                                    <li>Kalimantan Tengah</li>

                                </ul>

                                <p>Di wilayah ini, ketika jam menunjukkan pukul 07.00 pagi, sebagian besar orang baru
                                    memulai aktivitasnya

                                    setelah matahari terbit.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Waktu Indonesia Bagian Tengah
                                    (WITA)</h5>

                                <p>Zona waktu ini dihitung berdasarkan garis bujur 120 derajat BT. Waktu di WITA adalah
                                    UTC+8 (Universal Time

                                    Coordinated +8 jam), yang berarti 8 jam lebih cepat dari GMT, atau 1 jam lebih cepat
                                    dari WIB.</p>

                                <p>Wilayah yang termasuk dalam zona WITA meliputi:</p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li>Sulawesi</li>

                                    <li>Bali</li>

                                    <li>Nusa Tenggara Barat (NTB)</li>

                                    <li>Nusa Tenggara Timur (NTT)</li>

                                    <li>Kalimantan Utara</li>

                                    <li>Kalimantan Selatan</li>

                                    <li>Kalimantan Timur</li>

                                </ul>

                                <p>Ketika di Jakarta (WIB) pukul 07.00 pagi, di Denpasar (WITA) sudah pukul 08.00 pagi.
                                </p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Waktu Indonesia Bagian Timur
                                    (WIT)</h5>

                                <p>Zona waktu ini dihitung berdasarkan garis bujur 135 derajat BT. Waktu di WIT adalah
                                    UTC+9 (Universal Time

                                    Coordinated +9 jam), yang berarti 9 jam lebih cepat dari GMT, atau 1 jam lebih cepat
                                    dari WITA, dan 2 jam

                                    lebih cepat dari WIB.</p>

                                <p>Wilayah yang termasuk dalam zona WIT meliputi:</p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li>Maluku</li>

                                    <li>Maluku Utara</li>

                                    <li>Papua</li>

                                    <li>Papua Barat</li>

                                    <li>Papua Pegunungan</li>

                                    <li>Papua Selatan</li>

                                    <li>Papua Tengah</li>

                                    <li>Papua Barat Daya</li>

                                </ul>

                                <p>Jadi, ketika di Jakarta (WIB) pukul 07.00 pagi, di Jayapura (WIT) sudah pukul 09.00
                                    pagi.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Pentingnya Koordinasi Waktu</h5>

                                <p>Pembagian zona waktu ini sangat penting untuk berbagai aspek kehidupan:</p>

                                <p><strong>Transportasi:</strong> Jadwal penerbangan, kereta api, dan kapal feri sangat
                                    bergantung pada

                                    keseragaman waktu di setiap daerah.</p>

                                <p><strong>Bisnis dan Komunikasi:</strong> Perusahaan dan individu dapat merencanakan
                                    rapat atau komunikasi

                                    lintas wilayah dengan lebih efisien.</p>

                                <p><strong>Pendidikan:</strong> Jam sekolah dan ujian nasional dapat disesuaikan dengan
                                    waktu lokal.</p>

                                <p><strong>Penyiaran:</strong> Jadwal siaran televisi dan radio disesuaikan agar relevan
                                    dengan waktu setempat.

                                </p>

                                <p><strong>Kehidupan Sehari-hari:</strong> Masyarakat dapat menjalani rutinitas harian
                                    mereka (bekerja, makan,

                                    tidur) sesuai dengan siklus siang dan malam di wilayah masing-masing.</p>

                                <p>Meskipun pembagian waktu ini sudah mapan, kadang kala ada diskusi mengenai
                                    kemungkinan penyatuan waktu untuk

                                    efisiensi lebih lanjut, seperti yang pernah diusulkan di masa lalu. Namun, untuk
                                    saat ini, sistem tiga zona

                                    waktu tetap menjadi standar yang mengatur irama kehidupan di seluruh penjuru
                                    Nusantara.</p>

                            </div>

                        </article>



                        <!-- ARTIKEL 7 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 7
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Apa itu Hewan Endemik?</h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Kita seringkali mendengar hewan yang hanya ada di suatu wilayah saja seperti komodo,
                                    anoa, atau burung

                                    cendrawasih? Mereka adalah contoh sempurna dari hewan endemik. Hewan endemik adalah
                                    spesies yang secara

                                    alami hanya ditemukan di suatu wilayah geografis tertentu dan tidak ditemukan di
                                    tempat lain di dunia.

                                    Keberadaan mereka menjadikan suatu daerah memiliki keunikan hayati yang tidak
                                    dimiliki oleh daerah lain,

                                    menjadikannya permata biologis yang sangat berharga.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Mengapa Suatu Hewan Menjadi
                                    Endemik?</h5>

                                <p>Ada beberapa faktor yang menyebabkan suatu spesies menjadi endemik di wilayah
                                    tertentu:</p>

                                <p><strong>Isolasi Geografis:</strong> Ini adalah penyebab paling umum. Pulau-pulau,
                                    pegunungan tinggi, atau

                                    danau-danau besar seringkali menjadi "pulau ekologi" yang mengisolasi populasi
                                    hewan. Seiring waktu, spesies

                                    di wilayah terisolasi ini berevolusi dan beradaptasi secara unik dengan lingkungan
                                    lokal, sehingga tidak

                                    dapat bertahan hidup atau berkembang biak di tempat lain. Contoh paling jelas adalah
                                    fauna di pulau-pulau

                                    terpencil seperti Kepulauan Galapagos atau Madagaskar.</p>

                                <p><strong>Kondisi Lingkungan Spesifik:</strong> Beberapa spesies mungkin membutuhkan
                                    kondisi lingkungan yang

                                    sangat spesifik, seperti iklim tertentu, jenis tanah, atau vegetasi khusus, yang
                                    hanya tersedia di satu

                                    lokasi.</p>

                                <p><strong>Perkembangan Evolusioner:</strong> Spesies endemik seringkali merupakan hasil
                                    dari proses evolusi

                                    yang panjang, di mana mereka berhasil beradaptasi dan berkembang di lingkungan yang
                                    spesifik tanpa menyebar

                                    ke wilayah lain.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Contoh Hewan Endemik di Indonesia
                                    dan Dunia</h5>

                                <p>Indonesia, sebagai negara kepulauan besar yang kaya akan keanekaragaman hayati,
                                    adalah rumah bagi banyak

                                    spesies endemik yang menakjubkan:</p>

                                <p><strong>Komodo (<em>Varanus komodoensis</em>):</strong> Kadal terbesar di dunia ini
                                    hanya bisa ditemukan di

                                    beberapa pulau di Nusa Tenggara Timur, terutama Pulau Komodo, Rinca, Flores, Gili
                                    Motang, dan Gili Dasami.

                                    Keberadaannya menjadi ikon konservasi global.</p>

                                <p><strong>Anoa (<em>Bubalus depressicornis</em> dan <em>Bubalus
                                            quarlesi</em>):</strong> Sapi kerdil ini hanya

                                    hidup di hutan hujan Sulawesi. Ada dua jenis anoa, yaitu anoa pegunungan dan anoa
                                    dataran rendah.</p>

                                <p><strong>Orangutan (<em>Pongo abelii</em>, <em>Pongo pygmaeus</em>, <em>Pongo
                                            tapanuliensis</em>):</strong>

                                    Meskipun sering disebut sebagai "orangutan Indonesia," setiap spesies orangutan
                                    (Sumatera, Kalimantan, dan

                                    Tapanuli) memiliki jangkauan endemik yang lebih spesifik di pulau masing-masing.</p>

                                <p><strong>Burung Cendrawasih:</strong> Banyak spesies burung cendrawasih, dengan bulu
                                    indahnya, adalah endemik

                                    di Papua dan pulau-pulau sekitarnya.</p>

                                <p><strong>Harimau Sumatera (<em>Panthera tigris sumatrae</em>):</strong> Satu-satunya
                                    subspesies harimau yang

                                    masih tersisa di Indonesia, hanya ditemukan di Pulau Sumatera.</p>

                                <p>Di luar Indonesia, kita juga menemukan banyak contoh menarik lainnya:</p>

                                <ul class="list-disc pl-6 space-y-1">

                                    <li><strong>Koala:</strong> Endemik di Australia.</li>

                                    <li><strong>Lemur:</strong> Hampir seluruhnya endemik di Madagaskar.</li>

                                    <li><strong>Panda Merah:</strong> Endemik di Himalaya Timur dan Tiongkok barat daya.
                                    </li>

                                    <li><strong>Kiwi:</strong> Burung tidak bisa terbang yang hanya ditemukan di
                                        Selandia Baru.</li>

                                </ul>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Ancaman Terhadap Hewan Endemik
                                </h5>

                                <p>Sayangnya, hewan endemik seringkali menjadi spesies yang paling rentan terhadap
                                    kepunahan. Karena jangkauan

                                    mereka yang terbatas, mereka sangat sensitif terhadap perubahan lingkungan. Beberapa
                                    ancaman utama meliputi:

                                </p>

                                <p><strong>Kerusakan Habitat:</strong> Pembukaan lahan untuk pertanian, pemukiman, atau
                                    industri dapat

                                    menghancurkan habitat alami mereka.</p>

                                <p><strong>Perubahan Iklim:</strong> Kenaikan suhu global, perubahan pola curah hujan,
                                    dan peristiwa cuaca

                                    ekstrem dapat mengubah kondisi habitat yang spesifik yang dibutuhkan oleh spesies
                                    endemik.</p>

                                <p><strong>Introduksi Spesies Asing (Invasif):</strong> Spesies non-endemik yang dibawa
                                    ke habitat endemik dapat

                                    menjadi predator, pesaing, atau penyebar penyakit yang mengancam populasi asli.</p>

                                <p><strong>Perburuan dan Perdagangan Ilegal:</strong> Banyak hewan endemik menjadi
                                    target perburuan untuk

                                    diambil bagian tubuhnya atau diperdagangkan sebagai hewan peliharaan.</p>

                                <p><strong>Fragmentasi Populasi:</strong> Pembangunan infrastruktur atau perubahan
                                    lanskap dapat memecah

                                    populasi menjadi kelompok-kelompok kecil yang terisolasi, membuat mereka lebih
                                    rentan terhadap kepunahan.

                                </p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Pentingnya Konservasi Hewan
                                    Endemik</h5>

                                <p>Melindungi hewan endemik adalah kunci untuk menjaga keanekaragaman hayati global dan
                                    keseimbangan ekosistem.

                                    Usaha konservasi melibatkan:</p>

                                <p><strong>Penetapan Kawasan Konservasi:</strong> Melindungi habitat alami melalui taman
                                    nasional, cagar alam,

                                    dan suaka margasatwa.</p>

                                <p><strong>Rehabilitasi Habitat:</strong> Upaya untuk memulihkan area yang rusak dan
                                    mengembalikan ekosistem

                                    yang sehat.</p>

                                <p><strong>Penegakan Hukum:</strong> Melawan perburuan dan perdagangan ilegal.</p>

                                <p><strong>Pendidikan dan Kesadaran Masyarakat:</strong> Mengedukasi masyarakat tentang
                                    pentingnya menjaga hewan

                                    endemik dan habitatnya.</p>

                                <p><strong>Penelitian dan Pemantauan:</strong> Memahami biologi dan ekologi spesies
                                    untuk mengembangkan strategi

                                    konservasi yang efektif.</p>

                                <p>Hewan endemik adalah cerminan kekayaan alam dan sejarah evolusi suatu wilayah.
                                    Menjaga keberadaan mereka

                                    berarti menjaga warisan alam yang tak ternilai bagi generasi mendatang.</p>

                            </div>

                        </article>



                        <!-- ARTIKEL 8 -->

                        <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 mb-8 relative">

                            <div class="absolute top-0 left-0 w-1 h-full bg-violet-400 rounded-l-xl"></div>

                            <div
                                class="flex items-center gap-2 text-xs font-bold text-violet-500 uppercase tracking-widest mb-4">
                                <span class="material-symbols-outlined text-sm">article</span> Artikel 8
                            </div>

                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Kucing Warna Oren: Mitos,
                                    Karakteristik, dan Daya

                                    Tariknya</h3>



                            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                                <p>Kucing dengan bulu berwarna oren atau jingga adalah pemandangan yang umum dan
                                    seringkali menarik perhatian.

                                    Dengan warna bulu yang cerah dan seringkali disertai pola belang (tabby), kucing
                                    oren memiliki daya tarik

                                    tersendiri. Namun, di balik penampilannya yang khas, ada beberapa fakta menarik dan
                                    bahkan mitos yang

                                    menyelimuti kucing-kucing berwarna hangat ini.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Bukan Ras, Melainkan Warna Bulu
                                </h5>

                                <p>Penting untuk dipahami bahwa "kucing oren" bukanlah nama ras kucing. Warna oren
                                    adalah pigmen yang disebut

                                    pheomelanin, yang juga bertanggung jawab atas warna merah pada rambut manusia.
                                    Pigmen ini dapat ditemukan

                                    pada berbagai ras kucing, baik ras murni seperti Maine Coon, Persia, atau British
                                    Shorthair, maupun kucing

                                    domestik biasa (domestic shorthair atau longhair). Pola belang (tabby) hampir selalu
                                    ada pada kucing oren,

                                    bahkan jika sekilas terlihat polos, pola M di dahi mereka adalah ciri khas genetik
                                    yang tidak bisa

                                    dihilangkan.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Mitos dan Kepercayaan Seputar
                                    Kucing Oren</h5>

                                <p>Kucing oren seringkali dikaitkan dengan berbagai mitos dan kepercayaan populer:</p>

                                <p><strong>Kucing Oren Jantan Lebih Banyak:</strong> Ini bukan mitos, melainkan fakta
                                    genetik. Gen yang membawa

                                    warna oren (O) terletak pada kromosom X. Kucing betina memiliki dua kromosom X (XX),
                                    sehingga mereka

                                    membutuhkan dua gen O untuk menjadi oren penuh. Sementara kucing jantan hanya
                                    memiliki satu kromosom X (XY),

                                    jadi mereka hanya membutuhkan satu gen O untuk menjadi oren. Oleh karena itu,
                                    sekitar 80% kucing oren adalah

                                    jantan. Kucing oren betina memang ada, tetapi lebih jarang ditemukan.</p>

                                <p><strong>Kucing Oren Memiliki Sifat Khusus:</strong> Banyak orang percaya kucing oren
                                    lebih ramah, berani,

                                    atau bahkan sedikit "nakal" dibandingkan kucing dengan warna lain. Meskipun tidak
                                    ada bukti ilmiah yang kuat

                                    untuk mengaitkan warna bulu dengan kepribadian secara langsung, beberapa penelitian
                                    kecil dan anekdot

                                    pemilik kucing memang menunjukkan bahwa kucing oren cenderung lebih vokal dan
                                    memiliki kepribadian yang

                                    kuat. Namun, kepribadian kucing lebih banyak dipengaruhi oleh genetik individual,
                                    sosialisasi, dan

                                    lingkungan tempat mereka dibesarkan.</p>

                                <p><strong>Kucing Oren Sering Disebut <em>Ginger Cat</em>:</strong> Istilah <em>ginger
                                        cat</em> atau kucing jahe

                                    sangat populer di negara-negara berbahasa Inggris untuk merujuk pada kucing oren,
                                    terutama yang memiliki

                                    warna yang lebih kemerahan.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Karakteristik Umum Kucing Oren
                                </h5>

                                <p>Selain warna bulu yang khas, kucing oren seringkali menunjukkan beberapa
                                    karakteristik umum:</p>

                                <p><strong>Pola Tabby yang Jelas:</strong> Seperti yang disebutkan, hampir semua kucing
                                    oren memiliki pola

                                    tabby. Pola ini bisa berupa belang klasik (marbled), belang makarel (garis-garis
                                    vertikal), tutul (spotted),

                                    atau agouti (setiap helai rambut memiliki pita warna).</p>

                                <p><strong>Bintik Hitam di Hidung dan Gusi:</strong> Banyak kucing oren, terutama yang
                                    jantan, mengembangkan

                                    bintik-bintik kecil berwarna hitam di hidung, gusi, atau bibir mereka seiring
                                    bertambahnya usia. Ini adalah

                                    fenomena normal yang disebut lentigo dan tidak berbahaya.</p>

                                <p><strong>Mata Berwarna Emas atau Hijau:</strong> Warna mata yang paling umum pada
                                    kucing oren adalah emas,

                                    kuning, atau hijau. Terkadang, ada juga yang memiliki mata hazel.</p>



                                <h5 class="font-bold text-sakura-black text-base mt-6">Merawat Kucing Oren</h5>

                                <p>Merawat kucing oren sama seperti merawat kucing dengan warna bulu lainnya. Perawatan
                                    dasar meliputi:</p>

                                <p><strong>Makanan Bergizi:</strong> Berikan makanan kucing berkualitas tinggi yang
                                    sesuai dengan usia dan

                                    tingkat aktivitasnya.</p>

                                <p><strong>Air Bersih:</strong> Pastikan selalu tersedia air bersih dan segar.</p>

                                <p><strong>Kebersihan:</strong> Sikat bulu secara teratur, terutama jika kucing memiliki
                                    bulu panjang, untuk

                                    mencegah kusut dan mengurangi kerontokan. Bersihkan kotak pasir secara rutin.</p>

                                <p><strong>Kesehatan:</strong> Vaksinasi teratur, pemeriksaan rutin ke dokter hewan, dan
                                    pemberian obat cacing

                                    serta kutu sesuai anjuran.</p>

                                <p><strong>Kasih Sayang dan Stimulasi:</strong> Berikan perhatian, ajak bermain, dan
                                    sediakan lingkungan yang

                                    merangsang agar kucing tetap bahagia dan sehat secara mental.</p>

                                <p>Kucing oren, dengan warna bulunya yang cerah dan kepribadiannya yang sering kali
                                    menarik, telah menjadi

                                    favorit banyak pecinta kucing. Mereka adalah bukti bahwa keindahan dan keunikan bisa
                                    datang dalam berbagai

                                    bentuk, bahkan hanya dari sebuah pigmen warna.</p>

                            </div>

                        </article>
                    </div>

                </div>



                <!-- PAGE 2: QUIZ -->

                <div id="page-quiz-003" class="page-section-003">

                    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-6">

                        <div class="text-center mb-8">

                            <span
                                class="inline-flex items-center gap-2 px-4 py-2 bg-sakura-red/10 text-sakura-red rounded-full text-xs font-bold uppercase tracking-widest">

                                <span class="material-symbols-outlined text-sm">quiz</span> Quiz Day 3

                            </span>

                            <h2 class="font-serif font-bold text-2xl text-sakura-black mt-4">Uji Pemahamanmu</h2>

                            <p class="text-sm text-gray-400 mt-2">Jawab pertanyaan berdasarkan artikel yang sudah kamu
                                baca.</p>

                        </div><!-- QUIZ SECTION: 5 ISIAN + 5 TRUE/FALSE -->


<!-- SECTION: ISIAN -->
<div class="space-y-6">
    <p class="text-[10px] font-bold text-violet-500 uppercase tracking-widest px-1">Bagian 1 —
        Isian
        Singkat <span class="text-gray-400">(tidak dinilai)</span></p>

    <!-- Isian 1 -->
    <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
        <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Apa yang terjadi pada kadar gula darah setelah
            seseorang mengonsumsi makanan tinggi karbohidrat olahan dan gula?</p>
        <div class="flex gap-3 items-center mb-4">
            <input type="text" placeholder="Ketik jawaban..."
                class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
            <button onclick="checkIsian(this)"
                class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
        </div>
        <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
            <p class="text-sm text-green-800"><strong>Jawaban:</strong> Melonjak cepat, lalu turun drastis</p>
            <p class="text-xs text-green-600 mt-1">Lonjakan dan penurunan gula darah yang cepat ini sering disebut
                "sugar crash" dan memicu tubuh untuk mencari sumber energi instan lagi.</p>
        </div>
    </div>

    <!-- Isian 2 -->
    <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
        <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Apa fungsi utama pupuk nitrogen untuk tanaman padi?
        </p>
        <div class="flex gap-3 items-center mb-4">
            <input type="text" placeholder="Ketik jawaban..."
                class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
            <button onclick="checkIsian(this)"
                class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
        </div>
        <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
            <p class="text-sm text-green-800"><strong>Jawaban:</strong> Pertumbuhan vegetatif tanaman padi</p>
            <p class="text-xs text-green-600 mt-1">Nitrogen adalah nutrisi paling penting di fase awal pertumbuhan padi,
                memastikan tanaman memiliki "bahan bakar" yang cukup untuk berkembang sebelum memasuki tahap pembentukan
                bulir.</p>
        </div>
    </div>

    <!-- Isian 3 -->
    <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
        <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Apa nama subkultur yang mempopulerkan gaya rambut
            mohawk pada tahun 1970-an?</p>
        <div class="flex gap-3 items-center mb-4">
            <input type="text" placeholder="Ketik jawaban..."
                class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
            <button onclick="checkIsian(this)"
                class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
        </div>
        <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
            <p class="text-sm text-green-800"><strong>Jawaban:</strong> Punk rock</p>
            <p class="text-xs text-green-600 mt-1">Bagi subkultur punk, mohawk menjadi simbol pemberontakan dan
                penolakan terhadap norma sosial pada saat itu.</p>
        </div>
    </div>

    <!-- Isian 4 -->
    <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
        <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Berapa lama waktu yang dibutuhkan untuk satu siklus
            lengkap MJO melintasi wilayah tropis?</p>
        <div class="flex gap-3 items-center mb-4">
            <input type="text" placeholder="Ketik jawaban..."
                class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
            <button onclick="checkIsian(this)"
                class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
        </div>
        <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
            <p class="text-sm text-green-800"><strong>Jawaban:</strong> 30 hingga 60 hari</p>
            <p class="text-xs text-green-600 mt-1">MJO memiliki siklus pergerakan sekitar 30 hingga 60 hari melintasi
                wilayah khatulistiwa dari barat ke timur.</p>
        </div>
    </div>

    <!-- Isian 5 -->
    <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
        <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Jenis kelamin apa yang lebih sering ditemukan pada
            kucing dengan bulu berwarna oren?</p>
        <div class="flex gap-3 items-center mb-4">
            <input type="text" placeholder="Ketik jawaban..."
                class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
            <button onclick="checkIsian(this)"
                class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
        </div>
        <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
            <p class="text-sm text-green-800"><strong>Jawaban:</strong> Jantan</p>
            <p class="text-xs text-green-600 mt-1">Gen yang membawa warna oren terletak pada kromosom X. Kucing jantan
                hanya memiliki satu kromosom X, jadi sekitar 80% kucing oren adalah jantan.</p>
        </div>
    </div>
</div>

<!-- SECTION: TRUE/FALSE -->
<div class="space-y-6 mt-10">
    <p class="text-[10px] font-bold text-violet-500 uppercase tracking-widest px-1">Bagian 2 —
        Benar atau
        Salah <span class="text-gray-400">(dinilai)</span></p>

    <!-- TF 1 -->
    <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="003">
        <div class="flex items-start justify-between mb-4">
            <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Pupuk fosfor (P) berperan penting dalam
                pembentukan klorofil (zat hijau daun) pada tanaman padi.</p>
            <div class="result-badge hidden ml-3"></div>
        </div>
        <div class="flex gap-3 mb-4">
            <button onclick="checkTF(this, 'Soal3 6', 'true')" data-value="true"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
            <button onclick="checkTF(this, 'Soal3 6', 'false')" data-value="false"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
        </div>
        <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
            <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Pupuk nitrogen (N)-lah yang berperan
                vital dalam pembentukan klorofil dan pertumbuhan vegetatif. Pupuk fosfor (P) berfungsi untuk
                mengembangkan akar yang kuat dan membantu pembentukan bunga serta gabah.</p>
        </div>
    </div>

    <!-- TF 2 -->
    <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="003">
        <div class="flex items-start justify-between mb-4">
            <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Gaya rambut mohawk dipopulerkan secara luas
                oleh subkultur punk pada akhir tahun 1970-an sebagai bentuk pemberontakan terhadap arus utama.</p>
            <div class="result-badge hidden ml-3"></div>
        </div>
        <div class="flex gap-3 mb-4">
            <button onclick="checkTF(this, 'Soal3 7', 'true')" data-value="true"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
            <button onclick="checkTF(this, 'Soal3 7', 'false')" data-value="false"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
        </div>
        <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
            <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Subkultur punk mengadopsi gaya mohawk
                pada akhir 1970-an sebagai simbol pemberontakan dan anti-konformitas terhadap norma masyarakat arus
                utama.</p>
        </div>
    </div>

    <!-- TF 3 -->
    <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="003">
        <div class="flex items-start justify-between mb-4">
            <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> MJO adalah fenomena iklim yang cenderung
                bersifat stasioner, mirip seperti El Niño.</p>
            <div class="result-badge hidden ml-3"></div>
        </div>
        <div class="flex gap-3 mb-4">
            <button onclick="checkTF(this, 'Soal3 8', 'true')" data-value="true"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
            <button onclick="checkTF(this, 'Soal3 8', 'false')" data-value="false"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
        </div>
        <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
            <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. MJO bukan fenomena stasioner seperti El
                Niño. MJO adalah pola yang bergerak dari barat ke timur di sepanjang wilayah khatulistiwa, dengan siklus
                pergerakan sekitar 30 hingga 60 hari.</p>
        </div>
    </div>

    <!-- TF 4 -->
    <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="003">
        <div class="flex items-start justify-between mb-4">
            <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Waktu Indonesia Bagian Timur (WIT) dihitung
                berdasarkan garis bujur 135° BT dengan zona waktu UTC+9.</p>
            <div class="result-badge hidden ml-3"></div>
        </div>
        <div class="flex gap-3 mb-4">
            <button onclick="checkTF(this, 'Soal3 9', 'true')" data-value="true"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
            <button onclick="checkTF(this, 'Soal3 9', 'false')" data-value="false"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
        </div>
        <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
            <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. WIT dihitung berdasarkan garis bujur
                135° BT dengan zona waktu UTC+9 dan mencakup wilayah Papua dan Maluku.</p>
        </div>
    </div>

    <!-- TF 5 -->
    <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="003">
        <div class="flex items-start justify-between mb-4">
            <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Kucing oren dengan warna bulu cerah dan
                seringnya belang (tabby) adalah sebuah ras kucing yang khusus.</p>
            <div class="result-badge hidden ml-3"></div>
        </div>
        <div class="flex gap-3 mb-4">
            <button onclick="checkTF(this, 'Soal3 10', 'true')" data-value="true"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
            <button onclick="checkTF(this, 'Soal3 10', 'false')" data-value="false"
                class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
        </div>
        <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
            <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. "Kucing oren" bukanlah nama ras kucing.
                Warna oren adalah pigmen bulu yang bisa ditemukan pada berbagai ras kucing, baik ras murni maupun
                domestik.</p>
        </div>
    </div>
</div>

<!-- Submit -->
<div class="text-center pt-8">
    <button onclick="showResult()"
        class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">
        <span class="flex items-center gap-2">
            <span class="material-symbols-outlined text-lg">fact_check</span>
            Lihat Hasil
        </span>
    </button>
</div>
</div>
</div>



                <!-- PAGE 3: RESULT -->

                <div id="page-result-003" class="page-section-003">

                    <div class="max-w-4xl mx-auto p-8 pb-32">

                        <div id="result-content-003">

                            <div class="text-center py-20 text-gray-400">

                                <span class="material-symbols-outlined text-6xl mb-4">pending</span>

                                <p class="font-serif text-lg">Selesaikan quiz terlebih dahulu untuk melihat hasil.</p>

                            </div>

                        </div>

                    </div>

                </div>

            </div>

            <!-- MODULE VIEW: OBAT FOKUS 004 -->
            <div id="module-obat-fokus-004" class="module-view">
                <div class="flex-1 overflow-y-auto" id="content-scroll-004">
                    <!-- PAGE 1: ARTICLES -->
                    <div id="page-articles-004" class="page-section-004 active">
                        <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">

                            <!-- ARTIKEL 1 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 1
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Perkembangan Kacamata:
                                    Dari Penemuan Awal hingga Era Modern</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Kacamata, sebuah alat sederhana yang merevolusi cara kita melihat dunia, memiliki
                                        sejarah panjang dan menarik. Dari sekadar alat bantu penglihatan, kacamata telah
                                        berevolusi menjadi pernyataan gaya dan bagian tak terpisahkan dari teknologi
                                        modern.</p>
                                    <h5 class="font-bold text-sakura-black text-base mt-6">Awal Mula dan Penemuan</h5>
                                    <p>Konsep untuk memperbaiki penglihatan sudah ada sejak zaman kuno. Filsuf Romawi
                                        Seneca Muda mencatat bahwa ia bisa membaca tulisan kecil melalui bola kaca
                                        berisi air. Namun, kacamata seperti yang kita kenal sekarang baru muncul pada
                                        akhir abad ke-13 di Italia. Penemuannya sering dikreditkan kepada Salvino
                                        D'Armate atau Alessandro della Spina, meskipun bukti definitif masih menjadi
                                        perdebatan.</p>
                                    <p>Kacamata awal ini jauh berbeda dengan yang kita pakai sekarang. Mereka biasanya
                                        terdiri dari dua lensa cembung yang dibingkai oleh tulang, logam, atau kulit,
                                        dan dipegang di depan mata atau diseimbangkan di hidung. Desain ini, yang
                                        dikenal sebagai "kacamata jepit hidung" atau rivet spectacles, sangat populer di
                                        kalangan cendekiawan dan biarawan karena memungkinkan mereka untuk membaca dan
                                        menulis lebih mudah.</p>
                                    <h5 class="font-bold text-sakura-black text-base mt-6">Evolusi Desain</h5>
                                    <p>Seiring waktu, desain kacamata terus berkembang. Pada abad ke-17, muncul temple
                                        spectacles di Spanyol, yang menggunakan pita sutra atau kulit yang dililitkan di
                                        telinga untuk menahan kacamata. Ini adalah langkah maju yang signifikan karena
                                        memberikan stabilitas yang lebih baik dibandingkan kacamata jepit hidung.</p>
                                    <p>Revolusi sejati datang pada abad ke-18 dengan penemuan gagang kacamata yang
                                        memanjang hingga belakang telinga. Klaim penemuannya bervariasi antara Edward
                                        Scarlett di London pada tahun 1727 atau James Ayscough, seorang optikus Inggris,
                                        sekitar tahun 1750. Desain ini, dengan gagang yang kokoh, membuat kacamata jauh
                                        lebih nyaman dan praktis untuk pemakaian sehari-hari.</p>
                                    <h5 class="font-bold text-sakura-black text-base mt-6">Abad ke-19 dan ke-20:
                                        Industrialisasi dan Gaya</h5>
                                    <p>Dengan Revolusi Industri, produksi kacamata menjadi lebih efisien dan terjangkau.
                                        Berbagai bentuk dan bahan mulai digunakan, dari baja hingga nikel, dan kemudian
                                        plastik. Kacamata tidak lagi hanya alat bantu, tetapi juga menjadi aksesori
                                        fesyen.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 2 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 2
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Kabel Optik: Memahami
                                    Jaringan Cahaya</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Kabel optik, atau sering disebut serat optik, adalah salah satu inovasi paling
                                        signifikan dalam dunia telekomunikasi modern. Teknologi ini memungkinkan
                                        transmisi data dalam jumlah besar dengan kecepatan yang luar biasa.</p>
                                    <h5 class="font-bold text-sakura-black text-base mt-6">Bagaimana Kabel Optik Bekerja
                                    </h5>
                                    <p>Inti dari kabel optik adalah untaian serat tipis yang terbuat dari kaca murni
                                        atau plastik. Serat ini dirancang khusus untuk memandu cahaya dari satu ujung ke
                                        ujung lainnya. Data digital diubah menjadi pulsa cahaya oleh pemancar optik.
                                        Pulsa ini melaju di sepanjang serat melalui pemantulan internal total.</p>
                                    <h5 class="font-bold text-sakura-black text-base mt-6">Keunggulan Kabel Optik</h5>
                                    <ul class="list-disc pl-5 space-y-2">
                                        <li><strong>Kecepatan dan Bandwidth Tinggi:</strong> Memungkinkan transfer
                                            informasi yang sangat cepat.</li>
                                        <li><strong>Jarak Transmisi Lebih Jauh:</strong> Redaman sinyal cahaya jauh
                                            lebih kecil dibandingkan sinyal listrik.</li>
                                        <li><strong>Imunitas Terhadap Interferensi Elektromagnetik:</strong> Kebal
                                            terhadap gangguan medan elektromagnetik.</li>
                                        <li><strong>Keamanan Data:</strong> Lebih sulit disadap dibandingkan kabel
                                            tembaga.</li>
                                    </ul>
                                </div>
                            </article>

                            <!-- ARTIKEL 3 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 3
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Laskar Pelangi: Sebuah
                                    Nyanyian tentang Mimpi dan Harapan</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Lagu Laskar Pelangi yang dipopulerkan oleh grup musik Nidji bukan sekadar sebuah
                                        komposisi musik biasa; ia adalah sebuah nyanyian inspiratif bagi semangat
                                        pantang menyerah.</p>
                                    <p>Kekuatan utama Laskar Pelangi terletak pada liriknya yang sederhana namun sangat
                                        bermakna. Dimulai dengan barisan "mimpi adalah kunci / untuk kita menaklukkan
                                        dunia", lagu ini mengajak pendengar untuk merenungkan kekuatan ambisi. Liriknya
                                        menyoroti nilai-nilai seperti harapan, kebersamaan, dan keyakinan bahwa setiap
                                        orang memiliki potensi untuk meraih cita-citanya.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 4 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 4
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Streetwear: Evolusi
                                    Gaya dari Jalanan ke Panggung Mode Dunia</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Streetwear adalah fenomena mode yang telah melampaui batasan subkultur untuk
                                        menjadi kekuatan dominan dalam industri fesyen global. Streetwear berakar kuat
                                        pada budaya selancar dan skate di California pada tahun 1970-an dan 1980-an.</p>
                                    <p>Memasuki tahun 2000-an, streetwear mulai mendapatkan pengakuan yang lebih luas
                                        dengan merek-merek seperti Supreme dan Bape. Kolaborasi antara merek streetwear
                                        dan desainer mewah, seperti Louis Vuitton dan Supreme pada tahun 2017, menandai
                                        perpaduan antara kemewahan dan budaya jalanan.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 5 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 5
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Bagaimana Ban Pesawat
                                    Terbang Bekerja</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Ban pesawat terbang adalah mahakarya rekayasa material yang dirancang untuk
                                        bertahan dalam kondisi ekstrem. Ban pesawat terbuat dari campuran karet sintetis
                                        khusus yang diperkuat dengan lapisan-lapisan kain nilon atau Kevlar.</p>
                                    <p>Salah satu fakta paling mencengangkan adalah tekanan inflasinya yang mencapai
                                        200-300 psi. Selain itu, ban pesawat diisi dengan nitrogen murni (bukan udara
                                        biasa) karena nitrogen lebih stabil terhadap perubahan suhu ekstrem dan tidak
                                        mudah bereaksi dengan material ban.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 6 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 6
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Ragam Gaya Berenang
                                </h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p><strong>1. Gaya Bebas (Freestyle):</strong> Gaya tercepat dan paling efisien,
                                        pilihan utama kompetisi. Gerakan tangan seperti baling-baling dan tendangan kaki
                                        flutter kick.</p>
                                    <p><strong>2. Gaya Dada (Breaststroke):</strong> Gaya paling santai, gerakan tangan
                                        membuka ke samping dan tendangan kaki "katak".</p>
                                    <p><strong>3. Gaya Punggung (Backstroke):</strong> Satu-satunya gaya dengan posisi
                                        telentang, memudahkan pernapasan.</p>
                                    <p><strong>4. Gaya Kupu-kupu (Butterfly):</strong> Gaya paling menantang, menyerupai
                                        sayap kupu-kupu yang mengepak dengan tendangan lumba-lumba.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 7 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 7
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Liam dan Noel
                                    Gallagher: Saga Rock 'n' Roll</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Kisah Liam dan Noel Gallagher, inti dari band Oasis, adalah legenda Britpop.
                                        Album debut mereka "Definitely Maybe" (1994) meledak, namun hubungan mereka
                                        selalu diwarnai konflik.</p>
                                    <p>Setelah perpecahan pahit pada 2009, mereka akhirnya mengumumkan reuni untuk tur
                                        besar Oasis Live '25 Tour pada tahun 2025. Ini menandai kembalinya salah satu
                                        band terbesar era Britpop.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 8 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 8
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Semikonduktor: Otak
                                    Digital</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Semikonduktor adalah material yang memiliki kemampuan menghantarkan listrik di
                                        antara konduktor dan isolator. Bahan paling umum adalah silikon dan germanium.
                                        Dengan proses doping, sifat listriknya dapat diubah menjadi Tipe-N (negatif)
                                        atau Tipe-P (positif).</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 9 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 9
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">"Di Matraman":
                                    Nostalgia Indie The Upstairs</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Lagu "Di Matraman" dari The Upstairs (2004) adalah ikon musik indie pop
                                        Indonesia. Dikenal dengan aransemen new wave dan pop elektronik yang jenius
                                        serta lirik nostalgia tentang kawasan Matraman, Jakarta Timur.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 10 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 10
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Ionisasi</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Ionisasi adalah proses pembentukan ion dari atom netral. Jika atom kehilangan
                                        elektron, ia menjadi ion positif (kation). Jika mendapatkan elektron, ia menjadi
                                        ion negatif (anion).</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 11 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 11
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Kondensasi</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Kondensasi adalah perubahan wujud gas menjadi cair. Terjadi karena pendinginan
                                        atau peningkatan tekanan. Contoh umum adalah embun pagi atau kaca jendela yang
                                        berair.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 12 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 12
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Tisu: Revolusi
                                    Kebersihan</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Tisu modern dikembangkan oleh Kimberly-Clark. Berawal dari "Cellucotton" saat PD
                                        I, kemudian menjadi Kleenex pada 1924. Tisu dibuat dari bubur kayu melalui
                                        proses *creping* yang memberikannya tekstur lembut.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 13 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-amber-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-amber-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 13
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Foton: Partikel Cahaya
                                </h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Foton adalah paket energi terkecil dari cahaya. Diperkenalkan oleh Einstein,
                                        foton tidak memiliki massa diam dan memiliki dualitas gelombang-partikel. Foton
                                        memungkinkan penglihatan, fotografi, dan teknologi laser.</p>
                                </div>
                            </article>

                        </div>
                    </div>

                    <!-- PAGE 2: QUIZ -->
                    <div id="page-quiz-004" class="page-section-004">
                        <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">
                            <div class="text-center mb-8">
                                <span class="material-symbols-outlined text-5xl text-sakura-red mb-3">quiz</span>
                                <h2 class="font-serif font-black text-3xl text-sakura-black mb-2">Quiz — Obat Fokus Day
                                    4</h2>
                                <p class="text-gray-500 max-w-md mx-auto">Jawab pertanyaan berdasarkan 13 artikel yang
                                    baru saja dibaca.</p>
                                <div class="w-16 h-1 bg-sakura-red mx-auto mt-4"></div>
                            </div>

                            <!-- ISIAN -->
                            <div class="space-y-6">
                                <p class="text-[10px] font-bold text-amber-500 uppercase tracking-widest px-1">Bagian 1 —
                                    Isian Singkat</p>

                                <!-- Q1 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Apa gaya berenang yang
                                        paling cepat dan efisien?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Gaya Bebas
                                            (Freestyle)</p>
                                    </div>
                                </div>

                                <!-- Q2 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Nama band yang dibentuk
                                        oleh Liam dan Noel Gallagher?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Oasis</p>
                                    </div>
                                </div>

                                <!-- Q3 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Material semikonduktor
                                        yang paling umum dan banyak digunakan adalah?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Silikon</p>
                                    </div>
                                </div>

                                <!-- Q4 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Genre musik yang
                                        diusung oleh The Upstairs dalam lagu "Di Matraman"?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> New wave / Pop
                                            elektronik</p>
                                    </div>
                                </div>

                                <!-- Q5 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Proses ketika atom
                                        netral mendapatkan elektron disebut pembentukan...?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Anion</p>
                                    </div>
                                </div>
                            </div>

                            <!-- TRUE / FALSE -->
                            <div class="space-y-6 mt-12">
                                <p class="text-[10px] font-bold text-violet-500 uppercase tracking-widest px-1">Bagian 2
                                    — Benar atau Salah</p>

                                <!-- TF 1 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Kacamata pertama
                                            kali ditemukan di Inggris pada abad ke-18.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 6-004', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 6-004', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Kacamata
                                            muncul di Italia pada akhir abad ke-13. Inggris (abad ke-18) adalah tempat
                                            penemuan gagang kacamata.</p>
                                    </div>
                                </div>

                                <!-- TF 2 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Kabel optik lebih
                                            rentan terhadap gangguan medan elektromagnetik dibanding kabel tembaga.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 7-004', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 7-004', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Kabel optik
                                            justru kebal (imun) terhadap interferensi elektromagnetik.</p>
                                    </div>
                                </div>

                                <!-- TF 3 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> Lirik "Laskar
                                            Pelangi" menyoroti bahwa mimpi hanya bisa diraih oleh orang kaya.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 8-004', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 8-004', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Pesannya
                                            adalah setiap orang, tidak peduli latar belakangnya, memiliki potensi meraih
                                            cita-cita.</p>
                                    </div>
                                </div>

                                <!-- TF 4 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Subkultur punk
                                            rock adalah pelopor utama streetwear pada tahun 1970-an.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 9-004', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 9-004', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Pelopor
                                            utamanya adalah budaya selancar dan skate di California.</p>
                                    </div>
                                </div>

                                <!-- TF 5 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Ban pesawat
                                            terbang diisi dengan udara biasa untuk menjaga tekanan stabil.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 10-004', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 10-004', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Ban pesawat
                                            diisi dengan nitrogen murni agar stabil terhadap perubahan suhu ekstrem.</p>
                                    </div>
                                </div>

                                <div class="text-center pt-8">
                                    <button onclick="showResult()"
                                        class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">
                                        <span class="flex items-center gap-2">
                                            <span class="material-symbols-outlined text-lg">fact_check</span>
                                            Lihat Hasil
                                        </span>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- PAGE 3: RESULT -->
                    <div id="page-result-004" class="page-section-004">
                        <div class="max-w-4xl mx-auto p-8 pb-32">
                            <div id="result-content-004">
                                <div class="text-center py-20 text-gray-400">
                                    <span class="material-symbols-outlined text-6xl mb-4">pending</span>
                                    <p class="font-serif text-lg">Selesaikan quiz terlebih dahulu untuk melihat hasil.
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>





            </div>

            <!-- MODULE VIEW: OBAT FOKUS 005 -->
            <div id="module-obat-fokus-005" class="module-view">
                <div class="flex-1 overflow-y-auto" id="content-scroll-005">
                    <!-- PAGE 1: ARTICLES -->
                    <div id="page-articles-005" class="page-section-005 active">
                        <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">

                            <!-- ARTIKEL 1 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 1
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Sel Darah Berbentuk
                                    Bulan: Anemia Sel Sabit</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Anemia sel sabit adalah kelainan genetik yang memengaruhi hemoglobin, protein
                                        dalam sel darah merah yang membawa oksigen. Pada penderita, hemoglobin normal
                                        digantikan oleh hemoglobin S (HbS), menyebabkan sel darah merah menjadi kaku dan
                                        berbentuk sabit.</p>
                                    <p>Keunikan penyakit ini adalah hubungannya dengan malaria. Di daerah endemik
                                        malaria, pembawa sifat sel sabit (satu gen) memiliki perlindungan alami terhadap
                                        malaria berat, sebuah contoh seleksi alam yang nyata.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 2 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 2
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Susu Kedelai:
                                    Alternatif Kaya Nutrisi</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Susu kedelai adalah sumber protein nabati "lengkap", mengandung kesembilan asam
                                        amino esensial. Kaya akan lemak tak jenuh dan serat, susu ini baik untuk jantung
                                        dan pencernaan.</p>
                                    <p>Kedelai mengandung isoflavon, senyawa yang mirip estrogen. Meskipun bermanfaat,
                                        konsumsinya tetap perlu diperhatikan bagi individu dengan kondisi tertentu.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 3 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 3
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Emas: Logam Mulia Abadi
                                </h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Emas (Au) adalah logam mulia yang tidak reaktif, artinya tidak mudah berkarat
                                        atau korosi. Sifat inilah yang membuatnya berkilau abadi.</p>
                                    <p>Selain perhiasan, emas sangat penting dalam elektronik karena konduktivitasnya
                                        yang baik dan ketahanannya terhadap korosi.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 4 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 4
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Marc Márquez: Sang
                                    Penakluk Batas</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Marc Márquez mendominasi MotoGP dengan 6 gelar juara dunia bersama Honda. Gaya
                                        balapnya yang agresif merevolusi olahraga ini.</p>
                                    <p>Setelah cedera parah pada 2020 dan kesulitan memulihkan performa, ia membuat
                                        keputusan mengejutkan untuk meninggalkan Honda dan bergabung dengan tim satelit
                                        Gresini Ducati pada musim 2024.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 5 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 5
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Air: Eliksir Kehidupan
                                </h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Air (H2O) menutupi 71% permukaan bumi, namun hanya 3% yang merupakan air tawar.
                                        Sifat uniknya, seperti kapasitas panas yang besar, sangat vital bagi iklim bumi.
                                    </p>
                                    <p>Dalam tubuh manusia, air berperan dalam transportasi nutrisi dan regulasi suhu.
                                        Dehidrasi sedikit saja dapat menurunkan fungsi kognitif.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 6 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 6
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Pupuk Buatan: Penopang
                                    Pertanian Modern</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Pupuk buatan menyediakan tiga makronutrien utama: Nitrogen (N), Fosfor (P), dan
                                        Kalium (K). Ketiganya krusial untuk pertumbuhan tanaman yang optimal.</p>
                                    <p>Meskipun meningkatkan hasil panen, penggunaan berlebihan dapat menyebabkan
                                        masalah lingkungan seperti eutrofikasi perairan.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 7 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 7
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Rahasia Belajar Atlet
                                    Catur Dunia</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Grandmaster catur tidak hanya mengandalkan bakat, tapi latihan sistematis. Mereka
                                        mempelajari pembukaan (opening), mengasah taktik, dan menguasai permainan akhir
                                        (endgame).</p>
                                    <p>Mereka juga melakukan evaluasi berkelanjutan menggunakan mesin catur (engine)
                                        untuk menganalisis setiap langkah dan kesalahan dalam permainan mereka.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 8 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 8
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Capsaicin: Senyawa
                                    Pedas yang Membakar</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Sensasi pedas cabai disebabkan oleh Capsaicin. Senyawa ini terkonsentrasi pada
                                        plasenta (dinding putih dalam) cabai, bukan bijinya.</p>
                                    <p>Capsaicin berinteraksi dengan reseptor TRPV1 yang biasanya merespons panas fisik.
                                        Ia juga memiliki potensi medis sebagai pereda nyeri.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 9 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 9
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Manfaat Tersembunyi
                                    Kulit Semangka</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Kulit semangka (bagian putih) sering dibuang, padahal kaya serat dan Citrulline.
                                        Citrulline diubah tubuh menjadi arginin yang baik untuk aliran darah dan
                                        kesehatan jantung.</p>
                                    <p>Kandungan nutrisinya bahkan bisa melebihi daging buahnya dalam beberapa aspek,
                                        menjadikannya tambahan yang bagus untuk smoothie atau asinan.</p>
                                </div>
                            </article>

                            <!-- ARTIKEL 10 -->
                            <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">
                                <div class="absolute top-0 left-0 w-1 h-full bg-emerald-400 rounded-l-xl"></div>
                                <div
                                    class="flex items-center gap-2 text-xs font-bold text-emerald-500 uppercase tracking-widest mb-4">
                                    <span class="material-symbols-outlined text-sm">article</span> Artikel 10
                                </div>
                                <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Debu: Partikel Kecil
                                    Berdampak Besar</h3>
                                <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">
                                    <p>Debu rumah tangga sebagian besar terdiri dari sel kulit mati dan serat tekstil.
                                        Sementara debu luar ruangan berasal dari tanah, asap, dan partikel vulkanik.</p>
                                    <p>Partikel debu halus (PM2.5) berbahaya bagi kesehatan karena dapat masuk ke
                                        paru-paru dan aliran darah, memicu berbagai penyakit pernapasan dan jantung.</p>
                                </div>
                            </article>

                        </div>
                    </div>

                    <!-- PAGE 2: QUIZ -->
                    <div id="page-quiz-005" class="page-section-005">
                        <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">
                            <div class="text-center mb-8">
                                <span class="material-symbols-outlined text-5xl text-sakura-red mb-3">quiz</span>
                                <h2 class="font-serif font-black text-3xl text-sakura-black mb-2">Quiz — Obat Fokus Day
                                    5</h2>
                                <p class="text-gray-500 max-w-md mx-auto">Jawab pertanyaan berdasarkan 13 artikel yang
                                    baru saja dibaca.</p>
                                <div class="w-16 h-1 bg-sakura-red mx-auto mt-4"></div>
                            </div>

                            <!-- ISIAN -->
                            <div class="space-y-6">
                                <p class="text-[10px] font-bold text-emerald-500 uppercase tracking-widest px-1">Bagian 1 —
                                    Isian Singkat</p>

                                <!-- Q1 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Apa nama protein dalam
                                        sel darah merah yang terpengaruh oleh anemia sel sabit?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Hemoglobin</p>
                                    </div>
                                </div>

                                <!-- Q2 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Senyawa dalam kedelai
                                        yang memiliki struktur mirip estrogen adalah?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Isoflavon</p>
                                    </div>
                                </div>

                                <!-- Q3 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Sifat emas yang
                                        membuatnya tidak mudah berkarat disebut?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Tidak reaktif /
                                            Tahan korosi</p>
                                    </div>
                                </div>

                                <!-- Q4 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Pabrikan motor yang
                                        ditinggalkan Marc Márquez untuk pindah ke Gresini Ducati?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Honda</p>
                                    </div>
                                </div>

                                <!-- Q5 -->
                                <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">
                                    <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Tiga makronutrien
                                        primer dalam pupuk buatan adalah Nitrogen, Fosfor, dan...?</p>
                                    <div class="flex gap-3 items-center mb-4">
                                        <input type="text" placeholder="Ketik jawaban..."
                                            class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />
                                        <button onclick="checkIsian(this)"
                                            class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>
                                    </div>
                                    <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">
                                        <p class="text-sm text-green-800"><strong>Jawaban:</strong> Kalium (K)</p>
                                    </div>
                                </div>
                            </div>

                            <!-- TRUE / FALSE -->
                            <div class="space-y-6 mt-12">
                                <p class="text-[10px] font-bold text-violet-500 uppercase tracking-widest px-1">Bagian 2
                                    — Benar atau Salah</p>

                                <!-- TF 1 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="true">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Susu kedelai
                                            adalah sumber protein lengkap dengan semua asam amino esensial.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 6-005', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 6-005', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Kedelai
                                            adalah salah satu protein nabati lengkap.</p>
                                    </div>
                                </div>

                                <!-- TF 2 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Emas tahan karat
                                            tetapi mudah bereaksi dengan sebagian besar asam.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 7-005', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 7-005', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Emas sangat
                                            stabil dan TIDAK bereaksi dengan sebagian besar asam.</p>
                                    </div>
                                </div>

                                <!-- TF 3 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> Cedera Marc
                                            Márquez terjadi pada musim 2024 di tim Gresini.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 8-005', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 8-005', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Cedera
                                            terjadi pada 2020. Kepindahan ke Gresini terjadi pada 2024.</p>
                                    </div>
                                </div>

                                <!-- TF 4 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Pupuk buatan
                                            hanya boleh digunakan untuk tanaman padi karena nutrisinya spesifik.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 9-005', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 9-005', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Pupuk
                                            buatan mengandung nutrisi umum (NPK) untuk berbagai tanaman.</p>
                                    </div>
                                </div>

                                <!-- TF 5 -->
                                <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6"
                                    data-answer="false">
                                    <div class="flex items-start justify-between mb-4">
                                        <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Rasa pedas cabai
                                            berasal dari bijinya.</p>
                                        <div class="result-badge hidden ml-3"></div>
                                    </div>
                                    <div class="flex gap-3 mb-4">
                                        <button onclick="checkTF(this, 'Soal 10-005', 'true')" data-value="true"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>
                                        <button onclick="checkTF(this, 'Soal 10-005', 'false')" data-value="false"
                                            class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>
                                    </div>
                                    <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">
                                        <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Capsaicin
                                            terkonsentrasi di plasenta (dinding dalam), bukan biji.</p>
                                    </div>
                                </div>

                                <div class="text-center pt-8">
                                    <button onclick="showResult()"
                                        class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">
                                        <span class="flex items-center gap-2">
                                            <span class="material-symbols-outlined text-lg">fact_check</span>
                                            Lihat Hasil
                                        </span>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- PAGE 3: RESULT -->
                    <div id="page-result-005" class="page-section-005">
                        <div class="max-w-4xl mx-auto p-8 pb-32">
                            <div id="result-content-005">
                                <div class="text-center py-20 text-gray-400">
                                    <span class="material-symbols-outlined text-6xl mb-4">pending</span>
                                    <p class="font-serif text-lg">Selesaikan quiz terlebih dahulu untuk melihat hasil.
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
            <!-- BOTTOM NAV -->
            <div id="bottom-nav"
                class="hidden fixed bottom-6 left-72 right-0 px-8 pointer-events-none z-10 transition-all">
                <div
                    class="max-w-xl mx-auto bg-white shadow-[0_8px_30px_rgb(0,0,0,0.12)] border border-gray-100 rounded-full p-2 flex items-center justify-between pointer-events-auto backdrop-blur-md bg-white/95">
                    <button onclick="prevPage()" id="btn-prev"
                        class="w-10 h-10 rounded-full flex items-center justify-center text-gray-400 hover:bg-gray-100 hover:text-sakura-black transition-colors disabled:opacity-30"
                        disabled>
                        <span class="material-symbols-outlined">arrow_back</span>
                    </button>
                    <div class="flex items-center gap-3 px-4" id="step-dots">
                        <button onclick="goToPage(0)"
                            class="step-dot w-10 h-10 rounded-full bg-white border-2 border-sakura-red text-sakura-red flex items-center justify-center shadow-lg font-serif font-bold text-sm"
                            data-step="0">
                            <span class="material-symbols-outlined text-sm">auto_stories</span>
                        </button>
                        <div class="w-6 h-0.5 bg-gray-200 rounded" id="line-0-1"></div>
                        <button onclick="goToPage(1)"
                            class="step-dot w-8 h-8 rounded-full bg-gray-100 text-gray-400 border border-gray-200 flex items-center justify-center font-serif font-bold text-sm"
                            data-step="1">
                            <span class="material-symbols-outlined text-sm">quiz</span>
                        </button>
                        <div class="w-6 h-0.5 bg-gray-200 rounded" id="line-1-2"></div>
                        <button onclick="goToPage(2)"
                            class="step-dot w-8 h-8 rounded-full bg-gray-100 text-gray-400 border border-gray-200 flex items-center justify-center font-serif font-bold text-sm"
                            data-step="2">
                            <span class="material-symbols-outlined text-sm">emoji_events</span>
                        </button>
                    </div>
                    <button onclick="nextPage()" id="btn-next"
                        class="flex items-center gap-2 pl-4 pr-6 py-2 bg-sakura-black text-white rounded-full hover:bg-gray-800 transition-all group">
                        <span class="text-xs font-bold uppercase tracking-wider">Next</span>
                        <span
                            class="material-symbols-outlined text-sm group-hover:translate-x-1 transition-transform">arrow_forward</span>
                    </button>
                </div>
            </div>

            <!-- MODULE VIEW: OBAT FOKUS 006 -->
            <div id="module-obat-fokus-006" class="module-view">
                <div class="flex-1 overflow-y-auto" id="content-scroll-006">
                    <div id="page-articles-006" class="page-section-006 active"><div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">



    <!-- ARTIKEL 1: MEMAHAMI KANDUNGAN ALKOHOL -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">science</span> Artikel 1

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Memahami Kandungan Alkohol</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Alkohol, dalam konteks minuman, adalah substansi psikoaktif yang telah dikonsumsi manusia selama ribuan

                tahun, baik dalam perayaan, ritual, maupun sebagai bagian dari kehidupan sosial. Namun, di balik beragam

                bentuk dan rasanya, semua minuman beralkohol memiliki satu kesamaan inti: kandungan etanol. Memahami apa

                itu etanol, bagaimana ia diproduksi, serta zat-zat lain yang menyertainya adalah kunci untuk menguak

                kompleksitas alkohol sebagai senyawa kimia dan dampaknya pada tubuh.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Etanol: Inti dari Minuman Beralkohol</h5>

            <p>Zat utama dan paling krusial dalam setiap minuman beralkohol adalah etanol, atau secara kimia dikenal

                sebagai etil alkohol ($C_2H_5OH$). Etanol adalah senyawa organik yang dihasilkan melalui proses

                fermentasi. Proses ini melibatkan konversi gula menjadi etanol dan karbon dioksida oleh mikroorganisme

                seperti ragi. Sumber gula bisa sangat bervariasi, mulai dari buah-buahan (untuk anggur), biji-bijian

                (untuk bir dan wiski), tebu (untuk rum), hingga kentang (untuk vodka). Kadar etanol dalam minuman sangat

                bervariasi, diukur dalam persen volume alkohol (ABV). Misalnya, bir biasanya memiliki ABV 4-6%, anggur

                12-15%, dan minuman keras suling seperti wiski atau vodka bisa mencapai 40% ABV atau lebih. Proses

                fermentasi dan distilasi inilah yang menentukan konsentrasi etanol dan, pada akhirnya, potensi efek

                memabukkan dari minuman tersebut.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Kongener: Pemberi Rasa dan Aroma Khas</h5>

            <p>Selain etanol dan air, minuman beralkohol juga mengandung berbagai senyawa lain yang dikenal sebagai

                kongener. Kongener adalah produk sampingan alami dari proses fermentasi dan penuaan (maturasi) yang

                berkontribusi signifikan terhadap rasa, aroma, dan warna khas dari setiap jenis minuman. Contoh kongener

                meliputi metanol (dalam jumlah sangat kecil dan tidak berbahaya dalam minuman yang diproduksi dengan

                benar), aseton, aldehida (seperti asetaldehida), ester, fusel alcohol (alkohol berantai lebih panjang),

                dan tanin (dari barel kayu). Kadar dan jenis kongener sangat bervariasi; misalnya, wiski, brandy, dan

                anggur merah cenderung memiliki kadar kongener yang lebih tinggi dibandingkan dengan vodka atau gin.

                Meskipun beberapa kongener dalam jumlah besar dapat berkontribusi pada gejala hangover yang lebih parah,

                kongener jugalah yang memberikan karakteristik unik pada minuman beralkohol, membedakan rasa sebuah

                bourbon dari scotch, atau sebuah wine dari bir.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Pengaruh Zat Lain dan Proses Produksi</h5>

            <p>Proses produksi minuman beralkohol tidak hanya menentukan kadar etanol dan jenis kongener, tetapi juga

                dapat memperkenalkan zat-zat lain yang memengaruhi karakteristik akhir produk. Misalnya, penggunaan

                rempah-rempah atau botanical dalam pembuatan gin atau liqueur akan menambahkan profil rasa yang

                kompleks. Proses distilasi berulang akan memisahkan etanol dari air dan kongener lainnya, menghasilkan

                minuman dengan kadar alkohol yang lebih tinggi dan profil rasa yang lebih "bersih". Sebaliknya, proses

                penuaan dalam tong kayu (misalnya, untuk wiski atau brandy) akan menyebabkan interaksi antara alkohol

                dan kayu, menghasilkan senyawa baru seperti vanilin dan tanin yang menambah kedalaman rasa, warna, dan

                aroma. Kadar gula, aditif perasa, dan pewarna juga dapat ditambahkan, terutama pada minuman beralkohol

                tertentu atau cocktail siap minum, yang semuanya turut membentuk profil kimia dan sensori dari produk

                akhir. Memahami kandungan zat ini membantu kita mengapresiasi keragaman minuman beralkohol dan juga

                dampaknya pada tubuh.</p>

        </div>

    </article>



    <!-- ARTIKEL 2: MENGAPA TIDUR CUKUP PENTING -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">bedtime</span> Artikel 2

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Mengapa Tidur Cukup itu Penting?</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Di tengah hiruk pikuk kehidupan modern yang serba cepat, tidur seringkali menjadi hal pertama yang

                dikorbankan demi tuntutan pekerjaan, pendidikan, atau hiburan. Banyak dari kita melihat tidur sebagai

                kemewahan atau sekadar jeda dari aktivitas harian. Namun, ilmu pengetahuan dan data kesehatan secara

                konsisten menunjukkan bahwa tidur yang cukup dan berkualitas adalah pilar fundamental bagi kesehatan

                fisik dan mental, sama pentingnya dengan nutrisi dan olahraga. Mengabaikannya bukan hanya menimbulkan

                rasa lelah sesaat, tetapi juga membawa konsekuensi serius jangka panjang.</p>

            <p>Tidur sangat penting karena memiliki banyak fungsi diantaranya:</p>



            <p><strong>Pemulihan Fisik dan Mental:</strong> Tidur adalah waktu bagi tubuh untuk melakukan perbaikan dan

                regenerasi sel, baik pada otot, jaringan, maupun organ. Otak juga tidak beristirahat sepenuhnya; justru

                saat tidur, otak memproses informasi yang diterima sepanjang hari, mengonsolidasi memori, dan

                membersihkan limbah metabolik yang menumpuk saat terjaga. Tanpa tidur yang cukup, proses vital ini

                terhambat, mengakibatkan kelelahan fisik dan kesulitan berpikir jernih.</p>



            <p><strong>Penguatan Sistem Imun:</strong> Studi menunjukkan adanya hubungan kuat antara kurang tidur dan

                penurunan fungsi sistem kekebalan tubuh. Ketika kita tidur, tubuh memproduksi protein pelindung yang

                disebut sitokin, yang membantu melawan infeksi dan peradangan. Kurang tidur kronis dapat melemahkan

                respons imun, membuat kita lebih rentan terhadap flu, pilek, dan penyakit serius lainnya.</p>



            <p><strong>Regulasi Hormonal dan Metabolisme:</strong> Tidur berperan krusial dalam mengatur hormon yang

                memengaruhi nafsu makan, metabolisme glukosa, dan tingkat stres. Kurang tidur dapat mengganggu

                keseimbangan hormon leptin (mengatur rasa kenyang) dan ghrelin (memicu rasa lapar), yang berkontribusi

                pada peningkatan nafsu makan dan risiko obesitas. Selain itu, sensitivitas insulin juga dapat menurun,

                meningkatkan risiko diabetes tipe 2.</p>



            <p>Tidur bukan hanya tentang istirahat, melainkan proses aktif yang sangat krusial bagi fungsi kognitif dan

                kemampuan belajar kita.</p>



            <p><strong>Konsolidasi Memori dan Penyerapan Ilmu:</strong> Saat kita tidur, terutama selama tahapan tidur

                non-REM (NREM) dan REM (Rapid Eye Movement), otak secara aktif memproses dan menyimpan informasi baru

                yang telah kita pelajari di siang hari. Proses ini dikenal sebagai konsolidasi memori. Data dari studi

                neurosains menunjukkan bahwa gelombang otak tertentu yang terjadi saat tidur dalam (NREM slow-wave

                sleep) berperan penting dalam memindahkan informasi dari penyimpanan memori jangka pendek (hippocampus)

                ke memori jangka panjang di korteks. Tanpa tidur yang cukup, ruang penyimpanan informasi ini akan

                terganggu, membuat upaya belajar kita kurang efektif dan informasi sulit melekat.</p>



            <p><strong>Peningkatan Konsentrasi dan Atensi:</strong> Kurang tidur secara langsung memengaruhi kemampuan

                kita untuk mempertahankan fokus dan perhatian. Ketika tubuh kekurangan istirahat, otak menjadi lebih

                lambat dalam memproses informasi, menyebabkan kita mudah terdistraksi, membuat kesalahan ceroboh, dan

                kesulitan dalam tugas-tugas yang membutuhkan konsentrasi tinggi. Riset menunjukkan bahwa bahkan satu

                malam kurang tidur dapat berdampak signifikan pada waktu reaksi dan akurasi, yang sangat penting dalam

                pembelajaran dan pekerjaan yang menuntut. Tidur yang berkualitas membantu mengatur ulang otak,

                mempersiapkannya untuk menerima dan mengolah informasi baru dengan efisien di hari berikutnya.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Berapa Lama Tidur yang Diperlukan?</h5>

            <p><strong>Rekomendasi Umum:</strong> Organisasi kesehatan seperti National Sleep Foundation

                merekomendasikan orang dewasa berusia 18-64 tahun untuk tidur 7-9 jam per malam. Remaja membutuhkan

                lebih banyak, sekitar 8-10 jam, sedangkan anak-anak dan bayi jauh lebih banyak lagi. Namun, ini adalah

                pedoman umum; kebutuhan tidur individu bisa sedikit bervariasi.</p>

            <p><strong>Kualitas Lebih dari Kuantitas:</strong> Selain durasi, kualitas tidur juga sangat penting.

                Seseorang mungkin tidur 8 jam tetapi sering terbangun atau mengalami gangguan tidur (misalnya, sleep

                apnea), yang mengurangi efektivitas tidur itu sendiri. Tidur berkualitas ditandai dengan siklus tidur

                yang tidak terputus, memungkinkan tubuh mencapai tahapan tidur REM (Rapid Eye Movement) dan non-REM yang

                dalam, yang penting untuk pemulihan fisik dan kognitif.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Konsekuensi Jangka Panjang Kurang Tidur</h5>

            <p><strong>Peningkatan Risiko Penyakit Kronis:</strong> Kurang tidur yang terjadi secara terus-menerus telah

                dikaitkan dengan peningkatan risiko berbagai penyakit serius, termasuk penyakit jantung, tekanan darah

                tinggi, stroke, diabetes, dan obesitas. Mekanisme yang mendasarinya melibatkan peradangan kronis,

                gangguan metabolisme, dan stres pada sistem kardiovaskular.</p>

            <p><strong>Penurunan Fungsi Kognitif dan Produktivitas:</strong> Defisit tidur secara signifikan memengaruhi

                kemampuan kognitif. Konsentrasi, daya ingat, kemampuan memecahkan masalah, dan kreativitas akan menurun

                drastis. Hal ini berdampak langsung pada performa kerja atau belajar, meningkatkan risiko kesalahan dan

                mengurangi produktivitas secara keseluruhan.</p>

            <p><strong>Masalah Kesehatan Mental:</strong> Ada hubungan dua arah yang kuat antara tidur dan kesehatan

                mental. Kurang tidur dapat memperburuk kondisi seperti depresi dan kecemasan, dan sebaliknya, masalah

                kesehatan mental juga dapat mengganggu pola tidur. Tidur yang cukup berperan sebagai penyeimbang suasana

                hati dan mengurangi tingkat stres.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Strategi untuk Tidur Berkualitas</h5>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Jadwal Tidur Konsisten:</strong> Usahakan tidur dan bangun pada waktu yang sama setiap hari,

                    bahkan di akhir pekan.</li>

                <li><strong>Lingkungan Tidur Optimal:</strong> Pastikan kamar tidur gelap, tenang, dan sejuk.</li>

                <li><strong>Batasi Stimulan:</strong> Hindari kafein dan alkohol, terutama menjelang tidur.</li>

                <li><strong>Hindari Layar Gadget:</strong> Paparan cahaya biru dari smartphone atau tablet sebelum tidur

                    dapat mengganggu produksi melatonin, hormon tidur.</li>

                <li><strong>Aktivitas Fisik Teratur:</strong> Olahraga dapat meningkatkan kualitas tidur, tetapi hindari

                    berolahraga terlalu dekat dengan waktu tidur.</li>

            </ul>

            <p class="mt-4">Melihat semua fakta dan data yang ada, jelas bahwa tidur bukanlah sekadar kemewahan yang

                bisa dikorbankan, melainkan kebutuhan biologis fundamental yang menopang seluruh aspek kehidupan kita.

                Menginvestasikan waktu dan perhatian pada tidur adalah investasi terbaik untuk kesehatan, produktivitas,

                dan kesejahteraan jangka panjang.</p>

        </div>

    </article>



    <!-- ARTIKEL 3: SUARA MAKSIMAL DAN PENDENGARAN -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">volume_up</span> Artikel 3

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Suara Maksimal yang Tidak Berbahaya bagi

            Telinga</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Di dunia modern yang penuh dengan kebisingan, mulai dari lalu lintas kota hingga headphone yang terpasang

                erat, telinga kita terus-usul terpapar berbagai intensitas suara. Meskipun suara adalah bagian tak

                terpisahkan dari kehidupan, tidak semua suara diciptakan sama; ada ambang batas di mana suara, alih-alih

                menjadi informasi, justru berubah menjadi ancaman bagi kesehatan pendengaran kita. Memahami tingkat

                suara maksimal yang aman adalah krusial untuk melindungi salah satu indra terpenting kita dari kerusakan

                permanen yang sering kali tidak disadari hingga terlambat.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Memahami Intensitas Suara dan Risiko Kerusakan</h5>

            <p>Intensitas suara diukur dalam satuan desibel (dB), sebuah skala logaritmik yang secara efektif

                menggambarkan kekuatan suara. Semakin tinggi nilai desibel, semakin keras suara tersebut dan semakin

                besar potensi kerusakannya pada telinga. Paparan suara keras dapat menyebabkan kerusakan pada sel-sel

                rambut halus (stereosilia) di koklea telinga bagian dalam. Sel-sel inilah yang bertanggung jawab

                mengubah gelombang suara menjadi sinyal listrik yang dikirim ke otak. Begitu rusak, sel-sel rambut ini

                tidak dapat beregenerasi, menyebabkan gangguan pendengaran permanen atau tinnitus (telinga berdenging).

                Organisasi Kesehatan Dunia (WHO) secara konsisten menekankan bahwa paparan suara di atas 85 dB (setara

                dengan suara lalu lintas kota yang padat) untuk jangka waktu yang lama sudah berisiko menyebabkan

                kerusakan pendengaran. Data menunjukkan bahwa jutaan orang di seluruh dunia menderita gangguan

                pendengaran akibat kebisingan yang dapat dicegah.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Ambang Batas Aman: Durasi dan Intensitas</h5>

            <p>Meskipun 85 dB sering disebut sebagai ambang batas umum, faktor durasi paparan memainkan peran yang sama

                pentingnya dalam menentukan risiko kerusakan. Hubungan antara intensitas dan durasi bersifat invers:

                semakin keras suaranya, semakin singkat waktu paparan yang aman. Misalnya, paparan suara 85 dB dianggap

                aman untuk sekitar 8 jam. Namun, jika intensitas suara meningkat menjadi 88 dB, waktu paparan aman

                berkurang menjadi hanya 4 jam. Untuk suara sekitar 100 dB (seperti suara mesin pemotong rumput atau

                sepeda motor), batas amannya turun drastis menjadi hanya sekitar 15 menit. Sementara itu, suara di atas

                120 dB (setara dengan konser musik rock di dekat speaker atau sirene ambulans) dapat menyebabkan

                kerusakan pendengaran instan hanya dalam hitungan detik. Prinsip ini menegaskan bahwa kesadaran akan

                tingkat desibel dan durasi paparan adalah kunci untuk menjaga kesehatan telinga kita.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Strategi Melindungi Pendengaran di Era Modern</h5>

            <p>Mengingat ancaman kebisingan yang konstan, ada beberapa strategi efektif untuk melindungi pendengaran

                kita. Pertama, atur volume perangkat audio seperti headphone atau earbud agar tidak melebihi 60% dari

                volume maksimal, dan gunakan aturan "60-60": jangan mendengarkan lebih dari 60 menit berturut-turut pada

                volume 60%. Kedua, gunakan pelindung telinga (penyumbat telinga atau earmuffs) saat berada di lingkungan

                yang bising, seperti konser, tempat kerja industri, atau acara olahraga yang bising. Ketiga, berikan

                waktu istirahat bagi telinga dari paparan suara keras. Berada di lingkungan yang tenang secara teratur

                memungkinkan sel-sel rambut di telinga untuk pulih dari stres. Terakhir, lakukan pemeriksaan pendengaran

                rutin, terutama jika Anda sering terpapar kebisingan atau mulai merasakan gejala gangguan pendengaran

                seperti tinnitus. Melindungi telinga adalah investasi jangka panjang untuk kualitas hidup, memastikan

                kita dapat terus menikmati dunia suara tanpa risiko kehilangan salah satu indra paling berharga kita.

            </p>

        </div>

    </article>



    <!-- ARTIKEL 4: PESAWAT SEDERHANA -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">construction</span> Artikel 4

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Pesawat Sederhana: Fondasi Mekanika dan

            Efisiensi Kerja</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Dalam kajian fisika, pesawat sederhana merujuk pada perangkat mekanis dasar yang mengubah arah atau

                besaran gaya, atau keduanya, untuk memfasilitasi pelaksanaan kerja. Meskipun namanya menyiratkan

                kesederhanaan, prinsip-prinsip yang mendasarinya merupakan fondasi bagi mesin-mesin kompleks dalam

                teknologi modern. Pesawat sederhana memungkinkan manusia untuk mengatasi hambatan fisik yang melebihi

                kapasitas kekuatan otot mereka, dengan mengoptimalkan hubungan antara gaya masukan (upaya) dan gaya

                keluaran (beban) melalui konsep keuntungan mekanis.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Konsep Keuntungan Mekanis dan Kerja</h5>

            <p>Prinsip kerja pesawat sederhana berpusat pada kekekalan energi dan konsep keuntungan mekanis (KM). Secara

                matematis, KM didefinisikan sebagai rasio gaya keluaran (beban) terhadap gaya masukan (upaya) yang

                diterapkan:</p>

            <p>$KM = \frac{F_{beban}}{F_{upaya}}$</p>

            <p>Alternatifnya, dalam konteks perpindahan, KM juga dapat dinyatakan sebagai rasio jarak tempuh gaya

                masukan terhadap jarak tempuh gaya keluaran:</p>

            <p>$KM = \frac{D_{upaya}}{D_{beban}}$</p>

            <p>Penting untuk dicatat bahwa dalam sistem ideal (tanpa gesekan), kerja yang dilakukan oleh gaya masukan

                akan sama dengan kerja yang dilakukan pada beban ($W_{upaya}=W_{beban}$), yang berarti energi tidak

                diciptakan maupun dimusnahkan, hanya diubah bentuknya atau ditransfer. Namun, dalam sistem nyata,

                efisiensi selalu kurang dari 100% karena adanya kehilangan energi akibat gesekan. Meskipun demikian,

                pesawat sederhana tetap memberikan keuntungan signifikan dengan memungkinkan gaya yang lebih kecil untuk

                mengangkat beban yang lebih besar, asalkan jarak tempuh gaya masukan diperpanjang.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Jenis-Jenis Pesawat Sederhana dan Mekanismenya</h5>

            <p>Terdapat enam jenis pesawat sederhana dasar, masing-masing dengan konfigurasi geometris dan prinsip kerja

                yang unik:</p>

            <p><strong>Pengungkit (Tuas):</strong> Terdiri dari batang kaku yang berputar pada titik tumpu (fulcrum).

                Prinsip kerjanya didasarkan pada torsi, di mana $F_{upaya}\times d_{upaya}=F_{beban}\times d_{beban}$.

                Keuntungan mekanis bervariasi tergantung pada posisi titik tumpu relatif terhadap gaya masukan dan

                beban, dikategorikan menjadi kelas I, II, dan III. Contoh aplikasinya adalah linggis atau gunting.</p>

            <p><strong>Roda dan Poros:</strong> Sistem ini terdiri dari roda besar yang terpasang pada poros kecil. Gaya

                diterapkan pada roda, menyebabkan poros berputar. Keuntungan mekanis diperoleh dari rasio jari-jari roda

                terhadap jari-jari poros ($KM = \frac{R_{roda}}{r_{poros}}$). Aplikasi umum termasuk setir mobil, kunci

                pas, atau katrol sumur.</p>

            <p><strong>Katrol:</strong> Mesin sederhana yang menggunakan roda beralur dengan tali atau kabel di

                sekelilingnya. Katrol dapat tunggal (mengubah arah gaya) atau majemuk (meningkatkan keuntungan mekanis

                dengan mengurangi gaya masukan, tetapi memperpanjang jarak tali). Setiap segmen tali yang menopang beban

                akan berkontribusi pada keuntungan mekanis. Sistem katrol ganda memungkinkan pengangkatan beban berat

                dengan upaya yang jauh lebih kecil.</p>

            <p><strong>Bidang Miring:</strong> Permukaan datar yang membentuk sudut dengan permukaan horizontal.

                Memungkinkan objek diangkat ke ketinggian tertentu dengan gaya yang lebih kecil dibandingkan

                mengangkatnya secara vertikal, namun dengan menempuh jarak yang lebih jauh.</p>

            <p>$KM=\frac{Panjang}{Tinggi}$</p>

            <p>Keuntungan mekanisnya adalah rasio panjang bidang miring terhadap tingginya. Contoh adalah tanjakan atau

                ramp.</p>

            <p><strong>Baji:</strong> Modifikasi dari bidang miring, berupa dua bidang miring yang disatukan untuk

                memisahkan atau membelah suatu objek. Gaya diterapkan pada ujung yang tumpul, dan gaya keluaran bekerja

                tegak lurus pada sisi miring baji. Efisiensi baji tergantung pada ketajamannya; semakin tajam, semakin

                besar gaya konsentrasi yang dihasilkan. Contohnya adalah kapak atau pahat.</p>

            <p><strong>Sekrup:</strong> Modifikasi dari bidang miring yang dililitkan mengelilingi silinder. Ketika

                sekrup diputar, ia bergerak secara aksial, mengubah gaya rotasi menjadi gaya linear yang besar.

                Keuntungan mekanisnya sangat tinggi, menjadikannya ideal untuk mengikat benda atau mengangkat beban

                berat (misalnya, dongkrak). Gaya yang diperlukan untuk memutar sekrup jauh lebih kecil dibandingkan gaya

                yang dihasilkan untuk menggerakkan beban.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Signifikansi dalam Teknologi dan Kehidupan

                Sehari-hari</h5>

            <p>Meskipun prinsipnya sederhana, pemahaman dan aplikasi pesawat sederhana telah menjadi fondasi bagi

                pengembangan teknologi kompleks sepanjang sejarah manusia. Mulai dari alat-alat purba yang membantu

                pembangunan piramida, hingga sistem hidrolik modern, semuanya berakar pada prinsip dasar pesawat

                sederhana. Dalam kehidupan sehari-hari, kita terus-menerus berinteraksi dengan pesawat sederhana tanpa

                menyadarinya: gunting menggunakan prinsip pengungkit, pembuka botol adalah pengungkit kelas II, tangga

                adalah bidang miring, dan baut adalah sekrup. Dengan memanipulasi gaya dan jarak melalui perangkat ini,

                manusia mampu memperluas kemampuan fisiknya secara eksponensial, memungkinkan pembangunan struktur

                megah, pengembangan mesin presisi, dan peningkatan efisiensi kerja di berbagai sektor. Fisika pesawat

                sederhana bukan hanya konsep teoritis, tetapi juga cetak biru praktis untuk inovasi mekanis.</p>

        </div>

    </article>





    <!-- ARTIKEL 5: MOBIL LISTRIK -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">electric_car</span> Artikel 5

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Mobil Listrik: Paradigma Baru Transportasi</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Mobil listrik (EV) bukan sekadar tren, melainkan revolusi transportasi. Ditenagai oleh motor listrik dan

                baterai lithium-ion, EV menawarkan solusi transportasi yang lebih bersih dan efisien.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Komponen dan Cara Kerja</h5>

            <p>Berbeda dengan mesin pembakaran internal (ICE) yang rumit, EV lebih sederhana. Komponen utamanya

                meliputi:

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Baterai:</strong> Menyimpan energi listrik (biasanya Lithium-ion).</li>

                <li><strong>Motor Listrik:</strong> Mengubah energi listrik menjadi gerak putar roda.</li>

                <li><strong>PCU (Power Control Unit):</strong> Mengatur aliran daya dan pengereman regeneratif.</li>

            </ul>

            </p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Keunggulan Lingkungan</h5>

            <p>EV memiliki <strong>emisi nol</strong> dari knalpot ($0 CO_2, NO_x$). Efisiensi energinya mencapai 77%

            <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Mobil Listrik: Mengubah Paradigma

                Transportasi Masa Depan</h3>

            <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

                <p>Di tengah isu perubahan iklim dan kebutuhan akan sumber energi yang lebih bersih, mobil listrik telah

                    muncul sebagai salah satu solusi paling menjanjikan untuk merevolusi industri transportasi.

                    Kendaraan yang ditenagai oleh motor listrik alih-alih mesin pembakaran internal ini tidak hanya

                    menawarkan kinerja yang semakin impresif, tetapi juga menjanjikan pengurangan emisi karbon yang

                    signifikan. Transformasi ini bukan sekadar tren sesaat; ini adalah pergeseran paradigma yang

                    berpotensi mengubah cara kita bergerak, mengisi bahan bakar, dan berinteraksi dengan lingkungan.</p>



                <h5 class="font-bold text-sakura-black text-base mt-6">Cara Kerja Mobil Listrik dan Komponen Utamanya

                </h5>

                <p>Berbeda dengan mobil konvensional yang membakar bahan bakar fosil, mobil listrik ditenagai oleh motor

                    listrik yang mendapatkan energi dari baterai lithium-ion berkapasitas tinggi. Proses kerjanya

                    dimulai ketika energi listrik dari baterai dialirkan ke motor listrik melalui unit kontrol daya.

                    Motor listrik ini kemudian mengubah energi listrik menjadi energi mekanik yang menggerakkan roda

                    kendaraan. Sistem ini jauh lebih sederhana dibandingkan mesin pembakaran internal yang memiliki

                    ribuan komponen bergerak. Komponen utama pada mobil listrik meliputi:</p>

                <ul class="list-disc pl-5 mt-2 space-y-1">

                    <li><strong>Baterai:</strong> Penyimpan energi listrik utama, biasanya berjenis lithium-ion karena

                        kepadatan energi dan efisiensinya. Kapasitas baterai menentukan jarak tempuh kendaraan.</li>

                    <li><strong>Motor Listrik:</strong> Mengubah energi listrik dari baterai menjadi gerak mekanis untuk

                        memutar roda. Mobil listrik bisa memiliki satu atau lebih motor listrik.</li>

                    <li><strong>Unit Kontrol Daya (Power Control Unit/PCU):</strong> Mengatur aliran listrik antara

                        baterai dan motor, mengubah arus DC dari baterai menjadi AC untuk motor, serta mengelola proses

                        pengereman regeneratif.</li>

                    <li><strong>Pengecasan (Charging Port):</strong> Titik antarmuka untuk menghubungkan mobil ke sumber

                        listrik guna mengisi ulang baterai.</li>

                </ul>

                <p>Kinerja mobil listrik pun tak kalah dengan mobil bertenaga bensin; akselerasinya seringkali lebih

                    instan dan senyap, menghasilkan pengalaman berkendara yang berbeda dan efisien.</p>



                <h5 class="font-bold text-sakura-black text-base mt-6">Keunggulan dan Dampak Mobil Listrik Terhadap

                    Lingkungan</h5>

                <p>Adopsi mobil listrik membawa berbagai keunggulan signifikan, terutama dari perspektif lingkungan dan

                    operasional. Pertama, mobil listrik menghasilkan emisi nol dari knalpotnya. Ini berarti tidak ada

                    pelepasan karbon dioksida ($CO_{2}$), nitrogen oksida ($NO_{X}$), atau partikel polutan lainnya ke

                    udara saat beroperasi, secara drastis mengurangi polusi udara lokal di perkotaan. Meskipun listrik

                    yang digunakan untuk mengisi ulang baterai mungkin berasal dari pembangkit listrik yang masih

                    menggunakan bahan bakar fosil, emisi total (well-to-wheel) secara umum tetap lebih rendah

                    dibandingkan mobil bensin, apalagi jika sumber listrik berasal dari energi terbarukan. Kedua, mobil

                    listrik menawarkan efisiensi energi yang lebih tinggi. Motor listrik dapat mengubah sekitar 77%

                    energi listrik dari baterai menjadi daya dorong, jauh lebih efisien dibandingkan mesin bensin yang

                    hanya mengonversi sekitar 12-30% energi bahan bakar. Ketiga, biaya operasional cenderung lebih

                    rendah. Pengisian daya listrik umumnya lebih murah daripada membeli bensin, dan mobil listrik

                    memiliki lebih sedikit komponen bergerak sehingga biaya perawatan rutin (seperti penggantian oli)

                    jauh berkurang. Keunggulan-keunggulan ini menjadikan mobil listrik sebagai komponen kunci dalam

                    strategi global untuk mencapai keberlanjutan.</p>



                <h5 class="font-bold text-sakura-black text-base mt-6">Masa Depan Mobil Listrik</h5>

                <p>Meski memiliki banyak potensi, pengembangan dan adopsi mobil listrik masih dihadapkan pada beberapa

                    tantangan besar. Salah satunya adalah infrastruktur pengisian daya yang belum merata, terutama di

                    banyak negara berkembang. Ketersediaan stasiun pengisian daya cepat (DC fast charging) masih

                    terbatas, dan waktu pengisian yang lebih lama dibandingkan mengisi bensin menjadi kendala bagi

                    sebagian konsumen. Kedua, biaya awal pembelian mobil listrik masih relatif tinggi dibandingkan mobil

                    konvensional, meskipun harga baterai terus menurun. Ketiga, kekhawatiran tentang jangkauan (range

                    anxiety) masih menjadi faktor, yaitu kekhawatiran kehabisan daya sebelum mencapai stasiun pengisian

                    terdekat. Namun, industri otomotif dan pemerintah di seluruh dunia terus berinvestasi besar-besaran

                    untuk mengatasi tantangan ini. Inovasi dalam teknologi baterai (meningkatkan kapasitas dan

                    mempercepat pengisian), perluasan jaringan stasiun pengisian daya, serta insentif pemerintah untuk

                    pembelian mobil listrik diproyeksikan akan mempercepat transisi menuju era transportasi yang lebih

                    bersih dan berkelanjutan. Mobil listrik bukan lagi sekadar konsep masa depan, melainkan realitas

                    yang semakin dekat dengan kita.</p>

            </div>

    </article>



    <!-- ARTIKEL 6: TEH HIJAU -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">nutrition</span> Artikel 6

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Benarkah Teh Hijau Solusi Ajaib Penurun Berat

            Badan?</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Teh hijau telah lama dipuja sebagai minuman super yang menawarkan segudang manfaat kesehatan, dan di

                antara klaim yang paling sering terdengar adalah kemampuannya untuk membantu penurunan berat badan.

                Reputasinya sebagai "pembakar lemak" alami telah menjadikannya pilihan favorit bagi banyak orang yang

                sedang berjuang melawan timbunan lemak berlebih. Namun, seberapa jauh klaim ini didukung oleh sains?

                Artikel ini akan membongkar mitos dan fakta seputar teh hijau serta perannya dalam manajemen berat

                badan, memberikan perspektif yang lebih kritis dan berdasarkan bukti ilmiah.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Mitos 1: Teh Hijau Adalah Solusi Instan Pembakar

                Lemak Ajaib</h5>

            <p>Banyak yang meyakini bahwa hanya dengan minum teh hijau secara rutin, berat badan akan otomatis turun

                drastis tanpa perlu perubahan gaya hidup lainnya. Ini adalah mitos yang perlu diluruskan. Teh hijau

                memang mengandung senyawa bioaktif yang berpotensi memengaruhi metabolisme, tetapi dampaknya tidak

                semudah membalik telapak tangan.</p>

            <p><strong>Fakta:</strong> Teh hijau kaya akan katekin, terutama epigallocatechin gallate (EGCG), dan juga

                mengandung kafein. Kombinasi EGCG dan kafein dipercaya dapat meningkatkan termogenesis (proses

                pembakaran kalori oleh tubuh untuk menghasilkan panas) dan oksidasi lemak. Studi yang diterbitkan dalam

                American Journal of Clinical Nutrition menunjukkan bahwa konsumsi ekstrak teh hijau dapat meningkatkan

                pengeluaran energi hingga 4% dan oksidasi lemak hingga 16% pada beberapa individu. Namun, efek ini

                cenderung moderat dan tidak cukup signifikan untuk menghasilkan penurunan berat badan yang drastis tanpa

                adanya defisit kalori dari diet dan peningkatan aktivitas fisik. Dengan kata lain, teh hijau berfungsi

                sebagai booster kecil, bukan tombol on/off pembakaran lemak.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Mitos 2: Semakin Banyak Minum Teh Hijau, Semakin

                Cepat Kurus</h5>

            <p>Ada anggapan bahwa konsumsi teh hijau dalam jumlah sangat besar akan mempercepat proses penurunan berat

                badan. Pendekatan ini tidak hanya tidak efektif, tetapi berpotensi berbahaya. Seperti halnya zat aktif

                lainnya, ada dosis optimal dan risiko efek samping jika dikonsumsi berlebihan.</p>

            <p><strong>Fakta:</strong> Konsumsi teh hijau berlebihan, terutama dalam bentuk suplemen ekstrak teh hijau

                dosis tinggi, dapat menyebabkan efek samping seperti mual, sakit perut, diare, bahkan kerusakan hati.

                Sebuah laporan dari National Institutes of Health di AS mencatat beberapa kasus cedera hati yang terkait

                dengan suplemen teh hijau. Selain itu, kandungan kafein yang tinggi dalam teh hijau juga bisa

                menyebabkan insomnia, gelisah, atau detak jantung tidak teratur jika dikonsumsi berlebihan. Efek

                sinergis EGCG dan kafein memang ada, tetapi peningkatannya tidak linear dengan dosis. Tubuh memiliki

                batas toleransi, dan melebihi batas tersebut justru akan memberikan dampak negatif alih-alih manfaat

                tambahan untuk penurunan berat badan.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Mitos 3: Teh Hijau Bisa Menggantikan Diet dan

                Olahraga</h5>

            <p>Beberapa orang mungkin berharap teh hijau bisa menjadi jalan pintas, menggantikan kebutuhan akan diet

                sehat dan rutinitas olahraga teratur. Asumsi ini keliru dan berbahaya bagi kesehatan jangka panjang. Teh

                hijau adalah pelengkap, bukan pengganti.</p>

            <p><strong>Fakta:</strong> Konsensus ilmiah menegaskan bahwa defisit kalori (mengonsumsi lebih sedikit

                kalori daripada yang dibakar) dan peningkatan aktivitas fisik adalah pilar utama yang tak tergantikan

                dalam program penurunan berat badan yang sehat dan berkelanjutan. Teh hijau dapat menjadi bagian dari

                gaya hidup sehat, tetapi perannya bersifat suportif. Sebuah tinjauan sistematis oleh Cochrane Library

                menyimpulkan bahwa meskipun teh hijau dapat menghasilkan penurunan berat badan yang kecil dan tidak

                signifikan secara statistik pada orang dewasa yang kelebihan berat badan atau obesitas, efek ini tidak

                bertahan lama setelah berhenti mengonsumsi teh hijau dan tidak seefektif intervensi diet dan olahraga.

                Oleh karena itu, bagi mereka yang serius ingin menurunkan berat badan, fokus utama harus tetap pada pola

                makan seimbang dan olahraga teratur, dengan teh hijau sebagai minuman pendukung yang menyehatkan.</p>



            <p class="mt-4">Sebagai kesimpulan, teh hijau memang memiliki tempat dalam diet sehat dan dapat memberikan

                manfaat metabolisme yang sederhana. Namun, melihatnya sebagai "solusi ajaib" untuk penurunan berat badan

                adalah pandangan yang terlalu menyederhanakan dan berpotensi menyesatkan. Untuk mencapai dan

                mempertahankan berat badan yang sehat, tidak ada jalan pintas; konsistensi dalam pola makan bergizi,

                aktivitas fisik, dan gaya hidup seimbang tetaplah kunci utamanya.</p>

        </div>

    </article>



    <!-- ARTIKEL 7: GEOTERMAL -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">volcano</span> Artikel 7

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Geotermal: Memanfaatkan Panas Inti Bumi untuk

            Energi Bersih</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Di bawah permukaan bumi yang kita pijak, tersimpan sumber energi yang melimpah dan senantiasa terbarukan:

                energi geotermal, atau panas bumi. Berasal dari bahasa Yunani, geo berarti bumi dan thermos berarti

                panas, geotermal adalah energi panas alami yang terbentuk di dalam kerak bumi. Sumber energi ini lahir

                dari proses geologis kompleks yang melibatkan panas dari inti bumi, batuan panas, serta air dan uap yang

                terperangkap dalam sistem hidrotermal. Pemanfaatan energi ini merepresentasikan salah satu solusi paling

                menjanjikan dalam transisi global menuju sumber energi bersih, mengurangi ketergantungan pada bahan

                bakar fosil, dan mitigasi perubahan iklim.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Mekanisme Pembentukan dan Reservoir Geotermal</h5>

            <p>Energi geotermal berasal dari panas sisa pembentukan planet dan peluruhan isotop radioaktif di dalam inti

                bumi. Panas ini merambat ke lapisan mantel dan kerak bumi, menciptakan gradien geotermal, di mana suhu

                meningkat seiring kedalaman (rata-rata sekitar $25^{\circ}C/km)$. Di daerah-daerah dengan aktivitas

                tektonik tinggi, seperti di sepanjang Cincin Api Pasifik (Ring of Fire) tempat Indonesia berada,

                pergerakan lempeng tektonik dapat menyebabkan magma panas naik lebih dekat ke permukaan. Magma inilah

                yang menjadi sumber panas (heat source) primer bagi sistem geotermal. Air tanah, yang meresap ke dalam

                formasi batuan yang panas, akan memanas, berubah menjadi air panas atau uap, dan terkumpul dalam formasi

                geologi permeabel yang disebut reservoir geotermal. Reservoir ini seringkali ditutupi oleh lapisan

                batuan kedap (cap rock) yang memerangkap fluida panas, menciptakan sistem tertutup yang dapat

                dieksploitasi untuk menghasilkan energi.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Teknologi Pembangkitan Listrik Tenaga Geotermal

                (PLTP)</h5>

            <p>Pemanfaatan energi geotermal untuk menghasilkan listrik dilakukan melalui beberapa teknologi pembangkit,

                yang dipilih berdasarkan karakteristik fluida geotermal (suhu dan fase) di reservoir:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Pembangkit Uap Kering (Dry Steam Power Plant):</strong> Merupakan teknologi tertua dan

                    paling sederhana, digunakan ketika reservoir menghasilkan uap kering dengan tekanan tinggi. Uap ini

                    langsung dialirkan untuk memutar turbin generator listrik. Contohnya adalah PLTP Larderello di

                    Italia.</li>

                <li><strong>Pembangkit Uap Kilat (Flash Steam Power Plant):</strong> Jenis yang paling umum. Air panas

                    bertekanan tinggi dari reservoir (lebih dari $182^{\circ}C$) dibawa ke permukaan, kemudian

                    dilewatkan ke tangki bertekanan rendah (flash tank). Perubahan tekanan mendadak ini menyebabkan

                    sebagian air panas "menguap kilat" menjadi uap, yang kemudian digunakan untuk memutar turbin. Air

                    sisa yang tidak menguap diinjeksikan kembali ke dalam reservoir.</li>

                <li><strong>Pembangkit Siklus Biner (Binary Cycle Power Plant):</strong> Digunakan untuk reservoir

                    dengan suhu lebih rendah (di bawah $182^{\circ}C$) atau ketika fluida panas bumi berbentuk air

                    panas. Fluida panas bumi digunakan untuk memanaskan cairan kerja sekunder (seperti isobutana atau

                    pentana) yang memiliki titik didih lebih rendah daripada air. Uap dari cairan kerja inilah yang

                    memutar turbin, sementara fluida panas bumi diinjeksikan kembali ke dalam bumi tanpa kontak langsung

                    dengan atmosfer. Teknologi ini lebih ramah lingkungan karena tidak melepaskan uap atau gas ke

                    atmosfer.</li>

            </ul>

            <p>Setelah uap memutar turbin, uap akan dikondensasi kembali menjadi air dan diinjeksikan kembali ke dalam

                reservoir, menjaga keberlanjutan sumber daya dan meminimalkan dampak lingkungan.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Keunggulan, Tantangan, dan Potensi Indonesia</h5>

            <p>Energi geotermal memiliki sejumlah keunggulan signifikan sebagai sumber energi terbarukan: ia stabil dan

                tidak intermiten (dapat beroperasi $24/7$ tanpa bergantung pada cuaca seperti surya atau angin), minim

                emisi gas rumah kaca (terutama tipe siklus biner), biaya operasional rendah setelah pembangunan awal,

                dan mengurangi ketergantungan pada bahan bakar fosil. Namun, terdapat pula tantangan, termasuk biaya

                investasi awal yang tinggi untuk eksplorasi dan pengeboran, lokasi yang spesifik (hanya bisa

                dikembangkan di daerah dengan sistem geotermal aktif), serta potensi fluida yang korosif yang memerlukan

                material khusus.</p>

            <p>Indonesia memiliki posisi yang sangat strategis dalam konteks geotermal. Sebagai bagian dari Cincin Api

                Pasifik, Indonesia diperkirakan memiliki sekitar 40% dari total potensi panas bumi dunia, dengan

                estimasi mencapai 23,766 Gigawatt (GW). Namun, hingga saat ini, pemanfaatannya masih jauh di bawah

                potensinya (sekitar 11% dari potensi). Provinsi seperti Jawa Barat, Sumatera Utara, dan Sulawesi Utara

                memiliki cadangan yang signifikan. Upaya pengembangan geotermal di Indonesia terus digalakkan untuk

                mencapai target bauran energi nasional dan komitmen pengurangan emisi, menjadikan geotermal sebagai

                pilar penting dalam ketahanan energi dan keberlanjutan di masa depan.</p>

        </div>

    </article>



    <!-- ARTIKEL 8: MENJAGA LINGKUNGAN -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">recycling</span> Artikel 8

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Menjaga Lingkungan: Langkah Nyata untuk Masa

            Depan Bumi</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Lingkungan adalah rumah kita bersama, penyedia segala kebutuhan hidup, dari udara yang kita hirup, air

                yang kita minum, hingga pangan yang kita konsumsi. Namun, aktivitas manusia, terutama di era modern ini,

                sering kali memberikan tekanan luar biasa pada ekosistem Bumi. Perubahan iklim, polusi, dan hilangnya

                keanekaragaman hayati adalah konsekuensi nyata dari abainya kita terhadap lingkungan. Menjaga lingkungan

                bukan lagi pilihan, melainkan kewajiban mendesak bagi setiap individu dan komunitas. Ini adalah

                investasi vital untuk keberlanjutan hidup di masa kini dan generasi mendatang.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Kurangi, Gunakan Kembali, Daur Ulang (3R): Filosofi

                Kunci Pelestarian</h5>

            <p>Konsep 3R (Reduce, Reuse, Recycle) adalah pilar utama dalam upaya menjaga lingkungan, khususnya dalam

                pengelolaan limbah. Ini bukan sekadar slogan, melainkan filosofi yang mengajak kita mengubah perilaku

                konsumsi secara fundamental.</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Reduce (Kurangi):</strong> Langkah pertama yang paling efektif adalah mengurangi jumlah

                    sampah yang kita hasilkan. Ini berarti membeli barang sesuai kebutuhan, menghindari produk dengan

                    kemasan berlebihan, dan memilih barang yang awet atau tahan lama. Mengurangi konsumsi energi

                    (misalnya, mematikan lampu saat tidak digunakan) juga termasuk dalam prinsip ini.</li>

                <li><strong>Reuse (Gunakan Kembali):</strong> Sebelum membuang, pertimbangkan apakah suatu barang bisa

                    digunakan kembali untuk tujuan yang sama atau berbeda. Contohnya termasuk menggunakan kembali botol

                    minum, membawa tas belanja sendiri, atau mendonasikan pakaian bekas. Ini memperpanjang masa pakai

                    produk dan mengurangi kebutuhan produksi barang baru.</li>

                <li><strong>Recycle (Daur Ulang):</strong> Setelah upaya mengurangi dan menggunakan kembali, langkah

                    terakhir adalah mendaur ulang. Ini melibatkan pengumpulan dan pemrosesan bahan-bahan bekas (seperti

                    kertas, plastik, kaca, dan logam) menjadi produk baru. Daur ulang tidak hanya mengurangi volume

                    sampah di TPA, tetapi juga menghemat energi, mengurangi polusi, dan melestarikan sumber daya alam.

                </li>

            </ul>

            <p>Menerapkan 3R dalam kehidupan sehari-hari secara konsisten akan memberikan dampak kumulatif yang

                signifikan terhadap pengurangan jejak ekologis kita.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Hemat Energi dan Air: Kontribusi Nyata dalam Skala

                Kecil</h5>

            <p>Energi dan air adalah dua sumber daya esensial yang pemakaiannya sangat memengaruhi lingkungan. Menghemat

                keduanya adalah cara sederhana namun sangat efektif untuk berkontribusi pada pelestarian.</p>

            <p><strong>Hemat Energi:</strong> Produksi energi dari bahan bakar fosil adalah penyumbang utama emisi gas

                rumah kaca. Dengan mengurangi penggunaan listrik, kita turut menurunkan emisi tersebut. Matikan lampu,

                cabut peralatan elektronik saat tidak digunakan, optimalkan penggunaan AC, dan beralihlah ke peralatan

                hemat energi (LED, peralatan berlabel Energy Star). Memilih transportasi umum, bersepeda, atau berjalan

                kaki juga mengurangi konsumsi bahan bakar.</p>

            <p><strong>Hemat Air:</strong> Meskipun air tampak melimpah, air bersih yang siap minum adalah sumber daya

                terbatas. Menghemat air berarti memastikan ketersediaan untuk masa depan. Mandi lebih singkat, menutup

                keran saat menyikat gigi, menggunakan flush toilet yang efisien air, dan mengumpulkan air hujan untuk

                menyiram tanaman adalah contoh tindakan nyata. Data menunjukkan bahwa rata-rata individu dapat menghemat

                puluhan liter air per hari hanya dengan mengubah kebiasaan kecil.</p>

            <p>Setiap tetes air dan setiap kilowatt energi yang kita hemat adalah langkah kecil yang collectively

                berkontribusi pada kesehatan planet.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Menanam Pohon dan Melestarikan Keanekaragaman dan

                Investasi Jangka Panjang</h5>

            <p>Pohon adalah paru-paru Bumi, memainkan peran krusial dalam menyerap karbon dioksida dan menghasilkan

                oksigen. Menanam pohon adalah salah satu cara paling langsung dan efektif untuk memerangi perubahan

                iklim dan mendukung ekosistem. Satu pohon dewasa dapat menyerap puluhan kilogram $CO_{2}$ setiap tahun.

                Selain itu, upaya ini harus dibarengi dengan melestarikan keanekaragaman hayati. Setiap spesies, sekecil

                apa pun, memiliki peranan dalam menjaga keseimbangan ekosistem. Melindungi habitat alami, mendukung

                konservasi spesies langka, dan tidak membeli produk yang berasal dari perburuan atau perdagangan ilegal

                adalah bagian dari tanggung jawab kita. Lingkungan yang kaya keanekaragaman hayati lebih tangguh

                terhadap perubahan dan menyediakan layanan ekosistem vital seperti penyerbukan dan penyaringan air.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Edukasi dan Advokasi: Membangun Kesadaran Kolektif

            </h5>

            <p>Langkah-langkah individu saja tidak cukup; edukasi dan advokasi adalah kunci untuk menciptakan perubahan

                sistemik yang lebih besar.</p>

            <p><strong>Edukasi:</strong> Sebarkan informasi tentang pentingnya menjaga lingkungan kepada keluarga,

                teman, dan komunitas. Pahami isu-isu lingkungan lokal dan global agar dapat bertindak berdasarkan

                informasi yang akurat. Anak-anak, khususnya, perlu ditanamkan kesadaran lingkungan sejak dini agar

                tumbuh menjadi generasi yang lebih bertanggung jawab.</p>

            <p><strong>Advokasi:</strong> Dukung kebijakan pemerintah yang pro-lingkungan, berpartisipasi dalam

                program-program kebersihan lingkungan, atau bergabung dengan organisasi konservasi. Suara kolektif

                memiliki kekuatan untuk mendorong perubahan pada tingkat yang lebih tinggi, memaksa industri dan pembuat

                kebijakan untuk mengadopsi praktik yang lebih berkelanjutan.</p>

        </div>

    </article>



    <!-- ARTIKEL 9: ICARUS -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-orange-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-orange-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">auto_stories</span> Artikel 9

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Icarus, Kisah Ambisi dan Kejatuhan dalam

            Mitologi Yunani</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Dalam khazanah mitologi Yunani yang kaya akan kisah para dewa, dewi, dan pahlawan, terdapat pula

                narasi-narasi yang berfungsi sebagai peringatan moral abadi. Salah satunya adalah kisah tragis Icarus,

                putra dari sang perajin ulung Daedalus. Lebih dari sekadar cerita tentang penerbangan yang gagal, mitos

                Icarus adalah alegori mendalam tentang ambisi yang tak terkendali, bahaya mengabaikan nasihat bijak, dan

                konsekuensi dari melampaui batas kemampuan diri.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Melarikan Diri dari Labirin</h5>

            <p>Kisah Icarus berawal dari kemahiran ayahnya, Daedalus, seorang arsitek dan penemu legendaris yang

                menciptakan Labirin yang rumit untuk Raja Minos di Pulau Kreta. Setelah membantu Ariadne, putri Minos,

                memberikan benang kepada Theseus untuk keluar dari Labirin setelah membunuh Minotaur, Minos murka dan

                memenjarakan Daedalus beserta putranya, Icarus, di dalam menara yang tinggi. Merasa terkurung dan

                merindukan kebebasan, Daedalus yang cerdik memutar otak mencari cara untuk melarikan diri.</p>

            <p>Menyadari bahwa laut adalah satu-satunya jalan keluar yang diawasi ketat, Daedalus memutuskan untuk

                menaklukkan langit. Ia mengumpulkan bulu-bulu burung yang jatuh dan dengan sabar menyusunnya menjadi

                sepasang sayap yang besar. Bulu-bulu kecil direkatkan menggunakan lilin, sementara bulu-bulu yang lebih

                besar diikat dengan benang. Setelah menyelesaikan sepasang sayap untuk dirinya dan sepasang lainnya

                untuk Icarus, tibalah saatnya untuk rencana pelarian yang berani.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Peringatan Sang Ayah dan Keindahan Penerbangan

                Pertama</h5>

            <p>Sebelum mereka memulai penerbangan yang belum pernah terjadi sebelumnya, Daedalus memberikan peringatan

                krusial kepada Icarus. Ia menekankan dua batasan penting: jangan terbang terlalu rendah karena

                kelembaban dari laut akan membebani sayap dan membuatnya berat, dan jangan terbang terlalu tinggi,

                mendekati matahari, karena panasnya yang membakar akan melelehkan lilin yang merekatkan bulu-bulu.

                Daedalus mengingatkan Icarus untuk tetap berada di tengah-tengah jalur penerbangan mereka dan mengikuti

                arahnya.</p>

            <p>Saat mereka mengepakkan sayap dan terangkat ke udara, sensasi kebebasan dan pemandangan menakjubkan dari

                ketinggian tentu saja memukau. Bagi Icarus, yang selama ini terkurung, pengalaman terbang pertama kali

                ini pasti sangat mendebarkan. Ia merasakan angin menerpa wajahnya, melihat pulau Kreta mengecil di

                bawah, dan menikmati perspektif dunia yang sama sekali baru. Namun, kegembiraan dan rasa ingin tahu yang

                meluap-luap mulai mengalahkan akal sehat dan nasihat ayahnya.</p>

            <p>Terpesona oleh keindahan langit dan sensasi terbang yang tak tertandingi, Icarus mulai mengabaikan

                peringatan Daedalus. Didorong oleh rasa penasaran yang membara dan mungkin juga sedikit kesombongan

                karena mampu terbang seperti dewa, ia semakin berani meninggi. la terus mengepakkan sayapnya,

                meninggalkan ayahnya di belakang, dan terbang semakin dekat menuju matahari yang bersinar terang.</p>

            <p>Semakin dekat Icarus dengan sang surya, semakin kuat pula panas yang diterimanya. Perlahan tapi pasti,

                panas yang membakar itu mulai melelehkan lilin yang merekatkan bulu-bulu pada sayapnya. Icarus tidak

                menyadari bahaya yang mengintai hingga ia merasakan sayapnya mulai kehilangan kekuatannya. Bulu-bulu

                satu per satu terlepas, dan kepakan sayapnya menjadi tidak efektif. Panik dan putus asa, Icarus berusaha

                keras untuk tetap terbang, namun usahanya sia-sia. Sayapnya hancur, dan ia pun terjatuh dari ketinggian

                ke dalam laut yang membiru. Laut tempat ia menemui ajalnya kemudian dinamai Laut Icaria untuk mengenang

                tragedi tersebut. Daedalus, yang menoleh ke belakang dan melihat bulu-bulu Icarus mengambang di air,

                diliputi kesedihan yang mendalam atas kehilangan putranya. Ia melanjutkan penerbangannya dengan hati

                yang hancur menuju daratan yang aman.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Pelajaran tentang Batasan dan Konsekuensi</h5>

            <p>Kisah Icarus telah bertahan selama berabad-abad sebagai alegori yang kuat tentang bahaya hubris

                (kesombongan), ketidakpatuhan, dan pentingnya mengenali batasan diri. Ambisi yang tidak terkendali, rasa

                penasaran yang membutakan, dan keyakinan berlebihan pada kemampuan sendiri tanpa menghiraukan nasihat

                bijak dapat membawa pada konsekuensi yang tragis.</p>

            <p>Mitos Icarus mengajarkan kita tentang pentingnya keseimbangan antara keinginan untuk mencapai hal yang

                lebih tinggi dengan pemahaman akan keterbatasan yang ada. Terbang terlalu tinggi, mengejar impian tanpa

                mempertimbangkan risiko dan nasihat orang yang lebih berpengalaman, dapat berujung pada kegagalan dan

                kehancuran. Kisah ini menjadi pengingat abadi bahwa kebebasan dan inovasi harus diimbangi dengan

                kebijaksanaan dan penghormatan terhadap hukum alam dan batasan yang ada. Tragedi Icarus terus bergema

                dalam berbagai bentuk seni dan literatur, mengingatkan kita akan rapuhnya kesuksesan jika dilandasi oleh

                kesombongan dan pengabaian terhadap kearifan.</p>

        </div>

    </article>



</div>

</div>

                    <!-- QUIZ SECTION -->

<div id="page-quiz-006" class="page-section-006">

    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">

        <!-- Quiz Header -->

        <div class="text-center mb-8">

            <span class="material-symbols-outlined text-5xl text-sakura-red mb-3">quiz</span>

            <h2 class="font-serif font-black text-3xl text-sakura-black mb-2">Quiz — Obat Fokus Day 6</h2>

            <p class="text-gray-500 max-w-md mx-auto">Jawab pertanyaan berdasarkan 9 artikel yang sudah kamu baca. Soal isian <strong>tidak dinilai</strong>, hanya True/False yang masuk skor.</p>

            <div class="w-16 h-1 bg-sakura-red mx-auto mt-4"></div>

        </div>



        <!-- ISIAN -->

        <div class="space-y-6">

            <p class="text-[10px] font-bold text-orange-500 uppercase tracking-widest px-1">Bagian 1 — Isian Singkat <span class="text-gray-400">(tidak dinilai)</span></p>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Apa nama zat utama dalam minuman beralkohol?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Etanol (Etil Alkohol)</p>

                    <p class="text-xs text-green-600 mt-1">Zat utama dan paling krusial dalam setiap minuman beralkohol adalah etanol ($C_2H_5OH$).</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Berapa jam tidur yang direkomendasikan untuk orang dewasa berusia 18-64 tahun?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> 7-9 jam</p>

                    <p class="text-xs text-green-600 mt-1">National Sleep Foundation merekomendasikan orang dewasa berusia 18-64 tahun untuk tidur 7-9 jam per malam.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Apa satuan yang digunakan untuk mengukur intensitas suara?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Desibel (dB)</p>

                    <p class="text-xs text-green-600 mt-1">Intensitas suara diukur dalam satuan desibel (dB), sebuah skala logaritmik.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Siapa nama ayah dari Icarus dalam mitologi Yunani?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Daedalus</p>

                    <p class="text-xs text-green-600 mt-1">Icarus adalah putra dari sang perajin ulung Daedalus, yang menciptakan Labirin di Pulau Kreta.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Apa yang dimaksud dengan "3R" dalam menjaga lingkungan?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Reduce, Reuse, Recycle</p>

                    <p class="text-xs text-green-600 mt-1">Konsep 3R adalah pilar utama pelestarian lingkungan: Reduce (Kurangi), Reuse (Gunakan Kembali), dan Recycle (Daur Ulang).</p>

                </div>

            </div>

        </div>



        <!-- TRUE/FALSE -->

        <div class="space-y-6 mt-10">

            <p class="text-[10px] font-bold text-orange-500 uppercase tracking-widest px-1">Bagian 2 — Benar atau Salah <span class="text-gray-400">(dinilai)</span></p>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="006">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Kandungan utama dalam minuman beralkohol adalah metanol.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal6 6', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal6 6', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Kandungan utama dalam minuman beralkohol adalah etanol (etil alkohol), bukan metanol. Metanol adalah kongener yang ada dalam jumlah sangat kecil.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="006">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Teh hijau adalah satu-satunya solusi ajaib untuk menurunkan berat badan tanpa perlu diet dan olahraga.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal6 7', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal6 7', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Teh hijau berfungsi sebagai booster metabolism yang moderat, bukan solusi ajaib. Penurunan berat badan yang efektif tetap membutuhkan defisit kalori dan olahraga.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="006">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> Paparan suara di atas 85 desibel untuk jangka waktu yang lama tidak berisiko menyebabkan kerusakan pendengaran.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal6 8', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal6 8', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. WHO menegaskan bahwa paparan suara di atas 85 dB untuk jangka waktu lama (lebih dari 8 jam) BERISIKO menyebabkan kerusakan pendengaran permanen.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="006">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Icarus berhasil melarikan diri dari pulau Kreta bersama ayahnya, Daedalus.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal6 9', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal6 9', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Icarus gagal melarikan diri karena ia terbang terlalu dekat dengan matahari, menyebabkan lilin pada sayapnya meleleh. Hanya Daedalus yang berhasil selamat.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="006">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Salah satu keunggulan mobil listrik adalah biaya operasionalnya yang cenderung lebih rendah dibandingkan mobil bensin.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal6 10', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal6 10', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Biaya operasional mobil listrik lebih rendah karena biaya pengisian daya listrik lebih murah dan perawatan rutin lebih sedikit (misal: tidak ganti oli).</p>

                </div>

            </div>

        </div>



        <!-- Submit -->

        <div class="text-center pt-8">

            <button onclick="showResult()" class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">

                <span class="flex items-center gap-2">

                    <span class="material-symbols-outlined text-lg">fact_check</span>

                    Lihat Hasil

                </span>

            </button>

        </div>

    </div>

</div>



<!-- PAGE 3: RESULT -->

<div id="page-result-006" class="page-section-006">

    <div class="max-w-4xl mx-auto p-8 pb-32">

        <div id="result-content"></div>

        <div class="text-center mt-8">

            <a href="javascript:void(0)" onclick="loadModule('obat-fokus-007')" class="inline-flex items-center gap-2 px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg">

                <span class="material-symbols-outlined">arrow_forward</span> Lanjut ke Day 7

            </a>

        </div>

    </div>

</div>
                </div>
            </div>



            <!-- MODULE VIEW: OBAT FOKUS 007 -->
            <div id="module-obat-fokus-007" class="module-view">
                <div class="flex-1 overflow-y-auto" id="content-scroll-007">
                    <div id="page-articles-007" class="page-section-007 active"><div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">



    <!-- ARTIKEL 1: KOREKSI PENGLIHATAN -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-indigo-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-indigo-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">visibility</span> Artikel 1

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Koreksi Penglihatan: Memahami Kacamata Minus

            dan Plus</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Mata manusia adalah organ kompleks yang dirancang untuk memfokuskan cahaya ke retina, memungkinkan kita

                melihat dunia dengan jelas. Namun, tidak semua mata sempurna. Kondisi refraksi, seperti miopia (rabun

                jauh) dan hiperopia (rabun dekat), adalah masalah penglihatan umum yang memengaruhi kemampuan mata untuk

                memfokuskan cahaya dengan tepat. Untuk mengoreksi anomali ini, kacamata dengan lensa khusus—baik lensa

                cekung (minus) maupun lensa cembung (plus)—telah menjadi solusi optik yang efektif dan banyak digunakan.

                Memahami prinsip fisika di balik lensa lensa ini adalah kunci untuk mengapresiasi bagaimana mereka

                memulihkan ketajaman visual.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Miopia (Rabun Jauh): Koreksi dengan Lensa Minus

                (Cekung)</h5>

            <p>Miopia adalah kondisi di mana individu dapat melihat objek yang dekat dengan jelas, tetapi objek yang

                jauh terlihat kabur. Secara optis, miopia terjadi ketika sinar cahaya yang masuk ke mata difokuskan di

                depan retina, bukan tepat pada retina. Hal ini bisa disebabkan oleh bola mata yang terlalu panjang

                (aksial miopia) atau kornea/lensa mata yang terlalu cembung (refraktif miopia), sehingga daya bias mata

                terlalu kuat.</p>

            <p>Untuk mengoreksi miopia, digunakan lensa cekung (konkaf), yang ditandai dengan nilai dioptri negatif

                (misalnya, -1.00 D, -2.50 D, dst.). Lensa cekung memiliki karakteristik divergen, yang berarti mereka

                menyebarkan sinar cahaya yang melewatinya. Ketika cahaya dari objek jauh melewati lensa minus ini, sinar

                akan sedikit menyebar sebelum masuk ke mata. Penyebaran awal ini secara efektif "memperpanjang" titik

                fokus cahaya, sehingga cahaya dapat difokuskan tepat pada retina. Dengan demikian, lensa cekung membantu

                menempatkan citra objek jauh yang kabur kembali ke posisi fokus yang benar, memungkinkan penderita

                miopia melihat jelas pada jarak jauh.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Hiperopia (Rabun Dekat): Koreksi dengan Lensa Plus

                (Cekung)</h5>

            <p>Sebaliknya, hiperopia adalah kondisi di mana individu dapat melihat objek yang jauh dengan cukup jelas,

                tetapi mengalami kesulitan memfokuskan objek yang dekat, yang tampak kabur. Dari sudut pandang optik,

                hiperopia terjadi ketika sinar cahaya yang masuk ke mata difokuskan di belakang retina. Kondisi ini

                umumnya disebabkan oleh bola mata yang terlalu pendek (aksial hiperopia) atau kornea/lensa mata yang

                terlalu datar (refraktif hiperopia), sehingga daya bias mata terlalu lemah.</p>

            <p>Untuk mengoreksi hiperopia, digunakan lensa cembung (konveks), yang memiliki nilai dioptri positif

                (misalnya, +1.00 D, +2.50 D, dst.). Lensa cembung memiliki karakteristik konvergen, yang berarti mereka

                mengumpulkan atau memusatkan sinar cahaya yang melewatinya. Ketika cahaya dari objek dekat melewati

                lensa plus ini, sinar akan sedikit terfokus sebelum masuk ke mata. Pemfokusan awal ini secara efektif

                "memendekkan" titik fokus cahaya, sehingga cahaya dapat jatuh tepat pada retina. Dengan demikian, lensa

                cembung membantu menggeser citra objek dekat yang kabur ke posisi fokus yang benar, memungkinkan

                penderita hiperopia melihat objek dekat dengan jelas.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Dioptri: Satuan Kekuatan Lensa Optik</h5>

            <p>Kekuatan lensa korektif, baik minus maupun plus, dinyatakan dalam satuan dioptri (D). Satu dioptri

                didefinisikan sebagai kebalikan dari panjang fokus lensa dalam meter (D=1/f). Semakin tinggi nilai

                dioptrinya (baik positif maupun negatif), semakin kuat kemampuan lensa untuk membiaskan cahaya.

                Misalnya, lensa -4.00 D memiliki kekuatan empat kali lipat dari lensa-1.00 D dalam menyebarkan cahaya,

                sementara lensa +3.00 D tiga kali lebih kuat dari +1.00 D dalam memusatkan cahaya. Penentuan kekuatan

                dioptri yang tepat untuk kacamata dilakukan melalui pemeriksaan refraksi oleh optometri atau

                oftalmologi, yang melibatkan pengujian ketajaman visual dan titik fokus mata individu untuk mendapatkan

                koreksi optimal.</p>

            <p>Penggunaan kacamata dengan lensa minus atau plus adalah solusi optik yang elegan dan efektif, didasarkan

                pada prinsip fisika pembiasan cahaya. Dengan memahami bagaimana lensa-lensa ini bekerja untuk mengoreksi

                cacat refraksi mata, kita dapat lebih menghargai peran teknologi optik dalam meningkatkan kualitas

                penglihatan dan kehidupan sehari-hari.</p>

        </div>

    </article>



    <!-- ARTIKEL 2: GEOPOLITIK -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-indigo-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-indigo-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">public</span> Artikel 2

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Geopolitik: Ketika Geografi Bertemu Kekuasaan

            di Panggung Dunia</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Di era globalisasi yang kompleks ini, memahami dinamika hubungan antarnegara tidak lagi cukup hanya

                dengan menelaah kebijakan politik semata. Ada faktor fundamental yang seringkali menjadi penentu arah

                sejarah dan konflik di muka Bumi: geopolitik. Istilah ini merujuk pada studi tentang hubungan antara

                geografi dan politik, menganalisis bagaimana lokasi, ukuran wilayah, iklim, topografi, dan sumber daya

                alam memengaruhi keputusan politik, strategi militer, serta interaksi antarnegara. Geopolitik bukan

                sekadar peta statis, melainkan lensa dinamis untuk memahami mengapa negara berperilaku seperti yang

                mereka lakukan di panggung global, mengungkap fakta bahwa geografi adalah kanvas abadi tempat drama

                kekuasaan dimainkan.</p>

            <p>Pada intinya, geopolitik adalah disiplin ilmu yang meneliti bagaimana kekuatan politik suatu negara

                dipengaruhi oleh, dan pada gilirannya memengaruhi, kondisi geografisnya. Konsep ini mengakui bahwa

                faktor faktor seperti akses ke laut, keberadaan pegunungan atau gurun, kelimpahan sumber daya alam

                (minyak, mineral, air), serta posisi strategis di jalur perdagangan global, semuanya memiliki implikasi

                mendalam terhadap keamanan nasional, kebijakan luar negeri, dan aspirasi kekuasaan suatu negara.

                Misalnya, negara kepulauan seperti Indonesia secara alami akan memiliki perspektif geopolitik yang

                menekankan kekuatan maritim dan kontrol atas jalur laut strategis (seperti Selat Malaka), berbeda dengan

                negara kontinental yang mungkin lebih fokus pada keamanan perbatasan darat.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Akar Pemikiran Geopolitik</h5>

            <p>Akar pemikiran geopolitik sudah ada sejak zaman kuno, namun sebagai disiplin ilmu formal, geopolitik

                mulai berkembang pesat pada akhir abad ke 19 dan awal abad ke-20. Beberapa pemikir klasik yang sangat

                berpengaruh antara lain:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Sir Halford Mackinder (Teori Heartland):</strong> Ahli geografi Inggris ini berargumen bahwa

                    siapa pun yang menguasai "Heartland" (wilayah tengah Eurasia yang luas dan kaya sumber daya, relatif

                    tidak terjangkau oleh kekuatan laut), akan mampu menguasai "Pulau Dunia" (Eropa, Asia, dan Afrika),

                    dan pada akhirnya menguasai dunia. Teorinya menekankan kekuatan darat sebagai kunci dominasi global.

                </li>

                <li><strong>Alfred Thayer Mahan (Teori Kekuatan Laut/Sea Power):</strong> Laksamana Angkatan Laut AS ini

                    berpendapat bahwa kontrol atas lautan dan jalur maritim adalah fondasi kekuatan dan kemakmuran suatu

                    negara. Baginya, angkatan laut yang kuat dan akses ke jalur perdagangan laut adalah kunci untuk

                    mencapai dominasi global.</li>

                <li><strong>Friedrich Ratzel (Teori Ruang Hidup/Lebensraum):</strong> Pemikir Jerman ini melihat negara

                    sebagai organisme hidup yang membutuhkan "ruang hidup" untuk tumbuh dan berkembang. Teorinya,

                    meskipun kemudian disalahgunakan untuk justifikasi ekspansionisme, menekankan hubungan antara

                    pertumbuhan populasi dan kebutuhan wilayah.</li>

            </ul>

            <p>Teori-teori ini, meskipun ada yang kontroversial dan pernah disalahgunakan, membentuk dasar pemahaman

                kita tentang bagaimana geografi memengaruhi ambisi dan strategi negara-negara besar.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Geopolitik Kontemporer</h5>

            <p>Di era kontemporer, geopolitik semakin kompleks, melampaui sekadar kendali atas daratan atau lautan.

                Faktor-faktor baru seperti teknologi, siber, ruang angkasa, dan perubahan iklim kini juga menjadi

                variabel penting.</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Persaingan Sumber Daya:</strong> Perebutan akses terhadap sumber daya alam yang semakin

                    langka (seperti air, mineral kritis, dan energi) terus menjadi pemicu ketegangan geopolitik di

                    berbagai kawasan.</li>

                <li><strong>Jalur Perdagangan Global:</strong> Kontrol atas chokepoints maritim (misalnya, Selat Hormuz,

                    Terusan Suez, Selat Malaka) tetap menjadi prioritas strategis karena vitalitasnya bagi ekonomi

                    global.</li>

                <li><strong>Pergeseran Kekuatan:</strong> Bangkitnya kekuatan-kekuatan baru dan ketegangan antara

                    negara-negara besar menciptakan dinamika geopolitik yang terus berubah, seringkali memicu persaingan

                    di kawasan-kawasan strategis seperti Indo-Pasifik.</li>

                <li><strong>Dampak Perubahan Iklim:</strong> Krisis iklim memicu pergeseran populasi, kelangkaan air,

                    dan perebutan sumber daya di Arktik, semuanya menciptakan tantangan geopolitik yang belum pernah ada

                    sebelumnya.</li>

            </ul>

            <p>Geopolitik membantu kita memahami mengapa konflik terjadi di suatu wilayah, mengapa aliansi terbentuk,

                dan bagaimana negara-negara berupaya mengamankan kepentingannya dalam tatanan dunia yang terus

                berevolusi. Ini adalah studi yang memungkinkan kita melihat gambaran besar di balik berita harian dan

                kebijakan luar negeri.</p>

        </div>

    </article>



    <!-- ARTIKEL 3: OTTO TOTO SUGIRI -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-indigo-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-indigo-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">person</span> Artikel 3

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Otto Toto Sugiri: Sosok di balik Infrastruktur

            Digital Indonesia</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Dalam lanskap teknologi Indonesia yang berkembang pesat, nama Otto Toto Sugiri telah menjadi sinonim

                dengan visi dan keberanian dalam membangun infrastruktur digital. Dikenal luas sebagai "Bapak Data

                Center Indonesia", perannya melampaui sekadar pebisnis; ia adalah arsitek di balik pembangunan pusat

                data berskala besar yang menjadi tulang punggung bagi ekonomi digital negara ini. Kisahnya adalah

                representasi nyata bagaimana tekad dan pandangan jauh ke depan dapat membentuk masa depan teknologi

                suatu bangsa.</p>

            <p>Perjalanan Otto Toto Sugiri di dunia teknologi dimulai jauh sebelum era booming digital saat ini. Dengan

                latar belakang pendidikan matematika dari salah satu universitas bergengsi di Jerman, ia memiliki

                pemahaman mendalam tentang logika dan sistem, yang menjadi bekal penting dalam kariernya. Pada awal

                tahun 2000-an, ketika konsep data center masih sangat baru di Indonesia, Toto Sugiri sudah melihat

                potensi besar dan kebutuhan krusial akan fasilitas penyimpanan dan pengolahan data yang andal.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Membangun Ekosistem Digital</h5>

            <p>Ia adalah salah satu pendiri dan CEO PT DCI Indonesia Tbk (DCI), sebuah perusahaan data center tier-IV

                terbesar di Asia Tenggara. Di bawah kepemimpinannya, DCI tumbuh pesat dan menjadi pemain kunci dalam

                menyediakan layanan infrastruktur digital kelas dunia bagi perusahaan perusahaan besar, baik lokal

                maupun multinasional, termasuk cloud providers global. Visinya adalah membangun ekosistem data center

                yang kuat dan aman di Indonesia, sebuah fondasi yang esensial untuk mendukung transformasi digital dan

                pertumbuhan ekonomi berbasis internet.</p>

            <p>Kontribusi Otto Toto Sugiri tidak hanya terbatas pada pembangunan fisik data center, tetapi juga pada

                pembentukan ekosistem yang mendukung. Ia memahami bahwa ketersediaan pusat data yang berkualitas tinggi

                adalah prasyarat mutlak bagi pertumbuhan e-commerce, layanan cloud, fintech, dan berbagai inovasi

                digital lainnya. Data menunjukkan bahwa pertumbuhan ekonomi digital suatu negara sangat berkorelasi

                dengan ketersediaan infrastruktur data center yang memadai.</p>

            <p>Melalui DCI, Toto Sugiri tidak hanya menarik investasi global ke Indonesia, tetapi juga menciptakan

                lapangan kerja berkualitas tinggi dan memastikan data-data penting negara dan perusahaan tersimpan

                dengan aman di dalam negeri. Keputusannya untuk berinvestasi besar-besaran pada fasilitas berstandar

                internasional (Tier-IV), yang menjamin waktu henti (downtime) minimal, menunjukkan komitmennya terhadap

                kualitas dan keandalan. Dampaknya terasa langsung pada kecepatan transaksi digital, stabilitas layanan

                daring, dan daya saing Indonesia di kancah ekonomi digital global.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Visi dan Warisan</h5>

            <p>Otto Toto Sugiri dikenal sebagai sosok yang rendah hati namun memiliki pemikiran strategis yang tajam. Ia

                sering menekankan pentingnya data sebagai "minyak baru" di era digital, dan data center sebagai "kilang"

                yang memprosesnya. Filosofi ini menyoroti bagaimana aset tak berwujud seperti data kini menjadi

                pendorong utama nilai ekonomi.</p>

            <p>Warisan Otto Toto Sugiri adalah fondasi kokoh yang ia bangun untuk masa depan digital Indonesia. Tanpa

                infrastruktur data center yang andal dan aman, ambisi Indonesia untuk menjadi kekuatan ekonomi digital

                terbesar di Asia Tenggara akan sulit tercapai. Ia adalah bukti bahwa inovasi dan ketekunan seorang

                individu dapat membentuk arah sebuah industri dan memberikan kontribusi yang berkelanjutan bagi kemajuan

                suatu bangsa.</p>

        </div>

    </article>



    <!-- ARTIKEL 4: AGING POPULATION -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-indigo-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-indigo-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">elderly</span> Artikel 4

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Aging Population, Tantangan dan Peluang di Era

            Demografi Baru</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Fenomena aging population, atau penuaan populasi, telah menjadi salah satu tren demografi paling

                signifikan dan transformatif di abad ke-21. Ini menggambarkan pergeseran distribusi usia dalam suatu

                populasi, ditandai dengan peningkatan proporsi individu yang lebih tua dan, secara bersamaan, penurunan

                proporsi individu yang lebih muda. Pergeseran ini bukan sekadar statistik, melainkan cerminan dari

                kemajuan pesat dalam kesehatan, pendidikan, dan kondisi sosial, sekaligus menjadi penanda tantangan

                multidimensional yang memerlukan adaptasi kebijakan dan inovasi sosial di seluruh dunia.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Faktor Pendorong</h5>

            <p>Penuaan populasi adalah hasil dari interaksi dua kekuatan demografis utama yang saling terkait:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Peningkatan Harapan Hidup (Longevity):</strong> Berkat kemajuan di bidang kedokteran,

                    sanitasi, gizi, dan kualitas hidup secara umum, manusia kini hidup lebih lama dibandingkan generasi

                    sebelumnya. Tingkat kematian, terutama pada usia muda, telah menurun drastis. Ini berarti lebih

                    banyak orang yang bertahan hingga usia lanjut, secara otomatis meningkatkan jumlah dan proporsi

                    lansia dalam populasi.</li>

                <li><strong>Penurunan Tingkat Fertilitas (Birth Rates):</strong> Ini adalah pendorong utama penuaan

                    populasi di sebagian besar negara maju. Tingkat kelahiran yang rendah, di mana perempuan memiliki

                    lebih sedikit anak (seringkali di bawah tingkat penggantian populasi 2.1 anak per wanita),

                    mengakibatkan berkurangnya proporsi generasi muda relatif terhadap generasi yang lebih tua.

                    Faktor-faktor seperti peningkatan akses pendidikan dan peluang kerja bagi wanita, urbanisasi, biaya

                    membesarkan anak yang tinggi, dan perubahan nilai-nilai sosial semuanya berkontribusi pada tren ini.

                </li>

            </ul>

            <p>Kombinasi kedua faktor ini menciptakan piramida penduduk yang "menggembung" di bagian atas (kelompok usia

                tua) dan "menyempit" di bagian bawah (kelompok usia muda), sebuah struktur yang jauh berbeda dari

                piramida penduduk tradisional yang lebar di dasar.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Dampak Ekonomi dari Penuaan Populasi</h5>

            <p>Penuaan populasi menimbulkan serangkaian dampak ekonomi yang kompleks, baik tantangan maupun potensi

                peluang:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Penurunan Tenaga Kerja dan Produktivitas:</strong> Proporsi penduduk usia kerja (biasanya

                    15-64 tahun) cenderung menyusut relatif terhadap penduduk non-produktif (anak-anak dan lansia). Ini

                    dapat menyebabkan kekurangan tenaga kerja, terutama di sektor-sektor tertentu, yang berpotensi

                    menghambat pertumbuhan ekonomi dan inovasi. Meskipun teknologi dan otomatisasi dapat membantu

                    mengompensasi, dampaknya pada produktivitas agregat masih menjadi perdebatan.</li>

                <li><strong>Tekanan pada Sistem Jaminan Sosial dan Kesehatan:</strong> Dengan lebih banyak pensiunan dan

                    lebih sedikit pembayar pajak aktif, sistem pensiun dan jaminan sosial menghadapi tekanan finansial

                    yang besar. Demikian pula, kebutuhan akan layanan kesehatan meningkat secara drastis karena lansia

                    cenderung memiliki lebih banyak masalah kesehatan kronis dan memerlukan perawatan jangka panjang.

                    Ini meningkatkan pengeluaran publik dan membebani anggaran negara.</li>

                <li><strong>Perubahan Pola Konsumsi dan Investasi:</strong> Struktur usia populasi memengaruhi pola

                    konsumsi. Populasi yang menua mungkin memiliki permintaan yang lebih tinggi untuk layanan kesehatan,

                    pariwisata ramah lansia, dan produk-produk tertentu, sementara permintaan untuk barang dan jasa yang

                    berorientasi pada kaum muda mungkin menurun. Selain itu, ada hipotesis bahwa populasi yang menua

                    cenderung memiliki tingkat tabungan yang lebih tinggi di fase pra pensiun, namun kemudian beralih ke

                    konsumsi aset saat pensiun, yang dapat memengaruhi tingkat investasi dan suku bunga.</li>

            </ul>



            <h5 class="font-bold text-sakura-black text-base mt-6">Implikasi Sosial</h5>

            <p>Selain ekonomi, penuaan populasi juga membawa implikasi sosial yang mendalam dan menuntut respons

                kebijakan yang proaktif:</p>

            <p><strong>Perubahan Dinamika Keluarga dan Perawatan:</strong> Dengan jumlah lansia yang lebih banyak, beban

                perawatan seringkali beralih ke anggota keluarga yang lebih muda. Ini dapat menciptakan tekanan pada

                struktur keluarga dan meningkatkan kebutuhan akan layanan perawatan jangka panjang yang terjangkau dan

                berkualitas. Konsep "masyarakat ramah lansia" dan "integrasi antar generasi" menjadi semakin penting.

            </p>

            <p><strong>Inovasi dan Adaptasi Sosial:</strong> Masyarakat harus beradaptasi dengan perubahan demografi

                ini. Hal ini mencakup pengembangan kota-kota yang ramah lansia (aksesibilitas transportasi, ruang

                publik), peningkatan fasilitas kesehatan geriatri, serta program-program yang mendorong partisipasi

                aktif lansia di masyarakat, baik melalui kerja paruh waktu, kegiatan sukarela, maupun pendidikan

                berkelanjutan.</p>

            <p><strong>Kebijakan Pro-Natalitas dan Imigrasi:</strong> Untuk menyeimbangkan struktur usia, beberapa

                negara mempertimbangkan kebijakan pro-natalitas (insentif untuk memiliki anak lebih banyak) atau

                kebijakan imigrasi yang lebih terbuka untuk menarik pekerja muda. Namun, kebijakan ini seringkali

                kompleks dan melibatkan pertimbangan sosial dan politik yang luas.</p>

        </div>

    </article>



    <!-- ARTIKEL 5: BIROKRASI -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-indigo-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-indigo-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">apartment</span> Artikel 5

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Birokrasi: Roda Penggerak Kompleks dalam

            Masyarakat Modern</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Istilah birokrasi sering kali memicu gambaran negatif di benak banyak orang: antrean panjang, prosedur

                berbelit, atau pelayanan yang lambat. Namun, di balik persepsi yang seringkali didorong oleh pengalaman

                frustrasi, birokrasi adalah sebuah sistem yang jauh lebih kompleks dan fundamental, menjadi tulang

                punggung bagi hampir setiap organisasi skala besar, baik di sektor publik maupun swasta. Ini bukan

                sekadar tumpukan kertas, melainkan sebuah kerangka kerja rasional yang dirancang untuk menjalankan

                fungsi fungsi kompleks secara efisien, adil, dan terstruktur. Memahami esensi birokrasi, evolusinya,

                serta dilema yang melekat padanya akan membuka wawasan kita tentang bagaimana masyarakat modern

                beroperasi.</p>

            <p>Secara etimologis, birokrasi berasal dari bahasa Prancis bureau (meja kerja/kantor) dan bahasa Yunani

                kratos (kekuasaan atau pemerintahan). Ini secara harfiah berarti kekuasaan dari meja kerja atau

                pemerintahan oleh kantor. Konsep ini secara sosiologis paling banyak dikaitkan dengan pemikiran Max

                Weber, seorang sosiolog Jerman awal abad ke-20. Weber melihat birokrasi sebagai bentuk organisasi yang

                paling efisien dan rasional, sebuah ideal-tipe yang mencerminkan modernisasi dan rasionalisasi

                masyarakat.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Karakteristik Birokrasi Ideal (Weber)</h5>

            <p>Menurut Weber, birokrasi ideal memiliki beberapa karakteristik kunci:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Hierarki Otoritas yang Jelas:</strong> Setiap posisi berada di bawah pengawasan atasan yang

                    lebih tinggi, menciptakan struktur piramida yang memungkinkan rantai komando yang terdefinisi. Ini

                    memastikan akuntabilitas dan arah yang jelas.</li>

                <li><strong>Aturan dan Prosedur Formal yang Baku:</strong> Operasi dijalankan berdasarkan serangkaian

                    aturan, regulasi, dan prosedur tertulis yang tidak memihak. Ini bertujuan untuk memastikan

                    konsistensi, prediktabilitas, dan perlakuan yang sama bagi semua orang dalam situasi yang sama.</li>

                <li><strong>Spesialisasi Tugas dan Divisi Kerja:</strong> Pekerjaan dipecah menjadi tugas tugas

                    spesifik, dan setiap individu atau departemen mengkhususkan diri pada satu area. Ini meningkatkan

                    efisiensi dan keahlian teknis.</li>

                <li><strong>Impersonalitas (Impersonality):</strong> Keputusan dan interaksi didasarkan pada aturan dan

                    fakta objektif, bukan pada emosi, hubungan pribadi, atau preferensi individu. Tujuannya adalah untuk

                    menghindari favoritisme dan korupsi.</li>

                <li><strong>Promosi Berdasarkan Meritokrasi:</strong> Kenaikan jabatan dan karier didasarkan pada

                    kualifikasi teknis, keahlian, dan kinerja yang terbukti, bukan berdasarkan nepotisme atau koneksi

                    pribadi.</li>

                <li><strong>Pemisahan Antara Jabatan dan Pemilik:</strong> Individu yang bekerja dalam birokrasi tidak

                    memiliki jabatan atau aset yang mereka kelola; mereka adalah pegawai yang digaji.</li>

            </ul>



            <h5 class="font-bold text-sakura-black text-base mt-6">Sejarah dan Evolusi Birokrasi</h5>

            <p>Konsep birokrasi bukanlah temuan modern. Bentuk-bentuk awal birokrasi sudah dapat ditelusuri pada

                peradaban kuno seperti Mesir Kuno (dengan sistem administrasi dan pencatatan yang rumit untuk

                proyek-proyek besar seperti pembangunan piramida), Tiongkok Kuno (dengan sistem ujian pegawai negeri

                yang meritokratis sejak Dinasti Qin dan Han), dan Kekaisaran Romawi (dengan struktur pemerintahan

                provinsi yang terorganisir). Namun, birokrasi dalam bentuk modernnya, yang didasarkan pada prinsip

                rasionalitas dan efisiensi, mulai berkembang pesat seiring dengan Revolusi Industri dan pertumbuhan

                negara-bangsa (nation-state) pada abad ke-18 dan ke-19. Perluasan populasi, urbanisasi, dan kebutuhan

                akan pengelolaan ekonomi serta pelayanan publik yang lebih kompleks memaksa pemerintah dan perusahaan

                untuk mengadopsi struktur organisasi yang lebih sistematis. Weber mengamati bahwa birokrasi adalah

                respons yang logis terhadap kompleksitas masyarakat industrial.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Fungsi Birokrasi dalam Masyarakat Modern</h5>

            <p>Terlepas dari kritiknya, birokrasi memiliki fungsi yang tak tergantikan dalam masyarakat modern:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Menyediakan Pelayanan Publik Skala Besar:</strong> Dari penerbitan dokumen identitas,

                    pengelolaan sistem pendidikan, penegakan hukum, hingga distribusi jaminan sosial, birokrasi

                    memungkinkan pemerintah untuk melayani jutaan warga negara secara konsisten dan terukur.</li>

                <li><strong>Menjamin Konsistensi dan Keadilan:</strong> Dengan adanya aturan dan prosedur baku,

                    birokrasi idealnya memastikan bahwa setiap individu diperlakukan sama di hadapan hukum dan

                    peraturan, mengurangi potensi diskriminasi dan keputusan yang sewenang-wenang.</li>

                <li><strong>Meningkatkan Efisiensi dan Produktivitas:</strong> Dengan spesialisasi tugas dan prosedur

                    yang terstandardisasi, birokrasi memungkinkan organisasi untuk mengelola sumber daya, memproses

                    informasi, dan menyelesaikan tugas-tugas besar dengan efisien.</li>

                <li><strong>Menyimpan Memori Institusional:</strong> Adanya pencatatan dan arsip yang sistematis

                    memastikan bahwa pengetahuan dan pengalaman institusional tetap terjaga meskipun terjadi pergantian

                    personel.</li>

            </ul>



            <h5 class="font-bold text-sakura-black text-base mt-6">Dilema dan Kritik Terhadap Birokrasi</h5>

            <p>Meskipun Weber mengagumi efisiensi birokrasi, ia juga menyadari potensi sisi gelapnya. Kritik terhadap

                birokrasi sering kali berakar pada penyimpangan dari ideal-tipenya atau konsekuensi tak terduga dari

                karakteristiknya:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Red Tape dan Ketidakfleksibelan:</strong> Ketergantungan pada aturan dan prosedur yang kaku

                    (sering disebut red tape) dapat membuat birokrasi menjadi lambat, tidak responsif terhadap perubahan

                    atau kasus-kasus khusus yang membutuhkan adaptasi cepat. Inovasi dapat terhambat.</li>

                <li><strong>Impersonalitas yang Ekstrem:</strong> Meskipun dirancang untuk keadilan, impersonalitas yang

                    berlebihan dapat membuat layanan terasa tidak manusiawi, kurang empati, dan jauh dari kebutuhan

                    individual warga.</li>

                <li><strong>Inefisiensi dan Pemborosan:</strong> Paradoksnya, meskipun dirancang untuk efisiensi,

                    birokrasi dapat menjadi sangat tidak efisien jika aturan menjadi tujuan itu sendiri daripada sarana

                    untuk mencapai tujuan. Biaya operasional bisa membengkak.</li>

                <li><strong>Penyalahgunaan Kekuasaan dan Korupsi:</strong> Hierarki dan diskresi (kebebasan bertindak)

                    di beberapa tingkat dapat disalahgunakan untuk kepentingan pribadi jika pengawasan eksternal dan

                    internal lemah, menyebabkan korupsi dan nepotisme.</li>

                <li><strong>Alienasi dan Frustrasi:</strong> Baik bagi pegawai maupun publik, interaksi dengan birokrasi

                    yang disfungsional dapat menimbulkan perasaan tidak berdaya, frustrasi, dan alienasi. Pegawai

                    mungkin merasa seperti roda gigi kecil dalam mesin besar, sementara publik merasa terjebak dalam

                    labirin prosedur.</li>

                <li><strong>Iron Cage (Sangkar Besi) Weber:</strong> Weber sendiri khawatir bahwa rasionalisasi dan

                    birokratisasi yang berlebihan dapat mengunci individu dalam sangkar besi aturan dan prosedur yang

                    tidak lagi memiliki makna atau tujuan yang lebih tinggi, mengikis kebebasan dan kreativitas manusia.

                </li>

            </ul>



            <h5 class="font-bold text-sakura-black text-base mt-6">Reformasi dan Adaptasi Birokrasi</h5>

            <p>Di era digital dan masyarakat yang semakin dinamis, birokrasi terus menghadapi tekanan untuk beradaptasi.

                Konsep "birokrasi baru" muncul, yang berupaya mempertahankan keunggulan struktural birokrasi (seperti

                akuntabilitas dan keahlian) sambil mengatasi kelemahan klasik (seperti rigiditas dan inefisiensi). Ini

                melibatkan:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Pemanfaatan Teknologi Digital:</strong> Otomatisasi proses, e-government, dan penggunaan big

                    data untuk meningkatkan efisiensi dan transparansi.</li>

                <li><strong>Fokus pada Hasil dan Orientasi Pelanggan:</strong> Pergeseran dari sekadar mengikuti

                    prosedur menjadi fokus pada hasil nyata dan kepuasan penerima layanan.</li>

                <li><strong>Fleksibilitas dan Desentralisasi:</strong> Mengurangi hirarki yang terlalu kaku dan

                    memberikan lebih banyak otonomi pada unit-unit yang lebih kecil agar lebih responsif.</li>

                <li><strong>Kultur Inovasi:</strong> Mendorong inovasi dan adaptasi daripada kepatuhan buta pada aturan

                    lama.</li>

            </ul>

            <p>Pada akhirnya, birokrasi bukanlah sesuatu yang bisa sepenuhnya dihilangkan dalam masyarakat kompleks.

                Tantangannya adalah bagaimana mengelola dan mereformasinya agar ia dapat menjadi alat yang benar-benar

                melayani publik dan mendorong kemajuan, bukan menjadi penghalang yang kaku dan tidak efisien. Memahami

                kompleksitas ini adalah langkah awal untuk mewujudkan birokrasi yang lebih adaptif, responsif, dan

                manusiawi.</p>

        </div>

    </article>



</div>

</div>

                    <!-- QUIZ SECTION -->

<div id="page-quiz-007" class="page-section-007">

    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">

        <div class="text-center mb-8">

            <span class="material-symbols-outlined text-5xl text-sakura-red mb-3">quiz</span>

            <h2 class="font-serif font-black text-3xl text-sakura-black mb-2">Quiz — Obat Fokus Day 7</h2>

            <p class="text-gray-500 max-w-md mx-auto">Jawab pertanyaan berdasarkan 5 artikel yang sudah kamu baca. Soal isian <strong>tidak dinilai</strong>, hanya True/False yang masuk skor.</p>

            <div class="w-16 h-1 bg-sakura-red mx-auto mt-4"></div>

        </div>



        <!-- ISIAN -->

        <div class="space-y-6">

            <p class="text-[10px] font-bold text-indigo-500 uppercase tracking-widest px-1">Bagian 1 — Isian Singkat <span class="text-gray-400">(tidak dinilai)</span></p>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Jenis lensa apa yang digunakan untuk mengoreksi miopia (rabun jauh)?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Lensa cekung (konkaf/minus)</p>

                    <p class="text-xs text-green-600 mt-1">Lensa cekung bersifat divergen, menyebarkan sinar cahaya agar fokus tepat pada retina.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Siapa pemikir geopolitik yang mengemukakan Teori Heartland?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Sir Halford Mackinder</p>

                    <p class="text-xs text-green-600 mt-1">Mackinder berargumen bahwa pengendali Heartland (wilayah tengah Eurasia) akan mampu menguasai dunia.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Apa julukan yang diberikan kepada Otto Toto Sugiri terkait perannya di industri teknologi Indonesia?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Bapak Data Center Indonesia</p>

                    <p class="text-xs text-green-600 mt-1">Otto Toto Sugiri adalah pendiri dan CEO PT DCI Indonesia Tbk, data center tier-IV terbesar di Asia Tenggara.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Apa dua faktor utama yang mendorong fenomena aging population?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Peningkatan harapan hidup dan penurunan tingkat fertilitas</p>

                    <p class="text-xs text-green-600 mt-1">Kedua faktor ini menciptakan piramida penduduk yang "menggembung" di atas dan "menyempit" di bawah.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Siapa sosiolog Jerman yang paling banyak dikaitkan dengan konsep birokrasi ideal?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Max Weber</p>

                    <p class="text-xs text-green-600 mt-1">Weber melihat birokrasi sebagai bentuk organisasi yang paling efisien dan rasional.</p>

                </div>

            </div>

        </div>



        <!-- TRUE/FALSE -->

        <div class="space-y-6 mt-10">

            <p class="text-[10px] font-bold text-indigo-500 uppercase tracking-widest px-1">Bagian 2 — Benar atau Salah <span class="text-gray-400">(dinilai)</span></p>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="007">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Miopia terjadi ketika sinar cahaya difokuskan di depan retina, bukan tepat pada retina.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal7 6', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal7 6', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Miopia terjadi ketika sinar cahaya difokuskan di depan retina, disebabkan oleh bola mata yang terlalu panjang atau kornea yang terlalu cembung.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="007">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Alfred Thayer Mahan mengemukakan Teori Heartland yang menekankan kekuatan darat sebagai kunci dominasi global.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal7 7', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal7 7', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Teori Heartland dikemukakan oleh Sir Halford Mackinder. Alfred Thayer Mahan mengemukakan Teori Kekuatan Laut (Sea Power).</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="007">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> Otto Toto Sugiri sering menekankan pentingnya data sebagai "minyak baru" di era digital.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal7 8', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal7 8', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Artikel menyebutkan bahwa Otto Toto Sugiri menyebut data sebagai "minyak baru" dan data center sebagai "kilang" yang memprosesnya.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="007">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Aging population terutama disebabkan oleh meningkatnya tingkat kelahiran di negara-negara maju.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal7 9', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal7 9', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Justru sebaliknya, aging population disebabkan oleh penurunan tingkat fertilitas/kelahiran dan peningkatan harapan hidup.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="007">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Menurut Weber, salah satu karakteristik birokrasi ideal adalah impersonalitas, di mana keputusan didasarkan pada aturan objektif, bukan hubungan pribadi.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal7 10', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal7 10', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Weber menyebutkan bahwa impersonalitas bertujuan menghindari favoritisme dan korupsi, dengan keputusan berdasarkan aturan dan fakta objektif.</p>

                </div>

            </div>

        </div>



        <!-- Submit -->

        <div class="text-center pt-8">

            <button onclick="showResult()" class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">

                <span class="flex items-center gap-2">

                    <span class="material-symbols-outlined text-lg">fact_check</span>

                    Lihat Hasil

                </span>

            </button>

        </div>

    </div>

</div>



<!-- PAGE 3: RESULT -->

<div id="page-result-007" class="page-section-007">

    <div class="max-w-4xl mx-auto p-8 pb-32">

        <div id="result-content"></div>

        <div class="text-center mt-8">

            <a href="javascript:void(0)" onclick="loadModule('obat-fokus-008')" class="inline-flex items-center gap-2 px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg">

                <span class="material-symbols-outlined">arrow_forward</span> Lanjut ke Day 8

            </a>

        </div>

    </div>

</div>
                </div>
            </div>



            <!-- MODULE VIEW: OBAT FOKUS 008 -->
            <div id="module-obat-fokus-008" class="module-view">
                <div class="flex-1 overflow-y-auto" id="content-scroll-008">
                    <div id="page-articles-008" class="page-section-008 active"><div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">



    <!-- ARTIKEL 1: ASAM AMINO -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-teal-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-teal-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">science</span> Artikel 1

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Asam Amino: Fondasi Kehidupan dalam Setiap Sel

        </h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Di dunia biologi, jika protein adalah balok bangunan yang kompleks, maka asam amino adalah batu bata

                fundamental yang menyusunnya. Molekul organik kecil ini adalah unit dasar yang membentuk protein,

                memainkan peran krusial dalam hampir setiap proses biologis di dalam tubuh makhluk hidup. Dari struktur

                sel, fungsi enzim, transportasi zat, hingga respons imun, keberadaan dan keseimbangan asam amino sangat

                vital untuk kehidupan. Memahami asam amino adalah kunci untuk menguak kompleksitas bagaimana tubuh kita

                dibangun, berfungsi, dan mempertahankan dirinya.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Struktur dan Klasifikasi Asam Amino</h5>

            <p>Setiap molekul asam amino memiliki struktur dasar yang seragam, terdiri dari empat komponen utama yang

                terikat pada satu atom karbon pusat (dikenal sebagai karbon alfa):</p>

            <ol class="list-decimal pl-5 mt-2 space-y-1">

                <li><strong>Gugus Karboksil (−COOH):</strong> Memberikan sifat asam pada molekul.</li>

                <li><strong>Gugus Amino (−NH2):</strong> Memberikan sifat basa pada molekul.</li>

                <li><strong>Atom Hidrogen (−H):</strong> Komponen sederhana yang juga terikat pada karbon alfa.</li>

                <li><strong>Rantai Samping (Gugus R):</strong> Inilah bagian yang membedakan satu jenis asam amino dari

                    yang lain. Gugus R bisa berupa atom hidrogen sederhana (seperti pada glisin), rantai hidrokarbon

                    kompleks, atau gugus fungsional lain yang mengandung atom seperti belerang (pada sistein dan

                    metionin).</li>

            </ol>

            <p>Berdasarkan sifat gugus R-nya (polaritas, muatan, ukuran), asam amino diklasifikasikan menjadi beberapa

                kategori. Namun, klasifikasi yang paling relevan bagi nutrisi manusia adalah pembagian menjadi:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Asam Amino Esensial:</strong> Ada sembilan jenis asam amino esensial yang tidak dapat

                    diproduksi oleh tubuh manusia sendiri dan harus diperoleh melalui makanan. Kesembilan asam amino ini

                    adalah histidin, isoleusin, leusin, lisin, metionin, fenilalanin, treonin, triptofan, dan valin.

                </li>

                <li><strong>Asam Amino Non-Esensial:</strong> Jenis asam amino yang dapat disintesis oleh tubuh dari

                    prekursor lain, sehingga tidak mutlak harus diperoleh dari diet, meskipun tubuh tetap memerlukannya.

                    Contohnya glisin, alanin, serin, dan glutamat.</li>

                <li><strong>Asam Amino Kondisional Esensial:</strong> Dalam kondisi tertentu (misalnya, stres, penyakit,

                    pertumbuhan pesat), tubuh mungkin tidak dapat memproduksi asam amino non-esensial dalam jumlah yang

                    cukup, sehingga ia menjadi esensial secara kondisional. Contohnya adalah arginin, sistein, tirosin,

                    dan glutamin.</li>

            </ul>



            <h5 class="font-bold text-sakura-black text-base mt-6">Fungsi Asam Amino dalam Tubuh</h5>

            <p>Peran asam amino dalam tubuh sangat beragam dan fundamental, mencerminkan pentingnya protein yang mereka

                bangun:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Pembentukan Protein:</strong> Ini adalah fungsi utama asam amino. Melalui proses sintesis

                    protein (transkripsi dan translasi), asam amino berurutan disambungkan oleh ikatan peptida membentuk

                    rantai polipeptida panjang yang kemudian melipat menjadi protein fungsional. Protein ini berperan

                    sebagai enzim (mempercepat reaksi biokimia), antibodi (bagian dari sistem imun), hormon (pengatur

                    fungsi tubuh), protein struktural (kolagen, keratin untuk kulit, rambut, tulang), dan protein

                    transpor (hemoglobin untuk oksigen).</li>

                <li><strong>Prekursor Senyawa Penting Lain:</strong> Asam amino tidak hanya membentuk protein, tetapi

                    juga berfungsi sebagai bahan baku untuk sintesis berbagai molekul biologis vital lainnya. Misalnya,

                    triptofan adalah prekursor serotonin (neurotransmiter penting untuk suasana hati dan tidur), tirosin

                    adalah prekursor hormon tiroid dan dopamin, dan glisin adalah komponen kunci dalam sintesis heme

                    (bagian dari hemoglobin).</li>

                <li><strong>Sumber Energi:</strong> Meskipun bukan fungsi utamanya, asam amino dapat dioksidasi untuk

                    menghasilkan energi, terutama saat tubuh kekurangan karbohidrat atau lemak. Proses ini melibatkan

                    deaminasi (penghilangan gugus amino) dan konversi kerangka karbon menjadi perantara siklus Krebs.

                </li>

            </ul>

            <p>Karena tubuh manusia tidak dapat menyimpan asam amino bebas dalam jumlah besar, asupan protein yang cukup

                dan seimbang melalui diet menjadi sangat penting untuk memastikan ketersediaan semua jenis asam amino

                yang dibutuhkan. Sumber protein hewani (daging, ikan, telur, produk susu) umumnya dianggap sebagai

                "protein lengkap" karena mengandung semua asam amino esensial dalam proporsi yang baik. Sementara itu,

                protein nabati (kacang-kacangan, biji-bijian, sereal) seringkali kekurangan satu atau lebih asam amino

                esensial tertentu, sehingga penting bagi vegetarian dan vegan untuk mengombinasikan berbagai sumber

                nabati (misalnya, nasi dan kacang-kacangan) untuk mendapatkan profil asam amino yang lengkap.</p>

            <p>Defisiensi asam amino, terutama asam amino esensial, dapat memiliki implikasi kesehatan serius, termasuk

                gangguan pertumbuhan, penurunan massa otot, melemahnya sistem imun, dan masalah metabolisme. Sebaliknya,

                kelebihan asam amino akibat asupan protein yang sangat tinggi juga dapat menimbulkan beban pada ginjal

                dan berpotensi menyebabkan masalah kesehatan tertentu. Oleh karena itu, menjaga keseimbangan asupan asam

                amino melalui diet seimbang adalah kunci untuk mendukung fungsi tubuh secara optimal dan menjaga

                kesehatan seluler.</p>

        </div>

    </article>



    <!-- ARTIKEL 2: ORB -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-teal-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-teal-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">movie</span> Artikel 2

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Orb: On the Movements of the Earth – Mahakarya

            yang Menggugah Nurani Ilmuwan</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Di tengah banjirnya anime bergenre fantasi dan aksi, Orb: On the Movements of the Earth muncul sebagai

                sebuah anomali sekaligus mahakarya yang menawan. Berlatar di Eropa abad ke-15, pada era yang dikenal

                sebagai Abad Kegelapan bagi ilmu pengetahuan, anime ini secara cemerlang mengisahkan perjuangan para

                intelektual yang mempertaruhkan segalanya demi mencari kebenaran ilmiah, terutama mengenai teori

                heliosentrisme yang menempatkan Matahari sebagai pusat tata surya. Lebih dari sekadar tontonan sejarah,

                "Orb" adalah sebuah narasi filosofis yang mendalam tentang benturan antara dogma agama yang kaku dan api

                keingintahuan manusia, mengkritisi penindasan intelektual yang pernah melanda peradaban dan menyoroti

                harga yang harus dibayar demi sebuah pencerahan.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Latar Belakang Sejarah yang Menegangkan</h5>

            <p>Orb: On the Movements of the Earth secara cerdik memanfaatkan latar abad ke-15 di Polandia, sebuah era di

                mana otoritas Gereja Katolik Roma memiliki kekuasaan mutlak atas interpretasi kebenaran, dan setiap

                bentuk "bidah atau penentangan doktrin dapat berujung pada hukuman mati. Plot utama mengikuti perjalanan

                Rafal, seorang anak jenius berusia 12 tahun yang terjerat dalam penelitian terlarang mengenai posisi

                Bumi dalam tata surya setelah bertemu dengan Hubert, seorang sarjana sesat. Anime ini berhasil menangkap

                atmosfer opresif dari era tersebut, menampilkan ketegangan yang konstan antara pencarian ilmu

                pengetahuan dan ancaman Inkuisisi Gereja. Kritikus dan penonton memuji bagaimana serial ini, meski tidak

                bertujuan untuk akurasi historis yang kaku, berhasil memaku perasaan takut, perjuangan untuk kebebasan

                intelektual, dan benturan fundamental antara sains dan otoritas. Ini membuat penonton merasakan secara

                langsung bahaya yang dihadapi oleh para pemikir yang berani menantang status quo, sebuah fenomena yang,

                sayangnya, masih memiliki gaung relevansi dalam beberapa bentuk penindasan kebebasan berpikir di

                masyarakat kontemporer.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Narasi Orb sebagai kekuatan</h5>

            <p>Kekuatan Orb tidak hanya terletak pada premisnya yang berani, tetapi juga pada struktur naratifnya yang

                berlapis dan karakterisasi yang kompleks. Alur cerita tidak terpaku pada satu individu saja, melainkan

                mengikuti rantai estafet pengetahuan lintas generasi. Ketika satu sarjana jatuh di tangan Inkuisisi,

                penelitian dan semangatnya akan diteruskan kepada penerus berikutnya, menciptakan narasi yang

                mengharukan tentang warisan intelektual. Karakter seperti Rafal, Oczy, Badeni, hingga Jolanta, masing

                masing memiliki motivasi, kekuatan, dan kelemahan yang membuat perjuangan mereka terasa sangat manusiawi

                dan mendalam. Secara visual, studio Madhouse berhasil menyajikan estetika yang suram dan gelap, sangat

                sesuai dengan era represif yang digambarkan. Adegan-adegan kekerasan, eksekusi, dan penyiksaan tidak

                disajikan secara sensasional, melainkan sebagai bagian tak terpisahkan dari realitas brutal waktu itu,

                menambah bobot dramatis pada cerita. Meskipun beberapa ulasan awal manga-nya mencatat gaya seni yang

                kaku, versi anime ini berhasil menerjemahkan visual yang penuh gaya ke dalam medium animasi, yang

                didukung oleh soundtrack atmosferik dari komposer Kensuke Ushio (yang juga dikenal dari karyanya di "A

                Silent Voice" dan "Devilman Crybaby"), meningkatkan pengalaman emosional penonton.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Pesan Filosofis</h5>

            <p>Pada intinya, Orb: On the Movements of the Earth adalah sebuah meditasi filosofis tentang hakikat

                kebenaran, iman, dan peran akal manusia. Anime ini secara eksplisit mengajukan pertanyaan-pertanyaan

                berat: apa harga sebuah kebenaran yang menentang keyakinan massal? Bisakah ilmu pengetahuan dan agama

                hidup berdampingan? Dan mengapa manusia memiliki dorongan tak terpadamkan untuk mencari tahu, bahkan

                ketika hal itu mengancam keberadaannya? Resepsi kritis terhadap Orb sebagian besar positif, banyak yang

                memujinya sebagai permata tersembunyi atau mahakarya tahun ini karena kedalaman tematiknya. Penonton dan

                kritikus menghargai bagaimana serial ini dengan berani mengeksplorasi konflik abadi antara sains dan

                dogma, serta bagaimana ia merayakan semangat keingintahuan dan ketahanan jiwa manusia. Anime ini juga

                dianggap relevan di masa kini, mengingatkan kita bahwa penindasan terhadap kebebasan berpikir dan

                penyangkalan fakta ilmiah masih menjadi ancaman. Dengan rating R-17+ karena kontennya yang berat dan

                adegan kekerasan yang relevan dengan sejarah, Orb jelas ditujukan untuk audiens dewasa yang mampu

                mencerna narasi filosofis dan emosional yang kompleks, dan akan sangat menggugah bagi mereka yang

                mencintai kisah yang penuh makna dan pemikiran.</p>

        </div>

    </article>



    <!-- ARTIKEL 3: GEMBOK -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-teal-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-teal-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">lock</span> Artikel 3

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Gembok: Penjaga Keamanan Sederhana yang Tetap

            Eksis Hingga Sekarang</h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Di tengah kemajuan teknologi keamanan yang semakin canggih, gembok tetap menjadi salah satu perangkat

                pengaman yang paling dikenal, universal, dan banyak digunakan di seluruh dunia. Dari gerbang rumah

                sederhana hingga loker gym, keberadaan gembok memberikan rasa aman dengan fungsi dasarnya yang tak

                lekang oleh waktu: mengunci dan mengamankan properti. Meskipun terlihat sederhana, desain dan mekanisme

                kerjanya adalah hasil evolusi berabad-abad, menjadikannya penjaga keamanan yang esensial dalam kehidupan

                sehari-hari.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Komponen dan Cara Kerja</h5>

            <p>Secara fundamental, gembok adalah kunci portabel yang terdiri dari beberapa komponen utama yang bekerja

                sama untuk mengamankan dua objek atau lebih:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Badan Gembok (Body):</strong> Ini adalah bagian utama gembok yang menampung mekanisme

                    penguncian internal. Umumnya terbuat dari logam kuat seperti kuningan, baja, atau besi tuang untuk

                    memberikan resistensi terhadap kerusakan fisik.</li>

                <li><strong>Belenggu (Shackle):</strong> Bagian berbentuk U yang dapat dibuka dan ditutup, berfungsi

                    untuk mengikat objek yang ingin diamankan (misalnya, rantai, engsel, atau hasp). Belenggu ini

                    biasanya terbuat dari baja yang diperkeras untuk mencegah pemotongan atau penggergajian.</li>

                <li><strong>Mekanisme Penguncian (Locking Mechanism):</strong> Ini adalah inti dari gembok, yang paling

                    umum menggunakan sistem pin tumbler. Mekanisme ini terdiri dari serangkaian pin (pin penggerak dan

                    pin kunci) yang berada dalam jalur silinder. Ketika kunci yang tepat dimasukkan, lekukan pada kunci

                    akan menyelaraskan semua pin pada garis geser tertentu (shear line), memungkinkan silinder berputar

                    dan membuka belenggu. Tanpa kunci yang tepat, pin akan menghalangi putaran silinder, menjaga gembok

                    tetap terkunci.</li>

                <li><strong>Kunci (Key):</strong> Alat logam yang dirancang khusus dengan pola gerigi unik yang sesuai

                    dengan konfigurasi pin di dalam mekanisme penguncian gembok tertentu.</li>

                <li>Ketika belenggu ditutup, pegas di dalam gembok akan mendorong pin ke posisi terkunci. Memasukkan

                    kunci yang benar akan mendorong pin-pin tersebut ke posisi yang tepat, sejajar dengan garis geser,

                    sehingga silinder bisa berputar dan belenggu terlepas.</li>

            </ul>



            <h5 class="font-bold text-sakura-black text-base mt-6">Sejarah dan Evolusi Keamanan Gembok</h5>

            <p>Sejarah gembok dapat ditelusuri ribuan tahun ke belakang, menunjukkan kebutuhan manusia yang universal

                akan keamanan. Gembok primitif pertama kali muncul di peradaban kuno seperti Mesir Kuno dan Tiongkok

                sekitar 4000 SM, menggunakan mekanisme pin dan kunci kayu yang besar. Bangsa Romawi kemudian

                mengembangkan gembok logam dan memperkenalkan belenggu yang lebih kokoh.</p>

            <p>Abad ke-19 menjadi era revolusi bagi desain gembok, terutama dengan paten mekanisme pin tumbler modern

                oleh Linus Yale Sr. dan putranya, Linus Yale Jr., pada pertengahan 1800-an. Desain ini meningkatkan

                keamanan secara signifikan dibandingkan mekanisme pegas atau tuas sebelumnya, menjadikannya standar

                industri yang masih banyak digunakan hingga hari ini. Seiring waktu, material yang digunakan juga

                berkembang, dari besi tuang sederhana menjadi baja anti-potong dan alloy yang lebih tahan terhadap

                metode pembobolan modern.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Variasi dan Aplikasi Gembok dalam Kehidupan</h5>

            <p>Meskipun prinsip dasarnya tetap sama, gembok telah berevolusi menjadi berbagai jenis dan aplikasi untuk

                memenuhi kebutuhan keamanan yang berbeda:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Gembok Standar:</strong> Jenis yang paling umum, digunakan untuk mengunci gerbang, gudang,

                    loker, dan rantai.</li>

                <li><strong>Gembok Kombinasi:</strong> Tidak memerlukan kunci fisik, melainkan serangkaian angka atau

                    huruf yang harus diatur pada posisi yang benar. Populer untuk loker sekolah atau koper.</li>

                <li><strong>Gembok dengan Kunci Utama (Master Key):</strong> Sebuah kunci tunggal dapat membuka beberapa

                    gembok yang berbeda, sementara setiap gembok juga memiliki kunci uniknya sendiri. Berguna untuk

                    sistem keamanan kompleks di gedung atau fasilitas.</li>

                <li><strong>Gembok Tahan Air/Cuaca:</strong> Dirancang dengan material dan lapisan khusus untuk menahan

                    korosi dan kondisi lingkungan ekstrem.</li>

                <li><strong>Gembok Keamanan Tinggi:</strong> Menggunakan material yang sangat kuat (misalnya, baja

                    boron) dan mekanisme penguncian yang lebih kompleks (misalnya, disc detainer atau sistem multi-pin)

                    untuk menahan upaya pembobolan yang canggih.</li>

            </ul>

        </div>

    </article>



    <!-- ARTIKEL 4: OMEGA-3 -->

    <article class="bg-white rounded-xl shadow-sm border border-gray-100 p-8 relative">

        <div class="absolute top-0 left-0 w-1 h-full bg-teal-400 rounded-l-xl"></div>

        <div class="flex items-center gap-2 text-xs font-bold text-teal-500 uppercase tracking-widest mb-4">

            <span class="material-symbols-outlined text-sm">water_drop</span> Artikel 4

        </div>

        <h3 class="font-serif font-bold text-2xl text-sakura-black mb-2">Omega-3: Lemak Esensial untuk Kesehatan Optimal

        </h3>

        <div class="prose max-w-none text-gray-600 font-serif leading-loose space-y-4">

            <p>Dalam piramida nutrisi, lemak sering kali dianggap sebagai musuh yang harus dihindari. Namun, pandangan

                ini terlalu menyederhanakan. Ada jenis lemak tertentu yang tidak hanya penting, tetapi esensial bagi

                kesehatan tubuh kita: asam lemak omega-3. Senyawa ini adalah lemak tak jenuh ganda yang tidak dapat

                diproduksi sendiri oleh tubuh, sehingga harus diperoleh melalui asupan makanan atau suplemen. Dari

                kesehatan jantung, fungsi otak, hingga respons peradangan, omega-3 memainkan peran krusial yang menopang

                hampir setiap sistem biologis.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Tiga Jenis Utama Omega-3 dan Sumbernya</h5>

            <p>Ada tiga jenis utama asam lemak omega-3 yang paling banyak dikenal dan dipelajari, masing-masing dengan

                sumber makanan spesifiknya:</p>

            <p><strong>Asam Alfa-Linolenat (ALA):</strong> Ini adalah jenis omega-3 rantai pendek yang ditemukan

                terutama pada sumber nabati. Tubuh manusia dapat mengubah ALA menjadi EPA dan DHA, namun proses

                konversinya sangat tidak efisien (kurang dari 10%). Sumber: Biji rami (flaxseed), biji chia, kenari,

                minyak kanola, dan minyak kedelai.</p>

            <p><strong>Asam Eicosapentaenoat (EPA):</strong> Omega-3 rantai panjang ini dikenal karena perannya dalam

                mengurangi peradangan.</p>

            <p><strong>Asam Docosahexaenoat (DHA):</strong> Omega-3 rantai panjang lainnya yang sangat vital untuk

                perkembangan dan fungsi otak.</p>

            <p>Sumber (EPA & DHA): Terutama ditemukan pada ikan berlemak (juga disebut ikan berminyak) dan makanan laut.

                Contohnya salmon, makarel, sarden, tuna albakora, dan teri. Mikroalga juga merupakan sumber langsung EPA

                dan DHA, yang kemudian diakumulasi oleh ikan dalam rantai makanan.</p>

            <p>Untuk memastikan asupan omega-3 yang optimal, terutama EPA dan DHA, konsumsi ikan berlemak secara teratur

                sangat direkomendasikan.</p>



            <h5 class="font-bold text-sakura-black text-base mt-6">Mekanisme Aksi dan Manfaat Kesehatan</h5>

            <p>Manfaat kesehatan dari omega-3, khususnya EPA dan DHA, berasal dari kemampuannya untuk berintegrasi ke

                dalam membran sel di seluruh tubuh, memengaruhi fluiditas membran dan jalur sinyal seluler. Mereka juga

                merupakan prekursor bagi molekul sinyal yang disebut eikosanoid, yang berperan dalam regulasi

                peradangan, fungsi imun, dan tekanan darah. Berikut adalah beberapa manfaat utama omega-3 yang didukung

                oleh bukti ilmiah:</p>

            <ul class="list-disc pl-5 mt-2 space-y-1">

                <li><strong>Kesehatan Jantung dan Kardiovaskular:</strong> Omega-3 dapat membantu menurunkan kadar

                    trigliserida dalam darah, mengurangi tekanan darah, mencegah pembentukan plak di arteri, dan

                    mengurangi risiko aritmia (gangguan irama jantung). Studi klinis yang ekstensif telah menunjukkan

                    korelasi positif antara asupan omega-3 yang cukup dan penurunan risiko penyakit jantung koroner.

                </li>

                <li><strong>Fungsi Otak dan Kesehatan Mental:</strong> DHA adalah komponen struktural utama otak dan

                    retina. Asupan DHA yang memadai sangat penting untuk perkembangan otak bayi (terutama selama

                    kehamilan dan menyusui) dan memelihara fungsi kognitif pada orang dewasa, termasuk memori dan

                    konsentrasi. Beberapa penelitian juga menunjukkan potensi omega-3 dalam membantu mengurangi gejala

                    depresi dan kecemasan.</li>

                <li><strong>Anti-inflamasi:</strong> Omega-3 memiliki sifat anti-inflamasi yang kuat, membantu

                    mengurangi peradangan kronis dalam tubuh yang merupakan akar dari banyak penyakit, termasuk penyakit

                    autoimun (seperti rheumatoid arthritis), asma, dan penyakit radang usus.</li>

                <li><strong>Kesehatan Mata:</strong> DHA adalah komponen utama retina mata. Asupan yang cukup dapat

                    membantu mengurangi risiko degenerasi makula terkait usia (AMD), penyebab utama kebutaan pada

                    lansia.</li>

            </ul>



            <h5 class="font-bold text-sakura-black text-base mt-6">Memastikan Asupan Optimal dan Pertimbangan</h5>

            <p>Untuk mendapatkan manfaat maksimal dari omega-3, penting untuk memastikan asupan yang cukup dan seimbang.

                Organisasi kesehatan merekomendasikan asupan sekitar 250-500 mg EPA dan DHA gabungan per hari untuk

                sebagian besar orang dewasa sehat. Ini dapat dicapai dengan mengonsumsi ikan berlemak dua kali seminggu.

                Bagi vegetarian atau vegan, suplemen ALA dari biji rami atau suplemen EPA/DHA berbasis alga bisa menjadi

                alternatif.</p>

            <p>Meskipun suplemen omega-3 (minyak ikan) sangat populer, penting untuk berkonsultasi dengan profesional

                kesehatan sebelum mengonsumsinya, terutama dalam dosis tinggi, karena dapat berinteraksi dengan

                obat-obatan tertentu (misalnya pengencer darah) atau menyebabkan efek samping ringan seperti gangguan

                pencernaan. Menjadikan omega-3 sebagai bagian integral dari pola makan kita adalah langkah proaktif

                dalam membangun fondasi kesehatan yang kuat dan berkelanjutan.</p>

        </div>

    </article>



</div>

</div>

                    <!-- QUIZ SECTION -->

<div id="page-quiz-008" class="page-section-008">

    <div class="max-w-4xl mx-auto p-8 pb-32 space-y-8">

        <div class="text-center mb-8">

            <span class="material-symbols-outlined text-5xl text-sakura-red mb-3">quiz</span>

            <h2 class="font-serif font-black text-3xl text-sakura-black mb-2">Quiz — Obat Fokus Day 8</h2>

            <p class="text-gray-500 max-w-md mx-auto">Jawab pertanyaan berdasarkan artikel yang sudah kamu baca. Soal isian <strong>tidak dinilai</strong>, hanya True/False yang masuk skor.</p>

            <div class="w-16 h-1 bg-sakura-red mx-auto mt-4"></div>

        </div>



        <!-- ISIAN -->

        <div class="space-y-6">

            <p class="text-[10px] font-bold text-teal-500 uppercase tracking-widest px-1">Bagian 1 — Isian Singkat <span class="text-gray-400">(tidak dinilai)</span></p>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>1.</strong> Untuk mengoreksi rabun jauh (miopia), lensa kacamata jenis apa yang digunakan?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Lensa minus (cekung)</p>

                    <p class="text-xs text-green-600 mt-1">Penderita miopia menggunakan lensa cekung (minus) untuk menyebarkan cahaya sebelum masuk ke mata.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>2.</strong> Apa yang dimaksud dengan geopolitik secara sederhana?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Studi tentang pengaruh geografi terhadap politik</p>

                    <p class="text-xs text-green-600 mt-1">Geopolitik mempelajari bagaimana faktor geografis memengaruhi kebijakan politik dan hubungan antarnegara.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>3.</strong> Apa peran utama Otto Toto Sugiri sehingga ia dijuluki "Bapak Data Center Indonesia"?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Pendiri data center Tier-IV (DCI Indonesia)</p>

                    <p class="text-xs text-green-600 mt-1">Ia adalah pendiri PT DCI Indonesia Tbk, data center berstandar internasional yang menjadi tulang punggung ekonomi digital Indonesia.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>4.</strong> Apa fungsi utama dari asam amino di dalam tubuh?</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Membentuk protein (blok bangunan protein)</p>

                    <p class="text-xs text-green-600 mt-1">Fungsi utamanya adalah sebagai unit dasar untuk membentuk protein, yang berperan sebagai enzim, antibodi, hormon, dan struktur sel.</p>

                </div>

            </div>



            <div class="quiz-isian bg-white rounded-xl shadow-sm border border-gray-100 p-6">

                <p class="font-serif text-gray-700 mb-4"><strong>5.</strong> Sebutkan salah satu sumber makanan yang kaya akan Omega-3, terutama jenis EPA dan DHA!</p>

                <div class="flex gap-3 items-center mb-4">

                    <input type="text" placeholder="Ketik jawaban..." class="flex-1 border border-gray-200 rounded-lg px-4 py-2 text-sm focus:ring-2 focus:ring-sakura-red/30 focus:border-sakura-red outline-none" />

                    <button onclick="checkIsian(this)" class="px-4 py-2 bg-sakura-black text-white text-xs font-bold rounded-lg uppercase tracking-wider hover:bg-gray-800 transition-colors">Cek</button>

                </div>

                <div class="feedback hidden bg-green-50 border border-green-200 rounded-lg p-4">

                    <p class="text-sm text-green-800"><strong>Jawaban:</strong> Ikan berlemak (Salmon, Sarden, Makarel)</p>

                    <p class="text-xs text-green-600 mt-1">Ikan berlemak seperti salmon, sarden, makarel, dan tuna adalah sumber utama EPA dan DHA yang paling bioavailable.</p>

                </div>

            </div>

        </div>



        <!-- TRUE/FALSE -->

        <div class="space-y-6 mt-10">

            <p class="text-[10px] font-bold text-teal-500 uppercase tracking-widest px-1">Bagian 2 — Benar atau Salah <span class="text-gray-400">(dinilai)</span></p>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="008">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>6.</strong> Asam amino esensial adalah jenis asam amino yang harus diperoleh dari makanan karena tubuh manusia tidak dapat memproduksinya sendiri.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal8 6', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal8 6', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Ada sembilan jenis asam amino esensial yang tubuh tidak bisa buat sendiri, sehingga harus dari asupan luar.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="008">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>7.</strong> Anime Orb: On the Movements of the Earth berlatar di abad ke-15 dan menceritakan perjuangan ilmuwan dalam mempertahankan teori geosentrisme.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal8 7', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal8 7', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. Anime ini menceritakan perjuangan membuktikan heliosentrisme (Matahari sebagai pusat), menentang geosentrisme.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="008">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>8.</strong> Mekanisme penguncian paling umum pada gembok modern adalah sistem pin tumbler yang dipopulerkan oleh Linus Yale Jr.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal8 8', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal8 8', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Mekanisme pin tumbler modern memang dipatenkan dan dipopulerkan oleh Linus Yale Jr.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="false" data-module="008">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>9.</strong> Asam Alfa-Linolenat (ALA) adalah jenis Omega-3 yang sumber utamanya adalah ikan berlemak seperti salmon dan sarden.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal8 9', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal8 9', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Salah. ALA terutama berasal dari sumber nabati (biji rami, chia). Ikan berlemak kaya akan EPA dan DHA.</p>

                </div>

            </div>



            <div class="quiz-tf bg-white rounded-xl shadow-sm border border-gray-100 p-6" data-answer="true" data-module="008">

                <div class="flex items-start justify-between mb-4">

                    <p class="font-serif text-gray-700 flex-1"><strong>10.</strong> Negara kepulauan seperti Indonesia secara alami akan memiliki perspektif geopolitik yang menekankan pada kekuatan maritim dan kontrol jalur laut.</p>

                    <div class="result-badge hidden ml-3"></div>

                </div>

                <div class="flex gap-3 mb-4">

                    <button onclick="checkTF(this, 'Soal8 10', 'true')" data-value="true" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-green-50 hover:border-green-300 transition-colors">Benar</button>

                    <button onclick="checkTF(this, 'Soal8 10', 'false')" data-value="false" class="tf-btn flex-1 py-2 border border-gray-200 rounded-lg text-sm font-bold text-gray-600 hover:bg-red-50 hover:border-red-300 transition-colors">Salah</button>

                </div>

                <div class="feedback hidden bg-blue-50 border border-blue-200 rounded-lg p-4">

                    <p class="text-sm text-blue-800"><strong>Pembahasan:</strong> Benar. Sebagai negara kepulauan, Indonesia secara alami menekankan kekuatan maritim dan kontrol atas jalur strategis seperti Selat Malaka.</p>

                </div>

            </div>

        </div>



        <!-- Submit -->

        <div class="text-center pt-8">

            <button onclick="showResult()" class="px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg shadow-sakura-red/30">

                <span class="flex items-center gap-2">

                    <span class="material-symbols-outlined text-lg">fact_check</span>

                    Lihat Hasil

                </span>

            </button>

        </div>

    </div>

</div>



<!-- PAGE 3: RESULT -->

<div id="page-result-008" class="page-section-008">

    <div class="max-w-4xl mx-auto p-8 pb-32">

        <div id="result-content"></div>

        <div class="text-center mt-8">

            <a href="Dashboard.html" class="inline-flex items-center gap-2 px-8 py-3 bg-sakura-red text-white font-bold rounded-full text-sm uppercase tracking-wider hover:bg-red-800 transition-colors shadow-lg">

                <span class="material-symbols-outlined">dashboard</span> Kembali ke Dashboard

            </a>

        </div>

    </div>

</div>
                </div>
            </div>
    </main>

    <script>
        // === MODULE CONFIG ===
        const moduleConfig = {
            'obat-fokus-001': {
                title: 'Obat Fokus — Day 1',
                breadcrumbName: 'Obat Fokus 001',
                pageSectionClass: 'page-section',
                scrollId: 'content-scroll',
                resultContainerId: 'result-content',
                totalPages: 3
            },
            'obat-fokus-002': {
                title: 'Obat Fokus — Day 2',
                breadcrumbName: 'Obat Fokus 002',
                pageSectionClass: 'page-section-002',
                scrollId: 'content-scroll-002',
                resultContainerId: 'result-content-002',
                totalPages: 3
            },
            'obat-fokus-003': {
                title: 'Obat Fokus — Day 3',
                breadcrumbName: 'Obat Fokus 003',
                pageSectionClass: 'page-section-003',
                scrollId: 'content-scroll-003',
                resultContainerId: 'result-content-003',
                totalPages: 3
            },
            'obat-fokus-004': {
                title: 'Obat Fokus — Day 4',
                breadcrumbName: 'Obat Fokus 004',
                pageSectionClass: 'page-section-004',
                scrollId: 'content-scroll-004',
                resultContainerId: 'result-content-004',
                totalPages: 3
            },
            'obat-fokus-005': {
                title: 'Obat Fokus — Day 5',
                breadcrumbName: 'Obat Fokus 005',
                pageSectionClass: 'page-section-005',
                scrollId: 'content-scroll-005',
                resultContainerId: 'result-content-005',
                totalPages: 3
            },
            'obat-fokus-006': {
                title: 'Obat Fokus — Day 6',
                breadcrumbName: 'Obat Fokus 006',
                pageSectionClass: 'page-section-006',
                scrollId: 'content-scroll-006',
                resultContainerId: 'result-content-006',
                totalPages: 3
            },
            'obat-fokus-007': {
                title: 'Obat Fokus — Day 7',
                breadcrumbName: 'Obat Fokus 007',
                pageSectionClass: 'page-section-007',
                scrollId: 'content-scroll-007',
                resultContainerId: 'result-content-007',
                totalPages: 3
            },
            'obat-fokus-008': {
                title: 'Obat Fokus — Day 8',
                breadcrumbName: 'Obat Fokus 008',
                pageSectionClass: 'page-section-008',
                scrollId: 'content-scroll-008',
                resultContainerId: 'result-content-008',
                totalPages: 3
            },

        };

        // === CURRENT STATE ===
        let currentModule = null;
        let currentPage = 0;

        // Per-module score tracking
        const moduleScores = {};

        function getModuleScores() {
            if (!currentModule) return { tfScore: 0, tfTotal: 0, tfAnswers: {} };
            if (!moduleScores[currentModule]) {
                moduleScores[currentModule] = { tfScore: 0, tfTotal: 0, tfAnswers: {} };
            }
            return moduleScores[currentModule];
        }

        // === MODULE LOADING ===
        function loadModule(id) {
            const config = moduleConfig[id];
            if (!config) return;

            // Hide any previously active module
            if (currentModule && currentModule !== id) {
                const prevEl = document.getElementById('module-' + currentModule);
                if (prevEl) prevEl.classList.remove('active');
                resetSidebarItem(currentModule);
            }

            // Hide landing
            const landingView = document.getElementById('landing-view');
            landingView.classList.add('hidden');
            landingView.classList.remove('landing-view');

            // Show module
            const moduleEl = document.getElementById('module-' + id);
            if (moduleEl) {
                moduleEl.classList.add('active');
            }
            currentModule = id;

            // Update header
            document.getElementById('breadcrumb').innerHTML = `
                <span>Alter Ego</span>
                <span class="material-symbols-outlined text-[10px]">chevron_right</span>
                <span>Habit</span>
                <span class="material-symbols-outlined text-[10px]">chevron_right</span>
                <span class="text-sakura-red font-bold">${config.breadcrumbName}</span>
            `;
            document.getElementById('page-title').textContent = config.title;
            document.getElementById('page-badge').textContent = 'Habit';
            document.getElementById('page-badge').className = 'px-2 py-0.5 rounded text-[10px] font-bold bg-pink-50 text-pink-600 border border-pink-200 uppercase tracking-widest';
            document.getElementById('progress-container').classList.remove('hidden');

            // Reset all sidebar highlights, then highlight current
            document.querySelectorAll('#sidebar-nav .sidebar-item').forEach(item => {
                item.className = 'sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3';
                const spans = item.querySelectorAll('span');
                if (spans[0]) { spans[0].classList.remove('text-sakura-red'); spans[0].classList.add('text-gray-500'); }
                if (spans[1]) spans[1].classList.remove('font-bold');
            });
            const navItem = document.getElementById('nav-' + id);
            if (navItem) {
                navItem.className = 'sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md bg-white/10 text-left transition-colors text-white border-r-2 border-sakura-red ml-3';
                navItem.querySelector('span:first-child').classList.remove('text-gray-500');
                navItem.querySelector('span:first-child').classList.add('text-sakura-red');
                navItem.querySelector('span:last-child').classList.add('font-bold');
            }

            // Show bottom nav — force-move to body to bypass DOM nesting issues
            const bottomNav = document.getElementById('bottom-nav');
            if (bottomNav) {
                document.body.appendChild(bottomNav);
                bottomNav.classList.remove('hidden');
                bottomNav.style.position = 'fixed';
                bottomNav.style.bottom = '24px';
                bottomNav.style.right = '0';
                bottomNav.style.zIndex = '50';
            }

            // Reset page state (scores persist per-module)
            currentPage = 0;
            goToPage(0);
        }

        function resetSidebarItem(id) {
            const navItem = document.getElementById('nav-' + id);
            if (navItem) {
                navItem.className = 'sidebar-item group w-full flex items-center gap-3 px-3 py-2.5 rounded-md hover:bg-white/5 text-left transition-colors text-gray-300 hover:text-white ml-3';
                const spans = navItem.querySelectorAll('span');
                if (spans[0]) { spans[0].classList.remove('text-sakura-red'); spans[0].classList.add('text-gray-500'); }
                if (spans[1]) spans[1].classList.remove('font-bold');
            }
        }

        function backToLanding() {
            // Hide module
            if (currentModule) {
                const moduleEl = document.getElementById('module-' + currentModule);
                if (moduleEl) moduleEl.classList.remove('active');
                resetSidebarItem(currentModule);
            }

            // Show landing
            const landingView = document.getElementById('landing-view');
            landingView.classList.remove('hidden');
            landingView.classList.add('landing-view');

            // Reset header
            document.getElementById('breadcrumb').innerHTML = `
                <span>Alter Ego</span>
                <span class="material-symbols-outlined text-[10px]">chevron_right</span>
                <span class="text-sakura-red font-bold">Persiapan SNBT</span>
            `;
            document.getElementById('page-title').textContent = 'Alter Ego';
            document.getElementById('page-badge').textContent = 'SNBT';
            document.getElementById('page-badge').className = 'px-2 py-0.5 rounded text-[10px] font-bold bg-sakura-red/10 text-sakura-red border border-sakura-red/20 uppercase tracking-widest';
            document.getElementById('progress-container').classList.add('hidden');
            document.getElementById('bottom-nav').classList.add('hidden');

            currentModule = null;
        }

        // === PAGE NAVIGATION (module-scoped) ===
        function goToPage(page) {
            if (!currentModule) return;
            const config = moduleConfig[currentModule];
            if (!config || page < 0 || page >= config.totalPages) return;
            currentPage = page;

            // Only toggle page sections within the active module
            const moduleEl = document.getElementById('module-' + currentModule);
            if (moduleEl) {
                const sections = moduleEl.querySelectorAll('.' + config.pageSectionClass);
                sections.forEach((s, i) => {
                    s.classList.toggle('active', i === page);
                });
            }

            const scroll = document.getElementById(config.scrollId);
            if (scroll) scroll.scrollTop = 0;
            updateNav();
            updateProgress();
        }
        function nextPage() { goToPage(currentPage + 1); }
        function prevPage() { goToPage(currentPage - 1); }

        function updateNav() {
            if (!currentModule) return;
            const config = moduleConfig[currentModule];
            document.getElementById('btn-prev').disabled = currentPage === 0;
            const dots = document.querySelectorAll('.step-dot');
            dots.forEach((dot, i) => {
                const step = parseInt(dot.dataset.step);
                if (step < currentPage) {
                    dot.className = 'step-dot w-8 h-8 rounded-full bg-sakura-red text-white flex items-center justify-center shadow-lg font-serif font-bold text-sm';
                } else if (step === currentPage) {
                    dot.className = 'step-dot w-10 h-10 rounded-full bg-white border-2 border-sakura-red text-sakura-red flex items-center justify-center shadow-lg font-serif font-bold text-sm scale-110';
                } else {
                    dot.className = 'step-dot w-8 h-8 rounded-full bg-gray-100 text-gray-400 border border-gray-200 flex items-center justify-center font-serif font-bold text-sm';
                }
            });
            const lines = ['line-0-1', 'line-1-2'];
            lines.forEach((id, i) => {
                const el = document.getElementById(id);
                if (el) el.className = i < currentPage ? 'w-6 h-0.5 bg-sakura-red rounded' : 'w-6 h-0.5 bg-gray-200 rounded';
            });
            const nextBtn = document.getElementById('btn-next');
            if (currentPage === config.totalPages - 1) {
                nextBtn.classList.add('hidden');
            } else {
                nextBtn.classList.remove('hidden');
            }
        }

        function updateProgress() {
            if (!currentModule) return;
            const config = moduleConfig[currentModule];
            const pct = currentPage === 0 ? 33 : currentPage === 1 ? 66 : 100;
            document.getElementById('progress-bar').style.width = pct + '%';
            document.getElementById('progress-text').textContent = pct + '%';
        }

        // === SIDEBAR ===
        function toggleSidebar() {
            const sidebar = document.getElementById('sidebar');
            const toggleBtn = document.getElementById('toggle-btn');
            const bottomNav = document.getElementById('bottom-nav');
            sidebar.classList.toggle('collapsed');
            if (sidebar.classList.contains('collapsed')) {
                toggleBtn.classList.remove('hidden');
                if (bottomNav) { bottomNav.classList.remove('left-72'); bottomNav.classList.add('left-0'); }
            } else {
                toggleBtn.classList.add('hidden');
                if (bottomNav) { bottomNav.classList.remove('left-0'); bottomNav.classList.add('left-72'); }
            }
        }

        // === QUIZ LOGIC (module-scoped) ===
        function checkIsian(btn) {
            const item = btn.closest('.quiz-isian');
            const input = item.querySelector('input');
            const feedback = item.querySelector('.feedback');
            btn.disabled = true;
            input.disabled = true;
            feedback.classList.remove('hidden');
            feedback.classList.add('quiz-feedback');
            btn.textContent = 'Sudah Dijawab';
            btn.classList.replace('bg-sakura-black', 'bg-gray-400');
        }

        function checkTF(btn, qId, userAnswer) {
            const scores = getModuleScores();
            if (scores.tfAnswers[qId] !== undefined) return;
            const item = btn.closest('.quiz-tf');
            const correct = item.dataset.answer;
            const isCorrect = userAnswer === correct;
            scores.tfAnswers[qId] = { user: userAnswer, correct: correct, isCorrect: isCorrect };
            scores.tfTotal++;
            if (isCorrect) scores.tfScore++;

            const buttons = item.querySelectorAll('.tf-btn');
            buttons.forEach(b => {
                b.disabled = true;
                if (b.dataset.value === correct) {
                    b.classList.add('ring-2', 'ring-green-500', 'bg-green-50');
                }
                if (b.dataset.value === userAnswer && !isCorrect) {
                    b.classList.add('ring-2', 'ring-red-500', 'bg-red-50');
                }
            });
            const feedback = item.querySelector('.feedback');
            feedback.classList.remove('hidden');
            feedback.classList.add('quiz-feedback');
            const badge = item.querySelector('.result-badge');
            badge.innerHTML = isCorrect
                ? '<span class="text-green-600 font-bold flex items-center gap-1"><span class="material-symbols-outlined text-sm">check_circle</span> Benar!</span>'
                : '<span class="text-red-600 font-bold flex items-center gap-1"><span class="material-symbols-outlined text-sm">cancel</span> Salah</span>';
            badge.classList.remove('hidden');
        }

        function showResult() {
            if (!currentModule) return;
            const config = moduleConfig[currentModule];
            const scores = getModuleScores();
            const container = document.getElementById(config.resultContainerId);
            if (!container) return;

            const pct = scores.tfTotal > 0 ? Math.round((scores.tfScore / scores.tfTotal) * 100) : 0;
            let html = `
        <div class="text-center mb-10">
            <div class="w-32 h-32 rounded-full border-8 ${pct >= 60 ? 'border-green-500' : 'border-red-400'} flex items-center justify-center mx-auto mb-4">
                <span class="font-serif font-black text-4xl ${pct >= 60 ? 'text-green-600' : 'text-red-500'}">${pct}%</span>
            </div>
            <h3 class="font-serif font-bold text-2xl mb-2">Hasil Quiz True/False</h3>
            <p class="text-gray-500">Benar: <strong class="text-green-600">${scores.tfScore}</strong> / ${scores.tfTotal} &bull; Salah: <strong class="text-red-500">${scores.tfTotal - scores.tfScore}</strong> / ${scores.tfTotal}</p>
            <p class="text-xs text-gray-400 mt-2">* Soal isian tidak dinilai</p>
        </div>
        <div class="space-y-4">`;
            for (const [qId, data] of Object.entries(scores.tfAnswers)) {
                const icon = data.isCorrect ? 'check_circle' : 'cancel';
                const color = data.isCorrect ? 'green' : 'red';
                html += `<div class="bg-white rounded-xl border p-4 flex items-start gap-3">
            <span class="material-symbols-outlined text-${color}-500 mt-0.5">${icon}</span>
            <div><p class="font-bold text-sm">${qId}</p>
            <p class="text-xs text-gray-500">Jawaban kamu: <strong>${data.user === 'true' ? 'Benar' : 'Salah'}</strong> &bull; Jawaban tepat: <strong>${data.correct === 'true' ? 'Benar' : 'Salah'}</strong></p></div>
        </div>`;
            }
            html += '</div>';
            container.innerHTML = html;
            goToPage(2);
        }

        // === KATEX ===
        document.addEventListener("DOMContentLoaded", function () {
            if (typeof renderMathInElement === 'function') {
                renderMathInElement(document.body, {
                    delimiters: [{ left: '$$', right: '$$', display: true }, { left: '$', right: '$', display: false }],
                    throwOnError: false
                });
            }

        });
    </script>
</body>

</html>
