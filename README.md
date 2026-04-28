<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes" />
    <title>Ovozli O‘qish Dasturi | Matnni O‘qib Beruvchi</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #e0eafc 0%, #cfdef3 100%);
            font-family: 'Segoe UI', 'Roboto', 'Noto Sans', system-ui, -apple-system, sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 1.5rem;
        }

        .card {
            max-width: 950px;
            width: 100%;
            background: rgba(255, 255, 255, 0.96);
            border-radius: 2.5rem;
            box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.3), 0 4px 12px rgba(0, 0, 0, 0.05);
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.5);
        }

        .header {
            background: linear-gradient(135deg, #0f2b4d, #1a3a62);
            padding: 1.3rem 2rem;
            color: white;
        }

        .header h1 {
            font-size: 1.8rem;
            font-weight: 600;
            letter-spacing: -0.3px;
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .header h1:before {
            content: "🔊";
            font-size: 1.8rem;
            filter: drop-shadow(2px 2px 2px rgba(0,0,0,0.2));
        }

        .sub {
            font-size: 0.9rem;
            margin-top: 8px;
            opacity: 0.85;
            border-left: 3px solid #ffc857;
            padding-left: 12px;
        }

        .content {
            padding: 2rem 2rem 1.8rem 2rem;
        }

        .text-area-group {
            margin-bottom: 1.8rem;
        }

        label {
            font-weight: 600;
            color: #1f3a5f;
            display: block;
            margin-bottom: 8px;
            font-size: 1rem;
            letter-spacing: -0.2px;
        }

        textarea {
            width: 100%;
            height: 220px;
            padding: 1rem 1.2rem;
            font-size: 1rem;
            font-family: 'Segoe UI', 'Roboto', monospace;
            line-height: 1.5;
            background: #fefcf5;
            border: 1.5px solid #cddfea;
            border-radius: 24px;
            resize: vertical;
            transition: 0.2s;
            outline: none;
            color: #1a2c3e;
        }

        textarea:focus {
            border-color: #3f7eb6;
            box-shadow: 0 0 0 3px rgba(63, 126, 182, 0.2);
            background: #ffffff;
        }

        .controls {
            background: #f1f5f9;
            border-radius: 28px;
            padding: 1.2rem 1.3rem;
            margin-bottom: 1.6rem;
            display: flex;
            flex-wrap: wrap;
            gap: 1.7rem;
            align-items: flex-end;
            justify-content: space-between;
        }

        .control-item {
            flex: 1;
            min-width: 130px;
        }

        .control-item label {
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 6px;
            color: #2c4c7c;
        }

        input[type="range"] {
            width: 100%;
            height: 5px;
            -webkit-appearance: none;
            appearance: none;
            background: #cbdde9;
            border-radius: 10px;
            outline: none;
        }

        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 18px;
            height: 18px;
            background: #1f5e9e;
            border-radius: 50%;
            cursor: pointer;
            box-shadow: 0 1px 4px rgba(0,0,0,0.2);
            border: none;
        }

        .value-display {
            display: inline-block;
            background: white;
            padding: 2px 10px;
            border-radius: 40px;
            font-size: 0.75rem;
            font-weight: 500;
            margin-top: 6px;
            color: #1e466e;
        }

        select {
            width: 100%;
            padding: 8px 10px;
            border-radius: 40px;
            border: 1px solid #bbd0e0;
            background: white;
            font-weight: 500;
            font-family: inherit;
            color: #1f3a5f;
            outline: none;
            cursor: pointer;
        }

        .action-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 14px;
            margin-top: 8px;
            margin-bottom: 20px;
        }

        .btn {
            padding: 12px 24px;
            font-size: 1rem;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.2s ease;
            font-family: inherit;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.05);
        }

        .btn-primary {
            background: #2266aa;
            color: white;
            flex: 2;
            justify-content: center;
        }

        .btn-primary:hover {
            background: #0f4b7a;
            transform: translateY(-2px);
            box-shadow: 0 8px 18px rgba(34, 102, 170, 0.3);
        }

        .btn-danger {
            background: #af5e5e;
            color: white;
        }

        .btn-danger:hover {
            background: #8e4545;
            transform: translateY(-1px);
        }

        .btn-secondary {
            background: #e2eaf1;
            color: #1e466e;
            border: 1px solid #cbdbe0;
        }

        .btn-secondary:hover {
            background: #d0dde8;
        }

        .status {
            background: #eef3fc;
            border-radius: 60px;
            padding: 10px 18px;
            font-size: 0.85rem;
            color: #1f4970;
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-top: 10px;
        }

        .status span {
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .speaking-indicator {
            width: 10px;
            height: 10px;
            background: #44aa55;
            border-radius: 50%;
            display: inline-block;
            box-shadow: 0 0 4px #44aa55;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% { opacity: 0.4; transform: scale(0.9); }
            100% { opacity: 1; transform: scale(1.2); }
        }

        footer {
            text-align: center;
            font-size: 0.7rem;
            color: #5e7e9e;
            border-top: 1px solid #e2edf7;
            padding: 1rem;
            background: #f9fbfe;
        }

        @media (max-width: 650px) {
            .content {
                padding: 1.3rem;
            }

            .btn {
                padding: 9px 16px;
            }

            .controls {
                flex-direction: column;
                align-items: stretch;
            }
        }
    </style>
</head>
<body>
    <div class="card">
        <div class="header">
            <h1>Matnni o‘qib beruvchi dastur</h1>
            <div class="sub">📖 Istalgan matnni yozing va “O‘qish” tugmasini bosing — ovoz bilan eshiting</div>
        </div>

        <div class="content">
            <div class="text-area-group">
                <label for="textInput">✍️ Matn (o‘qiladigan matn)</label>
                <textarea id="textInput" placeholder="Masalan: Assalomu alaykum! Ushbu dastur matnni baland ovozda o‘qib beradi.">Assalomu alaykum!
Ushbu interaktiv dastur yordamida istalgan matnni tinglashingiz mumkin. Tezlik, balandlik va ovoz turini o‘zgartirib, qulay tarzda eshiting. Matnni o‘zgartiring va "O‘qish" tugmasini bosing.</textarea>
            </div>

            <div class="controls">
                <div class="control-item">
                    <label for="rateSlider">⚡ O‘qish tezligi (Rate)</label>
                    <input type="range" id="rateSlider" min="0.5" max="2" step="0.05" value="1.0">
                    <div class="value-display" id="rateValue">1.00x</div>
                </div>

                <div class="control-item">
                    <label for="pitchSlider">🎵 Balandlik (Pitch)</label>
                    <input type="range" id="pitchSlider" min="0.5" max="2" step="0.05" value="1.0">
                    <div class="value-display" id="pitchValue">1.00</div>
                </div>

                <div class="control-item">
                    <label for="voiceSelect">🗣️ Ovoz (Voice)</label>
                    <select id="voiceSelect">
                        <option value="">⏳ Ovozlar yuklanmoqda...</option>
                    </select>
                </div>
            </div>

            <div class="action-buttons">
                <button class="btn btn-primary" id="readBtn">🔊 O‘qish</button>
                <button class="btn btn-danger" id="stopBtn">⏹️ To‘xtatish</button>
                <button class="btn btn-secondary" id="sampleBtn">📄 Namuna matn</button>
                <button class="btn btn-secondary" id="clearBtn">🧹 Tozalash</button>
            </div>

            <div class="status" id="statusArea">
                <span>📌 Holat: <span id="statusMsg">Tayyor</span></span>
                <span id="liveIndicator" style="display: none;">🎙️ <span class="speaking-indicator"></span> O‘qilmoqda...</span>
            </div>
        </div>

        <footer>
            💡 Tavsiya: Chrome, Edge, Safari va zamonaviy brauzerlarda yaxshi ishlaydi.
        </footer>
    </div>

    <script>
        (() => {
            const textarea = document.getElementById('textInput');
            const readBtn = document.getElementById('readBtn');
            const stopBtn = document.getElementById('stopBtn');
            const sampleBtn = document.getElementById('sampleBtn');
            const clearBtn = document.getElementById('clearBtn');
            const rateSlider = document.getElementById('rateSlider');
            const pitchSlider = document.getElementById('pitchSlider');
            const rateValue = document.getElementById('rateValue');
            const pitchValue = document.getElementById('pitchValue');
            const voiceSelect = document.getElementById('voiceSelect');
            const statusMsgSpan = document.getElementById('statusMsg');
            const liveIndicatorSpan = document.getElementById('liveIndicator');

            const speechSynth = window.speechSynthesis;
            let currentUtterance = null;
            let availableVoices = [];
            let isSpeaking = false;

            if (!speechSynth) {
                statusMsgSpan.innerText = "Brauzeringiz matnni ovozga aylantirishni qo‘llab-quvvatlamaydi!";
                readBtn.disabled = true;
                stopBtn.disabled = true;
                voiceSelect.disabled = true;
                rateSlider.disabled = true;
                pitchSlider.disabled = true;
                return;
            }

            function updateRateDisplay() {
                rateValue.innerText = parseFloat(rateSlider.value).toFixed(2) + 'x';
            }

            function updatePitchDisplay() {
                pitchValue.innerText = parseFloat(pitchSlider.value).toFixed(2);
            }

            rateSlider.addEventListener('input', updateRateDisplay);
            pitchSlider.addEventListener('input', updatePitchDisplay);
            updateRateDisplay();
            updatePitchDisplay();

            function buildVoiceDropdown(voices) {
                availableVoices = voices || [];
                const selectedVoiceValue = voiceSelect.value;

                voiceSelect.innerHTML = '';

                const defaultOption = document.createElement('option');
                defaultOption.value = '';
                defaultOption.textContent = '🌐 Standart ovoz (brauzer)';
                voiceSelect.appendChild(defaultOption);

                availableVoices.forEach((voice, index) => {
                    const option = document.createElement('option');
                    option.value = String(index);
                    option.textContent = `${voice.name} (${voice.lang})${voice.default ? ' ⭐' : ''}`;
                    voiceSelect.appendChild(option);
                });

                if (selectedVoiceValue !== '' && availableVoices[parseInt(selectedVoiceValue, 10)]) {
                    voiceSelect.value = selectedVoiceValue;
                } else {
                    const uzVoiceIndex = availableVoices.findIndex(v =>
                        v.lang && v.lang.toLowerCase().includes('uz')
                    );
                    voiceSelect.value = uzVoiceIndex !== -1 ? String(uzVoiceIndex) : '';
                }
            }

            function loadVoices() {
                const voices = speechSynth.getVoices();
                if (voices.length > 0) {
                    buildVoiceDropdown(voices);
                    statusMsgSpan.innerText = "Tayyor";
                } else {
                    voiceSelect.innerHTML = '<option value="">⏳ Ovozlar yuklanmoqda...</option>';
                }
            }

            speechSynth.onvoiceschanged = loadVoices;
            loadVoices();

            function getSelectedVoice() {
                const selectedIndex = parseInt(voiceSelect.value, 10);
                if (Number.isNaN(selectedIndex) || !availableVoices[selectedIndex]) return null;
                return availableVoices[selectedIndex];
            }

            function stopSpeaking(resetStatus = true) {
                speechSynth.cancel();
                currentUtterance = null;
                isSpeaking = false;
                liveIndicatorSpan.style.display = "none";
                statusMsgSpan.innerText = resetStatus ? "To‘xtatildi" : "Tayyor";
            }

            function onSpeechEnd() {
                isSpeaking = false;
                currentUtterance = null;
                liveIndicatorSpan.style.display = "none";
                statusMsgSpan.innerText = "✅ O‘qish tugadi";
                setTimeout(() => {
                    if (!isSpeaking && !speechSynth.speaking) {
                        statusMsgSpan.innerText = "Tayyor";
                    }
                }, 1200);
            }

            function onSpeechError(event) {
                console.warn("Speech error:", event);
                isSpeaking = false;
                currentUtterance = null;
                liveIndicatorSpan.style.display = "none";
                statusMsgSpan.innerText = "⚠️ O‘qishda xatolik yuz berdi";
                setTimeout(() => {
                    if (!isSpeaking) statusMsgSpan.innerText = "Tayyor";
                }, 1500);
            }

            function speakText() {
                const textToRead = textarea.value.trim();

                if (!textToRead) {
                    statusMsgSpan.innerText = "❗ Iltimos, matn kiriting!";
                    liveIndicatorSpan.style.display = "none";
                    return;
                }

                speechSynth.cancel();
                speechSynth.resume();

                const utterance = new SpeechSynthesisUtterance(textToRead);
                utterance.rate = parseFloat(rateSlider.value);
                utterance.pitch = parseFloat(pitchSlider.value);
                utterance.volume = 1;

                const selectedVoice = getSelectedVoice();
                if (selectedVoice) {
                    utterance.voice = selectedVoice;
                    utterance.lang = selectedVoice.lang || 'uz-UZ';
                } else {
                    utterance.lang = 'uz-UZ';
                }

                utterance.onstart = () => {
                    isSpeaking = true;
                    statusMsgSpan.innerText = "🔊 Matn o‘qilmoqda...";
                    liveIndicatorSpan.style.display = "inline-flex";
                };

                utterance.onend = onSpeechEnd;
                utterance.onerror = onSpeechError;

                currentUtterance = utterance;
                speechSynth.speak(utterance);
            }

            function loadSampleText() {
                textarea.value = `Assalomu alaykum! Xush kelibsiz.
Bu matnni ovoz bilan o‘qish dasturi sizga har qanday matnni tinglash imkoniyatini beradi.
Siz tezlik va balandlikni o‘zgartirib, turli ovozlarni sinab ko‘rishingiz mumkin.
O‘zbek tilida matnlar bilan ishlash uchun mos ovozni tanlang va tugmani bosing.`;
                statusMsgSpan.innerText = "Namuna matn yuklandi.";
            }

            function clearText() {
                if (isSpeaking) stopSpeaking(true);
                textarea.value = "";
                statusMsgSpan.innerText = "Matn tozalandi";
                setTimeout(() => {
                    if (!isSpeaking && !speechSynth.speaking) {
                        statusMsgSpan.innerText = "Tayyor";
                    }
                }, 1000);
            }

            readBtn.addEventListener('click', speakText);
            stopBtn.addEventListener('click', () => stopSpeaking(true));
            sampleBtn.addEventListener('click', () => {
                if (isSpeaking) stopSpeaking(true);
                loadSampleText();
            });
            clearBtn.addEventListener('click', () => {
                if (isSpeaking) stopSpeaking(true);
                clearText();
            });

            window.addEventListener('beforeunload', () => {
                speechSynth.cancel();
            });
        })();
    </script>
</body>
</html>
