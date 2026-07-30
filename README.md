<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Judiciary Gold — Classroom se, Courtroom tak.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght,ital@9..144,300,0;9..144,500,0;9..144,600,0;9..144,700,0;9..144,900,0;9..144,600,1;9..144,900,1&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#14171C;
    --ink-2:#1C2028;
    --ink-line: rgba(241,236,223,0.14);
    --parchment:#EDE6D6;
    --parchment-2:#E2D7BE;
    --parchment-line: rgba(33,30,26,0.14);
    --brass:#C9A227;
    --brass-bright:#E4BE45;
    --oxblood:#7A1F2B;
    --cream:#F1ECDF;
    --ink-text:#211E1A;
    --muted-on-ink: rgba(241,236,223,0.68);
    --muted-on-parchment: rgba(33,30,26,0.66);
    --display: 'Fraunces', serif;
    --body: 'IBM Plex Sans', sans-serif;
    --mono: 'IBM Plex Mono', monospace;
    --max: 1180px;
  }

  *{ box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  body{
    margin:0;
    background:var(--ink);
    color:var(--cream);
    font-family:var(--body);
    line-height:1.55;
    -webkit-font-smoothing:antialiased;
  }
  img,svg{ display:block; max-width:100%; }
  a{ color:inherit; }
  h1,h2,h3{ font-family:var(--display); margin:0; font-weight:600; }
  p{ margin:0; }
  ul{ margin:0; padding:0; list-style:none; }
  .wrap{ max-width:var(--max); margin:0 auto; padding:0 clamp(1.25rem, 4vw, 2.5rem); }
  section{ position:relative; }

  :focus-visible{ outline:2px solid var(--brass-bright); outline-offset:3px; }

  .eyebrow{
    font-family:var(--mono);
    font-size:0.72rem;
    letter-spacing:0.16em;
    text-transform:uppercase;
    display:inline-flex;
    align-items:center;
    gap:0.6em;
    color:var(--brass-bright);
  }
  .eyebrow::before{
    content:"";
    width:1.4em; height:1px;
    background:var(--brass-bright);
    display:inline-block;
  }
  .on-parchment .eyebrow{ color:var(--oxblood); }
  .on-parchment .eyebrow::before{ background:var(--oxblood); }

  /* ---------- NAV ---------- */
  header{
    position:sticky; top:0; z-index:40;
    background:rgba(20,23,28,0.86);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--ink-line);
  }
  .nav{ display:flex; align-items:center; justify-content:space-between; padding:1.05rem clamp(1.25rem,4vw,2.5rem); }
  .brand{ display:flex; align-items:center; gap:0.65rem; text-decoration:none; }
  .brand .word{ font-family:var(--display); font-weight:600; font-size:1.15rem; letter-spacing:0.01em; }
  .brand .word small{ display:block; font-family:var(--mono); font-size:0.58rem; letter-spacing:0.22em; color:var(--muted-on-ink); font-weight:400; margin-top:0.15em; }
  .seal{ width:38px; height:38px; flex:none; }

  .nav-links{ display:flex; align-items:center; gap:2rem; }
  .nav-links a{ text-decoration:none; font-size:0.88rem; color:var(--muted-on-ink); transition:color .2s ease; }
  .nav-links a:hover{ color:var(--cream); }
  .btn{
    font-family:var(--mono);
    font-size:0.76rem;
    letter-spacing:0.04em;
    padding:0.7em 1.3em;
    border-radius:2px;
    border:1px solid transparent;
    cursor:pointer;
    text-decoration:none;
    display:inline-flex;
    align-items:center;
    gap:0.5em;
    transition:transform .18s ease, background .2s ease, border-color .2s ease;
  }
  .btn:hover{ transform:translateY(-1px); }
  .btn-brass{ background:var(--brass); color:var(--ink); }
  .btn-brass:hover{ background:var(--brass-bright); }
  .btn-ghost{ border-color:var(--ink-line); color:var(--cream); background:transparent; }
  .btn-ghost:hover{ border-color:var(--brass-bright); color:var(--brass-bright); }
  .btn-ghost.on-parchment{ border-color:var(--parchment-line); color:var(--ink-text); }
  .btn-ghost.on-parchment:hover{ border-color:var(--oxblood); color:var(--oxblood); }

  .menu-toggle{ display:none; background:none; border:1px solid var(--ink-line); color:var(--cream); width:40px; height:36px; border-radius:2px; cursor:pointer; }

  /* ---------- HERO ---------- */
  .hero{ padding:clamp(3rem,7vw,5.5rem) 0 clamp(3.5rem,8vw,6rem); overflow:hidden; }
  .hero .wrap{ display:grid; grid-template-columns:1.08fr 0.92fr; gap:clamp(2rem,5vw,4rem); align-items:center; }
  .hero h1{
    font-size:clamp(2.5rem, 5.6vw, 4.3rem);
    line-height:1.03;
    letter-spacing:-0.01em;
    margin:0.5rem 0 1.15rem;
  }
  .hero h1 em{ font-style:italic; color:var(--brass-bright); font-weight:500; }
  .hero .lede{ font-size:1.05rem; color:var(--muted-on-ink); max-width:34em; margin-bottom:1.9rem; }
  .hero-ctas{ display:flex; gap:0.9rem; flex-wrap:wrap; }

  /* order sheet card */
  .order-sheet{
    background:var(--parchment);
    color:var(--ink-text);
    padding:clamp(1.6rem,3vw,2.2rem);
    border:1px solid var(--parchment-line);
    position:relative;
    box-shadow:0 30px 60px -25px rgba(0,0,0,0.55);
    transform:rotate(1.1deg);
  }
  .order-sheet::before{
    content:"";
    position:absolute; inset:8px;
    border:1px solid rgba(33,30,26,0.22);
    pointer-events:none;
  }
  .os-head{ display:flex; justify-content:space-between; align-items:baseline; font-family:var(--mono); font-size:0.66rem; letter-spacing:0.08em; text-transform:uppercase; border-bottom:1px solid var(--parchment-line); padding-bottom:0.7rem; margin-bottom:1rem; color:var(--muted-on-parchment); }
  .os-title{ font-family:var(--mono); font-size:0.66rem; letter-spacing:0.1em; text-transform:uppercase; color:var(--oxblood); margin-bottom:0.15rem; }
  .os-matter{ font-family:var(--display); font-weight:600; font-size:1.28rem; margin-bottom:1rem; }
  .os-line{ font-family:var(--mono); font-size:0.68rem; letter-spacing:0.06em; text-transform:uppercase; color:var(--muted-on-parchment); margin-bottom:0.2rem; }
  .os-value{ font-size:0.92rem; margin-bottom:1rem; }
  .os-body{ font-size:0.9rem; color:var(--ink-text); margin-bottom:0.9rem; }
  .os-orders{ font-size:0.87rem; display:flex; flex-direction:column; gap:0.5rem; margin-bottom:1.3rem; }
  .os-orders li{ padding-left:1.5em; position:relative; }
  .os-foot{ display:flex; justify-content:space-between; align-items:flex-end; border-top:1px solid var(--parchment-line); padding-top:0.9rem; }
  .os-sig{ font-family:var(--display); font-style:italic; font-size:0.95rem; }
  .os-caseno{ font-family:var(--mono); font-size:0.62rem; color:var(--muted-on-parchment); text-align:right; }

  .stamp{
    position:absolute; top:-14px; right:-10px;
    width:118px; height:118px;
    border:2.5px solid var(--oxblood);
    border-radius:50%;
    display:flex; align-items:center; justify-content:center;
    transform:rotate(-16deg);
    color:var(--oxblood);
    font-family:var(--mono);
    font-size:0.62rem;
    letter-spacing:0.09em;
    text-transform:uppercase;
    text-align:center;
    line-height:1.3;
    background:rgba(122,31,43,0.04);
  }
  .stamp span{ padding:0 6px; }

  /* ---------- DOCKET STRIP ---------- */
  .docket{ border-top:1px solid var(--ink-line); border-bottom:1px solid var(--ink-line); background:var(--ink-2); }
  .docket .wrap{ display:flex; flex-wrap:wrap; }
  .docket-item{ flex:1 1 200px; padding:1.5rem clamp(1rem,3vw,2rem); border-right:1px solid var(--ink-line); }
  .docket-item:last-child{ border-right:none; }
  .docket-num{ font-family:var(--display); font-weight:600; font-size:1.9rem; color:var(--brass-bright); }
  .docket-label{ font-family:var(--mono); font-size:0.68rem; letter-spacing:0.06em; text-transform:uppercase; color:var(--muted-on-ink); margin-top:0.3rem; }

  /* ---------- SECTION SHELLS ---------- */
  .section{ padding:clamp(3.5rem,8vw,6rem) 0; }
  .on-parchment{ background:var(--parchment); color:var(--ink-text); }
  .section h2{ font-size:clamp(1.8rem,3.4vw,2.6rem); margin:0.6rem 0 0.9rem; letter-spacing:-0.01em; }
  .section .intro{ max-width:38em; color:var(--muted-on-ink); font-size:1rem; margin-bottom:2.6rem; }
  .on-parchment .intro{ color:var(--muted-on-parchment); }

  /* ---------- EXAMS GRID ---------- */
  .exam-grid{ display:grid; grid-template-columns:repeat(auto-fill,minmax(168px,1fr)); gap:0.85rem; margin-bottom:2.2rem; }
  .exam-pill{
    border:1px solid var(--parchment-line);
    background:var(--parchment-2);
    padding:0.95rem 1.1rem;
    transition:border-color .2s ease, transform .2s ease;
  }
  .exam-pill:hover{ border-color:var(--oxblood); transform:translateY(-2px); }
  .exam-state{ font-size:0.92rem; font-weight:500; margin-bottom:0.25rem; }
  .exam-code{ font-family:var(--mono); font-size:0.7rem; color:var(--oxblood); letter-spacing:0.05em; }
  .prosecution-note{ font-size:0.88rem; color:var(--muted-on-parchment); border-top:1px solid var(--parchment-line); padding-top:1.4rem; }
  .prosecution-note b{ color:var(--ink-text); }

  /* ---------- JOURNEY ---------- */
  .journey{ display:grid; grid-template-columns:repeat(3,1fr); gap:0; border-top:1px solid var(--ink-line); }
  .journey-step{ padding:2.4rem clamp(1rem,2.5vw,2rem); border-right:1px solid var(--ink-line); }
  .journey-step:last-child{ border-right:none; }
  .journey-num{ font-family:var(--mono); font-size:0.85rem; color:var(--brass-bright); margin-bottom:1rem; }
  .journey-step h3{ font-size:1.25rem; margin-bottom:0.65rem; }
  .journey-step p{ font-size:0.92rem; color:var(--muted-on-ink); }

  /* ---------- FEATURES ---------- */
  .feature-grid{ display:grid; grid-template-columns:repeat(auto-fit,minmax(255px,1fr)); gap:1px; background:var(--parchment-line); border:1px solid var(--parchment-line); }
  .feature-card{ background:var(--parchment); padding:1.9rem; }
  .feature-card h3{ font-size:1.05rem; margin-bottom:0.55rem; font-weight:600; }
  .feature-card p{ font-size:0.88rem; color:var(--muted-on-parchment); }
  .feature-tag{ font-family:var(--mono); font-size:0.64rem; letter-spacing:0.07em; text-transform:uppercase; color:var(--oxblood); margin-bottom:0.7rem; display:block; }

  /* ---------- RESULTS / CAUSE LIST ---------- */
  .causelist-note{ font-size:0.82rem; color:var(--muted-on-ink); margin-bottom:1.6rem; font-style:italic; }
  table.causelist{ width:100%; border-collapse:collapse; font-size:0.92rem; }
  table.causelist thead th{
    text-align:left; font-family:var(--mono); font-size:0.66rem; letter-spacing:0.08em; text-transform:uppercase;
    color:var(--brass-bright); padding:0.85rem 0.9rem; border-bottom:1px solid var(--ink-line);
  }
  table.causelist td{ padding:0.95rem 0.9rem; border-bottom:1px solid var(--ink-line); }
  table.causelist tbody tr{ transition:background .2s ease; }
  table.causelist tbody tr:hover{ background:rgba(201,162,39,0.06); }
  .rank-tag{ font-family:var(--mono); color:var(--brass-bright); }
  table.causelist td:first-child{ font-family:var(--mono); color:var(--muted-on-ink); width:2.5em; }

  /* ---------- TESTIMONIALS ---------- */
  .testi-grid{ display:grid; grid-template-columns:repeat(auto-fit,minmax(270px,1fr)); gap:1.4rem; }
  .testi-card{ background:var(--parchment-2); border:1px solid var(--parchment-line); padding:1.8rem; position:relative; }
  .testi-mark{ font-family:var(--display); font-size:2.6rem; color:var(--oxblood); line-height:1; margin-bottom:0.4rem; font-style:italic; }
  .testi-quote{ font-size:0.95rem; margin-bottom:1.3rem; }
  .testi-name{ font-family:var(--mono); font-size:0.72rem; letter-spacing:0.04em; color:var(--muted-on-parchment); text-transform:uppercase; }

  /* ---------- CENTRES ---------- */
  .centre-row{ display:flex; flex-wrap:wrap; gap:0.85rem; }
  .centre-chip{ border:1px solid var(--ink-line); padding:0.85rem 1.3rem; font-size:0.9rem; display:flex; align-items:center; gap:0.6rem; }
  .centre-chip .ho{ font-family:var(--mono); font-size:0.6rem; background:var(--brass); color:var(--ink); padding:0.2em 0.5em; letter-spacing:0.06em; }
  .centre-chip.online{ border-style:dashed; color:var(--muted-on-ink); }

  /* ---------- CTA BAND ---------- */
  .cta-band{ background:var(--brass); color:var(--ink); text-align:center; padding:clamp(3.5rem,7vw,5.5rem) 0; position:relative; overflow:hidden; }
  .cta-band .seal{ position:absolute; opacity:0.08; }
  .cta-band .seal.s1{ width:340px; height:340px; top:-90px; left:-90px; }
  .cta-band .seal.s2{ width:260px; height:260px; bottom:-80px; right:-60px; }
  .cta-band h2{ font-size:clamp(2rem,4.2vw,3.1rem); margin-bottom:0.8rem; position:relative; }
  .cta-band p{ font-size:1.02rem; max-width:32em; margin:0 auto 2rem; opacity:0.85; position:relative; }
  .cta-band .btn-brass{ background:var(--ink); color:var(--cream); }
  .cta-band .btn-brass:hover{ background:#252A33; }

  /* ---------- FOOTER ---------- */
  footer{ background:var(--ink-2); border-top:1px solid var(--ink-line); padding:3.5rem 0 1.6rem; }
  .foot-grid{ display:flex; flex-wrap:wrap; gap:3rem; justify-content:space-between; margin-bottom:2.5rem; }
  .foot-brand .word{ font-size:1.3rem; }
  .foot-tag{ font-family:var(--display); font-style:italic; color:var(--muted-on-ink); margin-top:0.6rem; font-size:0.95rem; }
  .foot-links{ display:flex; gap:3rem; flex-wrap:wrap; }
  .foot-col h4{ font-family:var(--mono); font-size:0.66rem; letter-spacing:0.08em; text-transform:uppercase; color:var(--brass-bright); margin-bottom:0.9rem; font-weight:500; }
  .foot-col ul{ display:flex; flex-direction:column; gap:0.55rem; }
  .foot-col a{ text-decoration:none; font-size:0.87rem; color:var(--muted-on-ink); }
  .foot-col a:hover{ color:var(--cream); }
  .foot-bottom{ border-top:1px solid var(--ink-line); padding-top:1.5rem; display:flex; justify-content:space-between; flex-wrap:wrap; gap:0.8rem; font-size:0.76rem; color:var(--muted-on-ink); }
  .disclaimer{ font-size:0.74rem; color:var(--muted-on-ink); max-width:60ch; }

  /* ---------- REVEAL ---------- */
  .reveal{ opacity:0; transform:translateY(16px); transition:opacity .7s ease, transform .7s ease; }
  .reveal.in{ opacity:1; transform:none; }

  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
    .reveal{ opacity:1; transform:none; transition:none; }
    .btn:hover{ transform:none; }
  }

  @media (max-width: 900px){
    .nav-links{ position:fixed; inset:64px 0 auto 0; background:var(--ink); flex-direction:column; align-items:flex-start; padding:1.5rem clamp(1.25rem,4vw,2.5rem); gap:1.1rem; border-bottom:1px solid var(--ink-line); transform:translateY(-130%); transition:transform .25s ease; }
    .nav-links.open{ transform:translateY(0); }
    .menu-toggle{ display:block; }
    .hero .wrap{ grid-template-columns:1fr; }
    .order-sheet{ transform:none; }
    .journey{ grid-template-columns:1fr; }
    .journey-step{ border-right:none; border-bottom:1px solid var(--ink-line); }
    .docket-item{ flex:1 1 45%; }
  }
