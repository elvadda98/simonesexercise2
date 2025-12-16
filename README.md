<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vocabulary Exercise: Relationships, Time, and Quantity</title>
    <style>
        :root {
            --primary-color: #008080; /* Teal */
            --secondary-color: #20b2aa; /* Light Sea Green */
            --accent-color: #3cb371; /* Medium Sea Green */
            --light-bg: #f0fff0;
            --dark-text: #333;
            --success-color: #28a745;
            --error-color: #dc3545;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--light-bg);
            color: var(--dark-text);
            line-height: 1.6;
        }

        header {
            background-color: var(--primary-color);
            color: white;
            padding: 15px 20px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        .score-display {
            position: absolute;
            top: 15px;
            right: 20px;
            font-weight: bold;
            background-color: rgba(255, 255, 255, 0.2);
            padding: 5px 10px;
            border-radius: 5px;
        }

        .container {
            max-width: 1000px;
            margin: 20px auto;
            padding: 0 15px;
        }

        .nav-buttons {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap; 
        }

        .nav-button {
            padding: 10px 15px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            background-color: var(--secondary-color);
            color: white;
            font-weight: bold;
            transition: background-color 0.3s, transform 0.1s;
            box-shadow: 0 3px var(--primary-color);
            flex-grow: 1;
            min-width: 150px;
        }

        .nav-button:hover {
            background-color: var(--accent-color);
        }

        .nav-button:active {
            transform: translateY(2px);
            box-shadow: 0 1px var(--primary-color);
        }

        .nav-button.active {
            background-color: var(--primary-color);
            box-shadow: 0 3px var(--secondary-color);
        }

        .exercise-section {
            background-color: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        h2 {
            color: var(--primary-color);
            border-bottom: 3px solid var(--secondary-color);
            padding-bottom: 10px;
            margin-top: 0;
            margin-bottom: 20px;
        }

        /* --- Vocabulary List Styles --- */

        .vocab-item {
            display: flex;
            align-items: flex-start;
            padding: 15px 0;
            border-bottom: 1px dashed #ccc;
        }

        .vocab-item:last-child {
            border-bottom: none;
        }

        .word-col {
            flex: 0 0 180px;
            font-size: 1.2em;
            font-weight: bold;
            color: var(--primary-color);
        }

        .details-col {
            flex: 1;
        }

        .context {
            font-style: italic;
            color: var(--accent-color);
            margin-bottom: 5px;
            display: block;
        }

        .meaning {
            margin-bottom: 5px;
        }

        .example {
            color: #555;
            font-size: 0.95em;
        }

        .listen-btn {
            background-color: var(--secondary-color);
            color: white;
            border: none;
            padding: 6px 10px;
            border-radius: 5px;
            cursor: pointer;
            margin-left: 10px;
            transition: background-color 0.3s;
        }

        .listen-btn:hover {
            background-color: var(--accent-color);
        }

        /* --- Word Bank Styles (Common) --- */

        .word-bank {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 8px;
            background: linear-gradient(45deg, var(--secondary-color), var(--accent-color));
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .word-bank-item {
            background-color: white;
            color: var(--dark-text);
            padding: 8px 12px;
            border-radius: 6px;
            font-weight: bold;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        /* --- Fill in the Gaps (Writing) Styles --- */

        .gap-sentence {
            margin-bottom: 15px;
            padding: 10px;
            border-left: 5px solid var(--secondary-color);
            background-color: #f9f9f9;
            border-radius: 5px;
        }

        .gap-input {
            width: 120px;
            padding: 5px;
            margin: 0 5px;
            border: 2px solid #ccc;
            border-radius: 4px;
            text-align: center;
            font-weight: bold;
            color: var(--primary-color);
        }

        .gap-input:focus {
            border-color: var(--accent-color);
            outline: none;
        }

        .feedback {
            margin-left: 10px;
            font-weight: bold;
        }

        .controls {
            margin-top: 20px;
            display: flex;
            gap: 10px;
        }

        .check-btn, .reset-btn {
            padding: 10px 15px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            transition: opacity 0.3s;
        }

        .check-btn {
            background-color: var(--success-color);
            color: white;
        }

        .reset-btn {
            background-color: var(--error-color);
            color: white;
        }

        /* --- Match Definitions Styles --- */

        .matching-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .match-item {
            padding: 15px;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.2s, transform 0.1s;
            user-select: none;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            border: 2px solid #ddd;
        }

        .match-word {
            background-color: #e0f7fa; /* Light Cyan */
            font-weight: bold;
            color: var(--primary-color);
        }

        .match-def {
            background-color: #f1f8e9; /* Light Greenish */
            color: var(--dark-text);
            font-size: 0.95em;
        }

        .match-item:not(.matched):hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .selected-match {
            border-color: var(--primary-color);
            background-color: #c8e6c9; /* Lighter Green */
        }

        .matched {
            cursor: default !important;
            background-color: var(--success-color) !important;
            color: white !important;
            border-color: var(--success-color) !important;
        }

        /* --- Fill in the Gaps (Pronunciation) Styles --- */

        .pron-sentence {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding: 10px;
            border-left: 5px solid var(--accent-color);
            background-color: #f9f9f9;
            border-radius: 5px;
        }

        .pron-placeholder {
            min-width: 120px;
            height: 25px;
            display: inline-block;
            border-bottom: 2px dashed var(--primary-color);
            margin: 0 5px;
            text-align: center;
            font-weight: bold;
            color: var(--success-color);
            line-height: 25px;
        }

        .mic-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 8px;
            border-radius: 50%;
            cursor: pointer;
            margin-left: 10px;
            font-size: 1.2em;
            transition: background-color 0.3s, transform 0.1s;
        }

        .mic-btn:hover {
            background-color: var(--accent-color);
        }

        .mic-btn:disabled {
            background-color: #ccc;
            cursor: not-allowed;
        }

        .pron-feedback {
            margin-left: 15px;
            font-style: italic;
            min-width: 100px;
        }
    </style>
</head>
<body>

    <header>
        <h1>English Vocabulary Interactive Practice</h1>
        <div class="score-display">
            Score: <span id="current-score">0</span> / <span id="max-score">30</span>
        </div>
    </header>

    <div class="container">
        <div class="nav-buttons">
            <button class="nav-button active" onclick="showSection('vocab-list-section', this)">1. 📚 Vocabulary List</button>
            <button class="nav-button" onclick="showSection('writing-gaps-section', this)">2. ✍️ Fill in Gaps (Writing)</button>
            <button class="nav-button" onclick="showSection('matching-section', this)">3. 🔗 Match Definitions</button>
            <button class="nav-button" onclick="showSection('pronunciation-gaps-section', this)">4. 🗣️ Fill in Gaps (Pronunciation)</button>
        </div>

        <div id="vocab-list-section" class="exercise-section">
            <h2>📚 Vocabulary List</h2>
            <div id="vocab-list-content">
                </div>
        </div>

        <div id="writing-gaps-section" class="exercise-section" style="display: none;">
            <h2>✍️ Fill in the Gaps (Writing)</h2>
            <p>Use the words in the bank to complete the sentences. Type the correct word in the blank.</p>
            <div class="word-bank" id="writing-word-bank">
                </div>
            <div id="writing-gaps-content">
                </div>
            <div class="controls">
                <button class="check-btn" onclick="checkWritingGaps()">Check Answers</button>
                <button class="reset-btn" onclick="resetWritingGaps()">Reset</button>
            </div>
        </div>

        <div id="matching-section" class="exercise-section" style="display: none;">
            <h2>🔗 Match Definitions</h2>
            <p>Click a word on the left, then click its correct definition on the right.</p>
            <div class="matching-grid" id="matching-grid">
                </div>
        </div>

        <div id="pronunciation-gaps-section" class="exercise-section" style="display: none;">
            <h2>🗣️ Fill in the Gaps (Pronunciation) </h2>
            <p>Click the microphone and say the word that belongs in the blank. *Requires Chrome/Edge.*</p>
            <div class="word-bank" id="pron-word-bank">
                </div>
            <div id="pronunciation-gaps-content">
                </div>
            <p style="margin-top: 15px; font-size: 0.9em; color: #666;">
                *Tip: You must pronounce the exact word clearly to fill the gap.*
            </p>
        </div>

    </div>

    <script>
        const vocabData = [
            {
                word: "older",
                context: "more advanced in age",
                meaning: "More advanced in age than someone or something else.",
                example: "My sister is three years **older** than me, so she started driving first.",
                writingSentence: "She looks much **___** in that photograph than I remember her.",
                definition: "Having lived for a greater number of years than another person or thing; senior.",
                pronSentence: "He is the **___** of the two brothers."
            },
            {
                word: "youngest",
                context: "the least advanced in age",
                meaning: "The one that is the least advanced in age; having lived for the fewest years.",
                example: "The **youngest** child in the family always gets the most attention.",
                writingSentence: "She is the **___** member of the team, but she is also the most skilled programmer.",
                definition: "Referring to the person or thing in a group that is shortest in duration of life or existence.",
                pronSentence: "Who is the **___** student in the class?"
            },
            {
                word: "went",
                context: "past tense of go (to a place)",
                meaning: "The past tense of the verb 'go'; moved from one place to another.",
                example: "They **went** to the cinema last weekend to see the new blockbuster movie.",
                writingSentence: "After the meeting, the CEO **___** directly to the airport for her flight.",
                definition: "The simple past form of 'go', meaning to have traveled or moved to a specific destination.",
                pronSentence: "We **___** swimming at the lake yesterday afternoon."
            },
            {
                word: "together",
                context: "in or into one place or group",
                meaning: "In or into one place, mass, or group; in collaboration or unison.",
                example: "We built the model airplane **together** over the course of three evenings.",
                writingSentence: "The four of them decided to rent an apartment **___** to save money.",
                definition: "In company or conjunction with; unitedly or simultaneously.",
                pronSentence: "The whole family ate dinner **___** every night."
            },
            {
                word: "find",
                context: "to discover or locate",
                meaning: "To discover or locate something or someone, either by chance or after a deliberate search.",
                example: "I hope you can **find** your lost keys before you leave the house.",
                writingSentence: "It is often difficult to **___** affordable accommodation near the city center.",
                definition: "To succeed in obtaining or locating something lost, desired, or hidden.",
                pronSentence: "Did you **___** the article I sent you about climate change?"
            },
            {
                word: "a lot",
                context: "a large amount or extent",
                meaning: "A large amount or large extent; much.",
                example: "She saves **a lot** of money by cycling to work instead of taking the bus.",
                writingSentence: "They have spent **___** of time preparing for the final exam.",
                definition: "A considerable quantity, degree, or extent.",
                pronSentence: "He eats **___** of vegetables to stay healthy."
            },
            {
                word: "both",
                context: "the two people or things",
                meaning: "Referring to the two people or things that have just been mentioned or are implied.",
                example: "She invited John and Sarah, but **both** said they couldn't make it.",
                writingSentence: "You can choose either the blue shirt or the green one, or you can take **___**.",
                definition: "Used to emphasize that two individuals or things are included.",
                pronSentence: "**___** of them agreed with the committee's final decision."
            },
            {
                word: "sooner or later",
                context: "eventually, after a period of time",
                meaning: "Eventually, after a period of time, even if it is not immediately.",
                example: "**Sooner or later**, the truth about the scandal will be revealed to the public.",
                writingSentence: "If you keep practicing the piano every day, you will master that piece **___**.",
                definition: "At some point in the future; eventually.",
                pronSentence: "We knew **___** they would apologize for their mistake."
            },
            {
                word: "same",
                context: "as lo stesso (the same)",
                meaning: "Identical; not different; or corresponding in shape, size, or general characteristics.",
                example: "I ordered the **same** meal as my friend because it looked delicious.",
                writingSentence: "I think we both chose the **___** answer, which makes me feel confident.",
                definition: "Being one and not merely similar; or exactly corresponding to something mentioned.",
                pronSentence: "They live in the **___** apartment building as us."
            },
            {
                word: "earphones",
                context: "small devices worn in the ears for listening to audio",
                meaning: "Small listening devices that are plugged directly into the ear canal or worn over the ear for private listening to audio.",
                example: "Don't forget to pack your **earphones** if you want to listen to music on the flight.",
                writingSentence: "He always uses noise-canceling **___** when he works in the open-plan office.",
                definition: "A pair of small sound speakers worn in or over the ears to allow private listening to audio.",
                pronSentence: "I can't hear you clearly, please take out your **___**."
            }
        ];

        let score = 0;
        const maxScore = vocabData.length * 3;
        let writingCorrect = new Array(vocabData.length).fill(false);
        let matchingCorrect = new Array(vocabData.length).fill(false);
        let pronCorrect = new Array(vocabData.length).fill(false);

        function updateScore() {
            score = writingCorrect.filter(c => c).length + 
                    matchingCorrect.filter(c => c).length + 
                    pronCorrect.filter(c => c).length;
            document.getElementById('current-score').textContent = score;
        }

        function speak(word) {
            if ('speechSynthesis' in window) {
                const u = new SpeechSynthesisUtterance(word);
                u.lang = "en-US";
                u.volume = 1;
                u.rate = 1;
                u.pitch = 1;
                speechSynthesis.speak(u);
            } else {
                alert("Speech Synthesis is not supported in your browser.");
            }
        }

        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
        }

        function showSection(sectionId, button) {
            document.querySelectorAll('.exercise-section').forEach(section => {
                section.style.display = 'none';
            });
            document.getElementById(sectionId).style.display = 'block';

            document.querySelectorAll('.nav-button').forEach(btn => {
                btn.classList.remove('active');
            });
            button.classList.add('active');
        }

        // --- 1. Vocabulary List Setup ---
        function setupVocabularyList() {
            const listContainer = document.getElementById('vocab-list-content');
            listContainer.innerHTML = vocabData.map(item => `
                <div class="vocab-item">
                    <div class="word-col">
                        ${item.word}
                        <button class="listen-btn" onclick="speak('${item.word.replace(/'/g, "\\'")}')">▶️ Hear</button>
                    </div>
                    <div class="details-col">
                        <span class="context">(${item.context})</span>
                        <p class="meaning">${item.meaning}</p>
                        <p class="example">Example: ${item.example}</p>
                    </div>
                </div>
            `).join('');
        }

        // --- 2. Fill in the Gaps (Writing) Setup ---
        function setupWritingGaps() {
            const container = document.getElementById('writing-gaps-content');
            const wordBank = document.getElementById('writing-word-bank');
            const shuffledData = [...vocabData].map((item, index) => ({...item, originalIndex: index}));
            shuffleArray(shuffledData);

            wordBank.innerHTML = vocabData.map(item => `<span class="word-bank-item">${item.word}</span>`).join('');

            container.innerHTML = shuffledData.map((item, index) => {
                const parts = item.writingSentence.split('___');
                // Ensure multi-word answers have enough space if they are the placeholder
                const inputWidth = item.word.length > 10 ? '200px' : '120px';
                const placeholder = `<input type="text" class="gap-input" style="width: ${inputWidth};" id="writing-gap-${item.originalIndex}" data-correct-word="${item.word.toLowerCase()}" data-index="${item.originalIndex}">`;
                return `
                    <div class="gap-sentence" id="writing-sentence-container-${item.originalIndex}">
                        ${parts[0]}${placeholder}${parts[1]}
                        <span class="feedback" id="writing-feedback-${item.originalIndex}"></span>
                    </div>
                `;
            }).join('');
        }

        function checkWritingGaps() {
            let allCorrect = true;
            document.querySelectorAll('#writing-gaps-content .gap-input').forEach(input => {
                const expected = input.getAttribute('data-correct-word');
                const actual = input.value.trim().toLowerCase();
                const index = parseInt(input.getAttribute('data-index'));
                const feedbackSpan = document.getElementById(`writing-feedback-${index}`);
                const container = document.getElementById(`writing-sentence-container-${index}`);

                if (writingCorrect[index]) return; // Skip already correct
                
                // Special handling for multi-word answers
                const normalizedExpected = expected.replace(/[^a-z0-9]/g, '');
                const normalizedActual = actual.replace(/[^a-z0-9]/g, '');


                if (normalizedActual === normalizedExpected) {
                    feedbackSpan.textContent = '✅ Correct!';
                    feedbackSpan.style.color = varToRgb('--success-color');
                    container.style.backgroundColor = '#e6ffe6';
                    input.value = expected; // Display the correct cased version
                    input.disabled = true;
                    writingCorrect[index] = true;
                    updateScore();
                } else {
                    feedbackSpan.textContent = '❌ Try again.';
                    feedbackSpan.style.color = varToRgb('--error-color');
                    container.style.backgroundColor = '#ffe6e6';
                    allCorrect = false;
                }
            });
            // Reset background color after a short time if not correct
            if (!allCorrect) {
                setTimeout(() => {
                    document.querySelectorAll('#writing-gaps-content .gap-sentence').forEach((container, index) => {
                        if (!writingCorrect[index]) {
                            container.style.backgroundColor = '#f9f9f9';
                        }
                    });
                }, 1000);
            }
        }

        function resetWritingGaps() {
            document.querySelectorAll('#writing-gaps-content .gap-input').forEach(input => {
                const index = parseInt(input.getAttribute('data-index'));
                input.value = '';
                input.disabled = false;
                document.getElementById(`writing-feedback-${index}`).textContent = '';
                document.getElementById(`writing-sentence-container-${index}`).style.backgroundColor = '#f9f9f9';
                if (writingCorrect[index]) {
                    writingCorrect[index] = false;
                    updateScore();
                }
            });
        }

        // --- 3. Match Definitions Setup ---
        let selectedWord = null;
        let selectedDef = null;

        function setupMatching() {
            const grid = document.getElementById('matching-grid');
            const words = vocabData.map((item, index) => ({ content: item.word, id: index, type: 'word' }));
            const definitions = vocabData.map((item, index) => ({ content: item.definition, id: index, type: 'def' }));

            shuffleArray(definitions);

            const allItems = [];
            for (let i = 0; i < words.length; i++) {
                allItems.push(words[i]);
                allItems.push(definitions[i]);
            }
            
            grid.innerHTML = allItems.map(item => `
                <div class="match-item match-${item.type}" data-id="${item.id}" data-type="${item.type}" onclick="handleMatchClick(this)">
                    ${item.content}
                </div>
            `).join('');
            
            // Reset state
            selectedWord = null;
            selectedDef = null;
            matchingCorrect.fill(false);
            updateScore();
        }

        function handleMatchClick(element) {
            if (element.classList.contains('matched')) return;

            // Deselect previous item of the same type
            document.querySelectorAll(`.match-${element.getAttribute('data-type')}`).forEach(item => {
                if (item.classList.contains('selected-match')) {
                    item.classList.remove('selected-match');
                }
            });

            // Select current item
            element.classList.add('selected-match');
            
            if (element.getAttribute('data-type') === 'word') {
                selectedWord = element;
            } else {
                selectedDef = element;
            }

            // Check for match
            if (selectedWord && selectedDef) {
                const wordId = selectedWord.getAttribute('data-id');
                const defId = selectedDef.getAttribute('data-id');

                if (wordId === defId) {
                    // Match found
                    selectedWord.classList.add('matched');
                    selectedDef.classList.add('matched');
                    selectedWord.classList.remove('selected-match');
                    selectedDef.classList.remove('selected-match');
                    
                    const index = parseInt(wordId);
                    if (!matchingCorrect[index]) {
                        matchingCorrect[index] = true;
                        updateScore();
                    }
                } else {
                    // Incorrect match - briefly highlight as error
                    selectedWord.style.backgroundColor = varToRgb('--error-color');
                    selectedDef.style.backgroundColor = varToRgb('--error-color');
                    selectedWord.style.color = 'white';
                    selectedDef.style.color = 'white';

                    setTimeout(() => {
                        selectedWord.classList.remove('selected-match');
                        selectedDef.classList.remove('selected-match');
                        selectedWord.style.backgroundColor = '';
                        selectedDef.style.backgroundColor = '';
                        selectedWord.style.color = '';
                        selectedDef.style.color = '';
                    }, 500);
                }

                // Reset selections
                selectedWord = null;
                selectedDef = null;
            }
        }

        // --- 4. Fill in the Gaps (Pronunciation) Setup ---
        let recognition = null;
        if ('webkitSpeechRecognition' in window) {
            recognition = new webkitSpeechRecognition();
        } else if ('SpeechRecognition' in window) {
            recognition = new SpeechRecognition();
        }
        
        function setupPronunciationGaps() {
            const container = document.getElementById('pronunciation-gaps-content');
            const wordBank = document.getElementById('pron-word-bank');
            const shuffledData = [...vocabData].map((item, index) => ({...item, originalIndex: index}));
            shuffleArray(shuffledData);

            wordBank.innerHTML = vocabData.map(item => `<span class="word-bank-item">${item.word}</span>`).join('');

            container.innerHTML = shuffledData.map((item, index) => {
                const parts = item.pronSentence.split('___');
                const inputWidth = item.word.length > 10 ? '200px' : '120px';
                const placeholder = `<span class="pron-placeholder" style="min-width: ${inputWidth};" id="pron-gap-${item.originalIndex}"></span>`;
                const micButton = `<button class="mic-btn" id="mic-btn-${item.originalIndex}" data-correct-word="${item.word.toLowerCase()}" data-index="${item.originalIndex}" onclick="startRecognition(this)">🎤</button>`;
                
                return `
                    <div class="pron-sentence" id="pron-sentence-container-${item.originalIndex}">
                        ${parts[0]}${placeholder}${parts[1]}
                        ${micButton}
                        <span class="pron-feedback" id="pron-feedback-${item.originalIndex}"></span>
                    </div>
                `;
            }).join('');
            
            pronCorrect.fill(false);
            updateScore();
            
            if (!recognition) {
                document.getElementById('pronunciation-gaps-section').querySelector('p').innerHTML = '<strong>Speech Recognition is NOT supported in your browser.</strong>';
                document.querySelectorAll('.mic-btn').forEach(btn => btn.disabled = true);
            }
        }

        function startRecognition(button) {
            if (!recognition) return;

            const index = parseInt(button.getAttribute('data-index'));
            const expectedWord = button.getAttribute('data-correct-word');
            const feedbackSpan = document.getElementById(`pron-feedback-${index}`);
            const placeholder = document.getElementById(`pron-gap-${index}`);
            
            if (pronCorrect[index]) return;

            recognition.lang = 'en-US';
            recognition.interimResults = false;
            recognition.maxAlternatives = 1;
            
            button.disabled = true;
            feedbackSpan.textContent = 'Listening...';
            feedbackSpan.style.color = '#ff8c00'; // Orange
            
            recognition.onresult = function(event) {
                const transcript = event.results[0][0].transcript.trim().toLowerCase();
                const spokenWordNormalized = transcript.replace(/[^a-z0-9]/g, '');
                
                let normalizedExpected = expectedWord.replace(/[^a-z0-9]/g, '');
                let isMatch = (spokenWordNormalized === normalizedExpected);

                // Special handling for multi-word phrases: 'a lot', 'sooner or later'
                if (expectedWord === 'a lot') {
                    if (transcript.includes('a lot')) isMatch = true;
                }
                if (expectedWord === 'sooner or later') {
                    if (transcript.includes('sooner or later')) isMatch = true;
                }


                if (isMatch) {
                    placeholder.textContent = expectedWord;
                    feedbackSpan.textContent = '✅ Success!';
                    feedbackSpan.style.color = varToRgb('--success-color');
                    document.getElementById(`pron-sentence-container-${index}`).style.backgroundColor = '#e6ffe6';
                    button.style.backgroundColor = varToRgb('--success-color');
                    
                    if (!pronCorrect[index]) {
                        pronCorrect[index] = true;
                        updateScore();
                    }
                } else {
                    feedbackSpan.textContent = `❌ Said: "${event.results[0][0].transcript.trim()}"`;
                    feedbackSpan.style.color = varToRgb('--error-color');
                    document.getElementById(`pron-sentence-container-${index}`).style.backgroundColor = '#ffe6e6';
                    setTimeout(() => {
                         document.getElementById(`pron-sentence-container-${index}`).style.backgroundColor = '#f9f9f9';
                    }, 1500);
                }
                
                button.disabled = false;
            };

            recognition.onerror = function(event) {
                feedbackSpan.textContent = '❌ Error: ' + event.error;
                feedbackSpan.style.color = varToRgb('--error-color');
                button.disabled = false;
            };

            recognition.onend = function() {
                if (!pronCorrect[index] && feedbackSpan.textContent === 'Listening...') {
                     feedbackSpan.textContent = '❌ No speech detected.';
                     feedbackSpan.style.color = varToRgb('--error-color');
                }
                if (!pronCorrect[index]) {
                    button.disabled = false;
                }
            };

            try {
                recognition.start();
            } catch (e) {
                feedbackSpan.textContent = '❌ Recognition is already running.';
                button.disabled = false;
            }
        }
        
        // Helper to get RGB for dynamic color usage
        function varToRgb(cssVar) {
            const style = getComputedStyle(document.body);
            let color = style.getPropertyValue(cssVar).trim();
            return color; 
        }

        // --- Initialization ---
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('max-score').textContent = maxScore;
            setupVocabularyList();
            setupWritingGaps();
            setupMatching();
            setupPronunciationGaps();
            updateScore();
        });
    </script>
</body>
</html>
