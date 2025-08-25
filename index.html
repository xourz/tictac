<!DOCTYPE html><html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Tic Tac Toe</title>
  <style>
    :root{
      --bg:#0f172a;        /* slate-900 */
      --panel:#111827;     /* gray-900 */
      --panel-2:#1f2937;   /* gray-800 */
      --accent:#38bdf8;    /* sky-400 */
      --accent-2:#22d3ee;  /* cyan-400 */
      --text:#e5e7eb;      /* gray-200 */
      --muted:#9ca3af;     /* gray-400 */
      --win:#22c55e;       /* green-500 */
      --lose:#ef4444;      /* red-500 */
    }
    *{box-sizing:border-box}
    body{
      margin:0; min-height:100svh; display:grid; place-items:center; background:radial-gradient(1200px 600px at 20% -10%, #0b1224, transparent),
      radial-gradient(1000px 600px at 120% 120%, #0b1224, transparent), var(--bg);
      color:var(--text); font-family:ui-rounded, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji", "Segoe UI Emoji";
    }
    .card{
      width:min(92vw, 780px); background:linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
      border:1px solid rgba(255,255,255,.08); backdrop-filter: blur(10px);
      border-radius:24px; padding:20px; box-shadow:0 20px 60px rgba(0,0,0,.35);
    }
    h1{margin:4px 0 14px; letter-spacing:.5px; font-size:clamp(22px, 2.8vw, 28px)}
    .top{display:flex; gap:14px; flex-wrap:wrap; align-items:center; justify-content:space-between}
    .mode{
      display:flex; gap:8px; align-items:center; padding:8px 10px; background:var(--panel-2); border-radius:999px; border:1px solid rgba(255,255,255,.08)
    }
    .mode button{border:0; background:transparent; color:var(--muted); padding:8px 14px; border-radius:999px; cursor:pointer; font-weight:700}
    .mode button.active{background:linear-gradient(90deg, var(--accent), var(--accent-2)); color:#0b1224; box-shadow:0 6px 20px rgba(56,189,248,.35)}.board{display:grid; grid-template-columns:repeat(3, 1fr); gap:12px; margin:18px 0}
.cell{
  width:min(24vw, 160px); aspect-ratio:1/1; display:grid; place-items:center; font-size:clamp(38px, 10vw, 72px);
  background:var(--panel); border-radius:20px; border:1px solid rgba(255,255,255,.08); color:var(--text);
  cursor:pointer; user-select:none; transition:transform .12s ease, box-shadow .2s ease, background .2s ease
}
.cell:hover{ transform: translateY(-2px); box-shadow:0 12px 28px rgba(0,0,0,.35); }
.cell:disabled{ cursor:not-allowed; opacity:.85 }
.cell.win{ outline:2px solid var(--win); box-shadow:0 0 0 4px rgba(34,197,94,.2) inset, 0 12px 24px rgba(34,197,94,.25) }

.status{ display:flex; gap:14px; align-items:center; justify-content:space-between; flex-wrap:wrap }
.status .turn{ font-weight:700 }
.status .badge{ padding:6px 10px; border-radius:999px; background:var(--panel-2); border:1px solid rgba(255,255,255,.08); color:var(--muted) }

.scores{ display:flex; gap:10px; align-items:center }
.score{ display:flex; gap:8px; align-items:center; background:var(--panel-2); border:1px solid rgba(255,255,255,.08); padding:8px 12px; border-radius:14px }
.tag{ font-weight:800; letter-spacing:.5px }

.actions{ display:flex; gap:10px; flex-wrap:wrap; justify-content:flex-end }
.btn{ border:0; padding:10px 14px; border-radius:12px; cursor:pointer; font-weight:700; letter-spacing:.2px }
.btn.primary{ background:linear-gradient(90deg, var(--accent), var(--accent-2)); color:#071122; box-shadow:0 10px 30px rgba(56,189,248,.35) }
.btn.ghost{ background:transparent; color:var(--text); border:1px solid rgba(255,255,255,.12) }
.footer{margin-top:12px; color:var(--muted); font-size:13px}
.x{ color:#fbbf24 } /* amber */
.o{ color:#60a5fa } /* blue */

  </style>
</head>
<body>
  <div class="card">
    <div class="top">
      <h1>🎮 Tic Tac Toe</h1>
      <div class="mode" role="tablist" aria-label="Mode Permainan">
        <button id="mode-pvp" class="active" aria-selected="true">👥 Player vs Player</button>
        <button id="mode-ai">🤖 Player vs AI</button>
      </div>
    </div><div class="status" aria-live="polite">
  <div class="turn">Giliran: <span id="turn" class="badge">X</span></div>
  <div class="scores">
    <div class="score"><span class="tag x">X</span><span id="scoreX">0</span></div>
    <div class="score"><span class="tag o">O</span><span id="scoreO">0</span></div>
    <div class="score"><span class="tag">Seri</span><span id="scoreD">0</span></div>
  </div>
</div>

<div class="board" id="board" role="grid" aria-label="Papan Tic Tac Toe"></div>

<div class="actions">
  <button id="resetRound" class="btn ghost">Ulangi Ronde</button>
  <button id="resetAll" class="btn primary">Reset Skor</button>
</div>
<p class="footer">Tip: di mode AI, kamu bermain sebagai <strong>X</strong>. AI akan gerak otomatis sebagai <strong>O</strong>.</p>

  </div>  <script>
    const boardEl = document.getElementById('board');
    const turnEl = document.getElementById('turn');
    const scoreXEl = document.getElementById('scoreX');
    const scoreOEl = document.getElementById('scoreO');
    const scoreDEl = document.getElementById('scoreD');
    const resetRoundBtn = document.getElementById('resetRound');
    const resetAllBtn = document.getElementById('resetAll');
    const modePvpBtn = document.getElementById('mode-pvp');
    const modeAiBtn = document.getElementById('mode-ai');

    let board = Array(9).fill(null);
    let current = 'X';
    let lock = false; // prevent input during AI move
    let mode = 'pvp'; // 'pvp' | 'ai'
    let scores = { X:0, O:0, D:0 };

    const lines = [
      [0,1,2],[3,4,5],[6,7,8], // rows
      [0,3,6],[1,4,7],[2,5,8], // cols
      [0,4,8],[2,4,6]          // diags
    ];

    function createBoard(){
      boardEl.innerHTML = '';
      for(let i=0;i<9;i++){
        const btn = document.createElement('button');
        btn.className = 'cell';
        btn.type = 'button';
        btn.setAttribute('data-i', i);
        btn.setAttribute('aria-label', 'Kotak '+(i+1));
        btn.addEventListener('click', onCellClick);
        boardEl.appendChild(btn);
      }
      render();
    }

    function onCellClick(e){
      if(lock) return;
      const idx = +e.currentTarget.dataset.i;
      if(board[idx] || winner(board)) return; // ignore filled or finished
      board[idx] = current;
      current = current === 'X' ? 'O' : 'X';
      render();

      const w = winner(board);
      if(w){ finish(w); return; }
      if(full(board)){ finish('D'); return; }

      if(mode === 'ai' && current === 'O'){
        lock = true;
        setTimeout(()=>{
          const move = bestMove(board, 'O');
          board[move] = 'O';
          current = 'X';
          lock = false;
          render();
          const w2 = winner(board);
          if(w2){ finish(w2); return; }
          if(full(board)){ finish('D'); return; }
        }, 400);
      }
    }

    function render(){
      [...boardEl.children].forEach((btn,i)=>{
        btn.textContent = board[i] ? board[i] : '';
        btn.disabled = !!winner(board) || lock || !!board[i];
        btn.classList.remove('win');
      });
      turnEl.textContent = current;
      scoreXEl.textContent = scores.X;
      scoreOEl.textContent = scores.O;
      scoreDEl.textContent = scores.D;

      const w = winner(board);
      if(w && w !== 'D'){
        const line = winLine(board);
        if(line) line.forEach(i=> boardEl.children[i].classList.add('win'));
      }
    }

    function finish(w){
      if(w === 'D'){ scores.D++; }
      else { scores[w]++; }
      // disable all cells
      [...boardEl.children].forEach(btn=> btn.disabled = true);
      render();
    }

    function resetRound(){
      board = Array(9).fill(null);
      current = 'X';
      lock = false;
      render();
    }

    function resetAll(){
      scores = {X:0,O:0,D:0};
      resetRound();
    }

    function full(b){ return b.every(Boolean); }

    function winner(b){
      for(const [a,c,d] of lines){
        if(b[a] && b[a]===b[c] && b[a]===b[d]) return b[a];
      }
      if(full(b)) return 'D';
      return null;
    }

    function winLine(b){
      for(const [a,c,d] of lines){
        if(b[a] && b[a]===b[c] && b[a]===b[d]) return [a,c,d];
      }
      return null;
    }

    // Minimax for perfect AI (O plays optimally)
    function bestMove(b, ai){
      let bestScore = -Infinity, move = -1;
      for(let i=0;i<9;i++){
        if(!b[i]){
          b[i] = ai;
          const score = minimax(b, 0, false, ai);
          b[i] = null;
          if(score > bestScore){ bestScore = score; move = i; }
        }
      }
      return move;
    }

    function minimax(b, depth, isMax, ai){
      const result = winner(b);
      if(result){
        if(result === 'D') return 0;
        return result === ai ? 10 - depth : depth - 10;
      }
      const human = ai === 'O' ? 'X' : 'O';
      if(isMax){
        let best = -Infinity;
        for(let i=0;i<9;i++) if(!b[i]){ b[i]=ai; best=Math.max(best, minimax(b, depth+1, false, ai)); b[i]=null; }
        return best;
      } else {
        let best = Infinity;
        for(let i=0;i<9;i++) if(!b[i]){ b[i]=human; best=Math.min(best, minimax(b, depth+1, true, ai)); b[i]=null; }
        return best;
      }
    }

    // UI bindings
    resetRoundBtn.addEventListener('click', resetRound);
    resetAllBtn.addEventListener('click', resetAll);
    modePvpBtn.addEventListener('click', ()=>{ mode='pvp'; modePvpBtn.classList.add('active'); modeAiBtn.classList.remove('active'); resetRound(); });
    modeAiBtn.addEventListener('click', ()=>{ mode='ai'; modeAiBtn.classList.add('active'); modePvpBtn.classList.remove('active'); resetRound(); });

    // init
    createBoard();
  </script></body>
</html>
