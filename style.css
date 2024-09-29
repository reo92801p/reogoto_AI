let timer;
let isRunning = false;
let remainingTime = 60000;  // 1分間（60秒）をミリ秒で設定
const initialTime = remainingTime;

const display = document.getElementById('timer-display');
const startBtn = document.getElementById('start-btn');
const pauseBtn = document.getElementById('pause-btn');
const resetBtn = document.getElementById('reset-btn');

// 時間をフォーマットする関数（分、秒表示）
function formatTime(ms) {
    const totalSeconds = Math.floor(ms / 1000);
    const minutes = String(Math.floor(totalSeconds / 60)).padStart(2, '0');
    const seconds = String(totalSeconds % 60).padStart(2, '0');
    return `${minutes}:${seconds}`;
}

// タイマーの表示を更新する関数
function updateDisplay() {
    if (remainingTime > 0) {
        display.textContent = formatTime(remainingTime);
    } else {
        display.textContent = 'Thinking Time終了';
    }
}

// タイマーをスタートする関数
function startTimer() {
    if (!isRunning && remainingTime > 0) {
        isRunning = true;
        const startTime = Date.now();
        timer = setInterval(() => {
            const elapsed = Date.now() - startTime;
            remainingTime = initialTime - elapsed;
            
            if (remainingTime <= 0) {
                clearInterval(timer);
                remainingTime = 0;
                isRunning = false;
            }
            
            updateDisplay();
        }, 1000);
    }
}

// タイマーを一時停止する関数
function pauseTimer() {
    if (isRunning) {
        clearInterval(timer);
        isRunning = false;
        initialTime = remainingTime;  // 残り時間を保存
    }
}

// タイマーをリセットする関数
function resetTimer() {
    clearInterval(timer);
    isRunning = false;
    remainingTime = 60000;  // 1分間にリセット
    updateDisplay();
}

// イベントリスナーを設定
startBtn.addEventListener('click', startTimer);
pauseBtn.addEventListener('click', pauseTimer);
resetBtn.addEventListener('click', resetTimer);

// 初期表示を更新
updateDisplay();
