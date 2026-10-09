# Kda-great
This is my first depositres.
<!DOCTYPE html>  
<html lang="hi">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Anmesh Studies - Math, English, Reasoning & GS</title>  
    <!-- Tailwind CSS for UI -->  
    <script src="https://cdn.tailwindcss.com"></script>  
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">  
    <link href="https://fonts.googleapis.com/css2?family=Merriweather:ital,wght@0,300;0,400;0,700;1,300&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">  
    <style>  
        body { font-family: 'Poppins', sans-serif; }  
        .editorial-font { font-family: 'Merriweather', serif; }  
        .view-section { display: none; }  
        .view-section.active { display: block; }  
    </style>  
</head>  
<body class="bg-slate-100 text-slate-800 antialiased min-h-screen flex flex-col">  

<!-- Header / Top Bar -->  
<header class="bg-slate-900 text-white shadow-md sticky top-0 z-30 transition-all duration-300">  
    <div class="max-w-7xl mx-auto px-4 py-3 flex justify-between items-center">  
          
        <!-- App Branding -->  
        <div id="app-branding" class="flex items-center space-x-3 cursor-pointer" onclick="showHomeView()">  
            <div class="bg-gradient-to-r from-amber-500 via-white to-emerald-600 p-2 rounded-lg flex items-center justify-center shadow">  
                <i class="fa-solid fa-graduation-cap text-slate-900 text-xl"></i>  
            </div>  
            <div>  
                <h1 class="font-bold text-lg leading-tight tracking-wide">ANMESH STUDIES</h1>  
                <p id="header-subtitle" class="text-xs text-slate-400">Math, English, Reasoning & GS</p>  
            </div>  
        </div>  

        <!-- Actions & Exit App Button -->  
        <div class="flex items-center space-x-3 ml-auto">  
            <button id="profile-btn" onclick="confirmExitApp()" class="bg-slate-800 hover:bg-slate-700 text-slate-300 px-3 py-2 rounded-lg text-xs font-medium border border-slate-700 flex items-center space-x-2 transition">  
                <i class="fa-solid fa-right-from-bracket text-red-400 text-base"></i>  
                <span class="hidden sm:inline">Exit App</span>  
            </button>  

            <!-- Timer & Question Palette (Visible ONLY during active test) -->  
            <div id="test-timer-container" class="hidden items-center space-x-2 sm:space-x-3">  
                <button onclick="confirmExitTest()" class="bg-slate-800 hover:bg-slate-700 text-slate-300 font-medium px-2.5 sm:px-3 py-2 rounded-lg transition text-xs flex items-center space-x-1 border border-slate-700">  
                    <i class="fa-solid fa-arrow-left"></i>  
                    <span class="hidden sm:inline">Exit</span>  
                </button>  
                <!-- Question Palette Button -->  
                <button onclick="openQuestionPalette()" class="bg-blue-600 hover:bg-blue-700 text-white font-medium px-2.5 sm:px-3 py-2 rounded-lg transition text-xs flex items-center space-x-1 shadow" title="Question Palette">  
                    <i class="fa-solid fa-table-cells"></i>  
                    <span class="hidden md:inline">Questions</span>  
                </button>  
                <div id="timer-wrapper" class="bg-slate-800 px-2.5 sm:px-4 py-2 rounded-lg border border-slate-700 flex items-center space-x-1 sm:space-x-2">  
                    <i class="fa-regular fa-clock text-amber-400 text-base sm:text-lg"></i>  
                    <span id="timer-display" class="font-mono text-base sm:text-xl font-bold text-amber-400">00:00</span>  
                </div>  
                <button onclick="confirmSubmitModal()" class="bg-emerald-600 hover:bg-emerald-700 text-white font-semibold px-3 sm:px-4 py-2 rounded-lg transition text-sm flex items-center space-x-1 shadow">  
                    <i class="fa-solid fa-check"></i>  
                    <span class="hidden sm:inline">Submit</span>  
                </button>  
            </div>  
        </div>  
    </div>  
</header>  

