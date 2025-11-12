[index5.html](https://github.com/user-attachments/files/23511266/index5.html)
<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Autology — СТО повного циклу</title>
  <meta name="description" content="Autology — ремонт, діагностика, тюнінг, електрика, ходова. Запис онлайн.">
  <style>
    :root{
      /* --- базовые палитры (тёмная по умолчанию) --- */
      --bg: #0b0b0b;
      --panel: #111111;
      --muted: #9aa0a6;
      --accent: #bdbdbd;
      --accent-strong: #ffffff;
      --action: #ff6b00;
      --glass: rgba(255,255,255,0.03);
      --radius: 12px;
      --container: 1100px;
      --shadow: 0 6px 20px rgba(0,0,0,0.6);
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    }

    /* --- светлая тема (переключаемая) --- */
    body.light {
      --bg: #f6f7f9;
      --panel: #ffffff;
      --muted: #556066;
      --accent: #222326;
      --accent-strong: #0b0b0b;
      --action: #ff6b00;
      --glass: rgba(10,10,10,0.03);
      --shadow: 0 6px 20px rgba(0,0,0,0.08);
    }

    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%}
    body{
      background:var(--bg);
      color:var(--accent);
      line-height:1.5;
      -webkit-font-smoothing:antialiased;
      transition:background .25s ease, color .25s ease;
    }
    a{text-decoration:none;color:var(--accent)}
    .container{max-width:var(--container);margin:0 auto;padding:28px}

    /* ========== HEADER ========== */
    header{
      display:flex;align-items:center;justify-content:space-between;
      padding:16px 28px;position:sticky;top:0;background:rgba(11,11,11,0.6);
      backdrop-filter:blur(6px);z-index:50;border-bottom:1px solid rgba(255,255,255,0.03);
    }
    body.light header{background:rgba(255,255,255,0.8)}
    .logo{display:flex;align-items:center;gap:10px;color:var(--accent-strong);font-weight:600;font-size:20px}
    .nav{display:flex;gap:18px;align-items:center}
    .nav a{color:var(--accent);font-weight:500}
    .btn,.btn-outline{padding:10px 16px;border-radius:10px;cursor:pointer;font-weight:600}
    .btn{background:var(--panel);color:var(--accent-strong);border:1px solid rgba(255,255,255,0.03)}
    .btn-outline{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--accent)}
    .theme-toggle{background:transparent;border:none;color:var(--accent);cursor:pointer;padding:8px;border-radius:8px;font-size:16px}

    /* ========== HERO ========== */
    section{padding:80px 28px;border-bottom:1px solid rgba(255,255,255,0.03)}
    .hero{position:relative;display:flex;flex-direction:column;align-items:center;text-align:center;justify-content:center;min-height:60vh;background:url('https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&w=1500&q=80') center/cover no-repeat}
    .hero::after{content:"";position:absolute;inset:0;background:linear-gradient(180deg, rgba(0,0,0,0.65), rgba(0,0,0,0.55))}
    body.light .hero::after{background:linear-gradient(180deg, rgba(255,255,255,0.05), rgba(255,255,255,0.02))}
    .hero-content{position:relative;z-index:1;color:var(--accent-strong);max-width:780px;padding:40px}
    .hero h1{font-size:40px;margin-bottom:12px}
    .hero p{color:var(--muted);margin-bottom:20px}
    .hero .actions{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}

    /* ========== SERVICES (grid + filter) ========== */
    .services-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:24px;margin-top:18px}
    .card{background:var(--panel);padding:18px;border-radius:14px;border:1px solid rgba(255,255,255,0.03);text-align:center;cursor:pointer;transition:transform .18s ease, box-shadow .18s ease, opacity .4s}
    .card img{width:100%;height:150px;object-fit:cover;border-radius:10px;margin-bottom:12px}
    .card:hover{transform:translateY(-6px);box-shadow:var(--shadow)}
    .filter-buttons{display:flex;justify-content:center;flex-wrap:wrap;gap:12px;margin-bottom:12px}

    .filter-buttons button{padding:8px 14px;border:none;border-radius:8px;background:var(--panel);color:var(--accent);cursor:pointer;transition:background .2s}
    .filter-active{background:var(--action);color:#fff}

    /* ========== SOCIALS ========== */
    #socials{text-align:center;background:transparent;padding:34px 28px}
    .social-links{display:flex;justify-content:center;gap:18px;margin-top:10px}
    .social-links a{font-size:20px;transition:transform .15s}
    .social-links a:hover{transform:scale(1.15)}

    /* ========== ABOUT, CONTACT ========== */
    .highlights{list-style:none;display:flex;flex-wrap:wrap;gap:18px;margin:18px 0}
    .highlights li{background:var(--glass);padding:12px 18px;border-radius:10px;color:var(--muted)}

    form{display:flex;flex-direction:column;gap:12px;max-width:520px;margin:0 auto}
    input,textarea,select{padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.06);background:var(--panel);color:var(--accent-strong)}
    textarea{min-height:90px;resize:vertical}

    /* ========== REVIEWS & GALLERY ========== */
    .reviews-container{display:flex;flex-wrap:wrap;justify-content:center;gap:20px;margin-top:12px}
    .review{background:var(--panel);padding:18px;border-radius:12px;width:300px;color:var(--accent)}
    .gallery-container{display:flex;flex-wrap:wrap;justify-content:center;gap:16px;margin-top:12px}
    .gallery-container img{width:250px;border-radius:12px;object-fit:cover}

    /* ========== MODAL ========== */
    .modal{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.65);align-items:center;justify-content:center;z-index:9999;padding:20px}
    .modal .modal-content{background:var(--panel);padding:22px;border-radius:12px;max-width:480px;width:100%}

    /* ========== TO-TOP & CHAT ========== */
    #toTop{
      position:fixed;right:20px;bottom:88px;width:48px;height:48px;border-radius:50%;border:none;background:var(--panel);color:var(--accent-strong);display:none;align-items:center;justify-content:center;cursor:pointer;z-index:1000;box-shadow:var(--shadow)
    }
    #chatBtn{
      position:fixed;right:20px;bottom:20px;width:56px;height:56px;border-radius:50%;border:none;background:#0088cc;color:#fff;display:flex;align-items:center;justify-content:center;font-size:22px;z-index:1000;box-shadow:var(--shadow);cursor:pointer
    }

    /* ========== SCROLL REVEAL PREP ========== */
    .reveal {opacity:0; transform: translateY(20px); transition:opacity .6s ease, transform .6s ease}
    .reveal.visible {opacity:1; transform: translateY(0)}

    /* ========== RESPONSIVE ========== */
    @media (max-width: 980px){
      .hero h1{font-size:34px}
      header{padding:12px 18px}
      .container{padding:18px}
    }
    @media (max-width: 780px){
      header{flex-direction:column;align-items:flex-start;gap:10px}
      .nav{flex-wrap:wrap;gap:8px}
      .hero{min-height:52vh;padding:30px 16px}
      .hero h1{font-size:26px}
      .services-grid{grid-template-columns:1fr}
      .card img{height:180px}
      .gallery-container img{width:100%;max-width:320px}
      .reviews-container{flex-direction:column;align-items:center}
      .modal .modal-content{padding:16px}
    }

    /* little utilities */
    .muted{color:var(--muted)}
    footer{padding:28px;text-align:center;color:var(--muted);font-size:14px}
  </style>
