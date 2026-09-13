(() => {
  'use strict';
  const cv = document.getElementById('game'); const ctx = cv.getContext('2d');
  const W = cv.width, H = cv.height;
  const dpr = Math.max(1, Math.min(3, window.devicePixelRatio || 1));
  cv.width = W * dpr; cv.height = H * dpr; ctx.scale(dpr, dpr);
  const youEl = document.getElementById('you'), cpuEl = document.getElementById('cpu'), drawEl = document.getElementById('draw');
  const overlay = document.getElementById('overlay'), ovTitle = document.getElementById('ov-title'), ovSub = document.getElementById('ov-sub');
  const N = 15, CELL = W / N;
  let board, over;

  function xy(idx) { return [Math.floor(idx / N), idx % N]; }
  function checkFive(idx, p) {
    const [r, c] = xy(idx); const dirs = [[1, 0], [0, 1], [1, 1], [1, -1]];
    for (const [dr, dc] of dirs) {
      let cnt = 1;
      for (let s = 1; s < 5; s++) { const nr = r + dr * s, nc = c + dc * s; if (nr < 0 || nr >= N || nc < 0 || nc >= N || board[nr * N + nc] !== p) break; cnt++; }
      for (let s = 1; s < 5; s++) { const nr = r - dr * s, nc = c - dc * s; if (nr < 0 || nr >= N || nc < 0 || nc >= N || board[nr * N + nc] !== p) break; cnt++; }
      if (cnt >= 5) return true;
    }
    return false;
  }
  function wouldWin(p, idx) { board[idx] = p; const w = checkFive(idx, p); board[idx] = 0; return w; }

  function cpuMove() {
    const empt = []; for (let i = 0; i < N * N; i++) if (!board[i]) empt.push(i);
    if (!empt.length) { over = true; drawEl.textContent = +drawEl.textContent + 1; ovTitle.textContent = '平局'; overlay.classList.remove('hidden'); return; }
    for (const i of empt) if (wouldWin(2, i)) { board[i] = 2; return cpuDone(i); }
    for (const i of empt) if (wouldWin(1, i)) { board[i] = 2; return cpuDone(i); }
    let best = empt[0], bestS = -1;
    for (const i of empt) {
      let s = 0; const [r, c] = xy(i);
      for (let dr = -2; dr <= 2; dr++) for (let dc = -2; dc <= 2; dc++) { const nr = r + dr, nc = c + dc; if (nr >= 0 && nr < N && nc >= 0 && nc < N && board[nr * N + nc] === 2) s += 2; }
      s += (N - Math.abs(r - 7) + N - Math.abs(c - 7)); // 中心偏好
      if (s > bestS) { bestS = s; best = i; }
    }
    board[best] = 2; cpuDone(best);
  }
  function cpuDone(idx) {
    if (checkFive(idx, 2)) { over = true; cpuEl.textContent = +cpuEl.textContent + 1; ovTitle.textContent = '电脑赢了'; ovSub.textContent = '五子连珠'; overlay.classList.remove('hidden'); return; }
    if (board.every(v => v)) { over = true; drawEl.textContent = +drawEl.textContent + 1; ovTitle.textContent = '平局'; overlay.classList.remove('hidden'); }
  }
  function clickCell(idx) {
    if (over || board[idx]) return;
    board[idx] = 1;
    if (checkFive(idx, 1)) { over = true; youEl.textContent = +youEl.textContent + 1; ovTitle.textContent = '你赢了！'; ovSub.textContent = '五子连珠'; overlay.classList.remove('hidden'); return; }
    cpuMove();
  }
  function draw() {
    ctx.fillStyle = '#e8c98a'; ctx.fillRect(0, 0, W, H);
    ctx.strokeStyle = '#9c7b3f'; ctx.lineWidth = 1;
    for (let i = 0; i < N; i++) { ctx.beginPath(); ctx.moveTo(i * CELL, 0); ctx.lineTo(i * CELL, H); ctx.stroke(); ctx.beginPath(); ctx.moveTo(0, i * CELL); ctx.lineTo(W, i * CELL); ctx.stroke(); }
    for (let i = 0; i < N * N; i++) {
      if (!board[i]) continue; const [r, c] = xy(i); const cx = c * CELL + CELL / 2, cy = r * CELL + CELL / 2;
      ctx.fillStyle = board[i] === 1 ? '#111' : '#f5f5f5'; ctx.beginPath(); ctx.arc(cx, cy, CELL * 0.42, 0, Math.PI * 2); ctx.fill();
      ctx.strokeStyle = '#000'; ctx.lineWidth = 1; ctx.stroke();
    }
  }
  function pick(e) {
    const rect = cv.getBoundingClientRect(); const px = (e.clientX - rect.left) / rect.width * W, py = (e.clientY - rect.top) / rect.height * H;
    const c = Math.round(px / CELL - 0.5), r = Math.round(py / CELL - 0.5);
    if (r < 0 || r >= N || c < 0 || c >= N) return -1; return r * N + c;
  }
  cv.addEventListener('click', e => { const i = pick(e); if (i >= 0) clickCell(i); });
  cv.addEventListener('touchend', e => { const t = e.changedTouches[0]; const rect = cv.getBoundingClientRect(); const px = (t.clientX - rect.left) / rect.width * W, py = (t.clientY - rect.top) / rect.height * H; const c = Math.round(px / CELL - 0.5), r = Math.round(py / CELL - 0.5); if (r >= 0 && r < N && c >= 0 && c < N) clickCell(r * N + c); }, { passive: true });
  document.getElementById('new').addEventListener('click', reset);
  document.getElementById('ov-btn').addEventListener('click', reset);
  function reset() { board = Array(N * N).fill(0); over = false; overlay.classList.add('hidden'); }
  function loop() { draw(); requestAnimationFrame(loop); }
  reset(); requestAnimationFrame(loop);
})();
