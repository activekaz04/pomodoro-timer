<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ポモドーロタイマー</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Comic Sans MS', 'Hiragino Maru Gothic ProN', 'メイリオ', 'Meiryo', cursive, sans-serif;
            background: #000000;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
        }

        .container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            text-align: center;
            max-width: 400px;
            width: 90%;
        }

        h1 {
            font-size: 2.2em;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            font-weight: bold;
            letter-spacing: 0px;
            white-space: nowrap;
            text-align: center;
            width: 100%;
            display: block;
        }

        .timer-display {
            font-size: 4em;
            font-weight: 900;
            margin: 30px 0;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            letter-spacing: 2px;
        }

        .session-info {
            font-size: 1.2em;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .progress-bar {
            width: 100%;
            height: 8px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 4px;
            margin: 20px 0;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #ff6b6b, #ffa500);
            border-radius: 4px;
            transition: width 0.1s ease;
        }

        .controls {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 30px;
        }

        button {
            padding: 15px 25px;
            font-size: 1.1em;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-family: 'Comic Sans MS', 'Hiragino Maru Gothic ProN', 'メイリオ', 'Meiryo', cursive, sans-serif;
        }

        .start-btn {
            background: linear-gradient(45deg, #4CAF50, #45a049);
            color: white;
        }

        .pause-btn {
            background: linear-gradient(45deg, #ff9800, #f57c00);
            color: white;
        }

        .reset-btn {
            background: linear-gradient(45deg, #f44336, #d32f2f);
            color: white;
        }

        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
        }

        button:active {
            transform: translateY(0);
        }

        .work-phase {
            color: #ffeb3b;
        }

        .break-phase {
            color: #4caf50;
        }

        .settings {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
        }

        .setting-group {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 10px 0;
        }

        .setting-group label {
            font-size: 0.9em;
        }

        .setting-group input {
            width: 60px;
            padding: 5px;
            border: none;
            border-radius: 5px;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            text-align: center;
        }

        .setting-group input::placeholder {
            color: rgba(255, 255, 255, 0.7);
        }

        .stats {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
        }

        .stat-item {
            display: flex;
            justify-content: space-between;
            margin: 10px 0;
            font-size: 0.9em;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .pulsing {
            animation: pulse 1s infinite;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>ポモドーロタイマー</h1>
        
        <div class="timer-display" id="timerDisplay">25:00</div>
        
        <div class="session-info">
            <span id="sessionType" class="work-phase">作業時間</span>
            <span id="sessionCount"> - セッション 1</span>
        </div>
        
        <div class="progress-bar">
            <div class="progress-fill" id="progressFill"></div>
        </div>
        
        <div class="controls">
            <button class="start-btn" id="startBtn">開始</button>
            <button class="pause-btn" id="pauseBtn" style="display: none;">一時停止</button>
            <button class="reset-btn" id="resetBtn">リセット</button>
        </div>
        
        <div class="settings">
            <div class="setting-group">
                <label>作業時間 (分):</label>
                <input type="number" id="workTime" value="25" min="1" max="60">
            </div>
            <div class="setting-group">
                <label>休憩時間 (分):</label>
                <input type="number" id="breakTime" value="5" min="1" max="30">
            </div>
            <div class="setting-group">
                <label>長休憩時間 (分):</label>
                <input type="number" id="longBreakTime" value="15" min="1" max="60">
            </div>
        </div>
        
        <div class="stats">
            <div class="stat-item">
                <span>完了セッション:</span>
                <span id="completedSessions">0</span>
            </div>
            <div class="stat-item">
                <span>今日の作業時間:</span>
                <span id="totalWorkTime">0分</span>
            </div>
        </div>
    </div>

    <script>
        class PomodoroTimer {
            constructor() {
                this.isRunning = false;
                this.isPaused = false;
                this.isWorkPhase = true;
                this.sessionCount = 1;
                this.completedSessions = 0;
                this.totalWorkTime = 0;
                this.timeLeft = 25 * 60; // 25 minutes in seconds
                this.totalTime = 25 * 60;
                this.interval = null;
                
                this.initializeElements();
                this.setupEventListeners();
                this.updateDisplay();
            }

            initializeElements() {
                this.timerDisplay = document.getElementById('timerDisplay');
                this.sessionType = document.getElementById('sessionType');
                this.sessionCountDisplay = document.getElementById('sessionCount');
                this.progressFill = document.getElementById('progressFill');
                this.startBtn = document.getElementById('startBtn');
                this.pauseBtn = document.getElementById('pauseBtn');
                this.resetBtn = document.getElementById('resetBtn');
                this.workTimeInput = document.getElementById('workTime');
                this.breakTimeInput = document.getElementById('breakTime');
                this.longBreakTimeInput = document.getElementById('longBreakTime');
                this.completedSessionsDisplay = document.getElementById('completedSessions');
                this.totalWorkTimeDisplay = document.getElementById('totalWorkTime');
            }

            setupEventListeners() {
                this.startBtn.addEventListener('click', () => this.start());
                this.pauseBtn.addEventListener('click', () => this.pause());
                this.resetBtn.addEventListener('click', () => this.reset());
                
                [this.workTimeInput, this.breakTimeInput, this.longBreakTimeInput].forEach(input => {
                    input.addEventListener('change', () => this.updateTimeSettings());
                });
            }

            start() {
                if (!this.isRunning) {
                    this.isRunning = true;
                    this.isPaused = false;
                    this.startBtn.style.display = 'none';
                    this.pauseBtn.style.display = 'inline-block';
                    
                    this.interval = setInterval(() => {
                        this.tick();
                    }, 1000);
                }
            }

            pause() {
                if (this.isRunning) {
                    this.isRunning = false;
                    this.isPaused = true;
                    this.pauseBtn.style.display = 'none';
                    this.startBtn.style.display = 'inline-block';
                    this.startBtn.textContent = '再開';
                    
                    clearInterval(this.interval);
                }
            }

            reset() {
                this.isRunning = false;
                this.isPaused = false;
                clearInterval(this.interval);
                
                this.startBtn.style.display = 'inline-block';
                this.pauseBtn.style.display = 'none';
                this.startBtn.textContent = '開始';
                
                this.updateTimeSettings();
                this.updateDisplay();
                this.timerDisplay.classList.remove('pulsing');
            }

            tick() {
                this.timeLeft--;
                this.updateDisplay();
                
                if (this.timeLeft <= 0) {
                    this.completeSession();
                }
                
                // 最後の10秒でパルス効果
                if (this.timeLeft <= 10 && this.timeLeft > 0) {
                    this.timerDisplay.classList.add('pulsing');
                } else {
                    this.timerDisplay.classList.remove('pulsing');
                }
            }

            completeSession() {
                this.isRunning = false;
                clearInterval(this.interval);
                this.timerDisplay.classList.remove('pulsing');
                
                // 通知音を鳴らす（可能な場合）
                this.playNotificationSound();
                
                if (this.isWorkPhase) {
                    this.completedSessions++;
                    this.totalWorkTime += parseInt(this.workTimeInput.value);
                    this.updateStats();
                    
                    // 4セッション完了後は長休憩
                    if (this.completedSessions % 4 === 0) {
                        this.switchToLongBreak();
                    } else {
                        this.switchToBreak();
                    }
                } else {
                    this.switchToWork();
                }
                
                this.startBtn.style.display = 'inline-block';
                this.pauseBtn.style.display = 'none';
                this.startBtn.textContent = '開始';
                this.updateDisplay();
            }

            switchToWork() {
                this.isWorkPhase = true;
                this.sessionCount++;
                this.timeLeft = parseInt(this.workTimeInput.value) * 60;
                this.totalTime = this.timeLeft;
                this.sessionType.textContent = '作業時間';
                this.sessionType.className = 'work-phase';
                this.updateSessionCount();
            }

            switchToBreak() {
                this.isWorkPhase = false;
                this.timeLeft = parseInt(this.breakTimeInput.value) * 60;
                this.totalTime = this.timeLeft;
                this.sessionType.textContent = '休憩時間';
                this.sessionType.className = 'break-phase';
            }

            switchToLongBreak() {
                this.isWorkPhase = false;
                this.timeLeft = parseInt(this.longBreakTimeInput.value) * 60;
                this.totalTime = this.timeLeft;
                this.sessionType.textContent = '長休憩時間';
                this.sessionType.className = 'break-phase';
            }

            updateTimeSettings() {
                if (!this.isRunning && !this.isPaused) {
                    if (this.isWorkPhase) {
                        this.timeLeft = parseInt(this.workTimeInput.value) * 60;
                    } else {
                        this.timeLeft = parseInt(this.breakTimeInput.value) * 60;
                    }
                    this.totalTime = this.timeLeft;
                }
            }

            updateDisplay() {
                const minutes = Math.floor(this.timeLeft / 60);
                const seconds = this.timeLeft % 60;
                this.timerDisplay.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
                
                // プログレスバーの更新
                const progress = ((this.totalTime - this.timeLeft) / this.totalTime) * 100;
                this.progressFill.style.width = `${progress}%`;
                
                this.updateSessionCount();
            }

            updateSessionCount() {
                this.sessionCountDisplay.textContent = ` - セッション ${this.sessionCount}`;
            }

            updateStats() {
                this.completedSessionsDisplay.textContent = this.completedSessions;
                this.totalWorkTimeDisplay.textContent = `${this.totalWorkTime}分`;
            }

            playNotificationSound() {
                // Web Audio APIを使用して通知音を作成
                try {
                    const audioContext = new (window.AudioContext || window.webkitAudioContext)();
                    const oscillator = audioContext.createOscillator();
                    const gainNode = audioContext.createGain();
                    
                    oscillator.connect(gainNode);
                    gainNode.connect(audioContext.destination);
                    
                    oscillator.frequency.value = 800;
                    oscillator.type = 'sine';
                    
                    gainNode.gain.setValueAtTime(0.1, audioContext.currentTime);
                    gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.5);
                    
                    oscillator.start(audioContext.currentTime);
                    oscillator.stop(audioContext.currentTime + 0.5);
                } catch (e) {
                    console.log('オーディオ通知を再生できませんでした');
                }
            }
        }

        // タイマーを初期化
        const timer = new PomodoroTimer();
    </script>
</body>
</html>