</style>
</head>
<body>

<!-- seal svg (reused) -->
<svg width="0" height="0" style="position:absolute">
  <symbol id="jg-seal" viewBox="0 0 64 64">
    <circle cx="32" cy="32" r="30" fill="none" stroke="currentColor" stroke-width="1.4"/>
    <line x1="32" y1="12" x2="32" y2="40" stroke="currentColor" stroke-width="1.6"/>
    <line x1="14" y1="20" x2="50" y2="20" stroke="currentColor" stroke-width="1.6"/>
    <path d="M14 20 L9 30 a5 5 0 0 0 10 0 Z" fill="none" stroke="currentColor" stroke-width="1.3"/>
    <path d="M50 20 L45 30 a5 5 0 0 0 10 0 Z" fill="none" stroke="currentColor" stroke-width="1.3"/>
    <rect x="26" y="40" width="12" height="4" fill="currentColor"/>
    <text x="32" y="55" text-anchor="middle" font-family="IBM Plex Mono, monospace" font-size="9" fill="currentColor">JG</text>
  </symbol>
</svg>

<header>
  <nav class="nav wrap">
    <a href="#top" class="brand">
      <svg class="seal" style="color:var(--brass-bright)"><use href="#jg-seal"/></svg>
      <span class="word">JUDICIARY GOLD<small>BY TOPRANKERS · EST. 2019</small></span>
    </a>
    <button class="menu-toggle" aria-label="Toggle menu" aria-expanded="false" id="menuToggle">☰</button>
    <div class="nav-links" id="navLinks">
      <a href="#journey">The Journey</a>
      <a href="#exams">Exams We Prepare For</a>
      <a href="#results">Results</a>
      <a href="#centres">Centres</a>
      <a href="#enrol" class="btn btn-brass">Enrol Now</a>
    </div>
  </nav>
