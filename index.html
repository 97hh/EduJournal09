<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EduJournal — Электронный журнал</title>
<style>
  :root {
    --mesh-blue: #0078d4;
    --mesh-blue-hover: #005a9e;
    --bg-gray: #f3f4f6;
    --border-color: #d1d5db;
    --text-main: #333333;
    --text-muted: #6b7280;
    --g5: #10b981; --g4: #3b82f6; --g3: #f59e0b; --g2: #ef4444;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Arial, sans-serif; }
  body { background-color: var(--bg-gray); color: var(--text-main); min-height: 100vh; overflow: hidden; }

  /* АНИМАЦИЯ ЗАГРУЗКИ */
  #loader {
    position: fixed; inset: 0; background: #ffffff; z-index: 9999;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    transition: opacity 0.5s ease;
  }
  .desk { width: 300px; height: 20px; background: #8b5a2b; border-radius: 10px; position: relative; box-shadow: 0 15px 20px rgba(0,0,0,0.1); }
  .cat { font-size: 70px; position: absolute; bottom: 20px; left: 10%; animation: walkCat 3s infinite ease-in-out alternate; filter: drop-shadow(0 10px 5px rgba(0,0,0,0.2)); }
  @keyframes walkCat { 0% { left: 10%; transform: translateY(0); } 50% { left: 80%; transform: translateY(-10px); } 100% { left: 10%; transform: translateY(0); } }
  .flowers { position: absolute; bottom: 20px; width: 100%; display: flex; justify-content: space-between; padding: 0 20px; pointer-events: none; }
  .flower { animation: bloom 1.5s infinite ease-in-out alternate; transform-origin: bottom center; }
  .flower:nth-child(2) { animation-delay: 0.5s; }
  .flower:nth-child(3) { animation-delay: 1s; }
  @keyframes bloom { 0% { transform: scale(0.8) rotate(-10deg); opacity: 0.5; } 100% { transform: scale(1.2) rotate(10deg); opacity: 1; } }
  .loader-text { margin-top: 40px; font-size: 20px; font-weight: bold; color: var(--mesh-blue); }

  /* АВТОРИЗАЦИЯ */
  #login-screen { position: fixed; inset: 0; background: var(--mesh-blue); z-index: 800; display: flex; align-items: center; justify-content: center; }
  .login-box { background: #fff; padding: 40px; border-radius: 8px; width: 100%; max-width: 400px; box-shadow: 0 10px 25px rgba(0,0,0,0.2); text-align: center; }
  .login-box h1 { color: #111; font-size: 24px; margin-bottom: 20px; }
  .login-box input { width: 100%; padding: 12px; margin-bottom: 15px; border: 1px solid var(--border-color); border-radius: 4px; font-size: 16px; }
  .login-box button { width: 100%; padding: 12px; background: var(--mesh-blue); color: #fff; border: none; border-radius: 4px; font-size: 16px; cursor: pointer; font-weight: bold; }
  .login-box button:hover { background: var(--mesh-blue-hover); }
  .hint { margin-top: 15px; font-size: 13px; color: var(--text-muted); }

  /* ПРИЛОЖЕНИЕ */
  #app { display: none; flex-direction: column; height: 100vh; }
  .top-header { background-color: var(--mesh-blue); color: #fff; height: 56px; display: flex; align-items: center; padding: 0 24px; justify-content: space-between; }
  .logo-area { display: flex; align-items: center; gap: 12px; font-size: 18px; font-weight: bold; }
  .user-area { display: flex; align-items: center; gap: 12px; font-size: 14px; }
  .avatar { width: 32px; height: 32px; background: #fff; color: var(--mesh-blue); border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: bold; }
  .logout-btn { background: transparent; border: 1px solid #fff; color: #fff; padding: 5px 10px; cursor: pointer; border-radius: 4px; }

  .main-container { display: flex; flex: 1; overflow: hidden; }
  .sidebar { width: 240px; background: #fff; border-right: 1px solid var(--border-color); padding-top: 16px; }
  .nav-item { padding: 12px 24px; font-size: 15px; color: #4b5563; cursor: pointer; display: flex; align-items: center; gap: 12px; border-left: 4px solid transparent; }
  .nav-item.active { background: #e6f2fc; color: var(--mesh-blue); font-weight: bold; border-left-color: var(--mesh-blue); }
  .nav-item:hover:not(.active) { background: #f3f4f6; }

  .content { flex: 1; padding: 24px; overflow-y: auto; }
  .page-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 20px; }
  .page-title { font-size: 24px; font-weight: bold; }
  
  .card { background: #fff; border: 1px solid var(--border-color); border-radius: 4px; padding: 20px; }
  .btn-add { background: var(--mesh-blue); color: #fff; border: none; padding: 8px 16px; border-radius: 4px; cursor: pointer; font-weight: bold; }

  .journal-table { width: 100%; border-collapse: collapse; }
  .journal-table th, .journal-table td { border: 1px solid var(--border-color); padding: 10px; text-align: center; font-size: 14px; }
  .journal-table th { background: #f8f9fa; color: var(--text-muted); font-weight: normal; }
  .journal-table th.date-col { min-width: 80px; }
  .grade-cell { cursor: pointer; transition: 0.1s; font-weight: bold; font-size: 18px; }
  .grade-cell:hover { background: #f0f8ff; }
  .g-5 { color: var(--g5); } .g-4 { color: var(--g4); } .g-3 { color: var(--g3); } .g-2 { color: var(--g2); }
  .lock-icon { font-size: 16px; opacity: 0.5; cursor: not-allowed; }

  .sched-item { display: flex; border: 1px solid var(--border-color); padding: 12px; margin-bottom: 10px; border-radius: 4px; background: #f9fafb; }
  .sched-time { font-weight: bold; width: 100px; color: var(--mesh-blue); }
  
  .view { display: none; }
  .view.active { display: block; }
</style>
</head>
<body>

  <!-- 1. АНИМАЦИЯ ЗАГРУЗКИ -->
  <div id="loader">
    <div class="desk">
      <div class="flowers">
        <div class="flower">🌸</div>
        <div class="flower">🌺</div>
        <div class="flower">🌻</div>
      </div>
      <div class="cat">🐈</div>
    </div>
    <div class="loader-text">Загрузка EduJournal...</div>
  </div>

  <!-- 2. АВТОРИЗАЦИЯ -->
  <div id="login-screen">
    <div class="login-box">
      <h1>Вход в EduJournal</h1>
      <input type="text" id="login-user" placeholder="Логин (admin или student)">
      <input type="password" id="login-pass" placeholder="Пароль (123)">
      <button onclick="login()">Войти</button>
      <div class="hint">
        <b>Учитель:</b> admin / 123<br>
        <b>Ученик:</b> student / 123
      </div>
    </div>
  </div>

  <!-- 3. ПРИЛОЖЕНИЕ -->
  <div id="app">
    <header class="top-header">
      <div class="logo-area">
        <div style="background:#fff; color:var(--mesh-blue); padding:2px 8px; border-radius:4px; font-size:14px;">EduJournal</div>
        <span>Электронный журнал</span>
      </div>
      <div class="user-area">
        <span id="user-display">Имя</span>
        <div class="avatar" id="user-avatar">И</div>
        <button class="logout-btn" onclick="logout()">Выйти</button>
      </div>
    </header>

    <div class="main-container">
      <aside class="sidebar">
        <div class="nav-item active" onclick="switchView('journal', this)">📓 Журнал</div>
        <div class="nav-item" onclick="switchView('schedule', this)">📅 Расписание</div>
      </aside>

      <main class="content">
        <div id="view-journal" class="view active">
          <div class="page-header">
            <div class="page-title">Журнал оценок</div>
            <div id="teacher-controls" style="display:none;">
              <button class="btn-add" onclick="addScheduleColumn()">+ Добавить урок</button>
            </div>
          </div>
          <div class="card">
            <table class="journal-table" id="journal-table"></table>
          </div>
        </div>

        <div id="view-schedule" class="view">
          <div class="page-header"><div class="page-title">Расписание</div></div>
          <div class="card" id="schedule-list"></div>
        </div>
      </main>
    </div>
  </div>

<script>
  let DB = JSON.parse(localStorage.getItem('eduJournalDB')) || {
    users: [
      { login: 'admin', pass: '123', role: 'teacher', name: 'Петрова А.С. (Учитель)' },
      { login: 'student', pass: '123', role: 'student', name: 'Иванов Иван' }
    ],
    lessons: [
      { id: 1, date: '02.11.2026', subject: 'Алгебра' },
      { id: 2, date: '03.11.2026', subject: 'Физика' },
      { id: 3, date: '05.11.2026', subject: 'История' },
      { id: 4, date: '10.11.2026', subject: 'Алгебра' }
    ],
    grades: { 1: { 'ivanov': 5 }, 2: { 'ivanov': 4 } }
  };

  function saveDB() { localStorage.setItem('eduJournalDB', JSON.stringify(DB)); }
  let currentUser = null;

  window.addEventListener('load', () => {
    setTimeout(() => {
      const loader = document.getElementById('loader');
      if (loader) { loader.style.opacity = '0'; setTimeout(() => loader.style.display = 'none', 500); }
    }, 1500);
  });
  setTimeout(() => { const l = document.getElementById('loader'); if (l && l.style.display !== 'none') l.style.display = 'none'; }, 3000);

  function login() {
    const u = document.getElementById('login-user').value;
    const p = document.getElementById('login-pass').value;
    const user = DB.users.find(x => x.login === u && x.pass === p);

    if (user) {
      currentUser = user;
      document.getElementById('login-screen').style.display = 'none';
      document.getElementById('app').style.display = 'flex';
      document.getElementById('user-display').textContent = user.name;
      document.getElementById('user-avatar').textContent = user.name[0];
      if (user.role === 'teacher') document.getElementById('teacher-controls').style.display = 'block';
      renderJournal();
      renderSchedule();
    } else { alert('Неверный логин или пароль!'); }
  }

  function logout() { location.reload(); }

  function switchView(viewId, el) {
    document.querySelectorAll('.view').forEach(v => v.classList.remove('active'));
    document.getElementById('view-' + viewId).classList.add('active');
    document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
    el.classList.add('active');
  }

  function renderJournal() {
    const table = document.getElementById('journal-table');
    table.innerHTML = '';
    let trHead = '<tr><th>Предмет</th>';
    DB.lessons.forEach(lesson => {
      trHead += `<th class="date-col">${lesson.date}<br><span style="font-size:12px;">${lesson.subject}</span></th>`;
    });
    trHead += '</tr>';
    table.innerHTML += trHead;

    let trRow = '<tr><td style="text-align:left; font-weight:bold; background:#f8f9fa;">Иванов Иван</td>';
    const now = new Date(); now.setHours(0,0,0,0);
    
    DB.lessons.forEach(lesson => {
      const parts = lesson.date.split('.');
      const lessonDate = new Date(parts[2], parts[1]-1, parts[0]);
      const isFuture = lessonDate > now;
      const grade = DB.grades[lesson.id] ? DB.grades[lesson.id]['ivanov'] : null;

      if (isFuture) {
        trRow += `<td><span class="lock-icon">🔒</span></td>`;
      } else {
        if (grade) {
          trRow += `<td><span class="grade-cell g-${grade}" onclick="setGrade(${lesson.id})">${grade}</span></td>`;
        } else {
          if (currentUser.role === 'teacher') {
            trRow += `<td onclick="setGrade(${lesson.id})" style="color:#ccc; cursor:pointer;">+</td>`;
          } else { trRow += `<td>-</td>`; }
        }
      }
    });
    trRow += '</tr>';
    table.innerHTML += trRow;
  }

  function setGrade(lessonId) {
    if (currentUser.role !== 'teacher') return;
    const g = prompt('Введите оценку (2, 3, 4 или 5):');
    if (['2','3','4','5'].includes(g)) {
      if (!DB.grades[lessonId]) DB.grades[lessonId] = {};
      DB.grades[lessonId]['ivanov'] = parseInt(g);
      saveDB(); renderJournal();
    }
  }

  function addScheduleColumn() {
    if (currentUser.role !== 'teacher') return;
    const subj = prompt('Название предмета:');
    const date = prompt('Дата (в формате ДД.ММ.ГГГГ, например 15.11.2026):');
    if (subj && date) {
      DB.lessons.push({ id: Date.now(), date: date, subject: subj });
      saveDB(); renderJournal(); renderSchedule();
    }
  }

  function renderSchedule() {
    const list = document.getElementById('schedule-list');
    list.innerHTML = '';
    const sorted = [...DB.lessons].sort((a,b) => {
        const p1 = a.date.split('.'); const p2 = b.date.split('.');
        return new Date(p1[2], p1[1]-1, p1[0]) - new Date(p2[2], p2[1]-1, p2[0]);
    });
    sorted.forEach(l => {
      list.innerHTML += `<div class="sched-item"><div class="sched-time">${l.date}</div><div style="flex:1; font-weight:bold;">${l.subject}</div></div>`;
    });
  }
</script>
</body>
</html>