</head>
<body>
<!-- весь контент как у тебя выше... -->

<!-- ====== UI: TO TOP + CHAT BUTTON ====== -->
<button id="toTop" title="Вгору">↑</button>
<a id="chatBtn" href="https://t.me/yourusername" target="_blank" rel="noopener" title="Написати в Telegram">✉️</a>

<!-- ====== SCRIPT: ВСЕ ФУНКЦИИ И АНИМАЦИИ ====== -->
<script>
/* ---------------- Modal ---------------- */
function openModal(){
  const m = document.getElementById('bookingModal');
  m.style.display='flex';
  m.setAttribute('aria-hidden','false');
  const first = m.querySelector('input[name="name"]');
  if(first) setTimeout(()=>first.focus(),120);
}
function closeModal(){
  const m = document.getElementById('bookingModal');
  m.style.display='none';
  m.setAttribute('aria-hidden','true');
}
document.addEventListener('keydown', e => { if(e.key==='Escape') closeModal(); });
const bookingModal = document.getElementById('bookingModal');
bookingModal.addEventListener('click', e => { if(e.target.id==='bookingModal') closeModal(); });
bookingModal.addEventListener('touchstart', e => { if(e.target.id==='bookingModal') closeModal(); });

/* ---------------- Forms (mailto fallback) ---------------- */
document.getElementById('bookingForm').addEventListener('submit', e=>{
  e.preventDefault();
  const d = new FormData(e.target);
  const to = 'info@autology.example';
  const subject = encodeURIComponent('Запис — ' + (d.get('service') || ''));
  const body = encodeURIComponent(
    `Ім’я: ${d.get('name')}\nТелефон: ${d.get('phone')}\nАвто: ${d.get('car')}\nПослуга: ${d.get('service')}\nДата: ${d.get('date')}\nКоментар: ${d.get('notes')||''}`
  );
  window.location.href = `mailto:${to}?subject=${subject}&body=${body}`;
  closeModal();
});
document.getElementById('contactForm').addEventListener('submit', e=>{
  e.preventDefault();
  const d = new FormData(e.target);
  const to = 'info@autology.example';
  const subject = encodeURIComponent('Повідомлення — ' + (d.get('name') || ''));
  const body = encodeURIComponent(`Ім’я: ${d.get('name')}\nEmail: ${d.get('email')}\n\n${d.get('message')}`);
  window.location.href = `mailto:${to}?subject=${subject}&body=${body}`;
});