</header>

<main id="top">

  <!-- HERO -->
  <section class="hero">
    <div class="wrap">
      <div>
        <span class="eyebrow">Admissions Open · Batch 2026</span>
        <h1>Classroom se,<br><em>Courtroom</em> tak.</h1>
        <p class="lede">Judiciary Gold trains law graduates for India's toughest judicial service examinations, taught by faculty who've sat on the other side of the bench — retired district judges, NLU alumni and practising advocates.</p>
        <div class="hero-ctas">
          <a href="#enrol" class="btn btn-brass">Book a Free Class</a>
          <a href="#exams" class="btn btn-ghost">Download Study Plan</a>
        </div>
      </div>

      <div class="order-sheet reveal">
        <div class="stamp"><span>Admissions<br>Open · 2026</span></div>
        <div class="os-head"><span>Judiciary Gold — Admissions Bench</span><span>No. ADM/2026/JG</span></div>
        <div class="os-title">In the matter of</div>
        <div class="os-matter">Your Judicial Career</div>
        <div class="os-line">Coram</div>
        <div class="os-value">Retired District Judges · NLU Alumni · Practising Advocates</div>
        <p class="os-body">Upon consideration of the applicant's ambition, diligence, and legal education, and upon perusal of the record of 500+ selections delivered since 2019, it is hereby ordered that —</p>
        <ul class="os-orders">
          <li>1. Admission to the Foundation Batch 2026 shall stand OPEN.</li>
          <li>2. A free demo class and diagnostic mock be extended forthwith.</li>
          <li>3. Seats, being limited, shall be allotted on a first-come basis.</li>
        </ul>
        <div class="os-foot">
          <span class="os-sig">Sd/- Admissions Bench</span>
          <span class="os-caseno">Dated · Pune Registry</span>
        </div>
      </div>
    </div>
  </section>

  <!-- DOCKET STRIP -->
  <div class="docket">
    <div class="wrap">
      <div class="docket-item"><div class="docket-num">2019</div><div class="docket-label">Year founded</div></div>
      <div class="docket-item"><div class="docket-num">500+</div><div class="docket-label">Selections in 4 years</div></div>
      <div class="docket-item"><div class="docket-num">14</div><div class="docket-label">State judiciary exams covered</div></div>
      <div class="docket-item"><div class="docket-num">8,000+</div><div class="docket-label">Aspirants mentored</div></div>
    </div>
  </div>

  <!-- EXAMS -->
  <section class="section on-parchment" id="exams">
    <div class="wrap">
      <span class="eyebrow">Coverage</span>
      <h2>What we prepare you for</h2>
      <p class="intro">Complete, exam-specific preparation for state-level Judicial Services Examinations across India — plus the prosecution exams that share their syllabus.</p>

      <div class="exam-grid reveal">
        <div class="exam-pill"><div class="exam-state">Delhi</div><div class="exam-code">DJS</div></div>
        <div class="exam-pill"><div class="exam-state">Madhya Pradesh</div><div class="exam-code">MPCJ</div></div>
        <div class="exam-pill"><div class="exam-state">Chhattisgarh</div><div class="exam-code">CGCJ</div></div>
        <div class="exam-pill"><div class="exam-state">Haryana</div><div class="exam-code">HJS</div></div>
        <div class="exam-pill"><div class="exam-state">Rajasthan</div><div class="exam-code">RJS</div></div>
        <div class="exam-pill"><div class="exam-state">Uttar Pradesh</div><div class="exam-code">UP PCS-J</div></div>
        <div class="exam-pill"><div class="exam-state">Bihar</div><div class="exam-code">BJS</div></div>
        <div class="exam-pill"><div class="exam-state">Gujarat</div><div class="exam-code">GJS</div></div>
        <div class="exam-pill"><div class="exam-state">Maharashtra</div><div class="exam-code">MJS</div></div>
        <div class="exam-pill"><div class="exam-state">Uttarakhand</div><div class="exam-code">UKPSC-J</div></div>
        <div class="exam-pill"><div class="exam-state">Punjab</div><div class="exam-code">PCS-J</div></div>
        <div class="exam-pill"><div class="exam-state">Himachal Pradesh</div><div class="exam-code">HP PCS-J</div></div>
        <div class="exam-pill"><div class="exam-state">Jharkhand</div><div class="exam-code">JJS</div></div>
        <div class="exam-pill"><div class="exam-state">West Bengal</div><div class="exam-code">WBJS</div></div>
      </div>

      <p class="prosecution-note"><b>Also preparing for prosecution exams —</b> MP APO, UP APO, Haryana ADA, Bihar ADPO, Rajasthan APO and Chhattisgarh ADPO, taught alongside the judiciary syllabus they share.</p>
    </div>
  </section>

  <!-- JOURNEY -->
  <section class="section" id="journey">
    <div class="wrap">
      <span class="eyebrow">The exam, in three stages</span>
      <h2>Every judicial exam runs the same course</h2>
      <p class="intro">Prelims screens. Mains tests reasoning. Interview tests presence. We prepare for each stage differently, because each one is judged differently.</p>
    </div>
    <div class="journey reveal">
      <div class="journey-step">
        <div class="journey-num">01 / Prelims</div>
        <h3>Objective screening</h3>
        <p>Constitutional law, procedural codes and general knowledge, drilled for concept clarity over recall — 100+ topic-wise tests before a single full-length mock.</p>
      </div>
      <div class="journey-step">
        <div class="journey-num">02 / Mains</div>
        <h3>Descriptive papers</h3>
        <p>Answer writing is a skill, not a memory test. Weekly practice papers are reviewed line by line, so reasoning on paper improves as fast as reasoning in class.</p>
      </div>
      <div class="journey-step">
        <div class="journey-num">03 / Interview</div>
        <h3>The viva voce</h3>
        <p>Mock panels of retired judges and senior advocates, run like the real thing — the first time you face one shouldn't be the day it counts.</p>
      </div>
    </div>
  </section>

  <!-- FEATURES -->
  <section class="section on-parchment">
    <div class="wrap">
      <span class="eyebrow">How the prep is built</span>
      <h2>Structure, not just study material</h2>
      <p class="intro">Six things that hold the programme together, from the first class to the interview panel.</p>
    </div>
    <div class="wrap">
      <div class="feature-grid reveal">
        <div class="feature-card">
          <span class="feature-tag">Format</span>
          <h3>Hybrid by design</h3>
          <p>Attend at a centre or online, and move between the two without losing a class — 1,200+ hours of instruction, whichever way you show up.</p>
        </div>
        <div class="feature-card">
          <span class="feature-tag">Analytics</span>
          <h3>bhAIya, the analytics bench</h3>
          <p>Our AI-powered testing engine breaks every mock down by time-per-question, section accuracy and topic strength — so revision has a target, not a guess.</p>
        </div>
        <div class="feature-card">
          <span class="feature-tag">Faculty</span>
          <h3>A faculty that notices</h3>
          <p>One mentor for every 50 students. Once a batch grows past that, we add a mentor before we add more seats.</p>
        </div>
        <div class="feature-card">
          <span class="feature-tag">Support</span>
          <h3>Doubts, heard on time</h3>
          <p>Live resolution inside class, a dedicated weekly session after it, and a faculty-monitored group for everything in between.</p>
        </div>
        <div class="feature-card">
          <span class="feature-tag">Testing</span>
          <h3>Mocks on a real clock</h3>
          <p>Weekly full-length papers early on, building to several a week as the exam nears — each one ranked against aspirants nationwide.</p>
        </div>
        <div class="feature-card">
          <span class="feature-tag">Syllabus</span>
          <h3>Three passes at the syllabus</h3>
          <p>Essentials, Empower, Enhance — the same syllabus, covered three times at increasing depth, so nothing is seen for the first time in the exam hall.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- RESULTS -->
  <section class="section" id="results">
    <div class="wrap">
      <span class="eyebrow">Cause list</span>
      <h2>Results on record</h2>
      <p class="causelist-note">A selection from Judiciary Gold's published results, reproduced here as reference data for this design mockup.</p>
      <table class="causelist reveal">
        <thead>
          <tr><th>Sr.</th><th>Candidate</th><th>Rank</th><th>Examination</th><th>Year</th></tr>
        </thead>
        <tbody>
          <tr><td>01</td><td>Lovnesh</td><td class="rank-tag">AIR 1</td><td>MPCJ</td><td>2025</td></tr>
          <tr><td>02</td><td>Samridhi Talwar</td><td class="rank-tag">AIR 1</td><td>DJS</td><td>2024</td></tr>
          <tr><td>03</td><td>Shweta Diwan</td><td class="rank-tag">AIR 1</td><td>CGPSC (J)</td><td>2024</td></tr>
          <tr><td>04</td><td>Tanurag S. Chauhan</td><td class="rank-tag">AIR 2</td><td>RJS</td><td>2024</td></tr>
          <tr><td>05</td><td>Shilpa Rani</td><td class="rank-tag">AIR 5</td><td>BPSC (J)</td><td>2024</td></tr>
          <tr><td>06</td><td>Mansukh Garg</td><td class="rank-tag">AIR 6</td><td>HJS</td><td>2023</td></tr>
          <tr><td>07</td><td>Ankit Baranwal</td><td class="rank-tag">AIR 12</td><td>UP PCS-J</td><td>2022</td></tr>
          <tr><td>08</td><td>Avni Vyas</td><td class="rank-tag">AIR 5</td><td>MPCJS</td><td>2021</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section class="section on-parchment">
    <div class="wrap">
      <span class="eyebrow">In their words</span>
      <h2>What the record doesn't show</h2>
      <div class="testi-grid reveal">
        <div class="testi-card">
          <div class="testi-mark">“</div>
          <p class="testi-quote">The mentors treated every doubt like it mattered — even the third time I asked the same question.</p>
          <div class="testi-name">Samridhi T. — AIR 1, DJS 2024</div>
        </div>
        <div class="testi-card">
          <div class="testi-mark">“</div>
          <p class="testi-quote">Mock interviews with real ex-judges took the fear out of the actual one. Nothing on interview day felt unfamiliar.</p>
          <div class="testi-name">Priyanka B. — AIR 8, RJS 2024</div>
        </div>
        <div class="testi-card">
          <div class="testi-mark">“</div>
          <p class="testi-quote">I walked in knowing the law. I walked out knowing how to argue it — that difference is the whole exam.</p>
          <div class="testi-name">Avni V. — AIR 5, MPCJS 2021</div>
        </div>
      </div>
    </div>
  </section>

  <!-- CENTRES -->
  <section class="section" id="centres">
    <div class="wrap">
      <span class="eyebrow">On the ground</span>
      <h2>Centres across the country</h2>
      <p class="intro">Walk into a classroom, or join live from anywhere — the syllabus, faculty and mocks stay the same either way.</p>
      <div class="centre-row reveal">
        <div class="centre-chip">Bhopal <span class="ho">HO</span></div>
        <div class="centre-chip">Indore</div>
        <div class="centre-chip">Delhi</div>
        <div class="centre-chip">Jabalpur</div>
        <div class="centre-chip">Jaipur</div>
        <div class="centre-chip">Lucknow</div>
        <div class="centre-chip">Prayagraj</div>
        <div class="centre-chip online">+ Live online, everywhere else</div>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <section class="cta-band" id="enrol">
    <svg class="seal s1"><use href="#jg-seal"/></svg>
    <svg class="seal s2"><use href="#jg-seal"/></svg>
    <div class="wrap">
      <span class="eyebrow" style="color:var(--oxblood)">Batch 2026</span>
      <h2>Your sanad is waiting.</h2>
      <p>Every judicial officer on the bench today once sat through a first class. Book yours — free, no obligation.</p>
      <a href="#top" class="btn btn-brass">Book a Free Class</a>
    </div>
  </section>