<!-- CONTAINER FOR VIEWS -->  
<div class="flex-1 max-w-7xl w-full mx-auto p-4 flex flex-col">  

    <!-- 1. HOME VIEW -->  
    <div id="home-view" class="view-section active py-6">  
        <div class="text-center mb-8">  
            <h2 class="text-3xl font-extrabold text-slate-900">Welcome to Anmesh Studies</h2>  
            <p class="text-slate-500 mt-2">Aap kis subject ki practice karna chahte hain?</p>  
        </div>  
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6 max-w-5xl mx-auto">  
            <div onclick="openCategory('Math')" class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 hover:border-blue-500 hover:shadow-md cursor-pointer transition flex flex-col items-center text-center">  
                <span class="text-5xl mb-3">📐</span>  
                <h3 class="text-xl font-bold text-slate-900">Math</h3>  
                <p class="text-xs text-slate-500 mt-1">Arithmetic & Advanced</p>  
            </div>  
            <div onclick="openCategory('English')" class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 hover:border-blue-500 hover:shadow-md cursor-pointer transition flex flex-col items-center text-center">  
                <span class="text-5xl mb-3">📚</span>  
                <h3 class="text-xl font-bold text-slate-900">English</h3>  
                <p class="text-xs text-slate-500 mt-1">Vocab, Grammar & Comprehension</p>  
            </div>  
            <div onclick="openCategory('Reasoning')" class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 hover:border-blue-500 hover:shadow-md cursor-pointer transition flex flex-col items-center text-center">  
                <span class="text-5xl mb-3">🧩</span>  
                <h3 class="text-xl font-bold text-slate-900">Reasoning</h3>  
                <p class="text-xs text-slate-500 mt-1">Verbal & Non-Verbal</p>  
            </div>  
            <div onclick="openCategory('GS')" class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 hover:border-blue-500 hover:shadow-md cursor-pointer transition flex flex-col items-center text-center">  
                <span class="text-5xl mb-3">🌍</span>  
                <h3 class="text-xl font-bold text-slate-900">GS</h3>  
                <p class="text-xs text-slate-500 mt-1">History, Polity, Science & GK</p>  
            </div>  
        </div>  
    </div>  

    <!-- 2. SUB-CATEGORY (TOPICS) VIEW -->  
    <div id="subcategory-view" class="view-section py-4">  
        <div class="flex flex-col sm:flex-row justify-between items-center mb-6 gap-4">  
            <button onclick="showHomeView()" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-medium px-4 py-2 rounded-lg text-sm transition flex items-center space-x-2">  
                <i class="fa-solid fa-arrow-left"></i> <span>Back to Home</span>  
            </button>  
            <div class="flex items-center space-x-3">  
                <h2 id="subcategory-header-title" class="text-2xl font-bold text-slate-900">Topics</h2>  
                <button onclick="openTopicModal(currentMainCategory, null)" class="bg-blue-600 hover:bg-blue-700 text-white text-xs font-semibold px-4 py-2.5 rounded-lg shadow transition flex items-center">  
                    <i class="fa-solid fa-plus mr-1.5"></i> Add Chapter  
                </button>  
            </div>  
        </div>  
          
        <div id="subcategory-list" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4 max-w-5xl mx-auto"></div>  
    </div>  

    <!-- 3. CHAPTER HUB VIEW (Notes & Tests Side-by-Side) -->  
    <div id="chapter-hub-view" class="view-section py-4 max-w-6xl mx-auto w-full">  
        <div class="flex flex-col sm:flex-row justify-between items-center mb-6 gap-4">  
            <button onclick="openCategory(currentMainCategory)" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-medium px-4 py-2 rounded-lg text-sm transition flex items-center space-x-2">  
                <i class="fa-solid fa-arrow-left"></i> <span>Back to Chapters</span>  
            </button>  
            <h2 id="chapter-hub-title" class="text-2xl font-bold text-slate-900">Chapter Title</h2>  
        </div>  

        <!-- Side-by-Side Grid for Notes and Tests -->  
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">  
            <!-- Notes Section Column -->  
            <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-200 flex flex-col">  
                <div class="flex justify-between items-center mb-4 pb-3 border-b">  
                    <h3 class="font-bold text-lg text-slate-900 flex items-center">  
                        <i class="fa-solid fa-book-open mr-2 text-blue-600"></i> Chapter Notes  
                    </h3>  
                    <button onclick="openNoteModal(null)" class="bg-blue-600 hover:bg-blue-700 text-white text-xs font-semibold px-3.5 py-2 rounded-lg shadow transition flex items-center">  
                        <i class="fa-solid fa-plus mr-1"></i> Add Note  
                    </button>  
                </div>  
                <div id="notes-list" class="space-y-3 flex-1 overflow-y-auto max-h-[550px] pr-1"></div>  
            </div>  

            <!-- Tests Section Column -->  
            <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-200 flex flex-col">  
                <div class="flex justify-between items-center mb-4 pb-3 border-b">  
                    <h3 class="font-bold text-lg text-slate-900 flex items-center">  
                        <i class="fa-solid fa-file-lines mr-2 text-emerald-600"></i> Tests & Quizzes  
                    </h3>  
                    <button onclick="openTestModal(null)" class="bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-semibold px-3.5 py-2 rounded-lg shadow transition flex items-center">  
                        <i class="fa-solid fa-plus mr-1"></i> Add Test  
                    </button>  
                </div>  
                <div id="test-list" class="space-y-3 flex-1 overflow-y-auto max-h-[550px] pr-1"></div>  
            </div>  
        </div>  
    </div>  

    <!-- 3.1. NOTE READER VIEW (Story Paragraph with Inline Underlined Vocab + Matching Meaning) -->  
    <div id="note-reader-view" class="view-section max-w-3xl w-full mx-auto py-4">  
        <div class="bg-white rounded-2xl shadow-md border border-slate-200 p-6 sm:p-10">  
            <div class="flex justify-between items-center mb-6 pb-4 border-b">  
                <button onclick="openChapterHub(currentSubcategory)" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-medium px-3.5 py-2 rounded-lg text-xs transition flex items-center space-x-2">  
                    <i class="fa-solid fa-arrow-left"></i> <span>Back</span>  
                </button>  
                <div id="note-action-btns" class="flex space-x-2">  
                    <!-- Edit & Delete Note buttons injected dynamically -->  
                </div>  
            </div>  

            <!-- Editorial Newspaper Style Title -->  
            <h2 id="reader-note-title" class="editorial-font text-2xl sm:text-3xl font-bold text-slate-900 mb-6 leading-snug tracking-tight">Note Title</h2>  
              
            <!-- Editorial Story Paragraph Container with Inline Underlined Vocab & Meaning -->  
            <div id="reader-note-content" class="editorial-font text-slate-800 text-base sm:text-lg leading-[2.5rem] bg-white p-2 mb-8 text-justify">  
                Note content goes here...  
            </div>  

            <!-- Detailed Analysis Section with Spaced Lines & Soft Color Matched Highlights -->  
            <div id="reader-meaning-container" class="p-6 sm:p-8 bg-slate-50 border border-slate-200 rounded-2xl shadow-sm">  
                <div class="flex items-center space-x-2 mb-6 text-slate-900 font-bold text-base sm:text-lg border-b pb-3">  
                    <i class="fa-solid fa-book-reader text-blue-600"></i>  
                    <span>Detailed Analysis / विस्तृत स्पष्टीकरण (हिंदी अर्थ / स्टोरी विश्लेषण):</span>  
                </div>  
                <div id="reader-note-analysis" class="editorial-font text-slate-800 text-base sm:text-lg space-y-6 leading-loose"></div>  
            </div>  
        </div>  
    </div>  

    <!-- 4. QUIZ INTERFACE VIEW -->  
    <main id="quiz-interface" class="view-section max-w-3xl w-full mx-auto flex-1 py-4">  
        <div class="bg-white rounded-xl shadow-sm border border-slate-200 flex flex-col h-full">  
            <div class="px-6 py-4 border-b border-slate-200 flex justify-between items-center bg-slate-50 rounded-t-xl">  
                <div class="flex items-center space-x-3">  
                    <span id="q-number" class="font-bold text-blue-600 text-lg">Question 1</span>  
                    <span id="quiz-type-badge" class="text-xs font-semibold px-2.5 py-1 rounded-full bg-blue-100 text-blue-800">Mock Test</span>  
                </div>  
                <span class="text-xs font-semibold bg-slate-100 text-slate-700 px-2.5 py-1 rounded-full">+2.0 / -0.5 Marks</span>  
            </div>  

            <div class="p-6 flex-1 overflow-y-auto">  
                <div id="q-phrase" class="text-lg font-medium text-slate-900 mb-6 p-4 bg-slate-50 rounded-lg border-l-4 border-blue-600"></div>  
                <div id="options-container" class="space-y-3"></div>  
            </div>  

            <div class="p-4 border-t border-slate-200 bg-slate-50 rounded-b-xl flex flex-wrap gap-2 justify-between items-center">  
                <div class="flex gap-2">  
                    <button onclick="clearResponse()" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-medium px-3 py-2 rounded-lg text-xs sm:text-sm transition">Clear Answer</button>  
                    <button onclick="toggleMarkForReview()" id="mark-review-btn" class="bg-amber-100 hover:bg-amber-200 text-amber-800 font-semibold px-3 py-2 rounded-lg text-xs sm:text-sm transition border border-amber-300">Mark for Review</button>  
                </div>  
                <div class="flex gap-2">  
                    <button onclick="prevQuestion()" class="bg-slate-700 hover:bg-slate-800 text-white font-medium px-3 sm:px-4 py-2 rounded-lg text-xs sm:text-sm transition"><i class="fa-solid fa-chevron-left"></i> Prev</button>  
                    <button onclick="saveAndNext()" class="bg-blue-600 hover:bg-blue-700 text-white font-semibold px-4 sm:px-5 py-2 rounded-lg text-xs sm:text-sm transition shadow">Next <i class="fa-solid fa-chevron-right ml-1"></i></button>  
                </div>  
            </div>  
        </div>  
    </main>  

    <!-- 5. ANALYSIS VIEW -->  
    <div id="analysis-screen" class="view-section max-w-5xl w-full mx-auto py-4">  
        <div class="bg-white rounded-xl shadow-md border p-6 mb-6">  
            <div class="flex flex-col md:flex-row justify-between items-center border-b pb-6 mb-6">  
                <div>  
                    <h2 class="text-2xl font-bold text-slate-900">Test Result & Analysis</h2>  
                </div>  
                <div class="flex space-x-3 mt-4 md:mt-0">  
                    <button onclick="openChapterHub(currentSubcategory)" class="bg-slate-200 hover:bg-slate-300 text-slate-700 px-4 py-2.5 rounded-lg text-sm font-semibold transition"><i class="fa-solid fa-arrow-left"></i> Back to Chapter Hub</button>  
                </div>  
            </div>  

            <div class="grid grid-cols-2 md:grid-cols-5 gap-4 text-center">  
                <div class="bg-blue-50 p-4 rounded-xl border border-blue-100">  
                    <p class="text-xs text-blue-600 font-semibold uppercase">Score</p>  
                    <p id="res-ssc-score" class="text-2xl font-extrabold text-blue-800">0 / 0</p>  
                </div>  
                <div class="bg-emerald-50 p-4 rounded-xl border border-emerald-100">  
                    <p class="text-xs text-emerald-600 font-semibold uppercase">Correct</p>  
                    <p id="res-correct" class="text-2xl font-extrabold text-emerald-700">0</p>  
                </div>  
                <div class="bg-red-50 p-4 rounded-xl border border-red-100">  
                    <p class="text-xs text-red-600 font-semibold uppercase">Incorrect</p>  
                    <p id="res-incorrect" class="text-2xl font-extrabold text-red-700">0</p>  
                </div>  
                <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">  
                    <p class="text-xs text-slate-500 font-semibold uppercase">Unattempted</p>  
                    <p id="res-unattempted" class="text-2xl font-extrabold text-slate-700">0</p>  
                </div>  
                <div class="bg-amber-50 p-4 rounded-xl border border-amber-100">  
                    <p class="text-xs text-amber-600 font-semibold uppercase">Accuracy</p>  
                    <p id="res-accuracy" class="text-2xl font-extrabold text-amber-700">0%</p>  
                </div>  
            </div>  
        </div>  
          
        <h3 class="text-xl font-bold text-slate-800 mb-4">Detailed Solutions & Meaning</h3>  
        <div id="solutions-container" class="space-y-6"></div>  
    </div>  

</div>  

<!-- MODALS -->  

