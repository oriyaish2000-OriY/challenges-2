<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>העט המשותף — The Shared Pen | קהילת כותבים גלובלית</title>
  <meta name="description" content="פלטפורמת הצ'אלנגים הספרותיים הגדולה בעולם — כתוב, התחרה, צמח. בהשראת TryHackMe לעולם הכתיבה היצירתית.">
  <link rel="stylesheet" href="css/style.css" />
  <style>
    /* ── Index-only styles ── */
    .hero-two-col {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 80px;
      align-items: center;
      padding: 120px 0 80px;
    }
    @media(max-width:900px){ .hero-two-col{ grid-template-columns:1fr; gap:50px; padding:100px 0 60px; } }

    .features-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 28px; }
    @media(max-width:900px){ .features-grid{ grid-template-columns:1fr; } }

    .feature-card {
      padding: 32px;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      transition: var(--trans);
    }
    .feature-card:hover { border-color: rgba(245,158,11,0.25); transform: translateY(-4px); box-shadow: 0 0 30px var(--gold-glow); }
    .feature-icon { font-size: 2.2rem; margin-bottom: 18px; }
    .feature-title{ font-size: 1.05rem; font-weight: 700; margin-bottom: 10px; }
    .feature-desc { font-size: 0.88rem; color: var(--text-muted); line-height: 1.8; }

    /* how-it-works alternating */
    .how-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; }
    @media(max-width:768px){ .how-grid{ grid-template-columns:1fr; gap:40px; } }
    .how-step-num {
      font-family: var(--font-display);
      font-size: 6rem;
      font-weight: 900;
      color: rgba(245,158,11,0.08);
      line-height: 1;
      margin-bottom: -20px;
    }
    .how-step-label { font-size: 0.78rem; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: var(--gold); margin-bottom: 12px; }
    .how-step-title { font-size: 1.7rem; font-weight: 800; margin-bottom: 14px; }
    .how-step-desc  { color: var(--text-muted); line-height: 1.9; }
    .how-step-points{ margin-top: 20px; display: flex; flex-direction: column; gap: 10px; }
    .how-point      { display: flex; align-items: center; gap: 12px; font-size: 0.9rem; color: var(--text-muted); }
    .how-point::before{ content:'→'; color: var(--gold); font-weight: 700; flex-shrink:0; }
    .how-visual {
      border-radius: var(--radius-xl);
      background: var(--bg-card);
      border: 1px solid var(--border);
      padding: 32px;
      position: relative;
      overflow: hidden;
    }
    .how-visual::after {
      content:'';
      position:absolute; inset:0;
      background: radial-gradient(ellipse at center, rgba(245,158,11,0.05), transparent 70%);
    }

    /* challenge preview strip */
    .challenges-preview { display: grid; grid-template-columns: repeat(3,1fr); gap: 24px; }
    @media(max-width:900px){ .challenges-preview{ grid-template-columns:1fr; } }

    /* creator strip */
    .creators-strip { display: grid; grid-template-columns: repeat(4,1fr); gap: 24px; }
    @media(max-width:1024px){ .creators-strip{ grid-template-columns:repeat(2,1fr); } }
    @media(max-width:600px) { .creators-strip{ grid-template-columns:1fr; } }

    /* testimonials */
    .testimonials-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 28px; }
    @media(max-width:900px){ .testimonials-grid{ grid-template-columns:1fr; } }

    /* brand logos / partners */
    .partners-strip { display: flex; align-items: center; justify-content: center; gap: 48px; flex-wrap: wrap; padding: 40px 0; border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
    .partner-logo { font-family: var(--font-display); font-size: 0.85rem; font-weight: 700; color: var(--text-dim); letter-spacing: 0.12em; transition: var(--trans); }
    .partner-logo:hover { color: var(--gold); }

    /* announcement bar */
    .announcement-bar {
      background: linear-gradient(90deg, var(--gold-dark), var(--gold), var(--gold-dark));
      background-size: 200% auto;
      animation: shimmer 3s linear infinite;
      padding: 10px 24px;
      text-align: center;
      font-size: 0.84rem;
      font-weight: 700;
      color: #000;
      letter-spacing: 0.04em;
      position: sticky; top: 0; z-index: 1001;
    }
    .announcement-bar a { color: #000; text-decoration: underline; }
  </style>
</head>
<body>

<!-- ─── Announcement Bar ───────────────────────────────────── -->
<div class="announcement-bar">
  🚀 עונה 2 של צ'אלנג "הרומן האבוד" מתחילה ב-15 אפריל — <a href="challenges.html">הרשמו עכשיו</a> | 🏆 פרסים: $10,000 לכותבים
</div>

<!-- ─── Navbar ──────────────────────────────────────────────── -->
<nav class="navbar" id="navbar">
  <div class="navbar-logo">
    <div class="logo-icon">✒</div>
    <div>
      <div class="logo-text">THE SHARED PEN</div>
      <div class="logo-sub">עט · קהילה · צ'אלנג</div>
    </div>
  </div>

  <ul class="navbar-nav">
    <li><a href="index.html" class="nav-link active">בית</a></li>
    <li><a href="challenges.html" class="nav-link">צ'אלנגים</a></li>
    <li><a href="creators.html" class="nav-link">יוצרים</a></li>
    <li><a href="programs.html" class="nav-link">תוכניות</a></li>
    <li><a href="products.html" class="nav-link">חנות</a></li>
  </ul>

  <div class="navbar-actions">
    <span class="nav-badge">BETA</span>
    <a href="#" class="btn btn-ghost btn-sm">התחבר</a>
    <a href="challenges.html" class="btn btn-primary btn-sm">הצטרף בחינם</a>
  </div>

  <button class="hamburger" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- Mobile Menu -->
<div class="mobile-menu">
  <a href="index.html" class="nav-link active">🏠 בית</a>
  <a href="challenges.html" class="nav-link">⚔️ צ'אלנגים</a>
  <a href="creators.html" class="nav-link">🎨 יוצרים</a>
  <a href="programs.html" class="nav-link">📚 תוכניות</a>
  <a href="products.html" class="nav-link">🛍️ חנות</a>
  <div style="margin-top:16px; display:flex; gap:10px;">
    <a href="#" class="btn btn-ghost btn-sm" style="flex:1;justify-content:center;">התחבר</a>
    <a href="challenges.html" class="btn btn-primary btn-sm" style="flex:1;justify-content:center;">הצטרף</a>
  </div>
</div>

<!-- ─── Hero ────────────────────────────────────────────────── -->
<section class="hero" id="home">
  <canvas id="particles" style="position:absolute;inset:0;width:100%;height:100%;z-index:0;pointer-events:none;"></canvas>
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>

  <div class="container">
    <div class="hero-two-col">
      <!-- Left: copy -->
      <div class="hero-content">
        <div class="hero-badge">
          <span class="dot"></span>
          הפלטפורמה הספרותית הראשונה מסוגה בעולם
        </div>

        <h1 class="heading-xl">
          <span class="gradient-text">כתוב.</span><br>
          <span style="color:var(--text)">התחרה.</span><br>
          <span class="gradient-text-blue">הפוך לאגדה.</span>
        </h1>

        <p class="hero-desc">
          העט המשותף היא פלטפורמת הצ'אלנגים הספרותיים הראשונה בעולם — גיימיפיקציה של כתיבה יצירתית בהשראת <strong style="color:var(--gold)">TryHackMe</strong>. השלם אתגרים, עלה ברמות, קבל מימון, ובנה קריירה בכתיבה.
        </p>

        <div class="hero-actions">
          <a href="challenges.html" class="btn btn-primary btn-lg">
            ⚔️ התחל לכתוב
          </a>
          <a href="programs.html" class="btn btn-outline btn-lg">
            📺 צפה בהדגמה
          </a>
        </div>

        <div class="hero-stats">
          <div>
            <div class="hero-stat-num"><span data-count="48000" data-suffix="+">0</span></div>
            <div class="hero-stat-label">כותבים פעילים</div>
          </div>
          <div>
            <div class="hero-stat-num"><span data-count="320" data-suffix="+">0</span></div>
            <div class="hero-stat-label">צ'אלנגים</div>
          </div>
          <div>
            <div class="hero-stat-num"><span data-count="127">0</span></div>
            <div class="hero-stat-label">מדינות</div>
          </div>
          <div>
            <div class="hero-stat-num">$<span data-count="2400000" data-suffix="">0</span></div>
            <div class="hero-stat-label">שולם ליוצרים</div>
          </div>
        </div>
      </div>

      <!-- Right: terminal card -->
      <div class="hero-visual animate-float">
        <div class="hero-terminal">
          <div class="terminal-header">
            <div class="terminal-dot" style="background:#ff5f57;"></div>
            <div class="terminal-dot" style="background:#febc2e;"></div>
            <div class="terminal-dot" style="background:#28c840;"></div>
            <span style="font-size:0.78rem;color:var(--text-dim);margin-right:auto;font-family:'Courier New',monospace;">shared-pen v2.4.1</span>
          </div>
          <div class="terminal-body">
            <div class="t-line"><span class="t-prompt">✒ ~</span><span class="t-text">&nbsp;pen start --challenge "הרומן האבוד"</span></div>
            <div class="t-output">▶ טוען צ'אלנג... [████████] 100%</div>
            <div class="t-output">✓ הצ'אלנג נפתח בהצלחה</div>
            <div class="t-line"><span class="t-prompt">✒ ~</span><span class="t-text">&nbsp;pen status</span></div>
            <div class="t-output">📊 רמה: <span style="color:var(--gold)">Master Writer</span> (12,450 XP)</div>
            <div class="t-output">🏆 דירוג גלובלי: <span style="color:var(--gold)">#47</span></div>
            <div class="t-output">💰 הכנסה חודשית: <span style="color:var(--emerald)">$840</span></div>
            <div class="t-line"><span class="t-prompt">✒ ~</span><span class="t-text">&nbsp;<span class="t-cursor"></span></span></div>
          </div>
        </div>

        <!-- Floating badges -->
        <div style="position:absolute; top:-16px; left:-20px; background:var(--bg-card); border:1px solid rgba(16,185,129,0.4); border-radius:12px; padding:10px 14px; display:flex; align-items:center; gap:8px; font-size:0.8rem; box-shadow: 0 4px 20px rgba(0,0,0,0.4);">
          <span style="color:var(--emerald);">✓</span>
          <span style="font-weight:600;">צ'אלנג הושלם!</span>
          <span style="color:var(--gold); font-weight:700;">+250 XP</span>
        </div>
        <div style="position:absolute; bottom:-16px; right:-20px; background:var(--bg-card); border:1px solid rgba(245,158,11,0.4); border-radius:12px; padding:10px 14px; display:flex; align-items:center; gap:8px; font-size:0.8rem; box-shadow: 0 4px 20px rgba(0,0,0,0.4);">
          <span>🏅</span>
          <span style="font-weight:600;">עלית לרמה!</span>
          <span style="color:var(--gold); font-weight:700;">Legend</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ─── Partners / As seen in ──────────────────────────────── -->
<section class="section-sm" style="background:var(--bg-secondary);">
  <div class="container">
    <p style="text-align:center;font-size:0.78rem;letter-spacing:0.12em;color:var(--text-dim);text-transform:uppercase;margin-bottom:32px;font-weight:700;">כפי שנראה ב-</p>
    <div class="partners-strip">
      <div class="partner-logo">MASHABLE</div>
      <div class="partner-logo">WIRED</div>
      <div class="partner-logo">THE GUARDIAN</div>
      <div class="partner-logo">HAARETZ</div>
      <div class="partner-logo">TECHCRUNCH</div>
      <div class="partner-logo">LITERARY HUB</div>
    </div>
  </div>
</section>

<!-- ─── Features ────────────────────────────────────────────── -->
<section class="section" id="features">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-tag">⚡ למה אנחנו</div>
      <h2 class="heading-lg">פלטפורמה שנבנתה<br><span class="gradient-text">לכותבים רציניים</span></h2>
      <p class="section-desc">גיימיפיקציה, מימון, קהילה ופיתוח מקצועי — הכל במקום אחד</p>
    </div>

    <div class="features-grid">
      <div class="feature-card reveal">
        <div class="feature-icon">⚔️</div>
        <h3 class="feature-title">צ'אלנגים מובנים</h3>
        <p class="feature-desc">מאות אתגרי כתיבה בכל רמות — מתחיל עד מאסטר — עם מסלולי למידה ופגישות פידבק אחת לשבוע.</p>
      </div>
      <div class="feature-card reveal" style="animation-delay:0.1s">
        <div class="feature-icon">🎮</div>
        <h3 class="feature-title">מערכת XP וסמלי כבוד</h3>
        <p class="feature-desc">כל מילה שאתה כותב מתרגמת לניקוד. עלה ברמות, זכה בתגים, הופיע בלוח המובילים העולמי.</p>
      </div>
      <div class="feature-card reveal" style="animation-delay:0.2s">
        <div class="feature-icon">💰</div>
        <h3 class="feature-title">מימון קבוע ליוצרים</h3>
        <p class="feature-desc">יוצרי תוכן שעוברים אודישן מקבלים מימון חודשי קבוע + אחוז ממכירות הקורסים והתוכן שלהם.</p>
      </div>
      <div class="feature-card reveal" style="animation-delay:0.1s">
        <div class="feature-icon">🌍</div>
        <h3 class="feature-title">קהילה גלובלית</h3>
        <p class="feature-desc">127 מדינות, 48,000+ כותבים. פגש שותפי כתיבה, השתתף בג'אמים, ופרסם לקהל בינלאומי.</p>
      </div>
      <div class="feature-card reveal" style="animation-delay:0.2s">
        <div class="feature-icon">📊</div>
        <h3 class="feature-title">דאשבורד אנליטיקה</h3>
        <p class="feature-desc">עקוב אחרי הצמיחה שלך — מילים ליום, קוראים פעילים, ציוני ביצוע, מגמות שיפור אישיות.</p>
      </div>
      <div class="feature-card reveal" style="animation-delay:0.3s">
        <div class="feature-icon">🏆</div>
        <h3 class="feature-title">תחרויות עם פרסים אמיתיים</h3>
        <p class="feature-desc">עונות תחרות רבעוניות עם פרסי כסף, חוזי פרסום, ביקורות מסוכנויות ספרותיות בינלאומיות.</p>
      </div>
    </div>
  </div>
</section>

<!-- ─── How It Works ─────────────────────────────────────────── -->
<section class="section" style="background:var(--bg-secondary);" id="how">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-tag">🗺️ איך זה עובד</div>
      <h2 class="heading-lg">מ<span class="gradient-text">כותב לאגדה</span> — בארבעה שלבים</h2>
    </div>

    <!-- Step 1 -->
    <div class="how-grid" style="margin-bottom:80px;">
      <div class="reveal">
        <div class="how-step-num">01</div>
        <div class="how-step-label">שלב ראשון</div>
        <h3 class="how-step-title">בחר מסלול ורמה</h3>
        <p class="how-step-desc">כל כותב מתחיל בהערכת בסיס קצרה שמאפשרת לנו לבנות עבורך מסלול אישי — מסתורין, פנטזיה, sci-fi, מציאות, שירה ועוד.</p>
        <div class="how-step-points">
          <div class="how-point">הערכת רמה חכמה ב-10 דקות</div>
          <div class="how-point">מסלולים בעברית, ערבית ואנגלית</div>
          <div class="how-point">התאמה לסגנון ולמטרות שלך</div>
        </div>
      </div>
      <div class="how-visual reveal">
        <div style="display:grid;gap:12px;">
          <div style="background:rgba(245,158,11,0.1);border:1px solid rgba(245,158,11,0.3);border-radius:12px;padding:18px;display:flex;align-items:center;gap:16px;">
            <div style="font-size:1.8rem;">🔮</div>
            <div>
              <div style="font-weight:700;margin-bottom:4px;">מסתורין ומתח</div>
              <div style="font-size:0.8rem;color:var(--text-muted);">340 צ'אלנגים · 12,400 כותבים</div>
            </div>
            <div style="margin-right:auto;"><span class="badge-medium challenge-badge">מוצלח</span></div>
          </div>
          <div style="background:rgba(99,102,241,0.08);border:1px solid rgba(99,102,241,0.2);border-radius:12px;padding:18px;display:flex;align-items:center;gap:16px;">
            <div style="font-size:1.8rem;">🚀</div>
            <div>
              <div style="font-weight:700;margin-bottom:4px;">מדע בדיוני</div>
              <div style="font-size:0.8rem;color:var(--text-muted);">280 צ'אלנגים · 8,900 כותבים</div>
            </div>
            <div style="margin-right:auto;"><span class="badge-hard challenge-badge">אתגר</span></div>
          </div>
          <div style="background:rgba(16,185,129,0.06);border:1px solid rgba(16,185,129,0.2);border-radius:12px;padding:18px;display:flex;align-items:center;gap:16px;">
            <div style="font-size:1.8rem;">🌹</div>
            <div>
              <div style="font-weight:700;margin-bottom:4px;">רומן וסיפורת</div>
              <div style="font-size:0.8rem;color:var(--text-muted);">190 צ'אלנגים · 15,200 כותבים</div>
            </div>
            <div style="margin-right:auto;"><span class="badge-easy challenge-badge">פתוח</span></div>
          </div>
        </div>
      </div>
    </div>

    <!-- Step 2 -->
    <div class="how-grid" style="margin-bottom:80px;">
      <div class="how-visual reveal" style="order:2;">
        <div style="text-align:center;">
          <div style="font-size:5rem;margin-bottom:16px;" class="animate-float">✍️</div>
          <div style="display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin-bottom:20px;">
            <span class="tag">⏱ 48 שעות</span>
            <span class="tag">📝 min 500 מילים</span>
            <span class="tag">🌐 פומבי</span>
          </div>
          <div style="background:rgba(245,158,11,0.08);border:1px solid rgba(245,158,11,0.2);border-radius:12px;padding:20px;text-align:right;">
            <div style="font-size:0.78rem;color:var(--gold);font-weight:700;margin-bottom:8px;">PROMPT // הנחיית הצ'אלנג</div>
            <p style="font-size:0.9rem;line-height:1.8;color:var(--text-muted);">"כתוב פתיחה לרומן שבה הגיבור מגלה שכל זכרונות ילדותו הם שקר — אך הסיבה לכך טומנת בחובה תקווה."</p>
          </div>
        </div>
      </div>
      <div class="reveal" style="order:1;">
        <div class="how-step-num">02</div>
        <div class="how-step-label">שלב שני</div>
        <h3 class="how-step-title">קבל את הפרומפט, כתוב</h3>
        <p class="how-step-desc">כל שבוע עולה פרומפט חדש עם זמן כתיבה מוגדר. הכותב קורא, מרגיש, ומוציא יצירה. ללא גבולות, עם כיוון.</p>
        <div class="how-step-points">
          <div class="how-point">פרומפטים שנכתבו על ידי סופרים מקצועיים</div>
          <div class="how-point">כלי עריכה מובנה בפלטפורמה</div>
          <div class="how-point">שמירה אוטומטית וגיבוי ענן</div>
        </div>
      </div>
    </div>

    <!-- Step 3 & 4 brief -->
    <div class="grid-2" style="gap:40px;">
      <div class="card reveal">
        <div class="how-step-num" style="font-size:4rem;margin-bottom:8px;">03</div>
        <div class="how-step-label">שלב שלישי</div>
        <h3 class="heading-sm" style="margin-bottom:12px;">קבל פידבק וניקוד</h3>
        <p style="font-size:0.9rem;color:var(--text-muted);line-height:1.8;">הקהילה מצביעת, AI נותן פידבק ראשוני, ויוצרי תוכן מוסמכים בוחרים מועדפים שמקבלים XP כפולה.</p>
      </div>
      <div class="card reveal" style="animation-delay:0.15s;">
        <div class="how-step-num" style="font-size:4rem;margin-bottom:8px;">04</div>
        <div class="how-step-label">שלב רביעי</div>
        <h3 class="heading-sm" style="margin-bottom:12px;">הרוויח ובנה מוניטין</h3>
        <p style="font-size:0.9rem;color:var(--text-muted);line-height:1.8;">כסף, ספרים, חוזים, קורסים — כל אחד שמגיע לרמת Creator+ מקבל גישה לתוכנית המימון הקבועה.</p>
      </div>
    </div>
  </div>
</section>

<!-- ─── Featured Challenges ──────────────────────────────────── -->
<section class="section" id="challenges-preview">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-tag">⚔️ צ'אלנגים</div>
      <h2 class="heading-lg">אתגרי הספרות <span class="gradient-text">הבוערים כעת</span></h2>
      <p class="section-desc">מאות אתגרים פעילים — כל אחד מחכה לקול שלך</p>
    </div>

    <div class="challenges-preview">
      <!-- Card 1 -->
      <div class="challenge-card reveal" data-category="mystery">
        <div class="challenge-header">
          <div class="challenge-icon" style="background:rgba(244,63,94,0.1);">🔮</div>
          <span class="challenge-badge badge-hard">קשה</span>
        </div>
        <h3 class="challenge-title">הרומן האבוד</h3>
        <p class="challenge-desc">מצא את הזהות האמיתית של הגיבור בעזרת רמזים טקסטואליים שמסתתרים בין השורות. צ'אלנג מרובה שלבים.</p>
        <div class="challenge-meta">
          <span>⚡ 1,240 XP</span>
          <span>👥 3,842 כותבים</span>
          <span>⏱ 72 שעות</span>
        </div>
        <div class="challenge-progress">
          <div class="progress-bar"><div class="progress-fill" style="width:0%" data-width="68%"></div></div>
          <div class="progress-text"><span>68% השלימו</span><span>🔥 טרנד</span></div>
        </div>
      </div>

      <!-- Card 2 -->
      <div class="challenge-card reveal card-glow" data-category="scifi" style="animation-delay:0.1s">
        <div style="position:absolute;top:16px;left:16px;background:var(--gold);color:#000;font-size:0.7rem;font-weight:800;padding:3px 10px;border-radius:99px;letter-spacing:0.08em;">🔥 HOT</div>
        <div class="challenge-header" style="margin-top:12px;">
          <div class="challenge-icon" style="background:rgba(99,102,241,0.1);">🚀</div>
          <span class="challenge-badge badge-expert">אקספרט</span>
        </div>
        <h3 class="challenge-title">שנת 2099: קריסת הזיכרון</h3>
        <p class="challenge-desc">בניית עולם sci-fi שלם בסיפור קצר — כלכלה, שפה, טכנולוגיה וקונפליקט. שופטים מסוכנויות ספרות בינלאומיות.</p>
        <div class="challenge-meta">
          <span>⚡ 2,800 XP</span>
          <span>👥 967 כותבים</span>
          <span>⏱ 5 ימים</span>
        </div>
        <div class="challenge-progress">
          <div class="progress-bar"><div class="progress-fill" style="width:0%" data-width="32%"></div></div>
          <div class="progress-text"><span>32% השלימו</span><span>⭐ מוצע</span></div>
        </div>
      </div>

      <!-- Card 3 -->
      <div class="challenge-card reveal" data-category="poetry" style="animation-delay:0.2s">
        <div class="challenge-header">
          <div class="challenge-icon" style="background:rgba(16,185,129,0.1);">🌿</div>
          <span class="challenge-badge badge-easy">קל</span>
        </div>
        <h3 class="challenge-title">שיר ה-6 המילים</h3>
        <p class="challenge-desc">ביטוי שלם בדיוק שש מילים — חלוצי הז'אנר של Hemingway, מועמד לפרסי הפלטפורמה השבועיים.</p>
        <div class="challenge-meta">
          <span>⚡ 350 XP</span>
          <span>👥 11,230 כותבים</span>
          <span>⏱ 24 שעות</span>
        </div>
        <div class="challenge-progress">
          <div class="progress-bar"><div class="progress-fill" style="width:0%" data-width="89%"></div></div>
          <div class="progress-text"><span>89% השלימו</span><span>✅ פתוח</span></div>
        </div>
      </div>
    </div>

    <div style="text-align:center;margin-top:48px;" class="reveal">
      <a href="challenges.html" class="btn btn-outline btn-lg">ראה את כל 320 הצ'אלנגים →</a>
    </div>
  </div>
</section>

<!-- ─── Stats ────────────────────────────────────────────────── -->
<section class="section-sm" style="background:var(--bg-secondary);">
  <div class="container">
    <div class="grid-4">
      <div class="stat-card reveal">
        <div class="stat-icon">✍️</div>
        <div class="stat-num"><span data-count="48000" data-suffix="+">0</span></div>
        <div class="stat-label">כותבים פעילים</div>
      </div>
      <div class="stat-card reveal" style="animation-delay:0.1s">
        <div class="stat-icon">📜</div>
        <div class="stat-num"><span data-count="320" data-suffix="+">0</span></div>
        <div class="stat-label">צ'אלנגים</div>
      </div>
      <div class="stat-card reveal" style="animation-delay:0.2s">
        <div class="stat-icon">💰</div>
        <div class="stat-num">$<span data-count="2400000" data-suffix="">0</span></div>
        <div class="stat-label">שולם ליוצרים</div>
      </div>
      <div class="stat-card reveal" style="animation-delay:0.3s">
        <div class="stat-icon">🌍</div>
        <div class="stat-num"><span data-count="127">0</span></div>
        <div class="stat-label">מדינות</div>
      </div>
    </div>
  </div>
</section>

<!-- ─── Featured Creators ───────────────────────────────────── -->
<section class="section" id="creators-preview">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-tag">🎨 יוצרי תוכן</div>
      <h2 class="heading-lg">הקולות שמניעים <span class="gradient-text">את הקהילה</span></h2>
      <p class="section-desc">יוצרים מממומנים שמייצרים תוכן, מנהלים צ'אלנגים ומחנכים את הדור הבא של הסופרים</p>
    </div>

    <div class="creators-strip">
      <div class="creator-card reveal">
        <div class="creator-avatar">🦁<div class="creator-verified">✓</div></div>
        <div class="creator-name">נועה כהן</div>
        <div class="creator-title">מאסטר מסתורין ופסיכולוגיה</div>
        <div class="creator-tags">
          <span class="creator-tag">מתח</span>
          <span class="creator-tag">פסיכולוגי</span>
          <span class="creator-tag">עברית</span>
        </div>
        <div class="creator-stats">
          <div><div class="creator-stat-num">8.4K</div><div class="creator-stat-label">עוקבים</div></div>
          <div><div class="creator-stat-num">42</div><div class="creator-stat-label">צ'אלנגים</div></div>
          <div><div class="creator-stat-num">4.9★</div><div class="creator-stat-label">דירוג</div></div>
        </div>
        <div class="creator-funding">💰 מימון קבוע: $640/חודש</div>
        <a href="creators.html" class="btn btn-outline" style="width:100%;justify-content:center;">פגוש את נועה</a>
      </div>

      <div class="creator-card reveal" style="animation-delay:0.1s">
        <div class="creator-avatar" style="background:linear-gradient(135deg,#6366f1,#06b6d4);">🌊<div class="creator-verified">✓</div></div>
        <div class="creator-name">Ahmad Khalil</div>
        <div class="creator-title">World-builder & Epic Fantasy</div>
        <div class="creator-tags">
          <span class="creator-tag">Fantasy</span>
          <span class="creator-tag">World Building</span>
          <span class="creator-tag">العربية</span>
        </div>
        <div class="creator-stats">
          <div><div class="creator-stat-num">12.1K</div><div class="creator-stat-label">Followers</div></div>
          <div><div class="creator-stat-num">67</div><div class="creator-stat-label">Challenges</div></div>
          <div><div class="creator-stat-num">4.8★</div><div class="creator-stat-label">Rating</div></div>
        </div>
        <div class="creator-funding">💰 מימון קבוע: $1,200/month</div>
        <a href="creators.html" class="btn btn-outline" style="width:100%;justify-content:center;">Meet Ahmad</a>
      </div>

      <div class="creator-card reveal" style="animation-delay:0.2s">
        <div class="creator-avatar" style="background:linear-gradient(135deg,#10b981,#06b6d4);">🌿<div class="creator-verified">✓</div></div>
        <div class="creator-name">Sara Okonkwo</div>
        <div class="creator-title">Afrofuturism & Literary Fiction</div>
        <div class="creator-tags">
          <span class="creator-tag">Sci-Fi</span>
          <span class="creator-tag">Literary</span>
          <span class="creator-tag">English</span>
        </div>
        <div class="creator-stats">
          <div><div class="creator-stat-num">19.3K</div><div class="creator-stat-label">Followers</div></div>
          <div><div class="creator-stat-num">89</div><div class="creator-stat-label">Challenges</div></div>
          <div><div class="creator-stat-num">5.0★</div><div class="creator-stat-label">Rating</div></div>
        </div>
        <div class="creator-funding">💰 Top Creator: $2,400/month</div>
        <a href="creators.html" class="btn btn-outline" style="width:100%;justify-content:center;">Meet Sara</a>
      </div>

      <div class="creator-card reveal" style="animation-delay:0.3s">
        <div class="creator-avatar" style="background:linear-gradient(135deg,#f43f5e,#f59e0b);">🔥<div class="creator-verified">✓</div></div>
        <div class="creator-name">דניאל לוי</div>
        <div class="creator-title">שירה וכתיבה ניסיונית</div>
        <div class="creator-tags">
          <span class="creator-tag">שירה</span>
          <span class="creator-tag">ניסיוני</span>
          <span class="creator-tag">עברית</span>
        </div>
        <div class="creator-stats">
          <div><div class="creator-stat-num">6.7K</div><div class="creator-stat-label">עוקבים</div></div>
          <div><div class="creator-stat-num">28</div><div class="creator-stat-label">צ'אלנגים</div></div>
          <div><div class="creator-stat-num">4.7★</div><div class="creator-stat-label">דירוג</div></div>
        </div>
        <div class="creator-funding">💰 מימון קבוע: $480/חודש</div>
        <a href="creators.html" class="btn btn-outline" style="width:100%;justify-content:center;">פגוש את דניאל</a>
      </div>
    </div>

    <div style="text-align:center;margin-top:48px;" class="reveal">
      <a href="creators.html" class="btn btn-ghost btn-lg">ראה את כל יוצרי התוכן →</a>
    </div>
  </div>
</section>

<!-- ─── Leaderboard Preview ──────────────────────────────────── -->
<section class="section" style="background:var(--bg-secondary);" id="leaderboard">
  <div class="container">
    <div class="grid-2" style="align-items:start;gap:60px;">
      <div>
        <div class="section-header" style="text-align:right;margin-bottom:40px;" class="reveal">
          <div class="section-tag">🏆 לוח מובילים</div>
          <h2 class="heading-lg">מי מוביל <span class="gradient-text">עכשיו?</span></h2>
          <p style="color:var(--text-muted);line-height:1.8;margin-top:12px;">לוח המובילים מתעדכן בזמן אמת. צבר XP, עלה בדירוג, שלוט בעולם הכתיבה.</p>
        </div>
        <div>
          <div class="leaderboard-row top-1 reveal">
            <div class="lb-rank" style="color:var(--gold);">🥇</div>
            <div class="lb-avatar">🦁</div>
            <div><div class="lb-name">נועה כהן</div><div class="lb-meta">ישראל · Master Writer</div></div>
            <div class="lb-points">48,920 XP</div>
            <div class="lb-badge">👑</div>
          </div>
          <div class="leaderboard-row top-2 reveal">
            <div class="lb-rank" style="color:#aaa;">🥈</div>
            <div class="lb-avatar">🌊</div>
            <div><div class="lb-name">Ahmad Khalil</div><div class="lb-meta">ירדן · Legend</div></div>
            <div class="lb-points">44,110 XP</div>
            <div class="lb-badge">⚡</div>
          </div>
          <div class="leaderboard-row top-3 reveal">
            <div class="lb-rank" style="color:#cd7f32;">🥉</div>
            <div class="lb-avatar">🌿</div>
            <div><div class="lb-name">Sara Okonkwo</div><div class="lb-meta">ניגריה · Legend</div></div>
            <div class="lb-points">41,850 XP</div>
            <div class="lb-badge">🔥</div>
          </div>
          <div class="leaderboard-row reveal">
            <div class="lb-rank" style="color:var(--text-dim);">4</div>
            <div class="lb-avatar">🔮</div>
            <div><div class="lb-name">Yuki Tanaka</div><div class="lb-meta">יפן · Expert</div></div>
            <div class="lb-points">38,240 XP</div>
            <div class="lb-badge">🌟</div>
          </div>
          <div class="leaderboard-row reveal">
            <div class="lb-rank" style="color:var(--text-dim);">5</div>
            <div class="lb-avatar">🔥</div>
            <div><div class="lb-name">דניאל לוי</div><div class="lb-meta">ישראל · Expert</div></div>
            <div class="lb-points">35,700 XP</div>
            <div class="lb-badge">✍️</div>
          </div>
        </div>
        <div style="margin-top:24px;" class="reveal">
          <a href="challenges.html" class="btn btn-primary">הצטרף לתחרות</a>
        </div>
      </div>

      <!-- Right: level system -->
      <div class="reveal">
        <h3 class="heading-md" style="margin-bottom:32px;">🎖️ מערכת הרמות</h3>
        <div style="display:flex;flex-direction:column;gap:14px;">
          <div style="display:flex;align-items:center;gap:16px;padding:16px 20px;border-radius:12px;background:rgba(16,185,129,0.06);border:1px solid rgba(16,185,129,0.2);">
            <div style="font-size:1.5rem;">🌱</div>
            <div style="flex:1;"><div style="font-weight:700;font-size:0.9rem;">Beginner</div><div style="font-size:0.78rem;color:var(--text-muted);">0 – 1,000 XP</div></div>
            <div class="progress-bar" style="width:80px;"><div class="progress-fill" data-width="100%" style="background:var(--emerald);width:100%;"></div></div>
          </div>
          <div style="display:flex;align-items:center;gap:16px;padding:16px 20px;border-radius:12px;background:rgba(6,182,212,0.06);border:1px solid rgba(6,182,212,0.2);">
            <div style="font-size:1.5rem;">📖</div>
            <div style="flex:1;"><div style="font-weight:700;font-size:0.9rem;">Storyteller</div><div style="font-size:0.78rem;color:var(--text-muted);">1,000 – 5,000 XP</div></div>
            <div class="progress-bar" style="width:80px;"><div class="progress-fill" data-width="75%" style="background:var(--cyan);width:75%;"></div></div>
          </div>
          <div style="display:flex;align-items:center;gap:16px;padding:16px 20px;border-radius:12px;background:rgba(245,158,11,0.06);border:1px solid rgba(245,158,11,0.2);">
            <div style="font-size:1.5rem;">✒️</div>
            <div style="flex:1;"><div style="font-weight:700;font-size:0.9rem;">Author</div><div style="font-size:0.78rem;color:var(--text-muted);">5,000 – 15,000 XP</div></div>
            <div class="progress-bar" style="width:80px;"><div class="progress-fill" data-width="50%" style="background:var(--gold);width:50%;"></div></div>
          </div>
          <div style="display:flex;align-items:center;gap:16px;padding:16px 20px;border-radius:12px;background:rgba(99,102,241,0.06);border:1px solid rgba(99,102,241,0.2);">
            <div style="font-size:1.5rem;">🏆</div>
            <div style="flex:1;"><div style="font-weight:700;font-size:0.9rem;">Master Writer</div><div style="font-size:0.78rem;color:var(--text-muted);">15,000 – 40,000 XP</div></div>
            <div class="progress-bar" style="width:80px;"><div class="progress-fill" data-width="30%" style="background:var(--indigo);width:30%;"></div></div>
          </div>
          <div style="display:flex;align-items:center;gap:16px;padding:16px 20px;border-radius:12px;background:rgba(245,158,11,0.1);border:1px solid rgba(245,158,11,0.4);">
            <div style="font-size:1.5rem;">👑</div>
            <div style="flex:1;"><div style="font-weight:700;font-size:0.9rem;">Legend</div><div style="font-size:0.78rem;color:var(--gold);">40,000+ XP · מימון קבוע</div></div>
            <div class="progress-bar" style="width:80px;"><div class="progress-fill" data-width="100%" style="background:linear-gradient(90deg,var(--gold),var(--indigo));width:100%;"></div></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ─── Testimonials ─────────────────────────────────────────── -->
<section class="section" id="testimonials">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-tag">💬 מה אומרים</div>
      <h2 class="heading-lg">הכותבים <span class="gradient-text">מדברים</span></h2>
    </div>
    <div class="testimonials-grid">
      <div class="testimonial-card reveal">
        <div class="stars">★★★★★</div>
        <p class="testimonial-quote">לפני שנה לא האמנתי שאפשר להרוויח כסף מכתיבה. היום אני מרוויחה $840 בחודש מהפלטפורמה — ועדיין עובדת על הרומן הראשון שלי.</p>
        <div class="testimonial-author">
          <div class="t-avatar">🦁</div>
          <div><div class="t-name">נועה כהן</div><div class="t-role">Master Writer · ישראל</div></div>
        </div>
      </div>
      <div class="testimonial-card reveal" style="animation-delay:0.1s">
        <div class="stars">★★★★★</div>
        <p class="testimonial-quote">The challenge system pushed me to write every single day. I went from a hobbyist to a published short story writer in 8 months. This platform changed my life.</p>
        <div class="testimonial-author">
          <div class="t-avatar" style="background:linear-gradient(135deg,#10b981,#06b6d4);">🌿</div>
          <div><div class="t-name">Sara Okonkwo</div><div class="t-role">Legend · Nigeria</div></div>
        </div>
      </div>
      <div class="testimonial-card reveal" style="animation-delay:0.2s">
        <div class="stars">★★★★★</div>
        <p class="testimonial-quote">المنصة غيّرت مفهومي عن الكتابة. الـ challenges أجبرتني على التفكير خارج الصندوق، والمجتمع يدعمك في كل خطوة. التمويل الشهري حقّق حلمي.</p>
        <div class="testimonial-author">
          <div class="t-avatar" style="background:linear-gradient(135deg,#6366f1,#06b6d4);">🌊</div>
          <div><div class="t-name">Ahmad Khalil</div><div class="t-role">Legend · Jordan</div></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ─── CTA ──────────────────────────────────────────────────── -->
<section class="section" style="background:var(--bg-secondary);">
  <div class="container">
    <div class="cta-banner reveal">
      <div class="section-tag" style="margin-bottom:24px;">🚀 הצטרף עכשיו</div>
      <h2 class="heading-lg" style="margin-bottom:16px;">מוכן לכתוב את <span class="gradient-text">הסיפור שלך?</span></h2>
      <p class="section-desc" style="margin:0 auto 44px;">הצטרף ל-48,000+ כותבים מ-127 מדינות. ההרשמה בחינם — תמיד.</p>
      <div style="display:flex;gap:16px;justify-content:center;flex-wrap:wrap;">
        <a href="challenges.html" class="btn btn-primary btn-lg">⚔️ התחל בצ'אלנג הראשון שלך</a>
        <a href="creators.html" class="btn btn-outline btn-lg">🎨 הפוך ליוצר תוכן</a>
      </div>
      <p style="margin-top:24px;font-size:0.82rem;color:var(--text-muted);">ללא כרטיס אשראי · ביטול בכל עת · ממשק בעברית, ערבית ואנגלית</p>
    </div>
  </div>
</section>

<!-- ─── Footer ───────────────────────────────────────────────── -->
<footer class="footer">
  <div class="container">
    <div class="footer-grid">
      <div>
        <div class="navbar-logo" style="margin-bottom:0;">
          <div class="logo-icon">✒</div>
          <div>
            <div class="logo-text">THE SHARED PEN</div>
            <div class="logo-sub">עט · קהילה · צ'אלנג</div>
          </div>
        </div>
        <p class="footer-brand-desc">פלטפורמת הכתיבה היצירתית הגלובלית הראשונה המבוססת על גיימיפיקציה, קהילה ומימון קבוע ליוצרים.</p>
        <div class="footer-social">
          <a href="#" class="social-btn">𝕏</a>
          <a href="#" class="social-btn">in</a>
          <a href="#" class="social-btn">▶</a>
          <a href="#" class="social-btn">📸</a>
          <a href="#" class="social-btn">💬</a>
        </div>
      </div>
      <div>
        <div class="footer-heading">פלטפורמה</div>
        <ul class="footer-links">
          <li><a href="challenges.html" class="footer-link">צ'אלנגים</a></li>
          <li><a href="programs.html" class="footer-link">תוכניות לימוד</a></li>
          <li><a href="#leaderboard" class="footer-link">לוח מובילים</a></li>
          <li><a href="creators.html" class="footer-link">יוצרי תוכן</a></li>
          <li><a href="products.html" class="footer-link">חנות</a></li>
        </ul>
      </div>
      <div>
        <div class="footer-heading">קהילה</div>
        <ul class="footer-links">
          <li><a href="#" class="footer-link">Discord</a></li>
          <li><a href="#" class="footer-link">פורום</a></li>
          <li><a href="#" class="footer-link">בלוג</a></li>
          <li><a href="#" class="footer-link">אירועים</a></li>
          <li><a href="#" class="footer-link">תחרויות</a></li>
        </ul>
      </div>
      <div>
        <div class="footer-heading">חברה</div>
        <ul class="footer-links">
          <li><a href="#" class="footer-link">אודות</a></li>
          <li><a href="#" class="footer-link">קריירה</a></li>
          <li><a href="#" class="footer-link">שותפים</a></li>
          <li><a href="#" class="footer-link">עיתונות</a></li>
          <li><a href="#" class="footer-link">צור קשר</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <div>© 2026 The Shared Pen. כל הזכויות שמורות.</div>
      <div class="footer-bottom-links">
        <a href="#" class="footer-link">פרטיות</a>
        <a href="#" class="footer-link">תנאי שימוש</a>
        <a href="#" class="footer-link">Cookies</a>
      </div>
      <div style="color:var(--gold);">✒ made with passion · בנוי עם תשוקה</div>
    </div>
  </div>
</footer>

<script src="js/main.js"></script>
</body>
</html>
