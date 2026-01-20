<!doctype html>
<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    * {
      font-family: 'Prompt', sans-serif;
    }
    .coin-spin {
      animation: spin 2s linear infinite;
    }
    @keyframes spin {
      from { transform: rotateY(0deg); }
      to { transform: rotateY(360deg); }
    }
    .float {
      animation: float 3s ease-in-out infinite;
    }
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
    }
    .pulse-gold {
      animation: pulseGold 2s ease-in-out infinite;
    }
    @keyframes pulseGold {
      0%, 100% { box-shadow: 0 0 0 0 rgba(251, 191, 36, 0.4); }
      50% { box-shadow: 0 0 20px 10px rgba(251, 191, 36, 0.2); }
    }
    .slide-in {
      animation: slideIn 0.5s ease-out;
    }
    @keyframes slideIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .shake {
      animation: shake 0.5s ease-in-out;
    }
    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-5px); }
      75% { transform: translateX(5px); }
    }
    .confetti {
      position: fixed;
      width: 10px;
      height: 10px;
      background: #f0f;
      animation: confetti-fall 3s ease-out forwards;
    }
    @keyframes confetti-fall {
      0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
      100% { transform: translateY(100%) rotate(720deg); opacity: 0; }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full bg-gradient-to-br from-amber-50 via-yellow-50 to-orange-50 overflow-auto">
  <div id="app" class="w-full min-h-full"><!-- Header -->
   <header id="header" class="bg-gradient-to-r from-amber-500 via-yellow-500 to-orange-500 text-white py-4 px-6 shadow-lg">
    <div class="max-w-4xl mx-auto flex items-center justify-between">
     <div class="flex items-center gap-3">
      <div class="text-4xl float">
       💰
      </div>
      <div>
       <h1 id="app-title" class="text-2xl font-bold">คณิตศาสตร์การเงิน ป.5</h1>
       <p id="welcome-text" class="text-amber-100 text-sm">ยินดีต้อนรับสู่โลกการเงิน!</p>
      </div>
     </div>
     <div id="score-display" class="bg-white/20 backdrop-blur rounded-xl px-4 py-2 flex items-center gap-2"><span class="text-2xl">⭐</span> <span id="score" class="text-xl font-bold">0</span> <span class="text-sm">คะแนน</span>
     </div>
    </div>
   </header><!-- Main Content -->
   <main class="max-w-4xl mx-auto p-4 md:p-6"><!-- Menu Screen -->
    <div id="menu-screen" class="slide-in">
     <div class="text-center mb-8">
      <div class="text-6xl mb-4">
       🏦
      </div>
      <h2 class="text-2xl font-bold text-amber-800 mb-2">เลือกบทเรียนที่ต้องการฝึก</h2>
      <p class="text-amber-600">เรียนรู้เรื่องเงินอย่างสนุกสนา���!</p>
     </div>
     <div class="grid grid-cols-1 md:grid-cols-2 gap-4"><!-- Lesson 1: รู้จักเงินตรา --> <button onclick="startLesson(1)" class="bg-white rounded-2xl p-6 shadow-lg hover:shadow-xl transition-all hover:scale-105 border-2 border-amber-200 text-left group">
       <div class="flex items-center gap-4">
        <div class="text-5xl group-hover:scale-110 transition-transform">
         🪙
        </div>
        <div>
         <h3 class="text-lg font-bold text-amber-800">บทที่ 1: รู้จักเงินตรา</h3>
         <p class="text-amber-600 text-sm">เรียนรู้ชนิดของเหรียญและธนบัตร</p>
        </div>
       </div></button> <!-- Lesson 2: การบวกลบเงิน --> <button onclick="startLesson(2)" class="bg-white rounded-2xl p-6 shadow-lg hover:shadow-xl transition-all hover:scale-105 border-2 border-green-200 text-left group">
       <div class="flex items-center gap-4">
        <div class="text-5xl group-hover:scale-110 transition-transform">
         ➕
        </div>
        <div>
         <h3 class="text-lg font-bold text-green-800">บทที่ 2: บวก-ลบเงิน</h3>
         <p class="text-green-600 text-sm">ฝึกคำนวณการบวกและลบเงิน</p>
        </div>
       </div></button> <!-- Lesson 3: การซื้อขาย --> <button onclick="startLesson(3)" class="bg-white rounded-2xl p-6 shadow-lg hover:shadow-xl transition-all hover:scale-105 border-2 border-blue-200 text-left group">
       <div class="flex items-center gap-4">
        <div class="text-5xl group-hover:scale-110 transition-transform">
         🛒
        </div>
        <div>
         <h3 class="text-lg font-bold text-blue-800">บทที่ 3: การซื้อของ</h3>
         <p class="text-blue-600 text-sm">คำนวณราคาและเงินทอน</p>
        </div>
       </div></button> <!-- Lesson 4: การออม --> <button onclick="startLesson(4)" class="bg-white rounded-2xl p-6 shadow-lg hover:shadow-xl transition-all hover:scale-105 border-2 border-purple-200 text-left group">
       <div class="flex items-center gap-4">
        <div class="text-5xl group-hover:scale-110 transition-transform">
         🐷
        </div>
        <div>
         <h3 class="text-lg font-bold text-purple-800">บทที่ 4: การออมเงิน</h3>
         <p class="text-purple-600 text-sm">วางแผนการออมอย่างฉลาด</p>
        </div>
       </div></button>
     </div><!-- Progress Section -->
     <div class="mt-8 bg-white rounded-2xl p-6 shadow-lg border-2 border-amber-100">
      <h3 class="text-lg font-bold text-amber-800 mb-4 flex items-center gap-2"><span>📊</span> ความก้าวหน้าของฉัน</h3>
      <div class="grid grid-cols-4 gap-4 text-center">
       <div class="bg-amber-50 rounded-xl p-3">
        <div class="text-2xl mb-1">
         🪙
        </div>
        <div id="progress-1" class="text-amber-800 font-bold">
         0/5
        </div>
       </div>
       <div class="bg-green-50 rounded-xl p-3">
        <div class="text-2xl mb-1">
         ➕
        </div>
        <div id="progress-2" class="text-green-800 font-bold">
         0/5
        </div>
       </div>
       <div class="bg-blue-50 rounded-xl p-3">
        <div class="text-2xl mb-1">
         🛒
        </div>
        <div id="progress-3" class="text-blue-800 font-bold">
         0/5
        </div>
       </div>
       <div class="bg-purple-50 rounded-xl p-3">
        <div class="text-2xl mb-1">
         🐷
        </div>
        <div id="progress-4" class="text-purple-800 font-bold">
         0/5
        </div>
       </div>
      </div>
     </div>
    </div><!-- Quiz Screen -->
    <div id="quiz-screen" class="hidden slide-in">
     <div class="bg-white rounded-2xl shadow-xl overflow-hidden"><!-- Quiz Header -->
      <div id="quiz-header" class="bg-gradient-to-r from-amber-500 to-orange-500 text-white p-4">
       <div class="flex justify-between items-center"><button onclick="goToMenu()" class="bg-white/20 hover:bg-white/30 rounded-lg px-3 py-1 text-sm transition-colors"> ← กลับเมนู </button>
        <div class="flex items-center gap-4"><span id="question-counter" class="text-sm">ข้อ 1/5</span>
         <div class="bg-white/20 rounded-full px-3 py-1 text-sm">
          ⭐ <span id="quiz-score">0</span>
         </div>
        </div>
       </div>
      </div><!-- Quiz Content -->
      <div id="quiz-content" class="p-6"><!-- Question will be loaded here -->
      </div>
     </div>
    </div><!-- Result Screen -->
    <div id="result-screen" class="hidden slide-in">
     <div class="bg-white rounded-2xl shadow-xl p-8 text-center">
      <div id="result-emoji" class="text-8xl mb-4">
       🎉
      </div>
      <h2 id="result-title" class="text-2xl font-bold text-amber-800 mb-2">ยอดเยี่ยมมาก!</h2>
      <p id="result-message" class="text-amber-600 mb-6">คุณทำได้ดีมาก!</p>
      <div class="bg-gradient-to-r from-amber-100 to-orange-100 rounded-xl p-6 mb-6">
       <div class="text-4xl font-bold text-amber-800 mb-2"><span id="final-score">5</span>/5
       </div>
       <p class="text-amber-600">คะแนนที่ได้</p>
      </div>
      <div class="flex gap-4 justify-center"><button onclick="restartLesson()" class="bg-amber-500 hover:bg-amber-600 text-white font-bold py-3 px-6 rounded-xl transition-colors"> 🔄 ลองอีกครั้ง </button> <button onclick="goToMenu()" class="bg-gray-200 hover:bg-gray-300 text-gray-700 font-bold py-3 px-6 rounded-xl transition-colors"> 📋 เมนูหลัก </button>
      </div>
     </div>
    </div>
   </main><!-- Footer -->
   <footer class="text-center py-6 text-amber-600 text-sm space-y-2">
    <p>💡 เรียนรู้อย่างสนุก พัฒนาทักษะการเงิน</p>
    <div class="bg-white/50 backdrop-blur rounded-xl px-4 py-3 inline-block border-2 border-amber-200">
     <p class="font-bold text-amber-800 mb-1">👨‍💻 ผู้สร้างเกม</p>
     <p class="text-amber-700">เด็กชายภัทรชนน พงษ์ญวน</p>
     <p class="text-amber-600 text-xs">ชั้นประถมศึกษาปีที่ 5/5 สาย MEP</p>
    </div>
   </footer>
  </div>
  <script>
    // Default configuration
    const defaultConfig = {
      app_title: 'คณิตศาสตร์การเงิน ป.5',
      welcome_message: 'ยินดีต้อนรับสู่โลกการเงิน!',
      primary_color: '#f59e0b',
      secondary_color: '#ffffff',
      text_color: '#92400e',
      accent_color: '#ea580c',
      bg_color: '#fffbeb'
    };

    // App state
    let currentLesson = 0;
    let currentQuestion = 0;
    let score = 0;
    let totalScore = 0;
    let lessonScores = {1: 0, 2: 0, 3: 0, 4: 0};
    let questions = [];

    // Question banks for each lesson
    const questionBanks = {
      // Lesson 1: รู้จักเงินตรา
      1: [
        {
          question: "เหรียญใดมีมูลค่ามากที่สุด?",
          image: "🪙",
          options: ["เหรียญ 25 สตางค์", "เหรียญ 50 สตางค์", "เหรียญ 1 บาท", "เหรียญ 10 บาท"],
          correct: 3,
          explanation: "เหรียญ 10 บาท มีมูลค่ามากที่สุดในตัวเลือกนี้"
        },
        {
          question: "ธนบัตร 100 บาท มีสีอะไร?",
          image: "💵",
          options: ["สีแดง", "สีเขียว", "สีน้ำเงิน", "สีม่วง"],
          correct: 0,
          explanation: "ธนบัตร 100 บ��ท มีสีแดงเป็นสีหลัก"
        },
        {
          question: "เหรียญ 5 บาท มีรูปอะไรอยู่ด้านหลัง?",
          image: "🏛️",
          options: ["วัดอรุณ", "พระปรางค์", "พระบรมมหาราชวัง", "วัดพระแก้ว"],
          correct: 1,
          explanation: "เหรียญ 5 บาท มีรูปพระปรางค์วัดอรุณอยู่ด้านหลัง"
        },
        {
          question: "1 บาท เท่ากับกี่สตางค์?",
          image: "💰",
          options: ["10 สตางค์", "50 สตางค์", "100 สตางค์", "1,000 สตางค์"],
          correct: 2,
          explanation: "1 บาท = 100 สตางค์"
        },
        {
          question: "ธนบัตรใดมี���ูลค่าน้อยที่สุด?",
          image: "📜",
          options: ["ธนบัตร 20 บาท", "ธนบัตร 50 บาท", "ธนบัตร 100 บาท", "ธนบัตร 500 บาท"],
          correct: 0,
          explanation: "ธนบัตร 20 บาท มีมูลค่าน้อยที่สุดในตัวเลือก"
        }
      ],
      // Lesson 2: การบวกลบเงิน
      2: [
        {
          question: "50 บาท + 30 บาท = ?",
          image: "➕",
          options: ["60 บาท", "70 บาท", "80 บาท", "90 บาท"],
          correct: 2,
          explanation: "50 + 30 = 80 บาท"
        },
        {
          question: "100 บาท - 45 บาท = ?",
          image: "➖",
          options: ["45 บาท", "55 บาท", "65 บาท", "75 บาท"],
          correct: 1,
          explanation: "100 - 45 = 55 บาท"
        },
        {
          question: "25 บาท + 25 บาท + 50 บาท = ?",
          image: "🧮",
          options: ["75 บาท", "100 บาท", "125 บาท", "150 บาท"],
          correct: 1,
          explanation: "25 + 25 + 50 = 100 บาท"
        },
        {
          question: "200 บาท - 75 บาท - 25 บาท = ?",
          image: "📊",
          options: ["75 บาท", "100 บาท", "125 บาท", "150 บาท"],
          correct: 1,
          explanation: "200 - 75 - 25 = 100 บาท"
        },
        {
          question: "ถ้ามีเงิน 500 บาท ใช้ไป 320 บาท จะเหลือ��งินเท่าไร?",
          image: "💸",
          options: ["160 บาท", "170 บาท", "180 บาท", "190 บาท"],
          correct: 2,
          explanation: "500 - 320 = 180 บาท"
        }
      ],
      // Lesson 3: การซื้อของ
      3: [
        {
          question: "ซื้อขนม 35 บาท จ่ายเงิน 50 บาท ได้เงินทอนเท่าไร?",
          image: "🍬",
          options: ["10 บาท", "15 บาท", "20 บาท", "25 บาท"],
          correct: 1,
          explanation: "เงินทอน = 50 - 35 = 15 บาท"
        },
        {
          question: "ซื้อสมุด 2 เล่ม ราคาเล่มละ 25 บาท ต้องจ่ายเงินเท่าไร?",
          image: "📓",
          options: ["40 บาท", "45 บาท", "50 บาท", "55 บาท"],
          correct: 2,
          explanation: "2 × 25 = 50 บาท"
        },
        {
          question: "ซื้อน้ำ 15 บาท และขนมปัง 20 บาท รวมเป็นเงินเท่าไร?",
          image: "🥪",
          options: ["30 บาท", "35 บาท", "40 บาท", "45 บาท"],
          correct: 1,
          explanation: "15 + 20 = 35 บาท"
        },
        {
          question: "มีเงิน 100 บาท ซื้อปากกา 28 บาท และสมุด 32 บาท เหลือเงินเท่าไร?",
          image: "✏️",
          options: ["30 บาท", "35 บาท", "40 บาท", "45 บาท"],
          correct: 2,
          explanation: "100 - 28 - 32 = 40 บาท"
        },
        {
          question: "ซ��้อของเล่น 89 บาท จ่ายเงิน 100 บาท ได้เงินทอนเท่าไร?",
          image: "🎮",
          options: ["9 บาท", "11 บาท", "19 บาท", "21 บาท"],
          correct: 1,
          explanation: "เงินทอน = 100 - 89 = 11 บาท"
        }
      ],
      // Lesson 4: การออมเงิน
      4: [
        {
          question: "ถ้าออมเงินวันละ 10 บาท 7 วัน จะมีเงินเท่าไร?",
          image: "🐷",
          options: ["60 บาท", "70 บาท", "80 บาท", "90 บาท"],
          correct: 1,
          explanation: "10 × 7 = 70 บาท"
        },
        {
          question: "ต้องการซื้อของราคา 200 บาท ถ้าออมวันละ 20 บาท กี่วันจะครบ?",
          image: "🎯",
          options: ["8 วัน", "10 วัน", "12 วัน", "15 วัน"],
          correct: 1,
          explanation: "200 ÷ 20 = 10 วัน"
        },
        {
          question: "ออมเงินได้ 150 บาท ต้องการเพิ่มอีก 50 บาท รวมเป็นเท่าไร?",
          image: "💵",
          options: ["180 บาท", "190 บาท", "200 บาท", "210 บาท"],
          correct: 2,
          explanation: "150 + 50 = 200 บาท"
        },
        {
          question: "ออมเ���ินเดือนละ 100 บาท 6 เดือน จะมีเงินเท่าไร?",
          image: "📅",
          options: ["400 บาท", "500 บาท", "600 บาท", "700 บาท"],
          correct: 2,
          explanation: "100 × 6 = 600 บาท"
        },
        {
          question: "มีเงินออม 500 บาท ถอนไปใช้ 120 บาท เหลือเงินออมเท่าไร?",
          image: "🏧",
          options: ["360 บาท", "370 บาท", "380 บาท", "390 บาท"],
          correct: 2,
          explanation: "500 - 120 = 380 บาท"
        }
      ]
    };

    // Initialize Element SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (config) => {
          const appTitle = document.getElementById('app-title');
          const welcomeText = document.getElementById('welcome-text');
          
          if (appTitle) {
            appTitle.textContent = config.app_title || defaultConfig.app_title;
          }
          if (welcomeText) {
            welcomeText.textContent = config.welcome_message || defaultConfig.welcome_message;
          }

          // Apply colors
          const header = document.getElementById('header');
          if (header) {
            header.style.background = `linear-gradient(to right, ${config.primary_color || defaultConfig.primary_color}, ${config.accent_color || defaultConfig.accent_color})`;
          }
        },
        mapToCapabilities: (config) => ({
          recolorables: [
            {
              get: () => config.primary_color || defaultConfig.primary_color,
              set: (value) => {
                config.primary_color = value;
                window.elementSdk.setConfig({ primary_color: value });
              }
            },
            {
              get: () => config.secondary_color || defaultConfig.secondary_color,
              set: (value) => {
                config.secondary_color = value;
                window.elementSdk.setConfig({ secondary_color: value });
              }
            },
            {
              get: () => config.text_color || defaultConfig.text_color,
              set: (value) => {
                config.text_color = value;
                window.elementSdk.setConfig({ text_color: value });
              }
            },
            {
              get: () => config.accent_color || defaultConfig.accent_color,
              set: (value) => {
                config.accent_color = value;
                window.elementSdk.setConfig({ accent_color: value });
              }
            },
            {
              get: () => config.bg_color || defaultConfig.bg_color,
              set: (value) => {
                config.bg_color = value;
                window.elementSdk.setConfig({ bg_color: value });
              }
            }
          ],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (config) => new Map([
          ['app_title', config.app_title || defaultConfig.app_title],
          ['welcome_message', config.welcome_message || defaultConfig.welcome_message]
        ])
      });
    }

    // Start a lesson
    function startLesson(lessonNum) {
      currentLesson = lessonNum;
      currentQuestion = 0;
      score = 0;
      questions = [...questionBanks[lessonNum]].sort(() => Math.random() - 0.5);
      
      document.getElementById('menu-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.add('hidden');
      document.getElementById('quiz-screen').classList.remove('hidden');
      
      updateQuizHeader();
      showQuestion();
    }

    // Update quiz header colors based on lesson
    function updateQuizHeader() {
      const header = document.getElementById('quiz-header');
      const colors = {
        1: 'from-amber-500 to-orange-500',
        2: 'from-green-500 to-emerald-500',
        3: 'from-blue-500 to-cyan-500',
        4: 'from-purple-500 to-pink-500'
      };
      header.className = `bg-gradient-to-r ${colors[currentLesson]} text-white p-4`;
    }

    // Show current question
    function showQuestion() {
      const q = questions[currentQuestion];
      const content = document.getElementById('quiz-content');
      
      document.getElementById('question-counter').textContent = `ข้อ ${currentQuestion + 1}/5`;
      document.getElementById('quiz-score').textContent = score;
      
      content.innerHTML = `
        <div class="slide-in">
          <div class="text-center mb-6">
            <div class="text-6xl mb-4">${q.image}</div>
            <h3 class="text-xl font-bold text-gray-800">${q.question}</h3>
          </div>
          
          <div class="grid grid-cols-1 md:grid-cols-2 gap-3" id="options-container">
            ${q.options.map((opt, idx) => `
              <button 
                onclick="checkAnswer(${idx})"
                class="option-btn bg-gray-50 hover:bg-amber-50 border-2 border-gray-200 hover:border-amber-400 rounded-xl p-4 text-left transition-all font-medium text-gray-700"
                data-index="${idx}"
              >
                <span class="inline-block w-8 h-8 rounded-full bg-gray-200 text-center leading-8 mr-3 font-bold">
                  ${String.fromCharCode(65 + idx)}
                </span>
                ${opt}
              </button>
            `).join('')}
          </div>
        </div>
      `;
    }

    // Check answer
    function checkAnswer(selectedIndex) {
      const q = questions[currentQuestion];
      const buttons = document.querySelectorAll('.option-btn');
      const isCorrect = selectedIndex === q.correct;
      
      // Disable all buttons
      buttons.forEach(btn => {
        btn.disabled = true;
        btn.classList.remove('hover:bg-amber-50', 'hover:border-amber-400');
      });
      
      // Highlight correct and wrong answers
      buttons.forEach((btn, idx) => {
        if (idx === q.correct) {
          btn.classList.remove('bg-gray-50', 'border-gray-200');
          btn.classList.add('bg-green-100', 'border-green-500', 'text-green-800');
        } else if (idx === selectedIndex && !isCorrect) {
          btn.classList.remove('bg-gray-50', 'border-gray-200');
          btn.classList.add('bg-red-100', 'border-red-500', 'text-red-800', 'shake');
        }
      });
      
      if (isCorrect) {
        score++;
        totalScore++;
        document.getElementById('score').textContent = totalScore;
        createConfetti();
      }
      
      // Show explanation
      const content = document.getElementById('quiz-content');
      const explanationDiv = document.createElement('div');
      explanationDiv.className = `mt-4 p-4 rounded-xl slide-in ${isCorrect ? 'bg-green-50 border-2 border-green-200' : 'bg-red-50 border-2 border-red-200'}`;
      explanationDiv.innerHTML = `
        <div class="flex items-start gap-3">
          <span class="text-2xl">${isCorrect ? '✅' : '❌'}</span>
          <div>
            <p class="font-bold ${isCorrect ? 'text-green-800' : 'text-red-800'}">
              ${isCorrect ? 'ถูกต้อง!' : 'ไม่ถูกต้อง'}
            </p>
            <p class="${isCorrect ? 'text-green-700' : 'text-red-700'}">${q.explanation}</p>
          </div>
        </div>
      `;
      content.appendChild(explanationDiv);
      
      // Next button
      const nextDiv = document.createElement('div');
      nextDiv.className = 'mt-4 text-center slide-in';
      nextDiv.innerHTML = `
        <button onclick="nextQuestion()" class="bg-amber-500 hover:bg-amber-600 text-white font-bold py-3 px-8 rounded-xl transition-colors">
          ${currentQuestion < 4 ? 'ข้อถัดไป →' : 'ดูผลคะแนน 🏆'}
        </button>
      `;
      content.appendChild(nextDiv);
    }

    // Next question
    function nextQuestion() {
      currentQuestion++;
      if (currentQuestion < 5) {
        showQuestion();
      } else {
        showResults();
      }
    }

    // Show results
    function showResults() {
      lessonScores[currentLesson] = score;
      updateProgress();
      
      document.getElementById('quiz-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.remove('hidden');
      document.getElementById('result-screen').classList.add('slide-in');
      
      document.getElementById('final-score').textContent = score;
      
      let emoji, title, message;
      if (score === 5) {
        emoji = '🏆';
        title = 'ยอดเยี่ยมมาก!';
        message = '��ุณตอบถูกทุกข้อ! เก่งมากๆ เลย!';
        createConfetti();
      } else if (score >= 4) {
        emoji = '🌟';
        title = 'เก่งมาก!';
        message = 'คุณทำได้ดีมาก ลองอีกครั้งเพื่อคะแนนเต็ม!';
      } else if (score >= 3) {
        emoji = '👍';
        title = 'ดีมาก!';
        message = 'คุณกำลังพัฒนา ฝึกเพิ่มอีกนิดนะ!';
      } else {
        emoji = '💪';
        title = 'พยายามต่อไป!';
        message = 'ลองทบทวนบทเรียนแล้วมาทำใหม่นะ!';
      }
      
      document.getElementById('result-emoji').textContent = emoji;
      document.getElementById('result-title').textContent = title;
      document.getElementById('result-message').textContent = message;
    }

    // Update progress display
    function updateProgress() {
      for (let i = 1; i <= 4; i++) {
        document.getElementById(`progress-${i}`).textContent = `${lessonScores[i]}/5`;
      }
    }

    // Go to menu
    function goToMenu() {
      document.getElementById('quiz-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.add('hidden');
      document.getElementById('menu-screen').classList.remove('hidden');
      document.getElementById('menu-screen').classList.add('slide-in');
    }

    // Restart lesson
    function restartLesson() {
      startLesson(currentLesson);
    }

    // Create confetti effect
    function createConfetti() {
      const colors = ['#f59e0b', '#10b981', '#3b82f6', '#8b5cf6', '#ec4899', '#ef4444'];
      for (let i = 0; i < 30; i++) {
        setTimeout(() => {
          const confetti = document.createElement('div');
          confetti.className = 'confetti';
          confetti.style.left = Math.random() * 100 + '%';
          confetti.style.background = colors[Math.floor(Math.random() * colors.length)];
          confetti.style.animationDelay = Math.random() * 0.5 + 's';
          document.body.appendChild(confetti);
          
          setTimeout(() => confetti.remove(), 3000);
        }, i * 50);
      }
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c0f0e03341dec6e',t:'MTc2ODkxNzE3My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