<!-- Question Palette Modal -->  
<div id="question-palette-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm hidden items-center justify-center z-50 p-4">  
    <div class="bg-white rounded-xl shadow-xl max-w-lg w-full p-6">  
        <div class="flex justify-between items-center mb-4 border-b pb-3">  
            <h3 class="text-lg font-bold text-slate-900">Question Palette</h3>  
            <button onclick="closeQuestionPalette()" class="text-slate-400 hover:text-slate-600 text-xl font-bold">&times;</button>  
        </div>  
        <div class="mb-4 grid grid-cols-2 sm:grid-cols-4 gap-2 text-xs font-semibold text-slate-700">  
            <div class="flex items-center space-x-1.5"><span class="w-3.5 h-3.5 rounded bg-blue-600 inline-block"></span><span>Not Attempt (Blue)</span></div>  
            <div class="flex items-center space-x-1.5"><span class="w-3.5 h-3.5 rounded bg-emerald-500 inline-block"></span><span>Attempt (Green)</span></div>  
            <div class="flex items-center space-x-1.5"><span class="w-3.5 h-3.5 rounded bg-red-500 inline-block"></span><span>Mark Review (Red)</span></div>  
            <div class="flex items-center space-x-1.5"><span class="w-3.5 h-3.5 rounded bg-amber-400 inline-block"></span><span>Unmark/Review (Yellow)</span></div>  
        </div>  
        <div id="palette-grid" class="grid grid-cols-5 sm:grid-cols-6 gap-2 max-h-60 overflow-y-auto p-1"></div>  
        <div class="flex justify-end mt-5">  
            <button onclick="closeQuestionPalette()" class="px-4 py-2 bg-slate-200 hover:bg-slate-300 text-slate-700 font-semibold rounded-lg text-sm">Close</button>  
        </div>  
    </div>  
</div>  

<!-- Custom Exit App Modal -->  
<div id="exit-app-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm hidden items-center justify-center z-50 p-4">  
    <div class="bg-white rounded-xl shadow-xl max-w-sm w-full p-6 text-center">  
        <div class="mx-auto flex items-center justify-center h-12 w-12 rounded-full bg-red-100 mb-4">  
            <i class="fa-solid fa-right-from-bracket text-red-600 text-xl"></i>  
        </div>  
        <h3 class="text-xl font-bold text-slate-900 mb-2">Exit App</h3>  
        <p class="text-sm text-slate-600 mb-6">Kya aap Anmesh Studies App se bahar nikalna chahte hain?</p>  
        <div class="flex justify-center space-x-3">  
            <button onclick="closeExitAppModal()" class="px-5 py-2.5 border border-slate-300 rounded-lg text-sm hover:bg-slate-50 font-medium text-slate-700 w-1/2 transition">Cancel</button>  
            <button onclick="executeExitApp()" class="px-5 py-2.5 bg-red-600 text-white font-semibold rounded-lg text-sm hover:bg-red-700 shadow w-1/2 transition">Exit</button>  
        </div>  
    </div>  
</div>  

<!-- Add/Edit Topic Modal -->  
<div id="topic-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm hidden items-center justify-center z-50 p-4">  
    <div class="bg-white rounded-xl shadow-xl max-w-sm w-full p-6">  
        <h3 id="topic-modal-title" class="text-xl font-bold text-slate-900 mb-4">Add New Chapter/Topic</h3>  
        <div class="space-y-4">  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Chapter Name</label>  
                <input type="text" id="topic-name-input" class="w-full p-2.5 border rounded-lg text-sm outline-none focus:ring-2 focus:ring-blue-500" placeholder="E.g. Algebra, Noun...">  
            </div>  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Chapter Icon/Emoji</label>  
                <input type="text" id="topic-icon-input" class="w-full p-2.5 border rounded-lg text-sm outline-none focus:ring-2 focus:ring-blue-500" placeholder="E.g. 📝, 📊, 📘...">  
            </div>  
        </div>  
        <div class="flex justify-end space-x-3 mt-6">  
            <button onclick="closeTopicModal()" class="px-4 py-2 border rounded-lg text-sm hover:bg-slate-100 font-medium">Cancel</button>  
            <button onclick="saveTopic()" class="px-5 py-2 bg-blue-600 text-white font-semibold rounded-lg text-sm hover:bg-blue-700">Save Chapter</button>  
        </div>  
    </div>  
</div>  

<!-- Add/Edit Note Modal -->  
<div id="note-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm hidden items-center justify-center z-50 p-4">  
    <div class="bg-white rounded-xl shadow-xl max-w-xl w-full p-6 max-h-[90vh] overflow-y-auto">  
        <h3 id="note-modal-title" class="text-xl font-bold text-slate-900 mb-4">Add New Note</h3>  
        <div class="space-y-4">  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Note Title (Hindi / English)</label>  
                <input type="text" id="note-title-input" class="w-full p-2.5 border rounded-lg text-sm outline-none focus:ring-2 focus:ring-blue-500" placeholder="E.g. EDITORIAL - The Hindu">  
            </div>  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Note Content / Story Paragraph</label>  
                <textarea id="note-content-input" class="w-full h-28 p-3 border rounded-lg text-xs sm:text-sm outline-none focus:ring-2 focus:ring-blue-500" placeholder="Yahan main content ya paragraph likhein..."></textarea>  
            </div>  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Vocabulary JSON Array ([{"word": "...", "meaning": "..."}])</label>  
                <textarea id="note-vocab-input" class="w-full h-24 p-3 border rounded-lg font-mono text-xs outline-none focus:ring-2 focus:ring-blue-500" placeholder='[{"word": "Monetary Policy", "meaning": "मौद्रिक नीति"}]'></textarea>  
            </div>  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Detailed Analysis / Sentences JSON Array ([{"english": "...", "hindi": "..."}])</label>  
                <textarea id="note-analysis-input" class="w-full h-28 p-3 border rounded-lg text-xs sm:text-sm outline-none focus:ring-2 focus:ring-blue-500" placeholder='[{"english": "Sentence...", "hindi": "वाक्य..."}]'></textarea>  
            </div>  
        </div>  
        <div class="flex justify-end space-x-3 mt-5">  
            <button onclick="closeNoteModal()" class="px-4 py-2 border rounded-lg text-sm hover:bg-slate-100 font-medium">Cancel</button>  
            <button onclick="saveNote()" class="px-5 py-2 bg-blue-600 text-white font-semibold rounded-lg text-sm hover:bg-blue-700 shadow">Save Note</button>  
        </div>  
    </div>  
</div>  

<!-- Add/Edit Test Modal (JSON Only) -->  
<div id="add-test-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm hidden items-center justify-center z-50 p-4">  
    <div class="bg-white rounded-xl shadow-xl max-w-xl w-full p-6">  
        <h3 id="test-modal-title" class="text-xl font-bold text-slate-900 mb-4">Add New Test / Quiz</h3>  
          
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-4">  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Test Title</label>  
                <input type="text" id="test-title-input" class="w-full p-2.5 border rounded-lg text-sm outline-none focus:ring-2 focus:ring-blue-500" placeholder="E.g. Percentage Quiz 1">  
            </div>  
            <div>  
                <label class="block text-xs font-semibold text-slate-600 mb-1">Test Type</label>  
                <select id="test-type-input" class="w-full p-2.5 border rounded-lg text-sm outline-none focus:ring-2 focus:ring-blue-500 bg-white">  
                    <option value="mock">Mock Test (Total Time = Qs × 36s)</option>  
                    <option value="practice">Practice Quiz (No timer)</option>  
                </select>  
            </div>  
        </div>  

        <div class="mb-4">  
            <label class="block text-xs font-semibold text-slate-600 mb-1">Questions JSON Array</label>  
            <textarea id="custom-test-code-json" class="w-full h-40 p-3 border rounded-lg font-mono text-xs outline-none focus:ring-2 focus:ring-blue-500" placeholder='[{"q": "Question?", "options": ["A","B","C","D"], "answer": 0, "hindi": "Hindi Meaning"}]'></textarea>  
        </div>  

        <div class="flex justify-end space-x-3 mt-5">  
            <button onclick="closeAddModal()" class="px-4 py-2 border rounded-lg text-sm hover:bg-slate-100 font-medium">Cancel</button>  
            <button onclick="saveAndRunCustomTest()" class="px-5 py-2 bg-emerald-600 text-white font-semibold rounded-lg text-sm hover:bg-emerald-700 shadow">Save Test</button>  
        </div>  
    </div>  
