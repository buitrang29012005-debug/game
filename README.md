[gemini-code-1788935150573.html](https://github.com/user-attachments/files/32547674/gemini-code-1788935150573.html)
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>웹 미니게임 모음 (Mini Game Hub)</title>
    <style>
        :root {
            --bg-color: #0f172a;
            --card-bg: #1e293b;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --accent: #6366f1;
            --accent-hover: #4f46e5;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 20px;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
        }

        header h1 {
            font-size: 2.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #a5b4fc, #6366f1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }

        header p {
            color: var(--text-secondary);
            font-size: 1.1rem;
        }

        /* 게임 카드 그리드 레이아웃 */
        .game-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 24px;
            width: 100%;
            max-width: 1100px;
        }

        /* 게임 카드 스타일 */
        .game-card {
            background-color: var(--card-bg);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            transition: transform 0.25s ease, box-shadow 0.25s ease;
            display: flex;
            flex-direction: column;
            text-decoration: none;
            color: inherit;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .game-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(99, 102, 241, 0.25);
            border-color: rgba(99, 102, 241, 0.4);
        }

        /* 썸네일 영역 (CSS SVG 디자인) */
        .thumbnail {
            height: 180px;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        /* 1번 카드 썸네일 배경 (주사위) */
        .thumb-dice {
            background: linear-gradient(135deg, #4f46e5, #818cf8);
        }
        /* 2번 카드 썸네일 배경 (빙고) */
        .thumb-bingo {
            background: linear-gradient(135deg, #059669, #34d399);
        }
        /* 3번 카드 썸네일 배경 (블록 블라스트) */
        .thumb-block {
            background: linear-gradient(135deg, #1e1b4b, #312e81);
        }
        /* 4번 카드 썸네일 배경 (스네이크) */
        .thumb-snake {
            background: linear-gradient(135deg, #064e3b, #047857);
        }

        .thumbnail svg {
            width: 80px;
            height: 80px;
            filter: drop-shadow(0 6px 10px rgba(0,0,0,0.3));
            transition: transform 0.3s ease;
        }

        .game-card:hover .thumbnail svg {
            transform: scale(1.15) rotate(5deg);
        }

        /* 카드 내용 레이아웃 */
        .card-content {
            padding: 20px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .card-title {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 8px;
        }

        .card-desc {
            font-size: 0.95rem;
            color: var(--text-secondary);
            line-height: 1.5;
            margin-bottom: 20px;
            flex-grow: 1;
        }

        .play-btn {
            background-color: var(--accent);
            color: #fff;
            padding: 10px 16px;
            border-radius: 8px;
            font-weight: 600;
            text-align: center;
            transition: background-color 0.2s;
        }

        .game-card:hover .play-btn {
            background-color: var(--accent-hover);
        }

        footer {
            margin-top: 60px;
            color: var(--text-secondary);
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <header>
        <h1>🎮 웹 미니게임 포털</h1>
        <p>원하는 게임을 선택하여 즐겨보세요!</p>
    </header>

    <main class="game-grid">

        <!-- 1. 주사위 게임 -->
        <a href="01_dice.html" class="game-card">
            <div class="thumbnail thumb-dice">
                <!-- 주사위 아이콘 SVG -->
                <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <rect x="3" y="3" width="18" height="18" rx="4" ry="4"/>
                    <circle cx="8.5" cy="8.5" r="1.5" fill="white"/>
                    <circle cx="12" cy="12" r="1.5" fill="white"/>
                    <circle cx="15.5" cy="15.5" r="1.5" fill="white"/>
                    <circle cx="15.5" cy="8.5" r="1.5" fill="white"/>
                    <circle cx="8.5" cy="15.5" r="1.5" fill="white"/>
                </svg>
            </div>
            <div class="card-content">
                <h2 class="card-title">🎲 주사위 3개 게임</h2>
                <p class="card-desc">3개의 주사위를 굴려 총합을 계산하고 높은 점수와 잭팟에 도전하는 간단한 행운 게임입니다.</p>
                <div class="play-btn">게임하기</div>
            </div>
        </a>

        <!-- 2. 빙고 게임 -->
        <a href="02_dice.html" class="game-card">
            <div class="thumbnail thumb-bingo">
                <!-- 빙고 보드 아이콘 SVG -->
                <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <rect x="3" y="3" width="18" height="18" rx="2" ry="2"/>
                    <line x1="9" y1="3" x2="9" y2="21"/>
                    <line x1="15" y1="3" x2="15" y2="21"/>
                    <line x1="3" y1="9" x2="21" y2="9"/>
                    <line x1="3" y1="15" x2="21" y2="15"/>
                </svg>
            </div>
            <div class="card-content">
                <h2 class="card-title">🎯 5x5 웹 빙고 게임</h2>
                <p class="card-desc">1부터 25까지 무작위로 배치된 숫자를 하나씩 선택하며 5줄의 빙고를 완성하는 퍼즐 게임입니다.</p>
                <div class="play-btn">게임하기</div>
            </div>
        </a>

        <!-- 3. 블록 블라스트 -->
        <a href="03_dice.html" class="game-card">
            <div class="thumbnail thumb-block">
                <!-- 블록 조각 아이콘 SVG -->
                <svg viewBox="0 0 24 24" fill="none" stroke="#e94560" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <rect x="3" y="3" width="7" height="7" rx="1" fill="#e94560"/>
                    <rect x="14" y="3" width="7" height="7" rx="1" fill="#e94560"/>
                    <rect x="14" y="14" width="7" height="7" rx="1" fill="#e94560"/>
                    <rect x="3" y="14" width="7" height="7" rx="1" fill="#0f3460"/>
                </svg>
            </div>
            <div class="card-content">
                <h2 class="card-title">🧩 블록 블라스트 (Block Blast)</h2>
                <p class="card-desc">8x8 보드 위에 여러 모양의 블록을 드래그해서 맞추고 가로·세로 줄을 제거하여 점수를 얻는 퍼즐 게임입니다.</p>
                <div class="play-btn">게임하기</div>
            </div>
        </a>

        <!-- 4. 스네이크 게임 -->
        <a href="04_dice.html" class="game-card">
            <div class="thumbnail thumb-snake">
                <!-- 뱀 아이콘 SVG -->
                <svg viewBox="0 0 24 24" fill="none" stroke="#4ecca3" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M18 15a3 3 0 0 1-3 3H9a3 3 0 0 1-3-3 3 3 0 0 1 3-3h6a3 3 0 0 0 3-3 3 3 0 0 0-3-3H6" />
                    <circle cx="5" cy="6" r="1" fill="#4ecca3" />
                </svg>
            </div>
            <div class="card-content">
                <h2 class="card-title">🐍 스네이크 게임 (Snake)</h2>
                <p class="card-desc">방향키 또는 화면 버튼으로 뱀을 조종하며 사과를 먹어 몸집을 키우고 기록에 도전하는 클래식 게임입니다.</p>
                <div class="play-btn">게임하기</div>
            </div>
        </a>

    </main>

    <footer>
        <p>© 2026 Web Mini Game Arcade. All rights reserved.</p>
    </footer>

</body>
</html>
