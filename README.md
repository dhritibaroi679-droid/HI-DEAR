<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Hi Dear 💖 from Dhriti</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600&display=swap">
<style>
  :root { --ink:#3b2a5a; --muted:#8a78a8; --card:rgba(255,255,255,.88); --line:#f0d9f5; --pink:#ff7eb6; --lav:#b79cff; --sky:#6cc6ff; --mint:#5fe3b4; --sun:#ffd166; }
  * { box-sizing: border-box; }
  html, body { height: 100%; margin: 0; }
  body { color: var(--ink); font-family: "Fredoka", system-ui, sans-serif; display: flex; flex-direction: column;
    background: linear-gradient(120deg,#ffd9ec,#d9f1ff,#e6dcff,#d9ffe9,#fff3c9); background-size: 300% 300%; animation: bg 18s ease infinite; }
  @keyframes bg { 0%,100% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } }
  button, input { font: inherit; color: inherit; }
  .hidden { display: none !important; }
  #login, #app { position: relative; z-index: 1; }

  .fl { position: fixed; bottom: -50px; z-index: 0; opacity: .55; pointer-events: none; animation: rise linear infinite; }
  @keyframes rise { to { transform: translateY(-120vh) rotate(25deg); } }
  .fx { position: fixed; bottom: -30px; z-index: 50; pointer-events: none; animation: up 2.2s ease-out forwards; }
  @keyframes up { to { transform: translateY(-110vh) rotate(40deg); opacity: 0; } }
  @keyframes bounce { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }
  @keyframes pop { from { transform: scale(.6); opacity: 0; } }
  @keyframes pulse { 50% { box-shadow: 0 0 0 6px rgba(95,227,180,.3); } }
  @keyframes fadein { from { opacity: 0; transform: translateY(6px); } }

  #login { margin: auto; width: min(350px, 90vw); display: grid; gap: 12px; text-align: center; }
  #login .chars { font-size: 3.4rem; display: flex; justify-content: center; gap: 10px; }
  #login .chars span { animation: bounce 1.6s ease-in-out infinite; }
  #login .chars span:nth-child(2) { animation-delay: .25s; font-size: 2rem; align-self: center; }
  #login .chars span:nth-child(3) { animation-delay: .5s; }
  #login h1 { font-size: 2.2rem; margin: 0; font-weight: 600; }
  #login p { margin: 0; color: var(--muted); font-size: .9rem; }
  #login input { padding: 13px; border-radius: 14px; border: 2px solid var(--line); background: var(--card); text-align: center; }
  .go, #chatForm button, #todoForm button { border: 0; border-radius: 999px; background: linear-gradient(135deg, var(--pink), var(--lav)); color: #fff; font-weight: 600; cursor: pointer; }
  .go { padding: 13px; border-radius: 14px; }
  #err { color: #d6336c; min-height: 1.2em; font-size: .9rem; }

  #app { display: flex; flex-direction: column; height: 100%; padding-top: env(safe-area-inset-top, 0px); }
  header { padding: 10px 14px; background: var(--card); border-bottom: 2px solid var(--line); display: flex; align-items: center; gap: 10px; flex-wrap: wrap; }
  .mascot { font-size: 1.9rem; animation: bounce 1.6s ease-in-out infinite; }
  .dot { width: 11px; height: 11px; border-radius: 50%; background: #c9bfe0; flex: none; }
  .dot.on { background: var(--mint); animation: pulse 1.8s infinite; }
  #status b { font-weight: 600; }
  #status small { display: block; color: var(--muted); }
  nav { margin-left: auto; display: flex; gap: 6px; }
  nav button { padding: 8px 12px; border-radius: 999px; border: 2px solid var(--line); background: #fff; cursor: pointer; }
  nav button.active { background: linear-gradient(135deg, var(--sun), var(--pink)); border-color: transparent; color: #fff; font-weight: 600; }
  @media (max-width: 480px) { nav { width: 100%; margin: 0; } nav button { flex: 1; padding: 8px 4px; } }

  main { flex: 1; min-height: 0; display: flex; flex-direction: column; }
  #chat, #todos { display: flex; flex-direction: column; flex: 1; min-height: 0; }
  #quote { margin: 10px 12px 0; padding: 10px 14px; border-radius: 18px; background: linear-gradient(135deg, #fff3c9, #ffe0f0); text-align: center; }
  #qt { display: block; font-weight: 500; animation: fadein .8s; }
  #quote small { color: var(--muted); }
  #msgs, #todoList { flex: 1; overflow-y: auto; padding: 14px; display: flex; flex-direction: column; gap: 10px; }
  .m { max-width: 80%; padding: 9px 14px; border-radius: 20px 20px 20px 6px; background: #fff; border: 2px solid var(--line); overflow-wrap: anywhere; cursor: pointer; }
  .m.me { align-self: flex-end; border-radius: 20px 20px 6px 20px; background: linear-gradient(135deg, #ff7eb6, #ff9a76); border-color: transparent; color: #fff; }
  .m.pop, .t.pop { animation: pop .35s ease-out; }
  .m time { display: block; font-size: .7rem; opacity: .65; margin-top: 2px; }
  .rx { display: flex; gap: 4px; flex-wrap: wrap; margin-top: 4px; }
  .rx span { background: rgba(255,255,255,.8); color: var(--ink); border-radius: 999px; padding: 1px 8px; font-size: .85rem; }
  .pick { display: none; gap: 4px; margin-top: 6px; }
  .m.open .pick { display: flex; }
  .pick button { border: 0; background: rgba(255,255,255,.85); border-radius: 999px; padding: 4px 8px; cursor: pointer; font-size: 1.15rem; }
  #chatForm, #todoForm { display: flex; gap: 8px; padding: 10px 12px calc(10px + env(safe-area-inset-bottom, 0px)); border-top: 2px solid var(--line); background: var(--card); }
  #chatForm input, #todoForm input { flex: 1; padding: 12px 16px; border-radius: 999px; border: 2px solid var(--line); background: #fff; }
  #chatForm button, #todoForm button { padding: 0 20px; }

  .t { background: var(--card); border: 2px solid var(--line); border-radius: 16px; padding: 10px 12px; display: flex; align-items: center; gap: 10px; }
  .t.done .tx { text-decoration: line-through; opacity: .5; }
  .t .tx { flex: 1; overflow-wrap: anywhere; }
  .t small { color: var(--muted); }
  .t input { width: 22px; height: 22px; accent-color: var(--pink); }
  .t button { border: 0; background: transparent; cursor: pointer; font-size: 1.1rem; padding: 4px; opacity: .85; }
  .t button.liked { opacity: 1; }

  #games { flex: 1; overflow-y: auto; padding: 18px 14px; display: flex; flex-direction: column; align-items: center; gap: 14px; }
  .gsel { display: flex; gap: 6px; flex-wrap: wrap; justify-content: center; }
  .gsel button { padding: 8px 14px; border-radius: 999px; border: 2px solid var(--line); background: #fff; cursor: pointer; }
  .gsel button.active { background: linear-gradient(135deg, var(--sky), var(--mint)); border-color: transparent; color: #fff; font-weight: 600; }
  .gbox { display: flex; flex-direction: column; align-items: center; gap: 14px; }
  .info { min-height: 1.4em; text-align: center; font-weight: 500; }
  .again { padding: 10px 18px; border-radius: 999px; border: 2px solid var(--line); background: #fff; cursor: pointer; }
  #board { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; width: min(320px, 85vw); }
  #board button { aspect-ratio: 1; font-size: 2.6rem; font-weight: 600; border-radius: 18px; border: 2px solid var(--line); background: #fff; cursor: pointer; }
  #board button.X { color: var(--pink); } #board button.O { color: var(--sky); }
  #c4 { display: grid; grid-template-columns: repeat(7, 1fr); gap: 5px; width: min(340px, 92vw); padding: 8px; background: var(--sky); border-radius: 18px; }
  #c4 button { aspect-ratio: 1; border-radius: 50%; border: 0; background: rgba(255,255,255,.85); cursor: pointer; padding: 0; }
  #c4 button.R { background: var(--pink); } #c4 button.Y { background: var(--sun); }
  #rps { display: flex; gap: 12px; }
  #rps button { font-size: 2.6rem; width: 84px; height: 84px; border-radius: 24px; border: 2px solid var(--line); background: #fff; cursor: pointer; transition: transform .15s; }
  #rps button:hover { transform: scale(1.1) rotate(-4deg); }
  #rps button.sel { background: linear-gradient(135deg, var(--sun), var(--pink)); border-color: transparent; }
  :focus-visible { outline: 3px solid var(--lav); outline-offset: 2px; }
  @media (prefers-reduced-motion: reduce) { * { animation: none !important; transition: none !important; } }
</style>
</head>
<body>

<form id="login">
  <div class="chars"><span>🐻</span><span>💞</span><span>🐰</span></div>
  <h1>Hi Dear 💖</h1>
  <p>Made with love by Dhriti. Type your name and the secret room code you both know.</p>
  <input id="name" placeholder="Your name" autocomplete="username" required>
  <input id="room" placeholder="Secret room code (e.g. mango-moon-4821)" autocomplete="off" required>
  <button class="go" type="submit">Come in 💌</button>
  <div id="err"></div>
</form>

<div id="app" class="hidden">
  <header>
    <span class="mascot">🐻</span>
    <span class="dot" id="dot"></span>
    <div id="status"><b id="otherName">Waiting for your person</b><small id="otherState"></small></div>
    <nav>
      <button id="tabChat" class="active">💬 Chat</button>
      <button id="tabTodo">✅ To-do</button>
      <button id="tabGames">🎮 Games</button>
    </nav>
  </header>
  <main>
    <section id="chat">
      <div id="quote"><span id="qt"></span><small>from Dhriti 💌</small></div>
      <div id="msgs"></div>
      <form id="chatForm">
        <input id="text" placeholder="Drop a message 💕" autocomplete="off">
        <button type="submit">Send</button>
      </form>
    </section>
    <section id="todos" class="hidden">
      <div id="todoList"></div>
      <form id="todoForm">
        <input id="todoText" placeholder="Add something to do together ✨" autocomplete="off">
        <button type="submit">Add</button>
      </form>
    </section>
    <section id="games" class="hidden">
      <div class="gsel">
        <button id="gT" class="active">⭕ Tic-Tac-Toe</button>
        <button id="gC">🔴 Connect 4</button>
        <button id="gR">✊ Rock Paper Scissors</button>
      </div>
      <div id="tttBox" class="gbox"><div id="tttInfo" class="info"></div><div id="board"></div><button id="reset" class="again">New round 🔄</button></div>
      <div id="c4Box" class="gbox hidden"><div id="c4Info" class="info"></div><div id="c4"></div><button id="c4reset" class="again">New round 🔄</button></div>
      <div id="rpsBox" class="gbox hidden">
        <div id="rpsInfo" class="info"></div>
        <div id="rps"><button data-c="r" aria-label="Rock">🪨</button><button data-c="p" aria-label="Paper">📄</button><button data-c="s" aria-label="Scissors">✂️</button></div>
        <button id="rpsReset" class="again">Play again 🔄</button>
      </div>
    </section>
  </main>
</div>

<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-database-compat.js"></script>
<script>
  // ====== PASTE YOUR FIREBASE CONFIG HERE ======
  const firebaseConfig = {
    apiKey: "PASTE_HERE",
    authDomain: "PASTE_HERE",
    databaseURL: "PASTE_HERE",
    projectId: "PASTE_HERE",
    appId: "PASTE_HERE"
  };
  // =============================================

  // Love quotes: edit or add your own here
  const QUOTES = [
    "Distance is just a number. You're always in my heart.",
    "Every day I'm proud of you, and today is no different.",
    "Smile, someone far away is thinking about you right now.",
    "You make ordinary days feel like little celebrations.",
    "No matter how far, you're my favorite hello.",
    "Drink some water, take a deep breath, and know you are loved.",
    "My best moments are the ones I get to share with you.",
    "You're my happy place, even through a screen."
  ];

  const $ = id => document.getElementById(id);
  const clean = s => s.trim().replace(/[.#$\[\]\/]/g, '').slice(0, 30);
  const EMOJI = ['❤️', '😂', '👍', '😮', '🥺'];
  let db, base, me, other = '', ttt = null, c4 = null, rps = {};

  // ---- cute animations ----
  ['💖','⭐','🌸','🦋','🎈','✨','🍓','☁️','💕','🌈','🐝','🌷'].forEach((e, i) => {
    const s = document.createElement('span'); s.className = 'fl'; s.textContent = e;
    s.style.left = (4 + i * 8) + 'vw'; s.style.fontSize = (20 + (i % 4) * 8) + 'px';
    s.style.animationDuration = (14 + (i % 5) * 4) + 's'; s.style.animationDelay = (-i * 2.3) + 's';
    document.body.append(s);
  });
  function burst(list = ['💖','⭐','🎉','🌸','✨'], n = 24) {
    for (let i = 0; i < n; i++) {
      const s = document.createElement('span'); s.className = 'fx'; s.textContent = list[i % list.length];
      s.style.left = (10 + Math.random() * 80) + 'vw'; s.style.fontSize = (18 + Math.random() * 20) + 'px';
      s.style.animationDelay = (Math.random() * .4) + 's';
      document.body.append(s); setTimeout(() => s.remove(), 2800);
    }
  }
  const seen = {};
  function cheer(k, w) { if (w && seen[k] !== w) burst(); seen[k] = w; }

  let qi = Math.floor(Math.random() * QUOTES.length);
  function showQuote() {
    const q = $('qt'); q.style.animation = 'none'; void q.offsetWidth; q.style.animation = '';
    q.textContent = '“' + QUOTES[qi] + '”'; qi = (qi + 1) % QUOTES.length;
  }
  showQuote(); setInterval(showQuote, 9000);

  // ---- login ----
  const saved = (() => { try { return JSON.parse(localStorage.getItem('hidear') || '{}'); } catch { return {}; } })();
  $('name').value = saved.name || ''; $('room').value = saved.room || '';
  $('login').addEventListener('submit', e => { e.preventDefault(); start(clean($('name').value), clean($('room').value)); });
  if (saved.name && saved.room) start(saved.name, saved.room);

  function start(name, room) {
    if (!name || !room) return;
    if (firebaseConfig.apiKey === 'PASTE_HERE') { $('err').textContent = 'Add your Firebase config in index.html first.'; return; }
    try { localStorage.setItem('hidear', JSON.stringify({ name, room })); } catch {}
    if (!firebase.apps.length) firebase.initializeApp(firebaseConfig);
    db = firebase.database(); base = db.ref('rooms/' + room); me = name;
    $('login').classList.add('hidden'); $('app').classList.remove('hidden');
    burst(['💖', '🌸', '✨'], 14);

    // presence: both of you see each other's, only what happens in this app
    const myP = base.child('presence/' + me);
    db.ref('.info/connected').on('value', s => {
      if (!s.val()) return;
      myP.onDisconnect().set({ online: false, activity: '', lastSeen: firebase.database.ServerValue.TIMESTAMP })
        .then(() => myP.set({ online: true, activity: 'Chatting', lastSeen: null }));
    });
    base.child('presence').on('value', s => {
      const all = s.val() || {};
      other = Object.keys(all).find(k => k !== me) || '';
      const p = all[other];
      $('otherName').textContent = other || 'Waiting for your person';
      $('dot').classList.toggle('on', !!(p && p.online));
      $('otherState').textContent = !p ? '' : p.online ? (p.activity || 'Online')
        : p.lastSeen ? 'Last seen ' + new Date(p.lastSeen).toLocaleString([], { hour: '2-digit', minute: '2-digit', day: 'numeric', month: 'short' }) : 'Offline';
    });

    const q = base.child('messages').limitToLast(200);
    q.on('child_added', s => renderMsg(s.key, s.val()));
    q.on('child_changed', s => renderMsg(s.key, s.val()));

    base.child('ttt').on('value', s => { ttt = s.val() || fresh(); drawBoard(); });
    base.child('c4').on('value', s => { c4 = s.val() || c4fresh(); drawC4(); });
    base.child('rps').on('value', s => { rps = s.val() || {}; drawRps(); });
    listenTodos();
  }

  // ---- chat ----
  $('chatForm').addEventListener('submit', e => {
    e.preventDefault();
    const text = $('text').value.trim().slice(0, 2000); if (!text) return;
    base.child('messages').push({ sender: me, text, ts: firebase.database.ServerValue.TIMESTAMP });
    $('text').value = ''; burst(['💌', '💖'], 8);
  });

  function renderMsg(key, m) {
    let d = document.getElementById('m-' + key);
    const isNew = !d;
    if (isNew) {
      d = document.createElement('div'); d.id = 'm-' + key;
      d.onclick = () => d.classList.toggle('open');
      $('msgs').append(d);
    }
    d.className = 'm' + (m.sender === me ? ' me' : '') + (d.classList.contains('open') ? ' open' : '') + (isNew ? ' pop' : '');
    d.textContent = '';
    const t = document.createElement('span'); t.textContent = m.text;
    const time = document.createElement('time');
    time.textContent = (m.sender === me ? '' : m.sender + ' · ') + (m.ts ? new Date(m.ts).toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' }) : '');
    const rx = document.createElement('div'); rx.className = 'rx';
    Object.entries(m.reactions || {}).forEach(([who, em]) => {
      const s = document.createElement('span'); s.textContent = em + (who === me ? '' : ' ' + who); rx.append(s);
    });
    const pick = document.createElement('div'); pick.className = 'pick';
    EMOJI.forEach(em => {
      const b = document.createElement('button'); b.textContent = em;
      b.onclick = ev => {
        ev.stopPropagation();
        const r = base.child('messages/' + key + '/reactions/' + me);
        if (m.reactions && m.reactions[me] === em) r.remove(); else { r.set(em); burst([em], 10); }
        d.classList.remove('open');
      };
      pick.append(b);
    });
    d.append(t, time, rx, pick);
    $('msgs').scrollTop = $('msgs').scrollHeight;
  }

  // ---- tabs ----
  const TABS = { chat: ['chat', 'tabChat', 'Chatting 💬'], todo: ['todos', 'tabTodo', 'On the to-do list ✅'], games: ['games', 'tabGames', null] };
  const GAMES = { 'Tic-Tac-Toe': ['gT', 'tttBox'], 'Connect 4': ['gC', 'c4Box'], 'Rock Paper Scissors': ['gR', 'rpsBox'] };
  let game = 'Tic-Tac-Toe';
  function tab(which) {
    for (const k in TABS) { $(TABS[k][0]).classList.toggle('hidden', k !== which); $(TABS[k][1]).classList.toggle('active', k === which); }
    base.child('presence/' + me + '/activity').set(TABS[which][2] || 'Playing ' + game + ' 🎮');
  }
  $('tabChat').onclick = () => tab('chat');
  $('tabTodo').onclick = () => tab('todo');
  $('tabGames').onclick = () => tab('games');
  function pickGame(g) {
    game = g;
    for (const k in GAMES) { $(GAMES[k][0]).classList.toggle('active', k === g); $(GAMES[k][1]).classList.toggle('hidden', k !== g); }
    base.child('presence/' + me + '/activity').set('Playing ' + g + ' 🎮');
  }
  for (const k in GAMES) $(GAMES[k][0]).onclick = () => pickGame(k);

  // ---- to-do list ----
  $('todoForm').addEventListener('submit', e => {
    e.preventDefault();
    const text = $('todoText').value.trim().slice(0, 300); if (!text) return;
    base.child('todos').push({ text, by: me, done: false, ts: firebase.database.ServerValue.TIMESTAMP });
    $('todoText').value = '';
  });
  function listenTodos() {
    const r = base.child('todos');
    r.on('child_added', s => renderTodo(s.key, s.val()));
    r.on('child_changed', s => renderTodo(s.key, s.val()));
    r.on('child_removed', s => { const d = document.getElementById('t-' + s.key); if (d) d.remove(); });
  }
  function renderTodo(key, t) {
    let d = document.getElementById('t-' + key), isNew = !d;
    if (isNew) { d = document.createElement('div'); d.id = 't-' + key; $('todoList').append(d); }
    d.className = 't' + (t.done ? ' done' : '') + (isNew ? ' pop' : ''); d.textContent = '';
    const cb = document.createElement('input'); cb.type = 'checkbox'; cb.checked = !!t.done; cb.setAttribute('aria-label', 'Done');
    cb.onchange = () => { base.child('todos/' + key + '/done').set(cb.checked); if (cb.checked) burst(['✅', '⭐'], 10); };
    const tx = document.createElement('span'); tx.className = 'tx'; tx.textContent = t.text;
    const by = document.createElement('small'); by.textContent = t.by === me ? 'you' : t.by;
    const likes = Object.entries(t.reactions || {});
    const like = document.createElement('button'); like.setAttribute('aria-label', 'React');
    like.textContent = likes.length ? '❤️' + (likes.length > 1 ? ' ' + likes.length : '') : '🤍';
    like.className = (t.reactions && t.reactions[me]) ? 'liked' : '';
    like.onclick = () => {
      const r = base.child('todos/' + key + '/reactions/' + me);
      if (t.reactions && t.reactions[me]) r.remove(); else { r.set('❤️'); burst(['❤️'], 8); }
    };
    const del = document.createElement('button'); del.textContent =