</main>

<footer>
  <div class="wrap">
    <div class="foot-grid">
      <div class="foot-brand">
        <a href="#top" class="brand" style="margin-bottom:0.3rem;">
          <svg class="seal" style="color:var(--brass-bright)"><use href="#jg-seal"/></svg>
          <span class="word">JUDICIARY GOLD</span>
        </a>
        <div class="foot-tag">"Classroom se, Courtroom tak."</div>
      </div>
      <div class="foot-links">
        <div class="foot-col">
          <h4>Programme</h4>
          <ul>
            <li><a href="#journey">The journey</a></li>
            <li><a href="#exams">Exams covered</a></li>
            <li><a href="#results">Results</a></li>
          </ul>
        </div>
        <div class="foot-col">
          <h4>Institute</h4>
          <ul>
            <li><a href="#centres">Centres</a></li>
            <li><a href="#enrol">Admissions</a></li>
            <li><a href="https://www.instagram.com/judiciarygold/" target="_blank" rel="noopener">Instagram</a></li>
          </ul>
        </div>
      </div>
    </div>
    <div class="foot-bottom">
      <span>© 2026 Judiciary Gold by Toprankers — design mockup</span>
      <span class="disclaimer">Concept &amp; visual design mockup created as an internship design assignment, built on publicly available brand information. Not an official Toprankers / Judiciary Gold property.</span>
    </div>
  </div>
</footer>

<script>
  // mobile nav toggle
  const toggle = document.getElementById('menuToggle');
  const links = document.getElementById('navLinks');
  toggle.addEventListener('click', () => {
    const open = links.classList.toggle('open');
    toggle.setAttribute('aria-expanded', open);
  });
  links.querySelectorAll('a').forEach(a => a.addEventListener('click', () => {
    links.classList.remove('open');
    toggle.setAttribute('aria-expanded', 'false');
  }));

  // reveal on scroll
  const prefersReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  if (!prefersReduced && 'IntersectionObserver' in window) {
    const io = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); } });
    }, { threshold: 0.15 });
    document.querySelectorAll('.reveal').forEach(el => io.observe(el));
  } else {
    document.querySelectorAll('.reveal').forEach(el => el.classList.add('in'));
  }
</script>

</body>
</html>