/* ---------------- Filter & card click (autofill modal) ---------------- */
const filterButtons = document.querySelectorAll('.filter-btn');
const serviceCards = document.querySelectorAll('.services-grid .card');
filterButtons.forEach(btn=>{
  btn.addEventListener('click', ()=>{
    filterButtons.forEach(b=>b.classList.remove('filter-active'));
    btn.classList.add('filter-active');
    const filter = btn.dataset.filter;
    serviceCards.forEach(card=>{
      card.style.display = (filter === 'all' || card.dataset.category === filter) ? 'block' : 'none';
    });
  });
});
serviceCards.forEach(card=>{
  card.addEventListener('click', ()=>{
    const service = card.dataset.service || '';
    const modal = document.getElementById('bookingModal');
    const sel = modal.querySelector('select[name="service"]');
    if(sel){
      let found = false;
      for(const opt of sel.options){
        if(opt.textContent.trim() === service){ opt.selected=true; found=true; break; }
      }
      if(!found) sel.value = sel.options[0].value;
    }
    openModal();
  });
});

/* ---------------- Scroll reveal ---------------- */
const observer = new IntersectionObserver((entries)=>{
  entries.forEach(entry=>{ if(entry.isIntersecting) entry.target.classList.add('visible'); });
}, { threshold: 0.15 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
window.addEventListener('load', () => {
  document.querySelectorAll('.reveal').forEach(el=>{
    const rect = el.getBoundingClientRect();
    if(rect.top < window.innerHeight) el.classList.add('visible');
  });
});

/* ---------------- To-top button ---------------- */
const toTop = document.getElementById('toTop');
window.addEventListener('scroll', ()=> { toTop.style.display = window.scrollY > 200 ? 'flex' : 'none'; });
toTop.addEventListener('click', ()=> window.scrollTo({top:0, behavior:'smooth'}));

/* ---------------- Theme toggle ---------------- */
const themeToggle = document.getElementById('themeToggle');
function applyTheme(t){ if(t==='light') document.body.classList.add('light'); else document.body.classList.remove('light'); }
const saved = localStorage.getItem('autology_theme');
if(saved) applyTheme(saved);
else {
  const prefers = window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches;
  applyTheme(prefers ? 'light' : 'dark');
}
themeToggle.addEventListener('click', ()=>{
  const isLight = document.body.classList.contains('light');
  const next = isLight ? 'dark' : 'light';
  applyTheme(next);
  localStorage.setItem('autology_theme', next);
});

/* ---------------- Accessibility: focus outlines ---------------- */
document.body.addEventListener('keydown', e=>{ if(e.key==='Tab') document.documentElement.classList.add('show-focus-outline'); });
document.body.addEventListener('mousedown', ()=>document.documentElement.classList.remove('show-focus-outline'));
</script>
</body>
</html>
