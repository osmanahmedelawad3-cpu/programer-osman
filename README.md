<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>أستاذي الذكي | رفيق الدراسة</title>
    <!-- ★★★ سياسة حماية المحتوى (CSP) ★★★ -->
    <meta http-equiv="Content-Security-Policy" content="
        default-src 'self';
        script-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com https://fonts.googleapis.com;
        style-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com https://fonts.googleapis.com;
        font-src 'self' https://fonts.gstatic.com;
        connect-src 'self' https://translate.googleapis.com;
        media-src 'self' blob:;
        img-src 'self' data:;
    ">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;900&display=swap" rel="stylesheet">
    <style>
        /* نفس الستايل اللي كان موجود، لم يتغير */
        :root {
            --bg: #f5f7fa;
            --card: #ffffff;
            --text: #2d3436;
            --primary: #6c5ce7;
            --primary-light: #a29bfe;
            --secondary: #00cec9;
            --accent: #fd79a8;
            --danger: #e17055;
            --success: #00b894;
            --border: #dfe6e9;
            --shadow: 0 2px 15px rgba(0,0,0,0.05);
            --radius: 16px;
            --transition: 0.3s ease;
        }
        .dark-mode {
            --bg: #1e272e;
            --card: #2d3436;
            --text: #dfe6e9;
            --primary: #a29bfe;
            --primary-light: #6c5ce7;
            --secondary: #00cec9;
            --border: #636e72;
            --shadow: 0 2px 15px rgba(0,0,0,0.3);
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Tajawal', sans-serif;
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
            transition: background 0.4s, color 0.4s;
            padding: 0;
        }
        .app-container {
            width: 100%;
            max-width: 100%;
            margin: 0 auto;
            background: var(--card);
            min-height: 100vh;
            box-shadow: none;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;
        }
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: white;
            position: relative;
        }
        header h1 {
            font-size: 22px;
            font-weight: 900;
            letter-spacing: -0.5px;
        }
        .dark-toggle {
            background: rgba(255,255,255,0.2);
            border: none;
            color: white;
            font-size: 20px;
            cursor: pointer;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: 0.3s;
        }
        .dark-toggle:hover {
            background: rgba(255,255,255,0.4);
            transform: rotate(20deg);
        }
        .tabs {
            display: flex;
            background: var(--card);
            border-bottom: 1px solid var(--border);
            overflow-x: auto;
            scrollbar-width: none;
            -webkit-overflow-scrolling: touch;
        }
        .tabs::-webkit-scrollbar {
            display: none;
        }
        .tab-btn {
            flex: 1 0 auto;
            padding: 14px 16px;
            background: none;
            border: none;
            font-family: 'Tajawal', sans-serif;
            font-weight: 700;
            font-size: 15px;
            color: var(--text);
            opacity: 0.7;
            cursor: pointer;
            transition: 0.3s;
            white-space: nowrap;
            display: flex;
            align-items: center;
            gap: 6px;
            border-bottom: 3px solid transparent;
        }
        .tab-btn i {
            font-size: 16px;
        }
        .tab-btn.active {
            opacity: 1;
            color: var(--primary);
            border-bottom-color: var(--primary);
            background: rgba(108, 92, 231, 0.05);
        }
        .tab-content {
            display: none;
            padding: 15px;
            animation: fade 0.4s;
            flex: 1;
        }
        .tab-content.active {
            display: block;
        }
        @keyframes fade {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .card {
            background: var(--card);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            padding: 15px;
            margin-bottom: 15px;
            box-shadow: var(--shadow);
            transition: 0.3s;
        }
        .card h2 {
            font-size: 18px;
            margin-bottom: 12px;
        }
        textarea, input[type="text"], select, input[type="number"] {
            width: 100%;
            padding: 12px 14px;
            border: 1px solid var(--border);
            border-radius: 12px;
            font-family: 'Tajawal', sans-serif;
            font-size: 15px;
            background: var(--bg);
            color: var(--text);
            margin: 8px 0;
            transition: 0.3s;
            resize: none;
        }
        .action-buttons-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px;
            margin-top: 5px;
        }
        button {
            background: var(--primary);
            color: white;
            border: none;
            padding: 12px 16px;
            border-radius: 12px;
            font-family: 'Tajawal', sans-serif;
            font-weight: 700;
            font-size: 15px;
            cursor: pointer;
            transition: 0.3s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            margin: 4px 0;
            width: 100%;
        }
        button:hover {
            opacity: 0.9;
        }
        button.secondary { background: var(--secondary); }
        button.danger { background: var(--danger); }
        button.success { background: var(--success); }
        
        .quote {
            text-align: center;
            font-style: italic;
            padding: 15px;
            margin-top: auto;
            opacity: 0.7;
            font-size: 13px;
        }
        .flashcard {
            background: var(--primary-light);
            color: white;
            padding: 20px;
            border-radius: 20px;
            text-align: center;
            margin: 15px 0;
            min-height: 130px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 18px;
            font-weight: 700;
            transition: 0.4s;
            user-select: none;
        }
        .flashcard.revealed {
            background: var(--secondary);
        }
        .timer-display {
            font-size: 45px;
            font-weight: 900;
            text-align: center;
            margin: 15px 0;
        }
        .voice-buttons {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        
        .translator-row {
            display: flex; 
            gap: 8px; 
            align-items: center;
            width: 100%;
        }
        .translator-row select {
            flex: 1;
            min-width: 0;
        }
        .translator-row button {
            width: auto;
            flex: 0 0 auto;
            padding: 12px;
        }
    </style>
</head>
<body>
    <div class="app-container">
        <header>
            <h1><i class="fas fa-graduation-cap"></i> أستاذي الذكي</h1>
            <button class="dark-toggle" id="darkModeToggle" title="الوضع المظلم"><i class="fas fa-moon"></i></button>
        </header>

        <div class="tabs">
            <button class="tab-btn active" data-tab="translator"><i class="fas fa-language"></i> المترجم</button>
            <button class="tab-btn" data-tab="summarizer"><i class="fas fa-compress-alt"></i> الملخّص</button>
            <button class="tab-btn" data-tab="flashcards"><i class="fas fa-clone"></i> بطاقات تعليمية</button>
            <button class="tab-btn" data-tab="pomodoro"><i class="fas fa-clock"></i> بومودورو</button>
            <button class="tab-btn" data-tab="notes"><i class="fas fa-microphone"></i> ملاحظات</button>
            <button class="tab-btn" data-tab="quiz"><i class="fas fa-question-circle"></i> اختبارات</button>
        </div>

        <!-- باقي الـ HTML نفس الموجود من غير تغيير -->
        <div class="tab-content active" id="translator">
            <div class="card">
                <h2><i class="fas fa-language"></i> المترجم الفوري</h2>
                <div class="translator-row">
                    <select id="translateFrom">
                        <option value="auto">اكتشاف اللغة</option>
                        <option value="ar">العربية</option>
                        <option value="en">English</option>
                        <option value="fr">Français</option>
                    </select>
                    <button id="swapLangBtn"><i class="fas fa-exchange-alt"></i></button>
                    <select id="translateTo">
                        <option value="ar">العربية</option>
                        <option value="en" selected>English</option>
                        <option value="fr">Français</option>
                    </select>
                </div>
                <textarea id="translateInput" placeholder="اكتب النص هنا..." rows="4"></textarea>
                
                <div class="action-buttons-grid">
                    <button id="translateBtn"><i class="fas fa-sync-alt"></i> ترجمة</button>
                    <button id="speakInputBtn"><i class="fas fa-volume-up"></i> استمع للنص</button>
                </div>
                
                <div id="translateOutput" style="margin-top:12px; padding:12px; background:var(--bg); border-radius:12px; min-height:60px; word-break: break-word;"></div>
                
                <div class="action-buttons-grid">
                    <button id="speakOutputBtn" style="display:none;"><i class="fas fa-volume-up"></i> استمع للترجمة</button>
                    <button id="saveTranslationBtn" style="display:none;"><i class="fas fa-save"></i> حفظ الترجمة</button>
                </div>

                <details style="margin-top:15px">
                    <summary>سجل الترجمات المحفوظة</summary>
                    <ul id="translationHistory" style="max-height:150px; overflow-y:auto; padding-right:15px; margin-top:8px;"></ul>
                </details>
            </div>
        </div>

        <div class="tab-content" id="summarizer">
            <div class="card">
                <h2><i class="fas fa-compress-alt"></i> الملخّص الذكي</h2>
                <textarea id="summarizerInput" placeholder="الصق النص الطويل هنا..." rows="6"></textarea>
                <div style="margin: 8px 0; display: flex; align-items: center; gap: 10px;">
                    <label style="white-space: nowrap;">عدد النقاط:</label> 
                    <input type="number" id="summaryPoints" value="5" min="1" max="10" style="margin:0; width:70px;">
                </div>
                <button id="summarizeBtn"><i class="fas fa-magic"></i> لخّص النص</button>
                <div id="summaryOutput" style="margin-top:15px; padding:15px; background:var(--bg); border-radius:12px; word-break: break-word;"></div>
            </div>
        </div>

        <div class="tab-content" id="flashcards">
            <div class="card">
                <h2><i class="fas fa-clone"></i> مصنع البطاقات التعليمية</h2>
                <input type="text" id="flashQuestion" placeholder="السؤال">
                <input type="text" id="flashAnswer" placeholder="الإجابة">
                
                <div class="action-buttons-grid">
                    <button id="addFlashcardBtn"><i class="fas fa-plus"></i> أضف بطاقة</button>
                    <button id="importFlashcardsBtn" class="secondary"><i class="fas fa-file-import"></i> استيراد س:ج</button>
                </div>
                
                <div style="margin-top:15px; text-align: center;">
                    <button id="startReviewBtn" class="success"><i class="fas fa-play"></i> ابدأ المراجعة</button>
                    <div id="flashcardStats" style="margin-top:8px; font-weight:bold; font-size:14px;"></div>
                </div>
                
                <div id="flashcardReviewArea" style="display:none; margin-top:15px;">
                    <div class="flashcard" id="currentFlashcard">اضغط للكشف</div>
                    <div class="action-buttons-grid">
                        <button id="knownBtn" class="success"><i class="fas fa-check"></i> عرفتها</button>
                        <button id="unknownBtn" class="danger"><i class="fas fa-times"></i> ما عرفتها</button>
                    </div>
                    <div style="text-align:center; margin-top:10px; font-size:14px;" id="reviewProgress"></div>
                </div>
            </div>
        </div>

        <div class="tab-content" id="pomodoro">
            <div class="card" style="text-align:center;">
                <h2><i class="fas fa-clock"></i> مؤقت بومودورو</h2>
                <div class="timer-display" id="pomodoroDisplay">25:00</div>
                <div style="margin:10px 0; display:flex; justify-content: space-around; gap:10px; font-size:14px;">
                    <label>المذاكرة: <input type="number" id="studyMinutes" value="25" min="1" style="width:55px; display:inline-block; padding:6px; margin:0;"></label>
                    <label>الراحة: <input type="number" id="breakMinutes" value="5" min="1" style="width:55px; display:inline-block; padding:6px; margin:0;"></label>
                </div>
                <button id="startPomodoroBtn" class="success"><i class="fas fa-play"></i> ابدأ المؤقت</button>
                <button id="pausePomodoroBtn" class="danger" style="display:none;"><i class="fas fa-pause"></i> إيقاف مؤقت</button>
                <button id="resetPomodoroBtn" class="secondary"><i class="fas fa-redo"></i> إعادة ضبط</button>
                <div style="margin-top:12px; font-size:14px;">الجلسات المكتملة: <span id="pomodoroSessions" style="font-weight:bold;">0</span></div>
            </div>
        </div>

        <div class="tab-content" id="notes">
            <div class="card">
                <h2><i class="fas fa-microphone-alt"></i> دفتر الملاحظات</h2>
                <div class="voice-buttons">
                    <button id="startDictateBtn" class="secondary"><i class="fas fa-keyboard"></i> ابدأ الإملاء الصوتي</button>
                    <div class="action-buttons-grid">
                        <button id="startRecordBtn"><i class="fas fa-microphone"></i> تسجيل صوتي</button>
                        <button id="stopRecordBtn" style="display:none;" class="danger"><i class="fas fa-stop"></i> إيقاف</button>
                    </div>
                </div>
                <audio id="audioPlayback" controls style="width:100%; margin-top:10px; display:none;"></audio>
                <textarea id="notesTextarea" placeholder="اكتب ملاحظاتك هنا..." rows="6"></textarea>
                
                <div class="action-buttons-grid">
                    <button id="saveNotesBtn" class="success"><i class="fas fa-save"></i> حفظ</button>
                    <button id="downloadNotesBtn"><i class="fas fa-download"></i> تحميل txt</button>
                </div>
            </div>
        </div>

        <div class="tab-content" id="quiz">
            <div class="card">
                <h2><i class="fas fa-question-circle"></i> صانع الاختبارات الذاتية</h2>
                <textarea id="quizMaterial" placeholder="الصق المادة الدراسية (نص عربي أو إنجليزي)..." rows="5"></textarea>
                <button id="generateQuizBtn"><i class="fas fa-cogs"></i> توليد الأسئلة</button>
                
                <div id="quizArea" style="display:none; margin-top:15px;">
                    <div id="quizQuestion" style="font-weight:700; margin-bottom:12px; font-size:16px;"></div>
                    <div id="quizOptions" style="display:flex; flex-direction:column; gap:8px;"></div>
                    <button id="nextQuestionBtn" style="display:none; margin-top:12px;" class="success">السؤال التالي</button>
                    <div id="quizResult" style="margin-top:10px; font-weight:bold; text-align:center;"></div>
                    <div style="margin-top:10px; font-size:14px; text-align:center;">النتيجة: <span id="quizScore">0</span>/<span id="quizTotal">0</span></div>
                    <button id="startTimedQuizBtn" class="secondary" style="margin-top:10px;">تحدي الوقت (دقيقة)</button>
                    <div id="timerDisplay" style="font-size:16px; margin-top:8px; text-align:center; font-weight:bold;"></div>
                </div>
            </div>
        </div>

        <div class="quote" id="motivationalQuote">"العلم نور والجهل ظلام" - مثل عربي</div>
    </div>

    <script>
        // ★★★ دوال مساعدة للأمان ★★★
        
        // لتشفير وفك تشفير البيانات في localStorage (بسيط)
        function encryptData(data) {
            return btoa(encodeURIComponent(JSON.stringify(data)));
        }
        function decryptData(encrypted) {
            try {
                return JSON.parse(decodeURIComponent(atob(encrypted)));
            } catch(e) {
                return null;
            }
        }
        
        // تنظيف النص من أي وسوم HTML ضارة (نستخدم textContent دائماً، لكن هذه احتياطية)
        function sanitizeText(str) {
            const temp = document.createElement('div');
            temp.textContent = str;
            return temp.innerHTML; // إرجاع النص بعد تحويل الكيانات
        }
        
        // جلب آمن مع مهلة زمنية
        async function safeFetch(url, options = {}, timeout = 5000) {
            const controller = new AbortController();
            const id = setTimeout(() => controller.abort(), timeout);
            try {
                const response = await fetch(url, { ...options, signal: controller.signal });
                clearTimeout(id);
                if (!response.ok) throw new Error('فشل الاتصال');
                return response;
            } catch (error) {
                clearTimeout(id);
                throw error;
            }
        }
        
        // قراءة آمنة من localStorage مع فك التشفير
        function getSecureItem(key) {
            const raw = localStorage.getItem(key);
            return raw ? decryptData(raw) : null;
        }
        function setSecureItem(key, value) {
            localStorage.setItem(key, encryptData(value));
        }

        // ================ الوضع المظلم ================
        const darkToggle = document.getElementById('darkModeToggle');
        darkToggle.addEventListener('click', () => {
            document.body.classList.toggle('dark-mode');
            const icon = darkToggle.querySelector('i');
            icon.classList.toggle('fa-moon');
            icon.classList.toggle('fa-sun');
            localStorage.setItem('darkMode', document.body.classList.contains('dark-mode'));
        });
        if (localStorage.getItem('darkMode') === 'true') {
            document.body.classList.add('dark-mode');
            darkToggle.querySelector('i').classList.replace('fa-moon', 'fa-sun');
        }

        // ================ التبويبات ================
        const tabs = document.querySelectorAll('.tab-btn');
        const contents = document.querySelectorAll('.tab-content');
        tabs.forEach(btn => {
            btn.addEventListener('click', () => {
                tabs.forEach(b => b.classList.remove('active'));
                contents.forEach(c => c.classList.remove('active'));
                btn.classList.add('active');
                document.getElementById(btn.dataset.tab).classList.add('active');
                btn.scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'center' });
            });
        });

        // ================ اقتباسات تحفيزية ================
        const quotes = [
            "العلم في الصغر كالنقش على الحجر",
            "اطلب العلم من المهد إلى اللحد",
            "من جد وجد ومن زرع حصد",
            "خير العلم ما نفع",
            "التعليم جواز السفر إلى المستقبل"
        ];
        const quoteEl = document.getElementById('motivationalQuote');
        function randomQuote() {
            quoteEl.textContent = '"' + quotes[Math.floor(Math.random() * quotes.length)] + '"';
        }
        setInterval(randomQuote, 30000);
        randomQuote();

        // ================ المترجم (مع إجراءات أمان) ================
        const translateInput = document.getElementById('translateInput');
        const translateOutput = document.getElementById('translateOutput');
        const translateBtn = document.getElementById('translateBtn');
        const swapLangBtn = document.getElementById('swapLangBtn');
        const fromSelect = document.getElementById('translateFrom');
        const toSelect = document.getElementById('translateTo');
        const speakInputBtn = document.getElementById('speakInputBtn');
        const speakOutputBtn = document.getElementById('speakOutputBtn');
        const saveTranslationBtn = document.getElementById('saveTranslationBtn');
        const translationHistory = document.getElementById('translationHistory');

        async function translateText(text, from, to) {
            const url = `https://translate.googleapis.com/translate_a/single?client=gtx&sl=${from}&tl=${to}&dt=t&q=${encodeURIComponent(text)}`;
            try {
                const response = await safeFetch(url);
                const data = await response.json();
                return data[0].map(item => item[0]).join('');
            } catch (e) {
                return 'تعذرت الترجمة، تحقق من الاتصال أو حاول لاحقاً';
            }
        }

        translateBtn.addEventListener('click', async () => {
            const text = translateInput.value.trim();
            if (!text || text.length > 5000) { // حد أقصى للنص
                alert('النص طويل جداً أو فارغ');
                return;
            }
            const from = fromSelect.value;
            const to = toSelect.value;
            const result = await translateText(text, from, to);
            translateOutput.textContent = result; // استخدام textContent الآمن
            speakOutputBtn.style.display = 'inline-flex';
            saveTranslationBtn.style.display = 'inline-flex';
        });

        swapLangBtn.addEventListener('click', () => {
            const temp = fromSelect.value;
            fromSelect.value = toSelect.value;
            toSelect.value = temp === 'auto' ? 'ar' : temp;
        });

        speakInputBtn.addEventListener('click', () => {
            const text = translateInput.value.trim();
            if (text) speakText(text, fromSelect.value !== 'auto' ? fromSelect.value : 'ar');
        });

        speakOutputBtn.addEventListener('click', () => {
            const text = translateOutput.textContent;
            if (text) speakText(text, toSelect.value);
        });

        function speakText(text, lang) {
            const utterance = new SpeechSynthesisUtterance(text);
            utterance.lang = lang === 'en' ? 'en-US' : lang === 'fr' ? 'fr-FR' : 'ar-SA';
            window.speechSynthesis.speak(utterance);
        }

        saveTranslationBtn.addEventListener('click', () => {
            const original = translateInput.value.trim();
            const translated = translateOutput.textContent;
            if (!original || !translated) return;
            let history = getSecureItem('translationHistory') || [];
            history.unshift({ original, translated, date: new Date().toLocaleString() });
            if (history.length > 20) history.pop();
            setSecureItem('translationHistory', history);
            renderTranslationHistory();
        });

        function renderTranslationHistory() {
            const history = getSecureItem('translationHistory') || [];
            translationHistory.innerHTML = ''; // تفريغ
            history.forEach(item => {
                const li = document.createElement('li');
                li.style.fontSize = '13px';
                li.style.marginBottom = '6px';
                li.style.borderBottom = '1px solid var(--border)';
                li.style.paddingBottom = '4px';
                // بناء النص بشكل آمن
                const strong = document.createElement('strong');
                strong.textContent = item.original;
                li.appendChild(strong);
                li.appendChild(document.createTextNode(' → ' + item.translated));
                translationHistory.appendChild(li);
            });
        }
        renderTranslationHistory();

        // ================ الملخّص (مع أمان) ================
        const summarizerInput = document.getElementById('summarizerInput');
        const summaryPoints = document.getElementById('summaryPoints');
        const summaryOutput = document.getElementById('summaryOutput');
        
        document.getElementById('summarizeBtn').addEventListener('click', () => {
            const text = summarizerInput.value.trim();
            if (!text || text.length > 10000) {
                alert('النص طويل جداً (الحد 10,000 حرف) أو فارغ');
                return;
            }
            let num = parseInt(summaryPoints.value) || 5;
            num = Math.min(Math.max(num, 1), 10); // تقييد بين 1 و 10
            const sentences = text.match(/[^\.!\?\n]+[\.!\?\n]*/g) || [text];
            if (sentences.length <= num) {
                summaryOutput.innerHTML = ''; // آمن: بنبني عناصر
                sentences.forEach(s => {
                    const p = document.createElement('p');
                    p.textContent = '• ' + s.trim();
                    summaryOutput.appendChild(p);
                });
                return;
            }
            const wordFreq = {};
            sentences.forEach(s => {
                s.split(/\s+/).forEach(w => {
                    const word = w.replace(/[^\w\u0621-\u064A]/g, '').toLowerCase();
                    if (word.length > 2) wordFreq[word] = (wordFreq[word] || 0) + 1;
                });
            });
            const scores = sentences.map(s => {
                let score = 0;
                s.split(/\s+/).forEach(w => {
                    const word = w.replace(/[^\w\u0621-\u064A]/g, '').toLowerCase();
                    score += wordFreq[word] || 0;
                });
                return { sentence: s.trim(), score };
            });
            scores.sort((a, b) => b.score - a.score);
            const top = scores.slice(0, num);
            summaryOutput.innerHTML = '';
            top.forEach(item => {
                const p = document.createElement('p');
                p.style.marginBottom = '6px';
                p.textContent = '• ' + item.sentence;
                summaryOutput.appendChild(p);
            });
            if (top.length === 0) {
                summaryOutput.textContent = 'لا توجد نقاط كافية.';
            }
        });

        // ================ البطاقات التعليمية (أمان) ================
        let flashcards = getSecureItem('flashcards') || [];
        let reviewIndex = 0;
        let reviewKnown = 0;
        let reviewUnknown = 0;

        function saveFlashcards() {
            setSecureItem('flashcards', flashcards);
            updateFlashcardStats();
        }

        function updateFlashcardStats() {
            document.getElementById('flashcardStats').textContent = `إجمالي البطاقات: ${flashcards.length}`;
        }
        updateFlashcardStats();

        document.getElementById('addFlashcardBtn').addEventListener('click', () => {
            const q = document.getElementById('flashQuestion').value.trim();
            const a = document.getElementById('flashAnswer').value.trim();
            if (!q || !a) return alert('أدخل السؤال والإجابة');
            flashcards.push({ question: q, answer: a, id: Date.now() });
            document.getElementById('flashQuestion').value = '';
            document.getElementById('flashAnswer').value = '';
            saveFlashcards();
        });

        document.getElementById('importFlashcardsBtn').addEventListener('click', () => {
            const text = prompt('الصق النص بصيغة "س: ... ج: ..." كل سؤال في سطر');
            if (!text) return;
            const lines = text.split('\n');
            lines.forEach(line => {
                const match = line.match(/س\s*[:]\s*(.+?)\s*ج\s*[:]\s*(.+)/i);
                if (match) {
                    flashcards.push({ question: match[1].trim(), answer: match[2].trim(), id: Date.now() + Math.random() });
                }
            });
            saveFlashcards();
        });

        const reviewArea = document.getElementById('flashcardReviewArea');
        const currentCard = document.getElementById('currentFlashcard');
        let cardRevealed = false;

        document.getElementById('startReviewBtn').addEventListener('click', () => {
            if (flashcards.length === 0) return alert('لا توجد بطاقات للمراجعة');
            reviewArea.style.display = 'block';
            reviewIndex = 0;
            reviewKnown = 0;
            reviewUnknown = 0;
            showFlashcard();
        });

        function showFlashcard() {
            if (reviewIndex >= flashcards.length) {
                currentCard.textContent = `انتهت المراجعة! ✅ عرفتها: ${reviewKnown} | ما عرفتها: ${reviewUnknown}`;
                document.getElementById('knownBtn').style.display = 'none';
                document.getElementById('unknownBtn').style.display = 'none';
                return;
            }
            cardRevealed = false;
            currentCard.textContent = flashcards[reviewIndex].question;
            currentCard.classList.remove('revealed');
            document.getElementById('knownBtn').style.display = 'inline-flex';
            document.getElementById('unknownBtn').style.display = 'inline-flex';
            document.getElementById('reviewProgress').textContent = `${reviewIndex + 1} / ${flashcards.length}`;
        }

        currentCard.addEventListener('click', () => {
            if (!cardRevealed && reviewIndex < flashcards.length) {
                currentCard.textContent = flashcards[reviewIndex].answer;
                currentCard.classList.add('revealed');
                cardRevealed = true;
            }
        });

        document.getElementById('knownBtn').addEventListener('click', () => {
            if (reviewIndex < flashcards.length) {
                reviewKnown++;
                reviewIndex++;
                showFlashcard();
            }
        });
        document.getElementById('unknownBtn').addEventListener('click', () => {
            if (reviewIndex < flashcards.length) {
                reviewUnknown++;
                reviewIndex++;
                showFlashcard();
            }
        });

        // ================ بومودورو (مع تحقق أمان) ================
        let pomodoroInterval;
        let pomodoroSeconds = 25 * 60;
        let isBreak = false;
        let sessions = parseInt(localStorage.getItem('pomodoroSessions') || '0') || 0;
        document.getElementById('pomodoroSessions').textContent = sessions;

        function updateTimerDisplay() {
            const mins = Math.floor(pomodoroSeconds / 60);
            const secs = pomodoroSeconds % 60;
            document.getElementById('pomodoroDisplay').textContent = `${String(mins).padStart(2,'0')}:${String(secs).padStart(2,'0')}`;
        }

        function stopPomodoro() {
            clearInterval(pomodoroInterval);
            document.getElementById('startPomodoroBtn').style.display = 'inline-flex';
            document.getElementById('pausePomodoroBtn').style.display = 'none';
        }

        document.getElementById('startPomodoroBtn').addEventListener('click', () => {
            let studyMin = parseInt(document.getElementById('studyMinutes').value) || 25;
            studyMin = Math.min(Math.max(studyMin, 1), 120); // التحقق من القيمة
            let breakMin = parseInt(document.getElementById('breakMinutes').value) || 5;
            breakMin = Math.min(Math.max(breakMin, 1), 60);
            
            if(!isBreak) {
                pomodoroSeconds = studyMin * 60;
            }
            updateTimerDisplay();
            document.getElementById('startPomodoroBtn').style.display = 'none';
            document.getElementById('pausePomodoroBtn').style.display = 'inline-flex';
            
            pomodoroInterval = setInterval(() => {
                if (pomodoroSeconds <= 0) {
                    clearInterval(pomodoroInterval);
                    if (!isBreak) {
                        sessions++;
                        localStorage.setItem('pomodoroSessions', sessions);
                        document.getElementById('pomodoroSessions').textContent = sessions;
                        alert('انتهت جلسة المذاكرة! استرح قليلاً.');
                        pomodoroSeconds = breakMin * 60;
                        isBreak = true;
                        updateTimerDisplay();
                        document.getElementById('startPomodoroBtn').click(); // بدء الراحة
                    } else {
                        isBreak = false;
                        alert('انتهت الراحة! يمكنك بدء جلسة جديدة.');
                        stopPomodoro();
                        pomodoroSeconds = studyMin * 60;
                        updateTimerDisplay();
                    }
                } else {
                    pomodoroSeconds--;
                    updateTimerDisplay();
                }
            }, 1000);
        });

        document.getElementById('pausePomodoroBtn').addEventListener('click', stopPomodoro);
        document.getElementById('resetPomodoroBtn').addEventListener('click', () => {
            stopPomodoro();
            isBreak = false;
            pomodoroSeconds = (parseInt(document.getElementById('studyMinutes').value) || 25) * 60;
            updateTimerDisplay();
        });

        // ================ الملاحظات الصوتية (أمان) ================
        const notesTextarea = document.getElementById('notesTextarea');
        notesTextarea.value = getSecureItem('notes') || '';

        document.getElementById('saveNotesBtn').addEventListener('click', () => {
            const notes = notesTextarea.value;
            if (notes.length > 50000) {
                alert('الملاحظات طويلة جداً، اختصرها');
                return;
            }
            setSecureItem('notes', notes);
            alert('تم حفظ الملاحظات');
        });
        document.getElementById('downloadNotesBtn').addEventListener('click', () => {
            const blob = new Blob([notesTextarea.value], {type: 'text/plain'});
            const a = document.createElement('a');
            a.href = URL.createObjectURL(blob);
            a.download = 'ملاحظاتي.txt';
            a.click();
        });

        let mediaRecorder;
        let audioChunks = [];
        const audioPlayback = document.getElementById('audioPlayback');
        document.getElementById('startRecordBtn').addEventListener('click', async () => {
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
                mediaRecorder = new MediaRecorder(stream);
                audioChunks = [];
                mediaRecorder.ondataavailable = e => audioChunks.push(e.data);
                mediaRecorder.onstop = () => {
                    const blob = new Blob(audioChunks, { type: 'audio/webm' });
                    audioPlayback.src = URL.createObjectURL(blob);
                    audioPlayback.style.display = 'block';
                };
                mediaRecorder.start();
                document.getElementById('startRecordBtn').style.display = 'none';
                document.getElementById('stopRecordBtn').style.display = 'inline-flex';
            } catch (err) {
                alert('لا يمكن الوصول للميكروفون');
            }
        });
        document.getElementById('stopRecordBtn').addEventListener('click', () => {
            mediaRecorder.stop();
            document.getElementById('startRecordBtn').style.display = 'inline-flex';
            document.getElementById('stopRecordBtn').style.display = 'none';
        });

        document.getElementById('startDictateBtn').addEventListener('click', () => {
            if (!('webkitSpeechRecognition' in window) && !('SpeechRecognition' in window)) {
                alert('المتصفح لا يدعم التعرف على الصوت');
                return;
            }
            const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
            const recognition = new SpeechRecognition();
            recognition.lang = 'ar-SA';
            recognition.interimResults = false;
            recognition.start();
            recognition.onresult = (event) => {
                const transcript = event.results[0][0].transcript;
                notesTextarea.value += ' ' + transcript;
            };
        });

        // ================ الاختبارات (آمنة) ================
        let quizQuestions = [];
        let currentQuizIndex = 0;
        let quizScore = 0;
        let timedQuizInterval;
        let timedSeconds = 60;

        document.getElementById('generateQuizBtn').addEventListener('click', () => {
            const text = document.getElementById('quizMaterial').value.trim();
            if (!text || text.length > 10000) {
                alert('النص طويل جداً (الحد 10,000 حرف)');
                return;
            }
            quizQuestions = generateMCQs(text);
            if (quizQuestions.length === 0) {
                alert('لم نتمكن من توليد أسئلة، حاول مع نص أطول.');
                return;
            }
            currentQuizIndex = 0;
            quizScore = 0;
            document.getElementById('quizArea').style.display = 'block';
            document.getElementById('quizScore').textContent = '0';
            document.getElementById('quizTotal').textContent = quizQuestions.length;
            document.getElementById('timerDisplay').textContent = '';
            showQuizQuestion();
        });

        function generateMCQs(text) {
            const sentences = text.match(/[^\.!\?\n]+[\.!\?\n]*/g) || [text];
            const questions = [];
            sentences.forEach(s => {
                const clean = s.replace(/[،,]/g, '').trim();
                const words = clean.split(/\s+/).filter(w => w.length > 3);
                if (words.length < 5) return;
                const keyIndex = Math.floor(Math.random() * words.length);
                const key = words[keyIndex];
                const question = clean.replace(key, '________');
                const distractors = [];
                const otherWords = words.filter(w => w !== key);
                while (distractors.length < 3 && otherWords.length > 0) {
                    const rand = otherWords.splice(Math.floor(Math.random() * otherWords.length), 1)[0];
                    if (!distractors.includes(rand)) distractors.push(rand);
                }
                if (distractors.length < 3) return;
                const options = [key, ...distractors].sort(() => Math.random() - 0.5);
                questions.push({ question, options, correct: key });
            });
            return questions.slice(0, 10);
        }

        function showQuizQuestion() {
            if (currentQuizIndex >= quizQuestions.length) {
                document.getElementById('quizQuestion').textContent = 'انتهى الاختبار! النتيجة النهائية: ' + quizScore;
                document.getElementById('quizOptions').innerHTML = '';
                document.getElementById('nextQuestionBtn').style.display = 'none';
                return;
            }
            const q = quizQuestions[currentQuizIndex];
            document.getElementById('quizQuestion').textContent = q.question;
            const optionsDiv = document.getElementById('quizOptions');
            optionsDiv.innerHTML = '';
            q.options.forEach(opt => {
                const btn = document.createElement('button');
                btn.textContent = opt; // آمن 100%
                btn.className = 'secondary';
                btn.style.display = 'block';
                btn.style.width = '100%';
                btn.addEventListener('click', () => selectAnswer(opt, q.correct));
                optionsDiv.appendChild(btn);
            });
            document.getElementById('nextQuestionBtn').style.display = 'none';
            document.getElementById('quizResult').textContent = '';
        }

        function selectAnswer(selected, correct) {
            const isCorrect = selected === correct;
            document.getElementById('quizResult').textContent = isCorrect ? '✅ إجابة صحيحة!' : `❌ خطأ، الصحيح: ${correct}`;
            if (isCorrect) quizScore++;
            document.getElementById('quizScore').textContent = quizScore;
            document.getElementById('nextQuestionBtn').style.display = 'inline-flex';
            document.querySelectorAll('#quizOptions button').forEach(b => b.disabled = true);
        }

        document.getElementById('nextQuestionBtn').addEventListener('click', () => {
            currentQuizIndex++;
            showQuizQuestion();
        });

        document.getElementById('startTimedQuizBtn').addEventListener('click', () => {
            if (quizQuestions.length === 0) return alert('ولّد الأسئلة أولاً');
            timedSeconds = 60;
            currentQuizIndex = 0;
            quizScore = 0;
            document.getElementById('quizScore').textContent = '0';
            document.getElementById('quizTotal').textContent = quizQuestions.length;
            document.getElementById('timerDisplay').textContent = `⏳ الوقت: ${timedSeconds}`;
            showQuizQuestion();
            clearInterval(timedQuizInterval);
            timedQuizInterval = setInterval(() => {
                timedSeconds--;
                document.getElementById('timerDisplay').textContent = `⏳ الوقت: ${timedSeconds}`;
                if (timedSeconds <= 0) {
                    clearInterval(timedQuizInterval);
                    alert('انتهى الوقت! عدد الإجابات الصحيحة: ' + quizScore);
                    document.getElementById('quizQuestion').textContent = 'انتهى تحدي الوقت';
                    document.getElementById('quizOptions').innerHTML = '';
                    document.getElementById('nextQuestionBtn').style.display = 'none';
                }
            }, 1000);
        });

        // ★★★ تنبيه عند فتح الموقع على HTTP بدلاً من HTTPS (اختياري) ★★★
        if (window.location.protocol !== 'https:') {
            console.warn('يُفضل تشغيل الموقع على HTTPS لحماية البيانات.');
        }
    </script>
</body>
</html>