</div>  

<!-- Submit Modal -->  
<div id="submit-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm hidden items-center justify-center z-50 p-4">  
    <div class="bg-white rounded-xl shadow-xl max-w-md w-full p-6">  
        <h3 class="text-xl font-bold text-slate-900 mb-2">Submit Test / Quiz</h3>  
        <p class="text-sm text-slate-600 mb-4">Kya aap test submit karna chahte hain?</p>  
        <div class="bg-slate-50 p-4 rounded-lg space-y-2 text-sm border mb-6">  
            <div class="flex justify-between"><span>Total Questions:</span> <span id="modal-total" class="font-bold">0</span></div>  
            <div class="flex justify-between text-emerald-600"><span>Answered:</span> <span id="modal-ans" class="font-bold">0</span></div>  
            <div class="flex justify-between text-red-500"><span>Not Answered:</span> <span id="modal-not-ans" class="font-bold">0</span></div>  
        </div>  
        <div class="flex justify-end space-x-3">  
            <button onclick="closeSubmitModal()" class="px-4 py-2 border rounded-lg text-sm hover:bg-slate-100">Cancel</button>  
            <button onclick="finalSubmitTest()" class="px-5 py-2 bg-emerald-600 text-white font-semibold rounded-lg text-sm hover:bg-emerald-700">Submit Test</button>  
        </div>  
    </div>  
</div>  

