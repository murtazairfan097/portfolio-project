# portfolio-project
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SkyShield Roofing – Built to Last. Trusted to Protect.</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@400;500;600;700&family=Barlow+Condensed:wght@600;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --orange: #F4720A;
    --orange-dark: #C85C06;
    --orange-light: #FF9A3C;
    --black: #0E0E0E;
    --dark: #141414;
    --dark2: #1C1C1C;
    --dark3: #242424;
    --steel: #2E2E2E;
    --gray: #888;
    --light: #F0EDE8;
    --white: #FFFFFF;
    --font-display: 'Bebas Neue', sans-serif;
    --font-cond: 'Barlow Condensed', sans-serif;
    --font-body: 'Barlow', sans-serif;
    --radius: 4px;
    --transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--font-body);
    background: var(--black);
    color: var(--light);
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ── NAVBAR ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 5%;
    height: 70px;
    background: rgba(14,14,14,0.95);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid #222;
    transition: all var(--transition);
  }
  nav.scrolled { box-shadow: 0 4px 30px rgba(0,0,0,0.6); }

  .nav-logo {
    display: flex; align-items: center; gap: 10px;
    text-decoration: none;
  }
  .logo-icon {
    width: 38px; height: 38px;
    background: var(--orange);
    clip-path: polygon(50% 0%, 100% 35%, 85% 100%, 15% 100%, 0% 35%);
    display: flex; align-items: center; justify-content: center;
    font-size: 18px; font-weight: 700; color: #fff;
    flex-shrink: 0;
  }
  .logo-text { font-family: var(--font-display); font-size: 26px; color: var(--white); letter-spacing: 1px; }
  .logo-text span { color: var(--orange); }

  .nav-links { display: flex; gap: 32px; list-style: none; }
  .nav-links a {
    font-family: var(--font-cond); font-size: 15px; font-weight: 600;
    letter-spacing: 1.5px; text-transform: uppercase;
    color: #aaa; text-decoration: none;
    transition: color var(--transition);
    position: relative;
  }
  .nav-links a::after {
    content: ''; position: absolute; bottom: -4px; left: 0; right: 0;
    height: 2px; background: var(--orange);
    transform: scaleX(0); transform-origin: right;
    transition: transform var(--transition);
  }
  .nav-links a:hover { color: var(--white); }
  .nav-links a:hover::after { transform: scaleX(1); transform-origin: left; }

  .nav-cta {
    background: var(--orange); color: var(--white);
    padding: 10px 22px; border-radius: var(--radius);
    font-family: var(--font-cond); font-size: 14px; font-weight: 700;
    letter-spacing: 1.5px; text-transform: uppercase;
    text-decoration: none;
    transition: background var(--transition), transform var(--transition);
  }
  .nav-cta:hover { background: var(--orange-dark); transform: translateY(-1px); }

  .hamburger {
    display: none; flex-direction: column; gap: 5px; cursor: pointer;
    background: none; border: none; padding: 4px;
  }
  .hamburger span {
    display: block; width: 26px; height: 2px; background: var(--white);
    transition: all var(--transition);
  }

  .mobile-menu {
    display: none; position: fixed; top: 70px; left: 0; right: 0; bottom: 0;
    background: var(--dark); z-index: 999;
    flex-direction: column; align-items: center; justify-content: center; gap: 28px;
  }
  .mobile-menu.open { display: flex; }
  .mobile-menu a {
    font-family: var(--font-display); font-size: 36px; color: var(--white);
    text-decoration: none; letter-spacing: 2px;
    transition: color var(--transition);
  }
  .mobile-menu a:hover { color: var(--orange); }

  /* ── HERO ── */
  #home {
    min-height: 100vh;
    display: flex; align-items: center;
    background:
      linear-gradient(to bottom, rgba(14,14,14,0.75) 0%, rgba(14,14,14,0.92) 100%),
      url('https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=1600&q=80') center/cover no-repeat;
    padding: 120px 5% 80px;
    position: relative; overflow: hidden;
  }
  #home::before {
    content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 120px;
    background: linear-gradient(to bottom, transparent, var(--black));
  }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(244,114,10,0.15); border: 1px solid rgba(244,114,10,0.4);
    color: var(--orange-light); padding: 6px 16px;
    border-radius: 2px; font-size: 12px; font-weight: 600;
    letter-spacing: 2px; text-transform: uppercase;
    margin-bottom: 20px;
  }
  .hero-badge::before { content: '●'; font-size: 8px; animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }

  h1 {
    font-family: var(--font-display);
    font-size: clamp(60px, 9vw, 120px);
    line-height: 0.92;
    letter-spacing: 2px;
    color: var(--white);
    margin-bottom: 24px;
  }
  h1 .accent { color: var(--orange); display: block; }
  h1 .stroke {
    -webkit-text-stroke: 2px var(--white);
    color: transparent;
  }

  .hero-sub {
    font-size: 18px; color: #bbb; max-width: 480px;
    line-height: 1.7; margin-bottom: 40px;
  }

  .hero-actions { display: flex; gap: 16px; flex-wrap: wrap; }

  .btn-primary {
    background: var(--orange); color: var(--white);
    padding: 16px 32px; border-radius: var(--radius);
    font-family: var(--font-cond); font-size: 16px; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase; text-decoration: none;
    border: none; cursor: pointer;
    transition: all var(--transition);
    display: inline-flex; align-items: center; gap: 10px;
  }
  .btn-primary:hover { background: var(--orange-dark); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(244,114,10,0.4); }
  .btn-primary svg { width: 18px; height: 18px; }

  .btn-secondary {
    background: transparent; color: var(--white);
    padding: 15px 32px; border-radius: var(--radius);
    font-family: var(--font-cond); font-size: 16px; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase; text-decoration: none;
    border: 1px solid rgba(255,255,255,0.3); cursor: pointer;
    transition: all var(--transition);
    display: inline-flex; align-items: center; gap: 10px;
  }
  .btn-secondary:hover { border-color: var(--orange); color: var(--orange); transform: translateY(-2px); }

  .hero-stats {
    display: flex; gap: 48px; margin-top: 60px;
    padding-top: 40px; border-top: 1px solid #333;
    flex-wrap: wrap;
  }
  .stat-num {
    font-family: var(--font-display); font-size: 48px; color: var(--orange);
    line-height: 1;
  }
  .stat-label { font-size: 12px; color: #888; letter-spacing: 1.5px; text-transform: uppercase; margin-top: 4px; }

  /* ── SECTION COMMONS ── */
  section { padding: 100px 5%; }

  .section-tag {
    font-family: var(--font-cond); font-size: 12px; font-weight: 700;
    letter-spacing: 3px; text-transform: uppercase; color: var(--orange);
    margin-bottom: 12px; display: block;
  }
  h2 {
    font-family: var(--font-display);
    font-size: clamp(40px, 5vw, 68px);
    line-height: 1; letter-spacing: 1px;
    color: var(--white); margin-bottom: 20px;
  }
  h2 em { color: var(--orange); font-style: normal; }
  .section-desc { font-size: 17px; color: #888; max-width: 560px; line-height: 1.8; }

  .divider {
    width: 60px; height: 3px; background: var(--orange);
    margin: 20px 0 40px;
  }

  /* ── ABOUT ── */
  #about { background: var(--dark); }

  .about-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center;
    margin-top: 60px;
  }
  @media(max-width:768px){ .about-grid { grid-template-columns: 1fr; gap: 40px; } }

  .about-img-wrap {
    position: relative;
  }
  .about-img {
    width: 100%; aspect-ratio: 4/3; object-fit: cover;
    border-radius: 4px; display: block;
  }
  .about-img-placeholder {
    width: 100%; aspect-ratio: 4/3;
    background: var(--steel);
    border-radius: 4px;
    display: flex; align-items: center; justify-content: center;
    font-size: 80px;
    background-image: url('https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=800&q=80');
    background-size: cover; background-position: center;
  }
  .about-badge {
    position: absolute; bottom: -20px; right: -20px;
    background: var(--orange); color: var(--white);
    padding: 20px 24px; text-align: center;
    border-radius: 4px;
  }
  .about-badge .big { font-family: var(--font-display); font-size: 40px; line-height: 1; display: block; }
  .about-badge .small { font-size: 11px; font-weight: 600; letter-spacing: 1.5px; text-transform: uppercase; opacity: 0.9; }

  .checkmark-list { list-style: none; display: flex; flex-direction: column; gap: 14px; margin: 32px 0; }
  .checkmark-list li {
    display: flex; align-items: center; gap: 12px;
    font-size: 15px; color: #ccc;
  }
  .checkmark-list li::before {
    content: '✓'; width: 24px; height: 24px; flex-shrink: 0;
    background: rgba(244,114,10,0.2); border: 1px solid rgba(244,114,10,0.5);
    color: var(--orange); font-size: 12px; font-weight: 700;
    display: flex; align-items: center; justify-content: center;
    border-radius: 2px;
  }

  /* ── SERVICES ── */
  #services { background: var(--black); }

  .services-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2px;
    margin-top: 60px; border: 2px solid var(--steel);
    border-radius: 4px; overflow: hidden;
  }
  .service-card {
    background: var(--dark2); padding: 40px 32px;
    border: 1px solid var(--steel);
    transition: all var(--transition); cursor: default;
    position: relative; overflow: hidden;
  }
  .service-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: var(--orange); transform: scaleX(0); transform-origin: left;
    transition: transform var(--transition);
  }
  .service-card:hover { background: var(--dark3); transform: translateY(-4px); }
  .service-card:hover::before { transform: scaleX(1); }

  .service-icon {
    width: 56px; height: 56px; margin-bottom: 24px;
    background: rgba(244,114,10,0.1); border: 1px solid rgba(244,114,10,0.3);
    border-radius: 4px; display: flex; align-items: center; justify-content: center;
    font-size: 26px;
  }
  .service-card h3 {
    font-family: var(--font-cond); font-size: 22px; font-weight: 700;
    letter-spacing: 1px; text-transform: uppercase; color: var(--white);
    margin-bottom: 12px;
  }
  .service-card p { font-size: 14px; color: #888; line-height: 1.7; margin-bottom: 20px; }
  .service-link {
    font-family: var(--font-cond); font-size: 13px; font-weight: 600;
    letter-spacing: 1.5px; text-transform: uppercase; color: var(--orange);
    text-decoration: none;
    display: inline-flex; align-items: center; gap: 6px;
    transition: gap var(--transition);
  }
  .service-link:hover { gap: 12px; }

  /* ── PROJECTS / GALLERY ── */
  #projects { background: var(--dark); }

  .before-after-wrap {
    margin-top: 60px; position: relative;
    border-radius: 4px; overflow: hidden;
    user-select: none; touch-action: none;
  }
  .ba-container {
    position: relative; width: 100%; max-width: 900px; margin: 0 auto;
    aspect-ratio: 16/9; overflow: hidden; border-radius: 4px;
    border: 2px solid var(--steel);
    cursor: col-resize;
  }
  .ba-after, .ba-before {
    position: absolute; top: 0; bottom: 0; left: 0; right: 0;
    background-size: cover; background-position: center;
    background-repeat: no-repeat;
  }
  .ba-before {
    background-image: url('https://images.unsplash.com/photo-1558036117-15d82a90b9b1?w=900&q=80');
    z-index: 1;
  }
  .ba-after {
    background-image: url('https://images.unsplash.com/photo-1513694203232-719a280e022f?w=900&q=80');
    z-index: 2; clip-path: inset(0 50% 0 0);
  }
  .ba-handle {
    position: absolute; top: 0; bottom: 0; z-index: 10;
    left: 50%; transform: translateX(-50%);
    width: 3px; background: var(--orange);
    display: flex; align-items: center; justify-content: center;
  }
  .ba-handle-btn {
    width: 44px; height: 44px; border-radius: 50%;
    background: var(--orange); border: 3px solid var(--white);
    display: flex; align-items: center; justify-content: center;
    box-shadow: 0 4px 16px rgba(0,0,0,0.6);
  }
  .ba-handle-btn svg { width: 20px; height: 20px; fill: white; }
  .ba-label {
    position: absolute; bottom: 16px; z-index: 11;
    font-family: var(--font-cond); font-size: 14px; font-weight: 700;
    letter-spacing: 1.5px; text-transform: uppercase;
    background: rgba(0,0,0,0.7); color: var(--white);
    padding: 6px 14px; border-radius: 2px;
  }
  .ba-label.before { left: 16px; }
  .ba-label.after { right: 16px; }
  .ba-instruction {
    text-align: center; margin-top: 16px; color: #666; font-size: 13px;
    letter-spacing: 1px;
  }

  .gallery-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 8px; margin-top: 40px;
  }
  .gallery-item {
    aspect-ratio: 4/3; border-radius: 4px; overflow: hidden; position: relative;
    background: var(--steel); cursor: pointer;
  }
  .gallery-item img {
    width: 100%; height: 100%; object-fit: cover;
    transition: transform 0.5s ease;
    display: block;
  }
  .gallery-item:hover img { transform: scale(1.06); }
  .gallery-overlay {
    position: absolute; inset: 0; background: rgba(244,114,10,0.85);
    display: flex; align-items: center; justify-content: center;
    opacity: 0; transition: opacity var(--transition);
  }
  .gallery-item:hover .gallery-overlay { opacity: 1; }
  .gallery-overlay span {
    font-family: var(--font-cond); font-size: 16px; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase; color: var(--white);
  }

  /* ── TESTIMONIALS ── */
  #testimonials { background: var(--black); }

  .testimonials-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 24px; margin-top: 60px;
  }
  .testimonial-card {
    background: var(--dark2); border: 1px solid var(--steel);
    border-radius: 4px; padding: 32px;
    transition: border-color var(--transition);
  }
  .testimonial-card:hover { border-color: var(--orange); }

  .stars { color: var(--orange); font-size: 18px; letter-spacing: 2px; margin-bottom: 16px; }
  .testimonial-text {
    font-size: 15px; color: #bbb; line-height: 1.8;
    margin-bottom: 24px; font-style: italic;
  }
  .testimonial-text::before { content: '"'; color: var(--orange); font-size: 32px; line-height: 0; vertical-align: -12px; margin-right: 4px; }
  .testimonial-author {
    display: flex; align-items: center; gap: 12px;
    padding-top: 20px; border-top: 1px solid var(--steel);
  }
  .avatar {
    width: 46px; height: 46px; border-radius: 50%;
    background: var(--orange); display: flex; align-items: center; justify-content: center;
    font-family: var(--font-cond); font-size: 16px; font-weight: 700; color: var(--white);
    flex-shrink: 0;
  }
  .author-name { font-weight: 600; font-size: 15px; color: var(--white); }
  .author-loc { font-size: 12px; color: #666; margin-top: 2px; }

  /* ── CONTACT ── */
  #contact { background: var(--dark); }

  .contact-wrapper {
    display: grid; grid-template-columns: 1fr 1.4fr; gap: 60px;
    align-items: start; margin-top: 60px;
  }
  @media(max-width:768px){ .contact-wrapper { grid-template-columns: 1fr; } }

  .contact-info h3 {
    font-family: var(--font-display); font-size: 32px; color: var(--white);
    margin-bottom: 8px; letter-spacing: 1px;
  }
  .contact-info p { font-size: 14px; color: #888; margin-bottom: 32px; }

  .contact-item {
    display: flex; align-items: flex-start; gap: 16px; margin-bottom: 24px;
  }
  .contact-icon {
    width: 46px; height: 46px; flex-shrink: 0;
    background: rgba(244,114,10,0.1); border: 1px solid rgba(244,114,10,0.3);
    border-radius: 4px; display: flex; align-items: center; justify-content: center; font-size: 20px;
  }
  .contact-item-label { font-size: 11px; color: #555; letter-spacing: 1.5px; text-transform: uppercase; font-weight: 600; }
  .contact-item-value { font-size: 15px; color: #ddd; margin-top: 2px; font-weight: 500; }

  .map-embed {
    margin-top: 32px; border-radius: 4px; overflow: hidden;
    border: 1px solid var(--steel);
  }
  .map-embed iframe { width: 100%; height: 220px; display: block; border: none; filter: grayscale(80%) invert(85%) contrast(90%); }

  /* FORM */
  .quote-form {
    background: var(--dark2); border: 1px solid var(--steel);
    border-radius: 4px; padding: 40px;
  }
  .form-title {
    font-family: var(--font-display); font-size: 28px; color: var(--white);
    margin-bottom: 6px; letter-spacing: 1px;
  }
  .form-sub { font-size: 13px; color: #666; margin-bottom: 28px; }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  @media(max-width:560px){ .form-row { grid-template-columns: 1fr; } }

  .form-group { margin-bottom: 16px; }
  .form-group label {
    display: block; font-size: 11px; font-weight: 600; letter-spacing: 1.5px;
    text-transform: uppercase; color: #666; margin-bottom: 8px;
  }
  .form-group input, .form-group select, .form-group textarea {
    width: 100%; background: var(--dark3); border: 1px solid var(--steel);
    border-radius: var(--radius); padding: 12px 16px;
    color: var(--white); font-family: var(--font-body); font-size: 15px;
    transition: border-color var(--transition);
    outline: none;
    appearance: none;
    -webkit-appearance: none;
  }
  .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
    border-color: var(--orange);
  }
  .form-group select option { background: var(--dark3); }
  .form-group textarea { resize: vertical; min-height: 100px; }

  .form-submit {
    width: 100%; padding: 16px; background: var(--orange);
    color: var(--white); border: none; border-radius: var(--radius);
    font-family: var(--font-cond); font-size: 16px; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase; cursor: pointer;
    transition: all var(--transition); margin-top: 8px;
  }
  .form-submit:hover { background: var(--orange-dark); transform: translateY(-2px); }

  .form-success {
    display: none; background: rgba(39,160,39,0.15); border: 1px solid rgba(39,160,39,0.4);
    color: #4caf50; padding: 16px; border-radius: 4px;
    text-align: center; font-weight: 600; margin-top: 16px;
  }

  /* ── CALL BANNER ── */
  .call-banner {
    background: var(--orange); padding: 40px 5%;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 24px;
  }
  .call-banner-text h3 {
    font-family: var(--font-display); font-size: 36px; color: var(--white);
    letter-spacing: 1px;
  }
  .call-banner-text p { font-size: 15px; color: rgba(255,255,255,0.8); margin-top: 4px; }
  .btn-call {
    background: var(--white); color: var(--orange);
    padding: 16px 36px; border-radius: 4px; text-decoration: none;
    font-family: var(--font-cond); font-size: 18px; font-weight: 700;
    letter-spacing: 1.5px; text-transform: uppercase;
    display: flex; align-items: center; gap: 10px;
    transition: all var(--transition); white-space: nowrap;
  }
  .btn-call:hover { background: var(--black); color: var(--orange); }

  /* ── FOOTER ── */
  footer {
    background: var(--dark); padding: 60px 5% 30px;
    border-top: 1px solid #1e1e1e;
  }
  .footer-top {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1.5fr; gap: 48px;
    padding-bottom: 48px; border-bottom: 1px solid #1e1e1e;
  }
  @media(max-width:768px){ .footer-top { grid-template-columns: 1fr 1fr; } }
  @media(max-width:480px){ .footer-top { grid-template-columns: 1fr; } }

  .footer-about p { font-size: 14px; color: #666; line-height: 1.8; margin: 16px 0 24px; max-width: 280px; }
  .footer-social { display: flex; gap: 10px; }
  .social-btn {
    width: 36px; height: 36px; border-radius: 4px;
    background: var(--dark3); border: 1px solid var(--steel);
    display: flex; align-items: center; justify-content: center;
    color: #888; text-decoration: none; font-size: 14px;
    transition: all var(--transition);
  }
  .social-btn:hover { background: var(--orange); border-color: var(--orange); color: var(--white); }

  .footer-col h4 {
    font-family: var(--font-cond); font-size: 14px; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase; color: var(--white); margin-bottom: 20px;
  }
  .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  .footer-col ul a {
    font-size: 14px; color: #666; text-decoration: none;
    transition: color var(--transition);
  }
  .footer-col ul a:hover { color: var(--orange); }

  .footer-hours p { font-size: 14px; color: #666; line-height: 2; }
  .footer-hours strong { color: #aaa; font-weight: 500; }

  .footer-bottom {
    display: flex; align-items: center; justify-content: space-between;
    padding-top: 28px; flex-wrap: wrap; gap: 12px;
  }
  .footer-bottom p { font-size: 13px; color: #555; }
  .footer-bottom a { color: var(--orange); text-decoration: none; }

  /* ── SCROLL TO TOP ── */
  .scroll-top {
    position: fixed; bottom: 28px; right: 28px; z-index: 900;
    width: 46px; height: 46px; border-radius: 4px;
    background: var(--orange); border: none; cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    opacity: 0; transform: translateY(20px);
    transition: all var(--transition);
    color: var(--white); font-size: 20px;
  }
  .scroll-top.visible { opacity: 1; transform: translateY(0); }
  .scroll-top:hover { background: var(--orange-dark); }

  /* ── RESPONSIVE ── */
  @media(max-width:900px){
    .nav-links, .nav-cta { display: none; }
    .hamburger { display: flex; }
  }
  @media(max-width:600px){
    section { padding: 70px 5%; }
    h1 { font-size: clamp(50px,12vw,80px); }
    .hero-stats { gap: 28px; }
    .stat-num { font-size: 36px; }
    .call-banner { text-align: center; justify-content: center; }
  }
</style>
</head>
<body>

<!-- ══ NAVBAR ══ -->
<nav id="navbar">
  <a href="#home" class="nav-logo">
    <div class="logo-icon">S</div>
    <span class="logo-text">Sky<span>Shield</span></span>
  </a>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#testimonials">Testimonials</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="tel:+10001234567" class="nav-cta">📞 Call Now</a>
  <button class="hamburger" id="hamburgerBtn" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- Mobile Menu -->
<div class="mobile-menu" id="mobileMenu">
  <a href="#home" onclick="closeMobile()">Home</a>
  <a href="#about" onclick="closeMobile()">About</a>
  <a href="#services" onclick="closeMobile()">Services</a>
  <a href="#projects" onclick="closeMobile()">Projects</a>
  <a href="#testimonials" onclick="closeMobile()">Reviews</a>
  <a href="#contact" onclick="closeMobile()">Contact</a>
  <a href="tel:+10001234567" class="btn-primary" style="font-size:20px; padding:16px 40px;">📞 Call Now</a>
</div>

<!-- ══ HERO ══ -->
<section id="home">
  <div>
    <div class="hero-badge">🏆 Lahore's #1 Rated Roofing Company</div>
    <h1>
      WE BUILD<br>
      <span class="accent">ROOFS</span>
      <span class="stroke">THAT LAST</span>
    </h1>
    <p class="hero-sub">Expert roofing installation, repair & restoration services. Licensed, insured, and built on 15+ years of unmatched craftsmanship.</p>
    <div class="hero-actions">
      <a href="#contact" class="btn-primary">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M9 12h6M12 9v6M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
        Get Free Quote
      </a>
      <a href="tel:+10001234567" class="btn-secondary">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" style="width:18px;height:18px"><path d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/></svg>
        +1 (000) 123-4567
      </a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">15+</div>
        <div class="stat-label">Years Experience</div>
      </div>
      <div>
        <div class="stat-num">2,400+</div>
        <div class="stat-label">Projects Done</div>
      </div>
      <div>
        <div class="stat-num">98%</div>
        <div class="stat-label">Client Satisfaction</div>
      </div>
      <div>
        <div class="stat-num">5★</div>
        <div class="stat-label">Google Rating</div>
      </div>
    </div>
  </div>
</section>

<!-- ══ ABOUT ══ -->
<section id="about">
  <span class="section-tag">Who We Are</span>
  <h2>Built On <em>Trust.</em><br>Roofed With Pride.</h2>
  <div class="divider"></div>
  <div class="about-grid">
    <div class="about-img-wrap">
      <div class="about-img-placeholder"></div>
      <div class="about-badge">
        <span class="big">15+</span>
        <span class="small">Years of Excellence</span>
      </div>
    </div>
    <div>
      <p style="color:#aaa; font-size:16px; line-height:1.9; margin-bottom:20px;">
        SkyShield Roofing was founded with one mission — to deliver honest, high-quality roofing solutions that homeowners and businesses can trust for decades. We combine traditional craftsmanship with modern materials.
      </p>
      <p style="color:#777; font-size:15px; line-height:1.9; margin-bottom:28px;">
        Our team of certified roofers handles every job — from minor leak repairs to complete roof overhauls — with the same level of care and precision. No shortcuts. No compromises.
      </p>
      <ul class="checkmark-list">
        <li>Licensed & Fully Insured Professionals</li>
        <li>10-Year Workmanship Warranty on All Jobs</li>
        <li>Free Detailed Roof Inspection & Quote</li>
        <li>Emergency Repair Services — 24/7 Available</li>
        <li>Premium Materials from Trusted Suppliers</li>
        <li>Clean Worksite — Zero Mess Guarantee</li>
      </ul>
      <a href="#contact" class="btn-primary" style="display:inline-flex; margin-top:8px;">Book Free Inspection →</a>
    </div>
  </div>
</section>

<!-- ══ SERVICES ══ -->
<section id="services">
  <span class="section-tag">What We Do</span>
  <h2>Our Core <em>Services</em></h2>
  <div class="divider"></div>
  <p class="section-desc">From residential repairs to large-scale commercial projects — we've got your roof covered.</p>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">🏗️</div>
      <h3>Roof Installation</h3>
      <p>Full roof installation using premium shingles, metal, tile, and flat roofing systems. Engineered for your climate and built to last 30+ years.</p>
      <a href="#contact" class="service-link">Get Quote →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🔧</div>
      <h3>Roof Repair</h3>
      <p>From missing shingles to structural damage — we diagnose and repair all roof types fast, efficiently, and at competitive prices.</p>
      <a href="#contact" class="service-link">Get Quote →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">💧</div>
      <h3>Leak Fixing</h3>
      <p>Persistent leaks? We locate and permanently seal every water intrusion point. Same-day emergency service available.</p>
      <a href="#contact" class="service-link">Get Quote →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🏢</div>
      <h3>Commercial Roofing</h3>
      <p>Large-scale commercial flat, metal, and TPO roofing systems. Minimal downtime, maximum protection for your business premises.</p>
      <a href="#contact" class="service-link">Get Quote →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🌿</div>
      <h3>Roof Restoration</h3>
      <p>Extend your roof's life by 10-15 years with our professional cleaning, recoating, and restoration programs.</p>
      <a href="#contact" class="service-link">Get Quote →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🛡️</div>
      <h3>Waterproofing</h3>
      <p>Industrial-grade waterproofing solutions for roofs, terraces, basements, and boundary walls. Guaranteed dry — for life.</p>
      <a href="#contact" class="service-link">Get Quote →</a>
    </div>
  </div>
</section>

<!-- ══ PROJECTS ══ -->
<section id="projects">
  <span class="section-tag">Our Work</span>
  <h2>Before & <em>After</em></h2>
  <div class="divider"></div>
  <p class="section-desc">Drag the slider to see the transformation. Real projects. Real results.</p>

  <div class="before-after-wrap">
    <div class="ba-container" id="baContainer">
      <div class="ba-before" id="baAfterImg"></div>
      <div class="ba-after" id="baBeforeImg"></div>
      <div class="ba-handle" id="baHandle">
        <div class="ba-handle-btn">
          <svg viewBox="0 0 24 24"><path d="M8 5l-7 7 7 7M16 5l7 7-7 7"/></svg>
        </div>
      </div>
      <span class="ba-label before">BEFORE</span>
      <span class="ba-label after">AFTER</span>
    </div>
    <p class="ba-instruction">← Drag slider left and right to compare →</p>
  </div>

  <h3 style="font-family:var(--font-display); font-size:32px; color:var(--white); margin:60px 0 24px; letter-spacing:1px;">Recent <em style="color:var(--orange); font-style:normal;">Projects</em></h3>
  <div class="gallery-grid">
    <div class="gallery-item">
      <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=600&q=80" alt="Residential roofing project" loading="lazy">
      <div class="gallery-overlay"><span>Residential Install</span></div>
    </div>
    <div class="gallery-item">
      <img src="https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=600&q=80" alt="Commercial roofing" loading="lazy">
      <div class="gallery-overlay"><span>Commercial Roof</span></div>
    </div>
    <div class="gallery-item">
      <img src="https://images.unsplash.com/photo-1513694203232-719a280e022f?w=600&q=80" alt="Leak repair" loading="lazy">
      <div class="gallery-overlay"><span>Leak Repair</span></div>
    </div>
    <div class="gallery-item">
      <img src="https://images.unsplash.com/photo-1518780664697-55e3ad937233?w=600&q=80" alt="Roof restoration" loading="lazy">
      <div class="gallery-overlay"><span>Roof Restoration</span></div>
    </div>
    <div class="gallery-item">
      <img src="https://images.unsplash.com/photo-1588880331179-bc9b93a8cb5e?w=600&q=80" alt="Metal roofing" loading="lazy">
      <div class="gallery-overlay"><span>Metal Roofing</span></div>
    </div>
    <div class="gallery-item">
      <img src="https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?w=600&q=80" alt="Waterproofing" loading="lazy">
      <div class="gallery-overlay"><span>Waterproofing</span></div>
    </div>
  </div>
</section>

<!-- ══ TESTIMONIALS ══ -->
<section id="testimonials">
  <span class="section-tag">Client Reviews</span>
  <h2>What Our <em>Clients</em> Say</h2>
  <div class="divider"></div>
  <div class="testimonials-grid">
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">SkyShield replaced our entire roof in just 2 days. The team was professional, clean, and the result is stunning. No more leaks after 5 years of suffering!</p>
      <div class="testimonial-author">
        <div class="avatar">AK</div>
        <div>
          <div class="author-name">Ahmed Karimi</div>
          <div class="author-loc">📍 DHA, Lahore</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">Best roofing company I've hired. They came for a free inspection, gave an honest quote (no hidden charges), and finished the waterproofing perfectly. Highly recommended!</p>
      <div class="testimonial-author">
        <div class="avatar">SF</div>
        <div>
          <div class="author-name">Sara Farooq</div>
          <div class="author-loc">📍 Gulberg, Lahore</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">Our factory roof was a mess. SkyShield handled the entire 8,000 sqft commercial project on schedule and within budget. Their team is world-class.</p>
      <div class="testimonial-author">
        <div class="avatar">ZM</div>
        <div>
          <div class="author-name">Zaheer Malik</div>
          <div class="author-loc">📍 Ferozepur Road, Lahore</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">Emergency leak in heavy rain — they responded within 2 hours. Fixed everything same day. These guys really mean business. Will use for my next property too.</p>
      <div class="testimonial-author">
        <div class="avatar">RH</div>
        <div>
          <div class="author-name">Rubina Hassan</div>
          <div class="author-loc">📍 Johar Town, Lahore</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">10-year warranty on workmanship is what sold me. The new roof looks incredible, and the team cleaned up every bit of debris. Zero complaints, 100% satisfaction.</p>
      <div class="testimonial-author">
        <div class="avatar">MB</div>
        <div>
          <div class="author-name">M. Bilal Chaudhry</div>
          <div class="author-loc">📍 Model Town, Lahore</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">Honest, reliable, and skilled. They told me I only needed a repair, not a full replacement — saving me thousands. This kind of integrity is rare. Truly the best!</p>
      <div class="testimonial-author">
        <div class="avatar">NT</div>
        <div>
          <div class="author-name">Nadia Tariq</div>
          <div class="author-loc">📍 Bahria Town, Lahore</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══ CALL BANNER ══ -->
<div class="call-banner">
  <div class="call-banner-text">
    <h3>ROOF EMERGENCY? WE'RE READY.</h3>
    <p>24/7 emergency response. Same-day service available.</p>
  </div>
  <a href="tel:+10001234567" class="btn-call">
    📞 Call +1 (000) 123-4567
  </a>
</div>

<!-- ══ CONTACT ══ -->
<section id="contact">
  <span class="section-tag">Get In Touch</span>
  <h2>Request a <em>Free</em> Quote</h2>
  <div class="divider"></div>
  <div class="contact-wrapper">
    <div class="contact-info">
      <h3>Let's Talk Roofing</h3>
      <p>Fill out the form or contact us directly. We respond within 2 hours on business days.</p>
      <div class="contact-item">
        <div class="contact-icon">📍</div>
        <div>
          <div class="contact-item-label">Our Office</div>
          <div class="contact-item-value">123 Builder's Avenue, DHA Phase 5, Lahore</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📞</div>
        <div>
          <div class="contact-item-label">Phone / WhatsApp</div>
          <div class="contact-item-value">+92 300 1234567</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">✉️</div>
        <div>
          <div class="contact-item-label">Email</div>
          <div class="contact-item-value">info@skyshieldroofing.com</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">🕐</div>
        <div>
          <div class="contact-item-label">Business Hours</div>
          <div class="contact-item-value">Mon–Sat: 8:00 AM – 6:00 PM</div>
        </div>
      </div>
      <div class="map-embed">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d108876.52785960416!2d74.21514767!3d31.48304!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x39190483e58107d9%3A0xc23abe6ccc7e2462!2sLahore%2C%20Punjab%2C%20Pakistan!5e0!3m2!1sen!2s!4v1700000000000!5m2!1sen!2s"
          allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"
          title="SkyShield Roofing Location">
        </iframe>
      </div>
    </div>

    <!-- QUOTE FORM -->
    <div class="quote-form">
      <div class="form-title">GET YOUR FREE QUOTE</div>
      <p class="form-sub">No obligation. Response within 2 hours.</p>
      <div class="form-row">
        <div class="form-group">
          <label>First Name</label>
          <input type="text" placeholder="Ahmed" id="fname">
        </div>
        <div class="form-group">
          <label>Last Name</label>
          <input type="text" placeholder="Khan" id="lname">
        </div>
      </div>
      <div class="form-row">
        <div class="form-group">
          <label>Phone / WhatsApp</label>
          <input type="tel" placeholder="+92 300 0000000" id="phone">
        </div>
        <div class="form-group">
          <label>Email Address</label>
          <input type="email" placeholder="you@email.com" id="email">
        </div>
      </div>
      <div class="form-group">
        <label>Service Needed</label>
        <select id="service">
          <option value="">— Select a service —</option>
          <option>Roof Installation</option>
          <option>Roof Repair</option>
          <option>Leak Fixing</option>
          <option>Commercial Roofing</option>
          <option>Roof Restoration</option>
          <option>Waterproofing</option>
          <option>Emergency Service</option>
        </select>
      </div>
      <div class="form-group">
        <label>Property Type</label>
        <select id="proptype">
          <option value="">— Select property type —</option>
          <option>Residential Home</option>
          <option>Commercial Building</option>
          <option>Factory / Warehouse</option>
          <option>Apartment / Flat</option>
        </select>
      </div>
      <div class="form-group">
        <label>Message / Details</label>
        <textarea placeholder="Describe your roofing issue, approximate roof size, location…" id="message"></textarea>
      </div>
      <button class="form-submit" onclick="submitQuote()">🚀 SUBMIT QUOTE REQUEST</button>
      <div class="form-success" id="formSuccess">
        ✅ Thank you! We've received your request and will contact you within 2 hours.
      </div>
    </div>
  </div>
</section>

<!-- ══ FOOTER ══ -->
<footer>
  <div class="footer-top">
    <div class="footer-about">
      <a href="#home" class="nav-logo" style="display:inline-flex; margin-bottom:4px;">
        <div class="logo-icon">S</div>
        <span class="logo-text">Sky<span>Shield</span></span>
      </a>
      <p>Lahore's most trusted roofing company. Licensed, insured, and committed to quality since 2009. We protect what matters most — your home and family.</p>
      <div class="footer-social">
        <a href="#" class="social-btn" aria-label="Facebook">f</a>
        <a href="#" class="social-btn" aria-label="Instagram">in</a>
        <a href="#" class="social-btn" aria-label="WhatsApp">W</a>
        <a href="#" class="social-btn" aria-label="YouTube">▶</a>
      </div>
    </div>
    <div class="footer-col">
      <h4>Services</h4>
      <ul>
        <li><a href="#services">Roof Installation</a></li>
        <li><a href="#services">Roof Repair</a></li>
        <li><a href="#services">Leak Fixing</a></li>
        <li><a href="#services">Commercial Roofing</a></li>
        <li><a href="#services">Roof Restoration</a></li>
        <li><a href="#services">Waterproofing</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul>
        <li><a href="#about">About Us</a></li>
        <li><a href="#projects">Our Projects</a></li>
        <li><a href="#testimonials">Reviews</a></li>
        <li><a href="#contact">Get a Quote</a></li>
        <li><a href="#">Careers</a></li>
        <li><a href="#">Privacy Policy</a></li>
      </ul>
    </div>
    <div class="footer-col footer-hours">
      <h4>Working Hours</h4>
      <p>
        <strong>Monday – Friday</strong><br>
        8:00 AM – 6:00 PM<br><br>
        <strong>Saturday</strong><br>
        9:00 AM – 4:00 PM<br><br>
        <strong>Sunday</strong><br>
        Emergency Only 🚨<br><br>
        <strong>Emergency Hotline</strong><br>
        <span style="color:var(--orange); font-weight:600;">+92 300 1234567</span>
      </p>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2025 SkyShield Roofing. All rights reserved.</p>
    <p>Designed with ❤️ in <a href="#">Lahore, Pakistan</a></p>
  </div>
</footer>

<!-- SCROLL TO TOP -->
<button class="scroll-top" id="scrollTop" onclick="window.scrollTo({top:0,behavior:'smooth'})" aria-label="Back to top">↑</button>

<script>
/* ── NAVBAR SCROLL ── */
window.addEventListener('scroll', () => {
  const nav = document.getElementById('navbar');
  const btn = document.getElementById('scrollTop');
  if (window.scrollY > 80) { nav.classList.add('scrolled'); btn.classList.add('visible'); }
  else { nav.classList.remove('scrolled'); btn.classList.remove('visible'); }
});

/* ── MOBILE MENU ── */
const hamburgerBtn = document.getElementById('hamburgerBtn');
const mobileMenu = document.getElementById('mobileMenu');
hamburgerBtn.addEventListener('click', () => {
  mobileMenu.classList.toggle('open');
});
function closeMobile() { mobileMenu.classList.remove('open'); }

/* ── BEFORE / AFTER SLIDER ── */
(function() {
  const container = document.getElementById('baContainer');
  const afterLayer = document.getElementById('baBeforeImg');
  const handle = document.getElementById('baHandle');
  let dragging = false;

  function setPos(x) {
    const rect = container.getBoundingClientRect();
    let pct = ((x - rect.left) / rect.width) * 100;
    pct = Math.max(5, Math.min(95, pct));
    afterLayer.style.clipPath = `inset(0 ${100 - pct}% 0 0)`;
    handle.style.left = pct + '%';
  }

  container.addEventListener('mousedown', (e) => { dragging = true; setPos(e.clientX); });
  window.addEventListener('mousemove', (e) => { if (dragging) setPos(e.clientX); });
  window.addEventListener('mouseup', () => { dragging = false; });

  container.addEventListener('touchstart', (e) => { dragging = true; setPos(e.touches[0].clientX); }, { passive: true });
  window.addEventListener('touchmove', (e) => { if (dragging) setPos(e.touches[0].clientX); }, { passive: true });
  window.addEventListener('touchend', () => { dragging = false; });
})();

/* ── FORM SUBMIT ── */
function submitQuote() {
  const fname = document.getElementById('fname').value.trim();
  const phone = document.getElementById('phone').value.trim();
  const service = document.getElementById('service').value;
  if (!fname || !phone || !service) {
    alert('Please fill in your name, phone number, and select a service.');
    return;
  }
  document.getElementById('formSuccess').style.display = 'block';
  document.querySelector('.form-submit').textContent = '✅ Request Sent!';
  document.querySelector('.form-submit').style.background = '#27a339';
}

/* ── COUNTER ANIMATION ── */
function animateCounters() {
  document.querySelectorAll('.stat-num').forEach(el => {
    const text = el.textContent;
    const num = parseInt(text.replace(/\D/g,''));
    const suffix = text.replace(/[\d]/g,'');
    if (!num) return;
    let start = 0; const duration = 1800;
    const step = (timestamp) => {
      if (!start) start = timestamp;
      const progress = Math.min((timestamp - start) / duration, 1);
      const eased = 1 - Math.pow(1 - progress, 3);
      el.textContent = Math.floor(eased * num) + suffix;
      if (progress < 1) requestAnimationFrame(step);
    };
    requestAnimationFrame(step);
  });
}

const heroObserver = new IntersectionObserver((entries) => {
  if (entries[0].isIntersecting) { animateCounters(); heroObserver.disconnect(); }
}, { threshold: 0.5 });
heroObserver.observe(document.querySelector('.hero-stats'));

/* ── FADE IN SECTIONS ── */
const style = document.createElement('style');
style.textContent = '.fade-section { opacity: 0; transform: translateY(30px); transition: opacity 0.7s ease, transform 0.7s ease; } .fade-section.visible { opacity: 1; transform: none; }';
document.head.appendChild(style);
document.querySelectorAll('section').forEach(s => s.classList.add('fade-section'));
const sectionObs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); sectionObs.unobserve(e.target); } });
}, { threshold: 0.1 });
document.querySelectorAll('section').forEach(s => sectionObs.observe(s));
</script>
</body>
</html>
