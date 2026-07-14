<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>홀짝 주사위 게임</title>
    <style>
        body {
            font-family: 'Pretendard', -apple-system, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background-color: #000000; 
            margin: 0;
            color: #333;
            padding: 20px;
            box-sizing: border-box;
            overflow-x: hidden;
        }

        /* 폭죽 캔버스 */
        #confetti-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 9999;
        }

        /* 공통 박스 디자인 */
        .box-container {
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(255, 255, 255, 0.1); 
            text-align: center;
            width: 380px; 
            position: relative;
            z-index: 10; 
            box-sizing: border-box;
            margin-bottom: 20px;
        }

        /* 로그인 전용 스타일 */
        .login-input {
            width: 100%; padding: 12px; margin-bottom: 12px; border: 1px solid #ccc;
            border-radius: 8px; box-sizing: border-box; font-size: 14px;
        }
        .btn-login {
            background-color: #2980b9; width: 100%; padding: 15px; font-size: 16px; margin-top: 10px; color: white; border: none; border-radius: 8px; cursor: pointer; font-weight: bold;
        }
        .btn-login:hover { opacity: 0.9; }
        .referral-section { margin-top: 15px; padding-top: 15px; border-top: 1px dashed #bdc3c7; }

        /* 게임 전용 스타일 */
        .status-board {
            display: flex; flex-direction: column; gap: 10px; background-color: #f1f2f6;
            padding: 15px; border-radius: 10px; margin-bottom: 20px; font-weight: bold; font-size: 16px;
        }
        .status-row { display: flex; justify-content: space-between; }
        .user-text { color: #2c3e50; font-size: 14px; }
        .coin-text { color: #f39c12; }
        .pot-text { color: #e74c3c; }

        .dice-display {
            font-size: 80px; margin: 20px 0; color: #2c3e50; font-weight: bold;
            height: 90px; display: flex; align-items: center; justify-content: center;
            background-color: #ecf0f1; border-radius: 15px;
        }

        .btn-group { display: flex; gap: 10px; justify-content: center; margin-bottom: 15px; }
        .btn-group-wrap { display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-bottom: 15px; }

        button {
            flex: 1; padding: 12px 8px; font-size: 15px; font-weight: bold; border: none;
            border-radius: 8px; cursor: pointer; transition: all 0.2s; color: white;
        }
        button:hover { opacity: 0.9; transform: translateY(-1px); }
        button:disabled { background-color: #bdc3c7; cursor: not-allowed; transform: none; }

        .btn-bet { background-color: #e67e22; min-width: 60px; }
        .btn-even { background-color: #27ae60; }
        .btn-odd { background-color: #2980b9; }
        .btn-continue { background-color: #c0392b; } 
        .btn-take { background-color: #8e44ad; }
        .btn-retry { background-color: #7f8c8d; }
        
        #result-message {
            font-size: 16px; font-weight: bold; min-height: 60px; padding: 10px;
            color: #555; display: flex; flex-direction: column; align-items: center;
            justify-content: center; margin-bottom: 15px; line-height: 1.6; word-break: keep-all; 
        }

        .highlight-multiplier { color: #e74c3c; font-size: 18px; }

        .admin-section { margin-top: 25px; border-top: 1px dashed #bdc3c7; padding-top: 15px; }
        .btn-admin-toggle { background-color: #34495e; font-size: 12px; padding: 6px 12px; width: auto; flex: none; }
        .admin-panel { display: none; margin-top: 12px; background: #f8f9fa; padding: 10px; border-radius: 8px; }
        .admin-input { padding: 8px; width: 100%; box-sizing: border-box; border-radius: 5px; border: 1px solid #ccc; text-align: center; font-size: 14px; margin-bottom: 10px; }
        .admin-btn-row { display: flex; gap: 5px; }
        .btn-admin-action { padding: 8px; width: 100%; font-size: 13px; }

        /* 외부 링크 버튼 스타일 */
        .external-link {
            display: inline-block;
            margin-top: 10px;
            color: #bdc3c7;
            text-decoration: none;
            font-size: 14px;
            transition: color 0.2s;
            z-index: 10;
        }
        .external-link:hover {
            color: #ffffff;
            text-decoration: underline;
        }
    </style>
</head>
<body>

<canvas id="confetti-canvas"></canvas>

<div class="box-container" id="login-screen">
    <h2>🔐 게임 로그인</h2>
    <input type="text" id="login-id" class="login-input" placeholder="아이디 입력 (영문/숫자)">
    <input type="password" id="login-pw" class="login-input" placeholder="비밀번호 입력">
    
    <div class="referral-section">
        <p style="font-size: 13px; color: #7f8c8d; margin-top: 0;">신규 가입 시 추천인 코드를 적으면 보너스 지급!</p>
        <input type="text" id="referral-code" class="login-input" placeholder="추천인 코드 (선택사항)">
    </div>

    <button class="btn-login" onclick="processLogin()">접속하기</button>
</div>

<div class="box-container" id="game-screen" style="display: none;">
    <h2>🎲 홀짝 주사위 게임</h2>
    
    <div class="status-board">
        <div class="status-row user-text">👤 현재 계정: <span id="current-user-id">-</span></div>
        <div class="status-row">
            <div class="coin-text">💰 내 코인: <span id="my-coins">0</span></div>
            <div class="pot-text">🔥 판돈: <span id="current-pot">0</span></div>
        </div>
    </div>
    
    <div class="dice-display" id="dice">?</div>
    
    <div id="result-message">먼저 베팅할 코인을 선택하세요!</div>

    <div class="btn-group-wrap" id="bet-buttons">
        <button class="btn-bet" onclick="selectBet(1)">1</button>
        <button class="btn-bet" onclick="selectBet(5)">5</button>
        <button class="btn-bet" onclick="selectBet(10)">10</button>
        <button class="btn-bet" onclick="selectBet(50)">50</button>
        <button class="btn-bet" onclick="selectBet(100)">100</button>
    </div>

    <div class="btn-group" id="choice-buttons" style="display: none;">
        <button class="btn-even" onclick="selectChoice('even')">짝 (Even)</button>
        <button class="btn-odd" onclick="selectChoice('odd')">홀 (Odd)</button>
    </div>

    <div class="btn-group" id="win-buttons" style="display: none;">
        <button class="btn-continue" onclick="continueGame()">계속하기 (다음 배수 도전!)</button>
        <button class="btn-take" onclick="takeReward()">보상받고 그만두기</button>
    </div>

    <div class="btn-group" id="lose-buttons" style="display: none;">
        <button class="btn-retry" onclick="resetGame()">다시 시도</button>
        <button class="btn-take" onclick="resetGame()">그만두기</button>
    </div>

    <div class="admin-section">
        <button class="btn-admin-toggle" onclick="toggleAdminView()">⚙️ 관리자 메뉴</button>
        <div class="admin-panel" id="admin-panel">
            <div id="admin-auth">
                <input type="password" id="admin-pw" class="admin-input" placeholder="비밀번호 입력">
                <button class="btn-admin-action" style="background-color: #2c3e50;" onclick="checkAdminPassword()">확인</button>
            </div>
            <div id="admin-controls" style="display: none;">
                <input type="number" id="coin-amount" class="admin-input" placeholder="코인 수 입력">
                <div class="admin-btn-row">
                    <button class="btn-admin-action" style="background-color: #27ae60;" onclick="adjustCoins('add')">코인 추가</button>
                    <button class="btn-admin-action" style="background-color: #e74c3c;" onclick="adjustCoins('remove')">코인 차감</button>
                </div>
            </div>
        </div>
    </div>
</div>

<a href="https://cafe.naver.com/" target="_blank" class="external-link">🌐 공식 커뮤니티(고객센터) 방문하기</a>

<script>
    // 구글 사이트 도구 샌드박스 오류 방지용 안전한 저장소 함수
    function safeSetItem(key, value) {
        try {
            localStorage.setItem(key, value);
        } catch (e) {
            console.warn("구글 사이트 보안 환경: 로컬 스토리지 저장이 제한되어 임시 메모리를 사용합니다.");
        }
    }

    function safeGetItem(key) {
        try {
            return localStorage.getItem(key);
        } catch (e) {
            console.warn("구글 사이트 보안 환경: 로컬 스토리지 읽기가 제한되어 초기값을 사용합니다.");
            return null;
        }
    }

    // 폭죽 이펙트
    function fireConfetti() {
        const canvas = document.getElementById('confetti-canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        let particles = [];
        for (let i = 0; i < 150; i++) {
            particles.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height - canvas.height,
                vx: (Math.random() - 0.5) * 10,
                vy: Math.random() * 10 + 5,
                color: `hsl(${Math.random() * 360}, 100%, 50%)`
            });
        }
        
        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach((p, i) => { p.x += p.vx; p.y += p.vy; ctx.fillStyle = p.color; ctx.fillRect(p.x, p.y, 8, 8); });
            if (particles[0].y < canvas.height) requestAnimationFrame(animate);
            else ctx.clearRect(0, 0, canvas.width, canvas.height);
        }
        animate();
    }

    // 전역 변수 설정
    let currentUserKey = ''; 
    let myCoins = 0;
    let initialBet = 0; let currentMultiplier = 2; let currentPot = 0; let isRolling = false; let userChoice = '';   

    const diceEl = document.getElementById('dice');
    const msgEl = document.getElementById('result-message');
    const myCoinsEl = document.getElementById('my-coins');
    const currentPotEl = document.getElementById('current-pot');
    
    const betBtns = document.getElementById('bet-buttons');
    const choiceBtns = document.getElementById('choice-buttons');
    const winBtns = document.getElementById('win-buttons');
    const loseBtns = document.getElementById('lose-buttons');

    /* 로그인 시스템 로직 */
    function processLogin() {
        const userId = document.getElementById('login-id').value.trim();
        const referral = document.getElementById('referral-code').value.trim();

        if (userId === '') {
            alert('아이디를 입력해주세요!');
            return;
        }

        currentUserKey = 'casino_coins_' + userId;
        
        // 안전한 저장소 함수 사용
        let savedCoins = safeGetItem(currentUserKey);

        if (savedCoins === null) {
            // 신규 가입 유저일 경우
            if (referral !== '') {
                alert(`추천인 코드 [${referral}] 확인!\n🎉 신규 가입 보너스 500 코인이 지급되었습니다!`);
                myCoins = 500;
            } else {
                alert(`환영합니다, ${userId}님!\n신규 계정이 생성되었습니다.`);
                myCoins = 0;
            }
        } else {
            // 기존 유저일 경우 정보 불러오기
            myCoins = parseInt(savedCoins);
            alert(`환영합니다, ${userId}님!\n계정 정보를 성공적으로 불러왔습니다.`);
        }

        // UI 업데이트 및 화면 전환
        document.getElementById('current-user-id').textContent = userId;
        updateBoard();

        document.getElementById('login-screen').style.display = 'none';
        document.getElementById('game-screen').style.display = 'block';
    }

    /* 게임 로직 */
    function updateBoard() { 
        myCoinsEl.textContent = myCoins; 
        currentPotEl.textContent = currentPot; 
        // 안전한 저장소 함수 사용
        if (currentUserKey !== '') {
            safeSetItem(currentUserKey, myCoins); 
        }
    }

    function selectBet(amount) {
        if (myCoins < amount) { alert("보유 코인이 부족합니다! 관리자 메뉴에서 충전하세요."); return; }
        myCoins -= amount; initialBet = amount; currentPot = amount; currentMultiplier = 2; updateBoard();
        betBtns.style.display = 'none'; choiceBtns.style.display = 'flex';
        msgEl.innerHTML = `<span><b>${amount}코인</b> 베팅 완료!</span><span>주사위가 짝일지 홀일지 고르세요. (현재 목표: <b>2배</b>)</span>`;
    }

    function selectChoice(choice) { if (isRolling) return; userChoice = choice; startDiceRoll(); }

    function startDiceRoll() {
        isRolling = true; choiceBtns.style.display = 'none';
        msgEl.textContent = "주사위를 마구 섞는 중... 🎲";
        
        let rollCount = 0;
        let rollInterval = setInterval(() => {
            diceEl.textContent = Math.floor(Math.random() * 6) + 1;
            rollCount++;
            if (rollCount >= 15) { clearInterval(rollInterval); finishGame(); }
        }, 80);
    }

    function finishGame() {
        isRolling = false;
        const isWin = Math.random() >= 0.8; 
        
        let finalNum;
        if (!isWin) {
            finalNum = (userChoice === 'even') ? [1, 3, 5][Math.floor(Math.random() * 3)] : [2, 4, 6][Math.floor(Math.random() * 3)];
        } else {
            finalNum = (userChoice === 'even') ? [2, 4, 6][Math.floor(Math.random() * 3)] : [1, 3, 5][Math.floor(Math.random() * 3)];
        }

        const isEven = (finalNum % 2 === 0);
        const korResult = isEven ? '짝' : '홀';
        diceEl.textContent = finalNum; 

        if (isWin) {
            currentPot = initialBet * currentMultiplier; 
            msgEl.innerHTML = `<span>정답입니다! 결과: <b>[${finalNum} / ${korResult}]</b></span>
                               <span>판돈이 <b class="highlight-multiplier">${currentMultiplier}배 (${currentPot}코인)</b>가 되었습니다! 🎉</span>`;
            currentMultiplier += 2; 
            winBtns.style.display = 'flex';
            fireConfetti(); 
        } else {
            currentPot = 0;
            msgEl.innerHTML = `<span>틀렸습니다! 결과: <b>[${finalNum} / ${korResult}]</b> 😢</span>`;
            loseBtns.style.display = 'flex';
        }
        updateBoard();
    }

    function continueGame() { winBtns.style.display = 'none'; choiceBtns.style.display = 'flex'; diceEl.textContent = '?'; msgEl.innerHTML = `<span>🔥 다음 성공 시 판돈의 <b class="highlight-multiplier">${currentMultiplier}배 (${initialBet * currentMultiplier}코인)</b> 획득!</span><span>다음 홀/짝을 신중하게 선택하세요!</span>`; }
    function takeReward() { myCoins += currentPot; msgEl.innerHTML = `<span>성공적으로 <b>${currentPot}코인</b>을 챙겼습니다! 💰</span>`; resetToMain(); }
    function resetGame() { msgEl.textContent = "베팅할 코인을 다시 선택하세요!"; resetToMain(); }
    function resetToMain() { currentPot = 0; initialBet = 0; currentMultiplier = 2; updateBoard(); winBtns.style.display = 'none'; loseBtns.style.display = 'none'; choiceBtns.style.display = 'none'; betBtns.style.display = 'flex'; diceEl.textContent = '?'; }

    /* 관리자 기능 (로그인된 유저 기준) */
    function toggleAdminView() { 
        const panel = document.getElementById('admin-panel'); 
        if (panel.style.display === 'none' || panel.style.display === '') {
            panel.style.display = 'block';
        } else {
            panel.style.display = 'none';
            document.getElementById('admin-auth').style.display = 'block';
            document.getElementById('admin-controls').style.display = 'none';
            document.getElementById('admin-pw').value = '';
        }
    }
    function checkAdminPassword() { 
        if (document.getElementById('admin-pw').value === '1111') { 
            document.getElementById('admin-auth').style.display = 'none'; 
            document.getElementById('admin-controls').style.display = 'block'; 
        } else { alert('비밀번호가 올바르지 않습니다!'); } 
    }
    function adjustCoins(mode) {
        let amount = parseInt(document.getElementById('coin-amount').value);
        if (isNaN(amount) || amount === 0) { alert('1 이상의 숫자를 입력해주세요.'); return; }
        
        amount = Math.abs(amount);

        if (mode === 'add') { 
            myCoins += amount; 
            alert(`${amount} 코인이 추가되었습니다.`); 
        } else { 
            if (myCoins < amount) {
                alert(`보유 코인(${myCoins}개)보다 많이 뺄 수 없어 0코인으로 초기화합니다.`);
                myCoins = 0;
            } else {
                myCoins -= amount; 
                alert(`${amount} 코인이 차감되었습니다.`); 
            }
        }
        
        updateBoard(); 
        document.getElementById('coin-amount').value = ''; 
    }
</script>

</body>
</html>