<script>  
    const DELETE_PASSWORD = "ANMES"; // Security Password for Deletion  
    const TOPICS_STORAGE_KEY = 'anmesh_app_topics_v35';  
    const TESTS_STORAGE_KEY = 'anmesh_topic_tests_v35';  
    const NOTES_STORAGE_KEY = 'anmesh_topic_notes_v35';  

    const defaultAppData = {  
        "Math": [{ name: "Percentage", icon: "📊" }],  
        "English": [{ name: "Vocabulary", icon: "📚" }],  
        "Reasoning": [{ name: "Coding-Decoding", icon: "🔤" }],  
        "GS": [{ name: "Indian History", icon: "🏛️" }]  
    };  

    const sampleDefaultQuestions = [  
        { q: "What is the synonym of 'Abundant'?", options: ["Scarce", "Plentiful", "Rare", "Short"], answer: 1, hindi: "Abundant का मतलब होता है 'प्रचुर' (बहुत अधिक मात्रा में)। इसलिए इसका Synonym 'Plentiful' होगा।" },  
        { q: "If 20% of X is 40, find X.", options: ["100", "150", "200", "250"], answer: 2, hindi: "20% of X = 40 <br> (20/100) * X = 40 <br> X = (40 * 100) / 20 = 200." }  
    ];  

    const sampleDefaultNotes = [  
        {   
            title: "Untying the knot in Telangana, one childhood at a time",   
            content: "Despite a steady decline in child marriages in Telangana, the practice continues. Poverty, social pressures and family circumstances continue to place girls at risk of being married early, with consequences for their education, health and independence. Abinay Deshpande examines the persisting issue and its impact on young lives",  
            vocab: [
                { word: "steady decline", meaning: "लगातार गिरावट" },
                { word: "circumstances", meaning: "परिस्थितियां" },
                { word: "persisting issue", meaning: "बनी हुई समस्या" }
            ],
            analysis: JSON.stringify([
                { english: "Despite a steady decline in child marriages in Telangana, the practice continues.", hindi: "तेलंगाना में बाल विवाहों में लगातार गिरावट के बावजूद, यह प्रथा जारी है।" },
                { english: "Poverty, social pressures and family circumstances continue to place girls at risk of being married early, with consequences for their education, health and independence.", hindi: "गरीबी, सामाजिक दबाव और पारिवारिक परिस्थितियां लड़कियों को कम उम्र में शादी के जोखिम में डाल रही हैं, जिसके उनके शिक्षा, स्वास्थ्य और स्वतंत्रता पर गंभीर परिणाम होते हैं।" },
                { english: "Abinay Deshpande examines the persisting issue and its impact on young lives.", hindi: "अभिनै देशपांडे इस लगातार बनी हुई समस्या और युवा जीवन पर इसके प्रभाव का परीक्षण करते हैं।" }
            ], null, 2) 
        }  
    ];  

    let appTopicsData = {};  
    let topicTests = {};  
    let topicNotes = {};  
      
    let currentMainCategory = '';  
    let currentSubcategory = '';  
    let activeViewId = 'home-view';  
      
    // Quiz State  
    let activeQuestionsList = [];  
    let currentIndex = 0;  
    let timeRemaining = 0;  
    let timerInterval = null;  
    let userResponses = [];  
    let questionStates = [];  
    let activeTestType = 'mock';  

    // Student-Friendly Pleasant Pastel Colors for Highlights & Underlines
    const vocabColors = [
        { text: 'text-indigo-700', deco: 'decoration-indigo-400', bg: 'bg-indigo-50/60' },
        { text: 'text-emerald-700', deco: 'decoration-emerald-400', bg: 'bg-emerald-50/60' },
        { text: 'text-amber-700', deco: 'decoration-amber-400', bg: 'bg-amber-50/60' },
        { text: 'text-purple-700', deco: 'decoration-purple-400', bg: 'bg-purple-50/60' },
        { text: 'text-rose-700', deco: 'decoration-rose-400', bg: 'bg-rose-50/60' }
    ];

    // Automatic Data Migration to Prevent Any Data Loss Across Updates
    function migrateOldDataStorage() {
        const oldTopicKeys = ['anmesh_app_topics_v34', 'anmesh_app_topics_v33', 'anmesh_app_topics_v32', 'anmesh_app_topics_v31', 'anmesh_app_topics_v30', 'anmesh_app_topics_v3'];
        const oldTestKeys = ['anmesh_topic_tests_v34', 'anmesh_topic_tests_v33', 'anmesh_topic_tests_v32', 'anmesh_topic_tests_v31', 'anmesh_topic_tests_v30', 'anmesh_topic_tests_v3'];
        const oldNoteKeys = ['anmesh_topic_notes_v34', 'anmesh_topic_notes_v33', 'anmesh_topic_notes_v32', 'anmesh_topic_notes_v31', 'anmesh_topic_notes_v30', 'anmesh_topic_notes_v3'];

        if (!localStorage.getItem(TOPICS_STORAGE_KEY)) {
            for (let k of oldTopicKeys) {
                if (localStorage.getItem(k)) {
                    localStorage.setItem(TOPICS_STORAGE_KEY, localStorage.getItem(k));
                    break;
                }
            }
        }
        if (!localStorage.getItem(TESTS_STORAGE_KEY)) {
            for (let k of oldTestKeys) {
                if (localStorage.getItem(k)) {
                    localStorage.setItem(TESTS_STORAGE_KEY, localStorage.getItem(k));
                    break;
                }
            }
        }
        if (!localStorage.getItem(NOTES_STORAGE_KEY)) {
            for (let k of oldNoteKeys) {
                if (localStorage.getItem(k)) {
                    localStorage.setItem(NOTES_STORAGE_KEY, localStorage.getItem(k));
                    break;
                }
            }
        }
    }

    // App Initialization  
    function loadAppDataFromStorage() {  
        migrateOldDataStorage();

        const storedTopics = localStorage.getItem(TOPICS_STORAGE_KEY);  
        const storedTests = localStorage.getItem(TESTS_STORAGE_KEY);  
        const storedNotes = localStorage.getItem(NOTES_STORAGE_KEY);  
          
        appTopicsData = storedTopics ? JSON.parse(storedTopics) : JSON.parse(JSON.stringify(defaultAppData));  
          
        if (storedTests) {  
            topicTests = JSON.parse(storedTests);  
        } else {  
            topicTests = {};  
            Object.keys(appTopicsData).forEach(cat => {  
                appTopicsData[cat].forEach(t => {  
                    topicTests[t.name] = [  
                        { title: "Mock Test 1", type: "mock", questions: JSON.parse(JSON.stringify(sampleDefaultQuestions)) },  
                        { title: "Practice Quiz 1", type: "practice", questions: JSON.parse(JSON.stringify(sampleDefaultQuestions)) }  
                    ];  
                });  
            });  
            saveTestsToStorage();  
        }  

        if (storedNotes) {  
            topicNotes = JSON.parse(storedNotes);  
        } else {  
            topicNotes = {};  
            Object.keys(appTopicsData).forEach(cat => {  
                appTopicsData[cat].forEach(t => {  
                    topicNotes[t.name] = JSON.parse(JSON.stringify(sampleDefaultNotes));  
                });  
            });  
            saveNotesToStorage();  
        }  

        if (!storedTopics) saveTopicsToStorage();  
    }  
      
    function saveTopicsToStorage() { localStorage.setItem(TOPICS_STORAGE_KEY, JSON.stringify(appTopicsData)); }  
    function saveTestsToStorage() { localStorage.setItem(TESTS_STORAGE_KEY, JSON.stringify(topicTests)); }  
    function saveNotesToStorage() { localStorage.setItem(NOTES_STORAGE_KEY, JSON.stringify(topicNotes)); }  

    // Security Password Verification Function  
    function verifySecurityPassword() {  
        let inputPwd = prompt("Delete karne ke liye Security Password enter karein:");  
        if (inputPwd === null) return false;  
        if (inputPwd.trim() === DELETE_PASSWORD) {  
            return true;  
        } else {  
            alert("Galat Password! Delete cancel kar diya gaya hai.");  
            return false;  
        }  
    }  

    // View Logic  
    function showView(viewId) {  
        activeViewId = viewId;  
        document.querySelectorAll('.view-section').forEach(v => v.classList.remove('active'));  
        document.getElementById(viewId).classList.add('active');  
          
        const branding = document.getElementById('app-branding');  
        const profileBtn = document.getElementById('profile-btn');  
        const timerBox = document.getElementById('test-timer-container');  

        if (viewId === 'quiz-interface') {  
            branding.style.display = 'none';  
            profileBtn.style.display = 'none';  
            timerBox.classList.remove('hidden');  
            timerBox.classList.add('flex');  
        } else {  
            branding.style.display = 'flex';  
            profileBtn.style.display = 'flex';  
            timerBox.classList.add('hidden');  
            timerBox.classList.remove('flex');  
        }  
    }  

    function showHomeView() {  
        if (timerInterval) clearInterval(timerInterval);  
        showView('home-view');  
    }  

    function confirmExitApp() {  
        document.getElementById('exit-app-modal').classList.replace('hidden', 'flex');  
    }  

    function closeExitAppModal() {  
        document.getElementById('exit-app-modal').classList.replace('flex', 'hidden');  
    }  

    function executeExitApp() {  
        closeExitAppModal();  
        if (typeof Android !== "undefined" && typeof Android.exitApp === "function") {  
            Android.exitApp();  
        } else {  
            window.close();  
            alert("Aap home page par hain. Tab/Browser close karke exit kar sakte hain.");  
        }  
    }  

    window.addEventListener('popstate', function (e) {  
        if (activeViewId === 'home-view') {  
            confirmExitApp();  
        } else if (activeViewId === 'quiz-interface') {  
            confirmExitTest();  
        } else if (activeViewId === 'note-reader-view') {  
            openChapterHub(currentSubcategory);  
        } else if (activeViewId === 'chapter-hub-view') {  
            openCategory(currentMainCategory);  
        } else {  
            showHomeView();  
        }  
        history.pushState(null, null, location.href);  
    });  

    history.pushState(null, null, location.href);  

    // ================= TOPIC/CHAPTER LOGIC =================  
    let currentEditingTopicIndex = null;  

    function openCategory(cat) {  
        currentMainCategory = cat;  
        document.getElementById('subcategory-header-title').innerText = `${cat} Chapters`;  
        const list = document.getElementById('subcategory-list');  
        list.innerHTML = '';  
          
        (appTopicsData[cat] || []).forEach((topic, idx) => {  
            const card = document.createElement('div');  
            card.className = 'relative bg-white p-6 rounded-xl shadow-sm border border-slate-200 hover:border-blue-500 hover:shadow-md transition flex flex-col items-center text-center';  
              
            card.innerHTML = `  
                <div class="absolute top-2 right-2 flex space-x-1 z-10">  
                    <button class="edit-btn text-blue-500 hover:bg-blue-50 p-1.5 rounded" title="Edit Chapter"><i class="fa-solid fa-pen text-sm"></i></button>  
                    <button class="delete-btn text-red-500 hover:bg-red-50 p-1.5 rounded" title="Delete Chapter"><i class="fa-solid fa-trash text-sm"></i></button>  
                </div>  
                <div class="w-full cursor-pointer pt-4">  
                    <span class="text-5xl mb-3 block">${topic.icon}</span>  
                    <h4 class="font-bold text-lg text-slate-800">${topic.name}</h4>  
                </div>  
            `;  
              
            card.querySelector('.edit-btn').onclick = (e) => { e.stopPropagation(); openTopicModal(cat, idx); };  
            card.querySelector('.delete-btn').onclick = (e) => { e.stopPropagation(); deleteTopic(cat, idx); };  
            card.querySelector('.cursor-pointer').onclick = () => openChapterHub(topic.name);  
              
            list.appendChild(card);  
        });  

        const addTopicCard = document.createElement('div');  
        addTopicCard.className = 'bg-blue-50 border-2 border-dashed border-blue-300 p-6 rounded-xl cursor-pointer hover:bg-blue-100 transition text-center flex flex-col items-center justify-center text-blue-600 min-h-[160px]';  
        addTopicCard.innerHTML = `<span class="text-4xl font-bold mb-2">+</span><h4 class="font-bold text-lg">Add Chapter</h4>`;  
        addTopicCard.onclick = () => openTopicModal(cat, null);  
        list.appendChild(addTopicCard);  

        showView('subcategory-view');  
    }  

    function openTopicModal(cat, index = null) {  
        currentEditingTopicIndex = index;  
        document.getElementById('topic-modal-title').innerText = index !== null ? "Edit Chapter" : "Add New Chapter";  
          
        if(index !== null) {  
            let t = appTopicsData[cat][index];  
            document.getElementById('topic-name-input').value = t.name;  
            document.getElementById('topic-icon-input').value = t.icon;  
        } else {  
            document.getElementById('topic-name-input').value = '';  
            document.getElementById('topic-icon-input').value = '📝';  
        }  
        document.getElementById('topic-modal').classList.replace('hidden', 'flex');  
    }  

    function closeTopicModal() {  
        document.getElementById('topic-modal').classList.replace('flex', 'hidden');  
    }  

    function saveTopic() {  
        let name = document.getElementById('topic-name-input').value.trim();  
        let icon = document.getElementById('topic-icon-input').value.trim() || '📝';  
          
        if(!name) return alert("Chapter ka naam daalna zaroori hai!");  
          
        if(currentEditingTopicIndex !== null) {  
            let oldName = appTopicsData[currentMainCategory][currentEditingTopicIndex].name;  
            appTopicsData[currentMainCategory][currentEditingTopicIndex].name = name;  
            appTopicsData[currentMainCategory][currentEditingTopicIndex].icon = icon;  
              
            if(oldName !== name) {  
                topicTests[name] = topicTests[oldName] || [];  
                delete topicTests[oldName];  
                topicNotes[name] = topicNotes[oldName] || [];  
                delete topicNotes[oldName];  
            }  
        } else {  
            if (appTopicsData[currentMainCategory].some(t => t.name.toLowerCase() === name.toLowerCase())) {  
                return alert("Ye Chapter pehle se maujud hai!");  
            }  
            appTopicsData[currentMainCategory].push({ name, icon });  
            topicTests[name] = [];   
            topicNotes[name] = [];  
        }  
          
        saveTopicsToStorage();  
        saveTestsToStorage();  
        saveNotesToStorage();  
        closeTopicModal();  
        openCategory(currentMainCategory);   
    }  

    function deleteTopic(cat, index) {  
        let name = appTopicsData[cat][index].name;  
        if (!verifySecurityPassword()) return;  

        if(confirm(`Kya aap sach me "${name}" aur iske sabhi notes & tests delete karna chahte hain?`)) {  
            appTopicsData[cat].splice(index, 1);  
            delete topicTests[name];  
            delete topicNotes[name];  
            saveTopicsToStorage();  
            saveTestsToStorage();  
            saveNotesToStorage();  
            openCategory(cat);  
        }  
    }  

    // ================= CHAPTER HUB (NOTES & TESTS SIDE-BY-SIDE) =================  
    function openChapterHub(topicName) {  
        currentSubcategory = topicName;  
        document.getElementById('chapter-hub-title').innerText = topicName;  
        renderNotesList();  
        renderTestsList();  
        showView('chapter-hub-view');  
    }  

    // ================= NOTES LOGIC =================  
    let currentEditingNoteIndex = null;  

    function renderNotesList() {  
        const notesListEl = document.getElementById('notes-list');  
        notesListEl.innerHTML = '';  

        const notes = topicNotes[currentSubcategory] || [];  
        if (notes.length === 0) {  
            notesListEl.innerHTML = `<div class="text-center py-6 text-slate-400 text-xs">Koi notes nahi hain. 'Add Note' par click karke jodein.</div>`;  
            return;  
        }  

        notes.forEach((note, idx) => {  
            const card = document.createElement('div');  
            card.className = 'bg-slate-50 p-4 rounded-xl border border-slate-200 hover:border-blue-400 transition flex justify-between items-center cursor-pointer';  
            card.onclick = () => openNoteReader(idx);  

            card.innerHTML = `  
                <div class="flex-1 pr-3">  
                    <h4 class="font-bold text-slate-800 text-sm sm:text-base">${note.title}</h4>  
                    <p class="text-[11px] text-slate-400 mt-0.5"><i class="fa-solid fa-book-open mr-1"></i> Click to read note page</p>  
                </div>  
                <div class="flex space-x-1" onclick="event.stopPropagation()">  
                    <button onclick="openNoteModal(${idx})" class="text-blue-500 hover:bg-blue-100 p-2 rounded transition" title="Edit"><i class="fa-solid fa-pen text-xs"></i></button>  
                    <button onclick="deleteNote(${idx})" class="text-red-500 hover:bg-red-100 p-2 rounded transition" title="Delete"><i class="fa-solid fa-trash text-xs"></i></button>  
                </div>  
            `;  
            notesListEl.appendChild(card);  
        });  
    }  

    function openNoteModal(index = null) {  
        currentEditingNoteIndex = index;  
        document.getElementById('note-modal-title').innerText = index !== null ? "Edit Note" : "Add New Note";  

        if (index !== null) {  
            let note = topicNotes[currentSubcategory][index];  
            document.getElementById('note-title-input').value = note.title;  
            document.getElementById('note-content-input').value = note.content;  
            document.getElementById('note-vocab-input').value = note.vocab ? JSON.stringify(note.vocab, null, 2) : '';  
            document.getElementById('note-analysis-input').value = note.analysis || '';  
        } else {  
            document.getElementById('note-title-input').value = '';  
            document.getElementById('note-content-input').value = '';  
            document.getElementById('note-vocab-input').value = '';  
            document.getElementById('note-analysis-input').value = '';  
        }  
        document.getElementById('note-modal').classList.replace('hidden', 'flex');  
    }  

    function closeNoteModal() {  
        document.getElementById('note-modal').classList.replace('flex', 'hidden');  
    }  

    function saveNote() {  
        let title = document.getElementById('note-title-input').value.trim();  
        let content = document.getElementById('note-content-input').value.trim();  
        let vocabStr = document.getElementById('note-vocab-input').value.trim();  
        let analysis = document.getElementById('note-analysis-input').value.trim();  

        if (!title || !content) return alert("Note Title aur Content dono bharna anivarya hai!");  

        let vocab = [];  
        if (vocabStr) {  
            try {  
                vocab = JSON.parse(vocabStr);  
                if (!Array.isArray(vocab)) throw new Error("Format Array hona chahiye");  
            } catch(e) {  
                return alert("Vocabulary JSON Error: " + e.message);  
            }  
        }  

        if (!topicNotes[currentSubcategory]) topicNotes[currentSubcategory] = [];  

        if (currentEditingNoteIndex !== null) {  
            topicNotes[currentSubcategory][currentEditingNoteIndex].title = title;  
            topicNotes[currentSubcategory][currentEditingNoteIndex].content = content;  
            topicNotes[currentSubcategory][currentEditingNoteIndex].vocab = vocab;  
            topicNotes[currentSubcategory][currentEditingNoteIndex].analysis = analysis;  
        } else {  
            topicNotes[currentSubcategory].push({ title, content, vocab, analysis });  
        }  

        saveNotesToStorage();  
        closeNoteModal();  
        renderNotesList();  
    }  

    function deleteNote(idx) {  
        if (!verifySecurityPassword()) return;  
        if (confirm("Kya aap sach me ye note delete karna chahte hain?")) {  
            topicNotes[currentSubcategory].splice(idx, 1);  
            saveNotesToStorage();  
            renderNotesList();  
        }  
    }  

    function openNoteReader(idx) {  
        const note = topicNotes[currentSubcategory][idx];  
        document.getElementById('reader-note-title').innerText = note.title;  

        // 1. Story Paragraph Content with Inline Underlined Vocab and Hindi Meaning right inside the paragraph!
        let processedContent = note.content || '';  
        if (note.vocab && Array.isArray(note.vocab) && note.vocab.length > 0) {  
            let sortedVocab = [...note.vocab].sort((a, b) => b.word.length - a.word.length);  
            sortedVocab.forEach((v, vIdx) => {  
                if (v.word && v.word.trim() !== '') {  
                    let col = vocabColors[vIdx % vocabColors.length];  
                    let escapedWord = v.word.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');  
                    let regex = new RegExp(`(${escapedWord})`, 'gi');  
                    processedContent = processedContent.replace(regex, `<span class="inline-flex flex-col items-center mx-1 my-1 px-2.5 py-0.5 ${col.bg} rounded border border-slate-200 align-middle"><span class="${col.text} font-bold underline ${col.deco} decoration-2">${v.word}</span><span class="${col.text} text-[11px] font-semibold whitespace-nowrap mt-0.5">${v.meaning}</span></span>`);  
                }  
            });  
        }  
        document.getElementById('reader-note-content').innerHTML = processedContent;  

        // 2. Sentence-by-Sentence Analysis Section with Student-Friendly Soft Color Matched Highlights & Underlines  
        const meaningContainer = document.getElementById('reader-meaning-container');  
        const analysisEl = document.getElementById('reader-note-analysis');  
        analysisEl.innerHTML = '';  

        if (note.analysis && note.analysis.trim() !== '') {  
            try {  
                let parsedAnalysis = JSON.parse(note.analysis);  
                if (Array.isArray(parsedAnalysis)) {  
                    let analysisHtml = `<div class="space-y-6">`;  
                    parsedAnalysis.forEach((item, pIdx) => {  
                        let engText = item.english || '';  
                        let hinText = item.hindi || '';  

                        if (note.vocab && Array.isArray(note.vocab)) {  
                            note.vocab.forEach((v, vIdx) => {  
                                let col = vocabColors[vIdx % vocabColors.length];  
                                  
                                // Highlight English word in engText with soft color & underline  
                                if (v.word && v.word.trim() !== '') {  
                                    let escWord = v.word.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');  
                                    let regEng = new RegExp(`(${escWord})`, 'gi');  
                                    engText = engText.replace(regEng, `<strong class="${col.text} underline ${col.deco} decoration-2 px-1 rounded ${col.bg}">$1</strong>`);  
                                }  

                                // Highlight Hindi meaning in hinText with exact same soft color & underline  
                                if (v.meaning && v.meaning.trim() !== '') {  
                                    let escMean = v.meaning.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');  
                                    let regHin = new RegExp(`(${escMean})`, 'gi');  
                                    hinText = hinText.replace(regHin, `<strong class="${col.text} underline ${col.deco} decoration-2 px-1 rounded ${col.bg}">$1</strong>`);  
                                }  
                            });  
                        }  

                        analysisHtml += `  
                            <div class="p-5 bg-white rounded-xl border border-slate-200 shadow-sm leading-loose">  
                                <p class="text-slate-900 font-medium text-base sm:text-lg mb-3"><strong>${pIdx + 1}.</strong> ${engText}</p>  
                                <p class="text-slate-700 font-semibold text-sm sm:text-base border-t border-dashed border-slate-200 pt-3">${hinText}</p>  
                            </div>  
                        `;  
                    });  
                    analysisHtml += `</div>`;  
                    analysisEl.innerHTML = analysisHtml;  
                } else {  
                    analysisEl.innerText = note.analysis;  
                }  
            } catch(e) {  
                analysisEl.innerText = note.analysis;  
            }  
            meaningContainer.style.display = 'block';  
        } else {  
            meaningContainer.style.display = 'none';  
        }  

        const actionBtns = document.getElementById('note-action-btns');  
        actionBtns.innerHTML = `  
            <button onclick="openNoteModal(${idx})" class="bg-blue-50 hover:bg-blue-100 text-blue-600 font-medium px-3.5 py-2 rounded-lg text-xs transition flex items-center"><i class="fa-solid fa-pen mr-1"></i> Edit</button>  
            <button onclick="deleteNoteFromReader(${idx})" class="bg-red-50 hover:bg-red-100 text-red-600 font-medium px-3.5 py-2 rounded-lg text-xs transition flex items-center"><i class="fa-solid fa-trash mr-1"></i> Delete</button>  
        `;  

        showView('note-reader-view');  
    }  

    function deleteNoteFromReader(idx) {  
        if (!verifySecurityPassword()) return;  
        if (confirm("Kya aap sach me ye note delete karna chahte hain?")) {  
            topicNotes[currentSubcategory].splice(idx, 1);  
            saveNotesToStorage();  
            openChapterHub(currentSubcategory);  
        }  
    }  

    // ================= TESTS LOGIC =================  
    let currentEditingTestIndex = null;  

    function renderTestsList() {  
        const list = document.getElementById('test-list');  
        list.innerHTML = '';  
          
        (topicTests[currentSubcategory] || []).forEach((test, idx) => {  
            const totalQ = test.questions.length;  
            const isPractice = test.type === 'practice';  
              
            const totalSecs = totalQ * 36;  
            const totalMins = isPractice ? 'No Timer' : `${Math.floor(totalSecs / 60)} Mins (${totalQ} Qs × 36s)`;  
              
            const badgeColor = isPractice ? 'bg-amber-100 text-amber-800' : 'bg-emerald-100 text-emerald-800';  
            const badgeText = isPractice ? 'Practice Quiz' : 'Mock Test';  

            const card = document.createElement('div');  
            card.className = 'bg-slate-50 p-4 rounded-xl border border-slate-200 hover:border-emerald-400 transition flex justify-between items-center';  
            card.innerHTML = `  
                <div class="cursor-pointer flex-1 pr-3" onclick="startTest(${idx})">  
                    <div class="flex items-center space-x-2 mb-1">  
                        <h4 class="font-bold text-slate-800 text-sm sm:text-base">${test.title}</h4>  
                        <span class="text-[9px] font-semibold px-2 py-0.5 rounded-full ${badgeColor}">${badgeText}</span>  
                    </div>  
                    <p class="text-[11px] text-slate-500 font-medium">  
                        <i class="fa-solid fa-list-ol mr-1"></i> ${totalQ} Qs &nbsp;|&nbsp; <i class="fa-regular fa-clock mr-1"></i> ${totalMins}  
                    </p>  
                </div>  
                <div class="flex space-x-1">  
                    <button class="edit-test-btn text-blue-500 hover:bg-blue-100 p-2 rounded transition" title="Edit"><i class="fa-solid fa-pen text-xs"></i></button>  
                    <button class="delete-test-btn text-red-500 hover:bg-red-100 p-2 rounded transition" title="Delete"><i class="fa-solid fa-trash text-xs"></i></button>  
                </div>  
            `;  
              
            card.querySelector('.edit-test-btn').onclick = (e) => { e.stopPropagation(); openTestModal(idx); };  
            card.querySelector('.delete-test-btn').onclick = (e) => { e.stopPropagation(); deleteTest(idx); };  
            list.appendChild(card);  
        });  

        if ((topicTests[currentSubcategory] || []).length === 0) {  
            list.innerHTML = `<div class="text-center py-6 text-slate-400 text-xs">Koi test nahi hain. 'Add Test' par click karke jodein.</div>`;  
        }  
    }  

    function openTestModal(index = null) {  
        currentEditingTestIndex = index;  
        document.getElementById('test-modal-title').innerText = index !== null ? "Edit Test / Quiz" : "Add New Test / Quiz";  

        if(index !== null) {  
            let test = topicTests[currentSubcategory][index];  
            document.getElementById('test-title-input').value = test.title;  
            document.getElementById('test-type-input').value = test.type || 'mock';  
            document.getElementById('custom-test-code-json').value = JSON.stringify(test.questions, null, 2);  
        } else {  
            let nextNum = (topicTests[currentSubcategory]?.length || 0) + 1;  
            document.getElementById('test-title-input').value = `Test ${nextNum}`;  
            document.getElementById('test-type-input').value = 'mock';  
            document.getElementById('custom-test-code-json').value = '';  
        }  
        document.getElementById('add-test-modal').classList.replace('hidden', 'flex');  
    }  

    function closeAddModal() {  
        document.getElementById('add-test-modal').classList.replace('flex', 'hidden');  
    }  

    function saveAndRunCustomTest() {  
        let title = document.getElementById('test-title-input').value.trim() || "Untitled Test";  
        let testType = document.getElementById('test-type-input').value;  
        let newQs = [];  

        try {  
            const jsonStr = document.getElementById('custom-test-code-json').value;  
            newQs = JSON.parse(jsonStr);  
            if (!Array.isArray(newQs) || newQs.length === 0) throw new Error("Format Array hona chahiye");  
              
            if(currentEditingTestIndex !== null) {  
                topicTests[currentSubcategory][currentEditingTestIndex].title = title;  
                topicTests[currentSubcategory][currentEditingTestIndex].type = testType;  
                topicTests[currentSubcategory][currentEditingTestIndex].questions = newQs;  
            } else {  
                topicTests[currentSubcategory].push({ title: title, type: testType, questions: newQs });  
            }  
              
            saveTestsToStorage();   
            closeAddModal();  
            renderTestsList();  
              
        } catch(e) { alert(`Error: ${e.message}`); }  
    }  

    function deleteTest(idx) {  
        if (!verifySecurityPassword()) return;  
        if(confirm("Kya aap sach me ye test delete karna chahte hain?")) {  
            topicTests[currentSubcategory].splice(idx, 1);  
            saveTestsToStorage();  
            renderTestsList();  
        }  
    }  

    // ================= QUIZ INTERFACE & TOTAL TIMER =================  
    function startTest(idx) {  
        const testObj = topicTests[currentSubcategory][idx];  
        activeQuestionsList = testObj.questions;  
        activeTestType = testObj.type || 'mock';  

        if(activeQuestionsList.length === 0) return alert("Is test me koi question nahi hai!");  

        userResponses = new Array(activeQuestionsList.length).fill(null);  
        questionStates = new Array(activeQuestionsList.length).fill('not_attempted');   
        currentIndex = 0;  
          
        showView('quiz-interface');  

        const timerWrapper = document.getElementById('timer-wrapper');  
        const typeBadge = document.getElementById('quiz-type-badge');  

        if (activeTestType === 'practice') {  
            timerWrapper.style.display = 'none';  
            typeBadge.innerText = "Practice Quiz (No Timer)";  
            typeBadge.className = "text-xs font-semibold px-2.5 py-1 rounded-full bg-amber-100 text-amber-800";  
            if(timerInterval) clearInterval(timerInterval);  
        } else {  
            timerWrapper.style.display = 'flex';  
            typeBadge.innerText = `Mock Test (${activeQuestionsList.length} Qs)`;  
            typeBadge.className = "text-xs font-semibold px-2.5 py-1 rounded-full bg-blue-100 text-blue-800";  
              
            timeRemaining = activeQuestionsList.length * 36;   
            startTimer();  
        }  

        loadQuestion(0);  
    }  

    function loadQuestion(idx) {  
        currentIndex = idx;  
        const qData = activeQuestionsList[idx];  
        document.getElementById('q-number').innerText = `Question ${idx + 1} of ${activeQuestionsList.length}`;  
          
        document.getElementById('q-phrase').innerHTML = qData.q;  
          
        const optContainer = document.getElementById('options-container');  
        optContainer.innerHTML = '';  
          
        qData.options.forEach((optText, optIdx) => {  
            const isSelected = userResponses[idx] === optIdx;  
            const div = document.createElement('div');  
            div.className = `p-3 border rounded-lg cursor-pointer flex items-center space-x-3 transition ${isSelected ? 'bg-blue-50 border-blue-500' : 'bg-white hover:bg-slate-50'}`;  
            div.onclick = () => selectOption(optIdx);  
            div.innerHTML = `  
                <div class="w-6 h-6 rounded-full border-2 flex items-center justify-center ${isSelected ? 'border-blue-600 bg-blue-600' : 'border-slate-300'}">  
                    ${isSelected ? '<div class="w-2.5 h-2.5 bg-white rounded-full"></div>' : ''}  
                </div>  
                <span class="text-slate-800 font-medium">${optText}</span>  
            `;  
            optContainer.appendChild(div);  
        });  
    }  

    function selectOption(optIdx) {  
        userResponses[currentIndex] = optIdx;  
        if (questionStates[currentIndex] !== 'review' && questionStates[currentIndex] !== 'answered_review') {  
            questionStates[currentIndex] = 'attempted';  
        } else if (questionStates[currentIndex] === 'review') {  
            questionStates[currentIndex] = 'answered_review';   
        }  
        loadQuestion(currentIndex);  
    }  

    function clearResponse() {  
        userResponses[currentIndex] = null;  
        questionStates[currentIndex] = 'not_attempted';   
        loadQuestion(currentIndex);  
    }  

    function toggleMarkForReview() {  
        if (userResponses[currentIndex] !== null) {  
            questionStates[currentIndex] = questionStates[currentIndex] === 'answered_review' ? 'attempted' : 'answered_review';   
        } else {  
            questionStates[currentIndex] = questionStates[currentIndex] === 'review' ? 'not_attempted' : 'review';   
        }  
        saveAndNext();  
    }  

    function saveAndNext() {  
        if (currentIndex < activeQuestionsList.length - 1) {  
            loadQuestion(currentIndex + 1);  
        } else {  
            confirmSubmitModal();  
        }  
    }  

    function prevQuestion() {  
        if (currentIndex > 0) loadQuestion(currentIndex - 1);  
    }  

    // ================= QUESTION PALETTE FUNCTIONS =================  
    function openQuestionPalette() {  
        const grid = document.getElementById('palette-grid');  
        grid.innerHTML = '';  
          
        activeQuestionsList.forEach((q, idx) => {  
            const state = questionStates[idx];  
            const isCurrent = idx === currentIndex;  
              
            let btnClass = 'bg-blue-600 text-white';   
            if (state === 'attempted') {  
                btnClass = 'bg-emerald-500 text-white';   
            } else if (state === 'review') {  
                btnClass = 'bg-red-500 text-white';   
            } else if (state === 'answered_review') {  
                btnClass = 'bg-amber-400 text-slate-900 font-bold';   
            }  

            if (isCurrent) {  
                btnClass += ' ring-4 ring-slate-900/30';  
            }  

            const btn = document.createElement('button');  
            btn.className = `h-10 rounded-lg text-sm font-semibold transition ${btnClass}`;  
            btn.innerText = idx + 1;  
            btn.onclick = () => {  
                loadQuestion(idx);  
                closeQuestionPalette();  
            };  
            grid.appendChild(btn);  
        });  

        document.getElementById('question-palette-modal').classList.replace('hidden', 'flex');  
    }  

    function closeQuestionPalette() {  
        document.getElementById('question-palette-modal').classList.replace('flex', 'hidden');  
    }  

    function startTimer() {  
        if(timerInterval) clearInterval(timerInterval);  
        timerInterval = setInterval(() => {  
            timeRemaining--;  
            let m = Math.floor(timeRemaining / 60);  
            let s = timeRemaining % 60;  
              
            let formattedTime = `${m < 10 ? '0' : ''}${m}:${s < 10 ? '0' : ''}${s}`;  
            document.getElementById('timer-display').innerText = formattedTime;  
              
            if (timeRemaining <= 0) {  
                clearInterval(timerInterval);  
                finalSubmitTest();  
            }  
        }, 1000);  
    }  

    function confirmExitTest() {  
        if(confirm("Kya aap test beech me chhodna chahte hain? Progress save nahi hogi.")) openChapterHub(currentSubcategory);  
    }  

    function confirmSubmitModal() {  
        let answered = userResponses.filter(ans => ans !== null).length;  
        let notAnswered = activeQuestionsList.length - answered;  

        document.getElementById('modal-total').innerText = activeQuestionsList.length;  
        document.getElementById('modal-ans').innerText = answered;  
        document.getElementById('modal-not-ans').innerText = notAnswered;  
        document.getElementById('submit-modal').classList.replace('hidden','flex');  
    }  

    function closeSubmitModal() { document.getElementById('submit-modal').classList.replace('flex','hidden'); }  

    // ================= ANALYSIS & RESULTS =================  
    function finalSubmitTest() {  
        if(timerInterval) clearInterval(timerInterval);  
        closeSubmitModal();  
          
        let correct = 0, incorrect = 0, unattempted = 0;  
        const solutionsContainer = document.getElementById('solutions-container');  
        solutionsContainer.innerHTML = '';  

        activeQuestionsList.forEach((q, i) => {  
            let uAns = userResponses[i];  
            let isCorrect = (uAns === q.answer);  
              
            if (uAns === null) unattempted++;  
            else if (isCorrect) correct++;  
            else incorrect++;  

            let cardClass = uAns === null ? 'border-slate-300' : (isCorrect ? 'border-emerald-300 bg-white' : 'border-red-300 bg-white');  
            let statusIcon = uAns === null ? '<span class="text-slate-400">Unattempted</span>' : (isCorrect ? '<span class="text-emerald-600 font-bold">✔️ Correct</span>' : '<span class="text-red-500 font-bold">❌ Incorrect</span>');  
              
            let optionsHtml = '<div class="space-y-2 mt-4">';  
            q.options.forEach((optText, optIdx) => {  
                let optClass = "bg-slate-50 border-slate-200 text-slate-700";  
                let optIcon = `<span class="w-5 h-5 rounded-full border border-slate-400 flex items-center justify-center text-[10px] bg-white mr-2">${String.fromCharCode(65 + optIdx)}</span>`;  

                if (optIdx === q.answer) {  
                    optClass = "bg-emerald-50 border-emerald-400 text-emerald-800 font-bold shadow-sm";  
                    optIcon = `<span class="w-5 h-5 rounded-full bg-emerald-500 flex items-center justify-center text-[10px] text-white mr-2">✔️</span>`;  
                } else if (optIdx === uAns && uAns !== q.answer) {  
                    optClass = "bg-red-50 border-red-400 text-red-800 shadow-sm";  
                    optIcon = `<span class="w-5 h-5 rounded-full bg-red-500 flex items-center justify-center text-[10px] text-white mr-2">❌</span>`;  
                }  

                optionsHtml += `  
                    <div class="flex items-center p-2.5 border rounded-lg ${optClass}">  
                        ${optIcon} <span>${optText}</span>  
                    </div>  
                `;  
            });  
            optionsHtml += '</div>';  

            let html = `  
            <div class="p-5 border-2 rounded-xl mb-4 shadow-sm ${cardClass}">  
                <div class="flex justify-between items-start mb-2">  
                    <p class="font-bold text-lg text-slate-900">Q${i+1}. ${q.q}</p>  
                    <div class="text-sm">${statusIcon}</div>  
                </div>  
                ${optionsHtml}  
                <div class="mt-5 p-4 rounded-lg bg-amber-50 border border-amber-200">  
                    <div class="flex items-center space-x-2 mb-1 text-amber-700 font-bold">  
                        <i class="fa-solid fa-language"></i>  
                        <span>Hindi Meaning / Solution:</span>  
                    </div>  
                    <p class="text-slate-800 text-sm leading-relaxed">${q.hindi || 'Is prashn ke liye detail solution available nahi hai.'}</p>  
                </div>  
            </div>`;  
            solutionsContainer.innerHTML += html;  
        });  

        let totalScore = (correct * 2) - (incorrect * 0.5);  
        let totalPossible = activeQuestionsList.length * 2;  
        let accuracy = (correct + incorrect > 0) ? Math.round((correct / (correct + incorrect)) * 100) : 0;  

        document.getElementById('res-ssc-score').innerText = `${totalScore} / ${totalPossible}`;  
        document.getElementById('res-correct').innerText = correct;  
        document.getElementById('res-incorrect').innerText = incorrect;  
        document.getElementById('res-unattempted').innerText = unattempted;  
        document.getElementById('res-accuracy').innerText = `${accuracy}%`;  

        showView('analysis-screen');  
    }  

    // Boot App  
    loadAppDataFromStorage();  
    showHomeView();  
</script>  

</body>  
</html>  
