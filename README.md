<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Timber Tribe | Carpentry & Joinery Portfolio</title>
  <meta name="description" content="Timber Tribe — quality carpentry & bespoke joinery. View services, projects, testimonials, and contact details.">
  <style>
    /* ---------- Base / Reset ---------- */
    *,*::before,*::after{box-sizing:border-box}
    :root{
      --bg:#faf8f5;
      --surface:#fff;
      --ink:#2a2a2a;
      --muted:#666;
      --brand:#8b5e34;     /* warm wood brown */
      --brand-2:#d1a677;   /* lighter accent */
      --accent:#3e7a5e;    /* subtle green */
      --shadow:0 6px 24px rgba(0,0,0,.08), 0 2px 6px rgba(0,0,0,.06);
      --radius:18px;
      --radius-sm:12px;
      --max:1100px;
    }
    html,body{height:100%}
    body{margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,"Helvetica Neue",Arial,sans-serif;color:var(--ink);background:var(--bg);line-height:1.6}
    img{max-width:100%;display:block;border-radius:12px}
    a{color:var(--brand);text-decoration:none}
    a:hover{opacity:.9}
    .container{width:100%;max-width:var(--max);margin-inline:auto;padding:0 20px}
    .btn{display:inline-block;padding:14px 18px;border-radius:999px;font-weight:600;border:1px solid var(--brand);background:var(--brand);color:#fff;box-shadow:var(--shadow);transition:.2s}
    .btn.ghost{background:transparent;color:var(--brand)}
    .btn:hover{transform:translateY(-2px)}

    /* ---------- Navbar ---------- */
    header{position:sticky;top:0;background:rgba(250,248,245,.75);backdrop-filter:saturate(180%) blur(10px);z-index:1000;border-bottom:1px solid #eee}
    .nav{display:flex;align-items:center;justify-content:space-between;padding:14px 0}
    .brand{display:flex;gap:12px;align-items:center;font-weight:800;letter-spacing:.3px}
    .logo{width:36px;height:36px;border-radius:10px;background:linear-gradient(135deg,var(--brand),#5f3b1b);display:grid;place-items:center;color:#fff;box-shadow:inset 0 0 0 2px rgba(255,255,255,.15)}
    .logo svg{width:22px;height:22px}
    nav ul{display:flex;gap:22px;list-style:none;margin:0;padding:0}
    nav a{font-weight:600;color:var(--ink)}
    .nav-actions{display:flex;align-items:center;gap:10px}
    .menu-btn{display:none}

    /* ---------- Hero ---------- */
    .hero{position:relative;overflow:hidden}
    .hero::before{content:"";position:absolute;inset:-40px;background:
      radial-gradient(1200px 400px at 40% -200px, rgba(139,94,52,.12), transparent),
      radial-gradient(1000px 500px at 100% 20%, rgba(209,166,119,.18), transparent),
      linear-gradient(180deg, #fff, #f7f3ee 60%, #f3eee7);
      z-index:-1}
    .hero-inner{display:grid;grid-template-columns:1.1fr .9fr;gap:32px;align-items:center;padding:64px 0}
    .kicker{color:var(--accent);font-weight:700;letter-spacing:.2em;text-transform:uppercase;font-size:.8rem}
    .hero h1{font-size:clamp(28px,5vw,48px);line-height:1.1;margin:10px 0 12px}
    .hero p{color:var(--muted);max-width:60ch}
    .hero-art{position:relative;border-radius:var(--radius);box-shadow:var(--shadow);overflow:hidden}
    .hero-art::after{content:"Crafted to last";position:absolute;bottom:14px;right:16px;background:rgba(0,0,0,.6);color:#fff;padding:6px 10px;border-radius:999px;font-size:12px}

    /* ---------- Section ---------- */
    section{padding:60px 0}
    .section-title{margin:0 0 8px;font-size:clamp(22px,3.4vw,34px)}
    .section-sub{color:var(--muted);margin:0 0 24px}

    /* ---------- Services ---------- */
    .grid{display:grid;gap:18px}
    .services{grid-template-columns:repeat(auto-fit,minmax(240px,1fr))}
    .card{background:var(--surface);border-radius:var(--radius);padding:22px;box-shadow:var(--shadow)}
    .service-icon{width:42px;height:42px;border-radius:12px;display:grid;place-items:center;background:#f2e8df;color:#4e2f12;margin-bottom:10px}
    .card h3{margin:6px 0 8px}
    .muted{color:var(--muted)}

    /* ---------- Projects ---------- */
    .projects{grid-template-columns:repeat(auto-fit,minmax(260px,1fr))}
    .project{overflow:hidden}
    .project figure{margin:0;position:relative}
    .badge{position:absolute;top:12px;left:12px;background:rgba(0,0,0,.65);color:#fff;padding:6px 10px;border-radius:999px;font-size:12px}

    /* ---------- Testimonials ---------- */
    .testimonials{position:relative}
    .t-wrap{display:flex;gap:16px;scroll-snap-type:x mandatory;overflow:auto;padding-bottom:10px}
    .t{min-width:320px;flex:0 0 320px;background:var(--surface);padding:20px;border-radius:var(--radius-sm);box-shadow:var(--shadow);scroll-snap-align:start}
    .t .who{display:flex;align-items:center;gap:10px;margin-top:14px}
    .avatar{width:36px;height:36px;border-radius:50%;background:#e8dccf}

    /* ---------- Contact ---------- */
    .contact{display:grid;grid-template-columns:1fr 1fr;gap:20px}
    form{background:var(--surface);padding:22px;border-radius:var(--radius);box-shadow:var(--shadow)}
    label{display:block;font-weight:600;margin:12px 0 6px}
    input,textarea{width:100%;padding:12px 14px;border-radius:12px;border:1px solid #e4e0da;background:#fff}
    textarea{min-height:120px;resize:vertical}
    .panel{background:linear-gradient(180deg,#fff,#f8f2eb);padding:24px;border-radius:var(--radius);box-shadow:var(--shadow)}

    /* ---------- Footer ---------- */
    footer{padding:28px 0;color:#887e73}
    .footer-inner{display:flex;gap:18px;align-items:center;justify-content:space-between;flex-wrap:wrap}

    /* ---------- Responsive ---------- */
    @media (max-width: 880px){
      .hero-inner{grid-template-columns:1fr}
      .contact{grid-template-columns:1fr}
      .menu-btn{display:inline-flex;align-items:center;gap:8px;border:1px solid #ddd;background:#fff;padding:10px 14px;border-radius:999px}
      nav ul{position:absolute;top:64px;left:0;right:0;background:#fff;border-bottom:1px solid #eee;display:none;flex-direction:column;padding:14px}
      nav ul.open{display:flex}
    }
  </style>
</head>
<body>
  <!-- =================== NAV =================== -->
  <header>
    <div class="container nav">
      <div class="brand">
        <div class="logo" aria-hidden="true">
          <!-- Simple wood-grain style logomark -->
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
            <circle cx="12" cy="12" r="8"/>
            <path d="M12 4c2.5 2 4 4.8 4 8s-1.5 6-4 8m0-9c1.2 1 2 2.4 2 4s-.8 3-2 4"/>
          </svg>
        </div>
        <span>Timber Tribe</span>
      </div>
      <nav>
        <button class="menu-btn" aria-label="Open menu" onclick="document.querySelector('nav ul').classList.toggle('open')">☰ Menu</button>
        <ul>
          <li><a href="#about">About</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#testimonials">Testimonials</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
      <div class="nav-actions">
        <a class="btn ghost" href="#contact">Get a Quote</a>
      </div>
    </div>
  </header>

  <!-- =================== HERO =================== -->
  <section class="hero">
    <div class="container hero-inner">
      <div>
        <div class="kicker">Carpentry & Bespoke Joinery</div>
        <h1>Crafted to last. Designed for your life.</h1>
        <p>We build custom woodwork that blends timeless technique with modern function — from fitted cabinetry and interior finishes to one‑of‑a‑kind furniture pieces.</p>
        <div style="margin-top:18px; display:flex; gap:10px; flex-wrap:wrap">
          <a class="btn" href="#projects">See Our Work</a>
          <a class="btn ghost" href="#services">Explore Services</a>
        </div>
      </div>
      <div class="hero-art">
        <img src="https://images.unsplash.com/photo-1519710164239-da123dc03ef4?q=80&w=1600&auto=format&fit=crop" alt="Close‑up of timber joinery in a workshop" />
      </div>
    </div>
  </section>

  <!-- =================== ABOUT =================== -->
  <section id="about">
    <div class="container">
      <h2 class="section-title">About Timber Tribe</h2>
      <p class="section-sub">We’re a team of makers who treat each project as a collaboration. From first sketch to final finish, we obsess over the little things — alignment, grain, joinery — so your space feels effortless for years to come.</p>
      <div class="panel">
        <p><strong>Our approach</strong> blends traditional craftsmanship with thoughtful design. We source dependable materials, prototype where needed, and communicate clearly at every step.</p>
        <p style="margin:0"><strong>What we value:</strong> care, integrity, longevity, and solutions that fit the way you actually live and work.</p>
      </div>
    </div>
  </section>

  <!-- =================== SERVICES =================== -->
  <section id="services">
    <div class="container">
      <h2 class="section-title">Services</h2>
      <p class="section-sub">Tailored carpentry and joinery for homes and commercial spaces.</p>
      <div class="grid services">
        <div class="card">
          <div class="service-icon" aria-hidden="true">🪵</div>
          <h3>Custom Furniture</h3>
          <p class="muted">Bespoke tables, storage, and statement pieces designed around your space and style.</p>
        </div>
        <div class="card">
          <div class="service-icon" aria-hidden="true">🧰</div>
          <h3>Cabinetry & Storage</h3>
          <p class="muted">Fitted kitchens, wardrobes, shelving and built‑ins that maximize function and flow.</p>
        </div>
        <div class="card">
          <div class="service-icon" aria-hidden="true">🏡</div>
          <h3>Interior Woodwork</h3>
          <p class="muted">Doors, trim, wall paneling and feature details that add warmth and character.</p>
        </div>
        <div class="card">
          <div class="service-icon" aria-hidden="true">🛠️</div>
          <h3>Renovations & Upgrades</h3>
          <p class="muted">From concept to install — careful improvements that stand the test of time.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- =================== PROJECTS =================== -->
  <section id="projects">
    <div class="container">
      <h2 class="section-title">Recent Projects</h2>
      <p class="section-sub">A few highlights from the workshop. Replace these images and captions with your own work.</p>
      <div class="grid projects">
        <article class="card project">
          <figure>
            <span class="badge">Kitchen cabinetry</span>
            <img src="https://images.unsplash.com/photo-1497366754035-f200968a6e72?q=80&w=1400&auto=format&fit=crop" alt="Warm wood kitchen cabinetry"/>
          </figure>
          <h3>Walnut kitchen with integrated storage</h3>
          <p class="muted">Custom cabinetry, soft‑close hardware, and hand‑finished panels for a durable, timeless space.</p>
        </article>
        <article class="card project">
          <figure>
            <span class="badge">Feature wall</span>
            <img src="https://images.unsplash.com/photo-1616597151169-23167689d636?q=80&w=1400&auto=format&fit=crop" alt="Wood slat feature wall"/>
          </figure>
          <h3>Slatted oak living‑room feature</h3>
          <p class="muted">Acoustic slat wall with invisible fixings — warmth, texture, and sound control in one.</p>
        </article>
        <article class="card project">
          <figure>
            <span class="badge">Bespoke piece</span>
            <img src="https://images.unsplash.com/photo-1541753866388-0b3c701627d3?q=80&w=1400&auto=format&fit=crop" alt="Handmade wooden table"/>
          </figure>
          <h3>Handmade dining table</h3>
          <p class="muted">Solid top with traditional joinery and a protective oil‑wax finish for everyday life.</p>
        </article>
      </div>
    </div>
  </section>

  <!-- =================== TESTIMONIALS =================== -->
  <section id="testimonials" class="testimonials">
    <div class="container">
      <h2 class="section-title">What Clients Say</h2>
      <p class="section-sub">Drop in your real reviews here. These are sample quotes you can keep or replace.</p>
      <div class="t-wrap" id="twrap">
        <div class="t">
          <p><em>“From the first consultation to the final installation, Timber Tribe delivered excellence. The custom cabinets fit perfectly and the process was stress‑free.”</em></p>
          <div class="who">
            <div class="avatar" aria-hidden="true"></div>
            <strong>Sarah M.</strong><span class="muted"> • Homeowner</span>
          </div>
        </div>
        <div class="t">
          <p><em>“They listened to our ideas and delivered a coffee table that’s now the centerpiece of our living room. The craftsmanship speaks for itself.”</em></p>
          <div class="who">
            <div class="avatar" aria-hidden="true"></div>
            <strong>Daniel K.</strong><span class="muted"> • Client</span>
          </div>
        </div>
        <div class="t">
          <p><em>“For our office renovation they finished on time, kept communication clear, and the wood finishes transformed the space beautifully.”</em></p>
          <div class="who">
            <div class="avatar" aria-hidden="true"></div>
            <strong>Lydia O.</strong><span class="muted"> • Project Manager</span>
          </div>
        </div>
      </div>
      <div style="margin-top:14px;display:flex;gap:10px">
        <button class="btn ghost" onclick="scrollTestimonials(-1)">◀︎ Prev</button>
        <button class="btn" onclick="scrollTestimonials(1)">Next ▶︎</button>
      </div>
    </div>
  </section>

  <!-- =================== CONTACT =================== -->
  <section id="contact">
    <div class="container">
      <h2 class="section-title">Let’s Build Something</h2>
      <p class="section-sub">Tell us a little about your project, timeline, and budget. We’ll get back within 1–2 business days.</p>
      <div class="contact">
        <form onsubmit="event.preventDefault(); alert('Thanks! We\'ll be in touch shortly.'); this.reset();">
          <label for="name">Name</label>
          <input id="name" name="name" placeholder="Your name" required>
          <label for="email">Email</label>
          <input id="email" type="email" name="email" placeholder="you@example.com" required>
          <label for="message">Project details</label>
          <textarea id="message" name="message" placeholder="Briefly describe what you have in mind…"></textarea>
          <div style="margin-top:14px"><button class="btn" type="submit">Request a Quote</button></div>
        </form>
        <div class="panel">
          <h3>Contact</h3>
          <p style="margin:8px 0 0"><strong>Timber Tribe</strong></p>
          <p class="muted" style="margin:6px 0">Nairobi, Kenya</p>
          <p style="margin:8px 0">📞 <a href="tel:+254724263464">+254 724 263 464</a><br>✉️ <a href="mailto:hello@timbertribe.co">hello@timbertribe.co</a></p>
          <p style="margin:8px 0">Instagram · Facebook · WhatsApp</p>
          <p class="muted" style="margin:10px 0 0;font-size:14px">Replace these details with your real business info. You can also embed a map or WhatsApp link here.</p>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container footer-inner">
      <div style="display:flex;align-items:center;gap:10px">
        <div class="logo" aria-hidden="true">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round">
            <circle cx="12" cy="12" r="8"/>
            <path d="M12 4c2.5 2 4 4.8 4 8s-1.5 6-4 8m0-9c1.2 1 2 2.4 2 4s-.8 3-2 4"/>
          </svg>
        </div>
        <strong>Timber Tribe</strong>
      </div>
      <small>© <span id="year"></span> Timber Tribe. All rights reserved.</small>
    </div>
  </footer>

  <script>
    // Year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Simple testimonial scroller
    function scrollTestimonials(dir){
      const el = document.getElementById('twrap');
      el.scrollBy({left: dir * 360, behavior: 'smooth'});
    }

    // Smooth-scroll for in-page links (nice UX)
    document.querySelectorAll('a[href^="#"]').forEach(a=>{
      a.addEventListener('click',e=>{
        const id = a.getAttribute('href');
        const target = document.querySelector(id);
        if(target){ e.preventDefault(); target.scrollIntoView({behavior:'smooth', block:'start'}); }
      });
    });
  </script>
</body>
</html>
