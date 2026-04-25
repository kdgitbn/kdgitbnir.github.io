<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EduLuma — Glow with Knowledge</title>
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,300&display=swap" rel="stylesheet">
<style>
:root {
  --navy: #0B1D3A;
  --navy-light: #132848;
  --orange: #FF6B00;
  --orange-light: #FF8C38;
  --gold: #FFB800;
  --white: #FFFFFF;
  --off-white: #F7F8FC;
  --gray: #8A94A6;
  --gray-light: #E8ECF4;
  --text: #1A2740;
}

* { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
  font-family: 'DM Sans', sans-serif;
  color: var(--text);
  background: var(--white);
  overflow-x: hidden;
}

/* ===== NAVBAR ===== */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  background: rgba(11, 29, 58, 0.97);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255,107,0,0.15);
  transition: all 0.3s ease;
}

.nav-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-family: 'Sora', sans-serif;
  font-size: 1.6rem;
  font-weight: 800;
  color: var(--white);
  text-decoration: none;
  letter-spacing: -0.5px;
}

.logo span { color: var(--orange); }

.nav-links {
  display: flex;
  align-items: center;
  gap: 8px;
  list-style: none;
}

.nav-links a {
  color: rgba(255,255,255,0.8);
  text-decoration: none;
  font-size: 0.92rem;
  font-weight: 500;
  padding: 8px 14px;
  border-radius: 8px;
  transition: all 0.2s;
  cursor: pointer;
}

.nav-links a:hover, .nav-links a.active {
  color: var(--white);
  background: rgba(255,107,0,0.15);
}

.nav-cta {
  background: var(--orange) !important;
  color: var(--white) !important;
  padding: 10px 22px !important;
  border-radius: 50px !important;
  font-weight: 600 !important;
}

.nav-cta:hover { background: var(--orange-light) !important; }

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
  padding: 8px;
}

.hamburger span {
  width: 24px; height: 2px;
  background: var(--white);
  border-radius: 2px;
  transition: all 0.3s;
}

/* ===== PAGES ===== */
.page { display: none; }
.page.active { display: block; }

/* ===== HOME PAGE ===== */

/* Hero */
.hero {
  min-height: 100vh;
  background: var(--navy);
  position: relative;
  display: flex;
  align-items: center;
  overflow: hidden;
  padding-top: 70px;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 60% 50% at 70% 50%, rgba(255,107,0,0.12) 0%, transparent 70%),
    radial-gradient(ellipse 40% 60% at 10% 80%, rgba(255,184,0,0.06) 0%, transparent 60%);
}

.hero-grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
  background-size: 60px 60px;
}

.hero-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding: 80px 24px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
  position: relative;
  z-index: 2;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(255,107,0,0.15);
  border: 1px solid rgba(255,107,0,0.3);
  color: var(--orange-light);
  padding: 8px 16px;
  border-radius: 50px;
  font-size: 0.82rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  margin-bottom: 24px;
  text-transform: uppercase;
}

.hero-badge::before {
  content: '';
  width: 6px; height: 6px;
  background: var(--orange);
  border-radius: 50%;
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.5; transform: scale(1.3); }
}

.hero h1 {
  font-family: 'Sora', sans-serif;
  font-size: clamp(2.2rem, 4vw, 3.4rem);
  font-weight: 800;
  color: var(--white);
  line-height: 1.15;
  letter-spacing: -1px;
  margin-bottom: 20px;
}

.hero h1 .highlight {
  color: var(--orange);
  position: relative;
}

.hero p {
  color: rgba(255,255,255,0.65);
  font-size: 1.05rem;
  line-height: 1.7;
  margin-bottom: 36px;
  max-width: 480px;
}

.hero-btns {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
}

.btn-primary {
  background: var(--orange);
  color: var(--white);
  border: none;
  padding: 14px 28px;
  border-radius: 50px;
  font-size: 0.95rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  font-family: 'DM Sans', sans-serif;
  text-decoration: none;
  display: inline-block;
}

.btn-primary:hover {
  background: var(--orange-light);
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(255,107,0,0.4);
}

.btn-secondary {
  background: rgba(255,255,255,0.08);
  color: var(--white);
  border: 1px solid rgba(255,255,255,0.2);
  padding: 14px 28px;
  border-radius: 50px;
  font-size: 0.95rem;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s;
  font-family: 'DM Sans', sans-serif;
}

.btn-secondary:hover {
  background: rgba(255,255,255,0.15);
  border-color: rgba(255,255,255,0.4);
}

/* Stats */
.hero-stats {
  display: grid;
  grid-template-columns: repeat(2,1fr);
  gap: 16px;
  margin-top: 48px;
}

.stat-card {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 16px;
  padding: 20px;
}

.stat-card .num {
  font-family: 'Sora', sans-serif;
  font-size: 2rem;
  font-weight: 800;
  color: var(--orange);
  line-height: 1;
}

.stat-card .label {
  color: rgba(255,255,255,0.55);
  font-size: 0.82rem;
  margin-top: 4px;
}

/* Hero visual */
.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.hero-card-stack {
  position: relative;
  width: 340px;
  height: 400px;
}

.glow-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(60px);
  pointer-events: none;
}

.orb1 {
  width: 300px; height: 300px;
  background: rgba(255,107,0,0.25);
  top: 50%; left: 50%;
  transform: translate(-50%,-50%);
}

.orb2 {
  width: 200px; height: 200px;
  background: rgba(255,184,0,0.15);
  top: 0; right: 0;
}

.float-card {
  position: absolute;
  background: rgba(255,255,255,0.07);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 20px;
  padding: 20px 24px;
  color: white;
}

.float-card.main {
  top: 50%; left: 50%;
  transform: translate(-50%,-50%);
  width: 280px;
  text-align: center;
  animation: floatUp 3s ease-in-out infinite;
}

.float-card.badge1 {
  top: 10%; right: -20px;
  font-size: 0.82rem;
  animation: floatUp 3s ease-in-out infinite 0.5s;
}

.float-card.badge2 {
  bottom: 15%; left: -20px;
  font-size: 0.82rem;
  animation: floatUp 3s ease-in-out infinite 1s;
}

@keyframes floatUp {
  0%, 100% { transform: translate(-50%,-50%) translateY(0); }
  50% { transform: translate(-50%,-50%) translateY(-12px); }
}

.float-card.badge1, .float-card.badge2 {
  animation: floatSimple 3s ease-in-out infinite;
}

@keyframes floatSimple {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.luma-icon {
  font-size: 3rem;
  margin-bottom: 12px;
}

.float-card.main h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 6px;
}

.float-card.main p {
  font-size: 0.82rem;
  color: rgba(255,255,255,0.6);
  margin-bottom: 0;
  max-width: none;
}

.badge-icon { font-size: 1.4rem; margin-bottom: 4px; }
.badge-text { font-weight: 600; font-size: 0.85rem; }
.badge-sub { font-size: 0.75rem; color: rgba(255,255,255,0.55); }

/* Marquee */
.marquee-bar {
  background: var(--orange);
  padding: 12px 0;
  overflow: hidden;
  white-space: nowrap;
}

.marquee-track {
  display: inline-block;
  animation: marquee 25s linear infinite;
}

.marquee-track span {
  color: white;
  font-size: 0.88rem;
  font-weight: 600;
  margin: 0 40px;
  letter-spacing: 0.3px;
}

.marquee-track span::before {
  content: '★ ';
  opacity: 0.8;
}

@keyframes marquee {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}

/* Section styles */
section {
  padding: 90px 24px;
}

.section-inner {
  max-width: 1200px;
  margin: 0 auto;
}

.section-label {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: var(--orange);
  font-size: 0.82rem;
  font-weight: 700;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  margin-bottom: 14px;
}

.section-label::before {
  content: '';
  width: 20px; height: 2px;
  background: var(--orange);
  border-radius: 2px;
}

.section-title {
  font-family: 'Sora', sans-serif;
  font-size: clamp(1.8rem, 3vw, 2.6rem);
  font-weight: 800;
  color: var(--navy);
  letter-spacing: -0.5px;
  line-height: 1.2;
  margin-bottom: 16px;
}

.section-subtitle {
  color: var(--gray);
  font-size: 1rem;
  line-height: 1.7;
  max-width: 540px;
}

.text-center { text-align: center; }
.text-center .section-label { justify-content: center; }
.text-center .section-subtitle { margin: 0 auto; }

/* Features grid */
.features-section { background: var(--off-white); }

.features-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 56px;
}

.feature-card {
  background: var(--white);
  border-radius: 20px;
  padding: 32px 28px;
  border: 1px solid var(--gray-light);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.feature-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: var(--orange);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 50px rgba(0,0,0,0.08);
  border-color: transparent;
}

.feature-card:hover::before { transform: scaleX(1); }

.feature-icon {
  width: 56px; height: 56px;
  background: rgba(255,107,0,0.1);
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  margin-bottom: 20px;
}

.feature-card h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1.05rem;
  font-weight: 700;
  color: var(--navy);
  margin-bottom: 10px;
}

.feature-card p {
  color: var(--gray);
  font-size: 0.9rem;
  line-height: 1.65;
}

/* Courses */
.courses-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 56px;
}

.course-card {
  background: var(--navy);
  border-radius: 24px;
  overflow: hidden;
  transition: all 0.3s ease;
  position: relative;
}

.course-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 25px 60px rgba(11,29,58,0.3);
}

.course-top {
  padding: 32px 28px 24px;
  position: relative;
}

.course-emoji { font-size: 2.5rem; margin-bottom: 16px; display: block; }

.course-tag {
  position: absolute;
  top: 20px; right: 20px;
  background: rgba(255,107,0,0.2);
  color: var(--orange-light);
  font-size: 0.75rem;
  font-weight: 700;
  padding: 5px 12px;
  border-radius: 50px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.course-card h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--white);
  margin-bottom: 8px;
}

.course-card p {
  color: rgba(255,255,255,0.55);
  font-size: 0.88rem;
  line-height: 1.6;
}

.course-bottom {
  padding: 20px 28px 28px;
  border-top: 1px solid rgba(255,255,255,0.07);
}

.course-meta {
  display: flex;
  gap: 16px;
  margin-bottom: 20px;
}

.meta-item {
  display: flex;
  align-items: center;
  gap: 6px;
  color: rgba(255,255,255,0.55);
  font-size: 0.82rem;
}

.meta-item span:first-child { font-size: 0.9rem; }

.course-btn {
  width: 100%;
  background: rgba(255,107,0,0.15);
  color: var(--orange-light);
  border: 1px solid rgba(255,107,0,0.3);
  padding: 12px;
  border-radius: 12px;
  font-size: 0.88rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  font-family: 'DM Sans', sans-serif;
}

.course-btn:hover {
  background: var(--orange);
  color: white;
  border-color: var(--orange);
}

/* Toppers */
.toppers-section { background: var(--navy); }
.toppers-section .section-title { color: var(--white); }
.toppers-section .section-label { color: var(--gold); }
.toppers-section .section-label::before { background: var(--gold); }

.toppers-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  margin-top: 56px;
}

.topper-card {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 20px;
  padding: 28px 20px;
  text-align: center;
  transition: all 0.3s;
}

.topper-card:hover {
  background: rgba(255,107,0,0.1);
  border-color: rgba(255,107,0,0.3);
  transform: translateY(-4px);
}

.topper-avatar {
  width: 72px; height: 72px;
  background: linear-gradient(135deg, var(--orange), var(--gold));
  border-radius: 50%;
  margin: 0 auto 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Sora', sans-serif;
  font-size: 1.5rem;
  font-weight: 800;
  color: white;
}

.topper-card h4 {
  font-family: 'Sora', sans-serif;
  font-size: 0.95rem;
  font-weight: 700;
  color: var(--white);
  margin-bottom: 4px;
}

.topper-exam {
  color: rgba(255,255,255,0.45);
  font-size: 0.78rem;
  margin-bottom: 12px;
}

.topper-rank {
  background: var(--orange);
  color: white;
  font-size: 0.82rem;
  font-weight: 700;
  padding: 5px 14px;
  border-radius: 50px;
  display: inline-block;
}

/* Testimonials */
.testimonials-section { background: var(--off-white); }

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 56px;
}

.testimonial-card {
  background: var(--white);
  border-radius: 20px;
  padding: 28px;
  border: 1px solid var(--gray-light);
  transition: all 0.3s;
}

.testimonial-card:hover {
  box-shadow: 0 12px 40px rgba(0,0,0,0.07);
  border-color: transparent;
}

.stars { color: var(--gold); font-size: 0.9rem; margin-bottom: 14px; }

.testimonial-card p {
  color: var(--gray);
  font-size: 0.92rem;
  line-height: 1.7;
  font-style: italic;
  margin-bottom: 20px;
}

.testimonial-author {
  display: flex;
  align-items: center;
  gap: 12px;
}

.author-avatar {
  width: 44px; height: 44px;
  background: linear-gradient(135deg, var(--navy), var(--navy-light));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: 700;
  font-size: 0.85rem;
}

.author-name {
  font-weight: 600;
  font-size: 0.9rem;
  color: var(--navy);
}

.author-class {
  font-size: 0.78rem;
  color: var(--gray);
}

/* Contact section */
.contact-section { background: var(--white); }

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  margin-top: 56px;
  align-items: start;
}

.contact-info h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--navy);
  margin-bottom: 16px;
}

.contact-info p {
  color: var(--gray);
  font-size: 0.95rem;
  line-height: 1.7;
  margin-bottom: 32px;
}

.contact-items { display: flex; flex-direction: column; gap: 16px; }

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 14px;
}

.contact-item-icon {
  width: 44px; height: 44px;
  background: rgba(255,107,0,0.1);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.1rem;
  flex-shrink: 0;
}

.contact-item-text strong {
  display: block;
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--navy);
  margin-bottom: 2px;
}

.contact-item-text span {
  color: var(--gray);
  font-size: 0.88rem;
}

.contact-form {
  background: var(--off-white);
  border-radius: 24px;
  padding: 36px 32px;
}

.contact-form h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--navy);
  margin-bottom: 24px;
}

.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }

.form-group { margin-bottom: 14px; }

.form-group label {
  display: block;
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--navy);
  margin-bottom: 6px;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 12px 16px;
  border: 1.5px solid var(--gray-light);
  border-radius: 12px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.9rem;
  color: var(--text);
  background: var(--white);
  transition: border-color 0.2s;
  outline: none;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  border-color: var(--orange);
}

.form-group textarea { resize: none; height: 90px; }

.form-submit {
  width: 100%;
  background: var(--orange);
  color: white;
  border: none;
  padding: 14px;
  border-radius: 12px;
  font-size: 0.95rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  font-family: 'DM Sans', sans-serif;
  margin-top: 6px;
}

.form-submit:hover {
  background: var(--orange-light);
  transform: translateY(-2px);
}

/* ===== WHY US PAGE ===== */
.page-hero {
  background: var(--navy);
  padding: 140px 24px 80px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.page-hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse 70% 60% at 50% 50%, rgba(255,107,0,0.1) 0%, transparent 70%);
}

.page-hero .section-label { justify-content: center; color: var(--gold); }
.page-hero .section-label::before { background: var(--gold); }

.page-hero h1 {
  font-family: 'Sora', sans-serif;
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 800;
  color: var(--white);
  letter-spacing: -0.5px;
  margin-bottom: 16px;
  position: relative;
}

.page-hero p {
  color: rgba(255,255,255,0.6);
  font-size: 1.05rem;
  max-width: 540px;
  margin: 0 auto;
  line-height: 1.7;
  position: relative;
}

.why-us-section { background: var(--white); padding: 80px 24px; }

.why-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
  margin-top: 56px;
}

.why-card {
  display: flex;
  gap: 20px;
  background: var(--off-white);
  border-radius: 20px;
  padding: 28px;
  border: 1px solid var(--gray-light);
  transition: all 0.3s;
}

.why-card:hover {
  border-color: var(--orange);
  box-shadow: 0 8px 30px rgba(255,107,0,0.1);
  transform: translateY(-3px);
}

.why-icon {
  width: 52px; height: 52px;
  background: rgba(255,107,0,0.1);
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.4rem;
  flex-shrink: 0;
}

.why-content h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1rem;
  font-weight: 700;
  color: var(--navy);
  margin-bottom: 8px;
}

.why-content p {
  color: var(--gray);
  font-size: 0.88rem;
  line-height: 1.65;
}

.numbers-section {
  background: var(--navy);
  padding: 80px 24px;
}

.numbers-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
  margin-top: 48px;
  text-align: center;
}

.number-item .big-num {
  font-family: 'Sora', sans-serif;
  font-size: 3rem;
  font-weight: 800;
  color: var(--orange);
  line-height: 1;
  margin-bottom: 8px;
}

.number-item .num-label {
  color: rgba(255,255,255,0.6);
  font-size: 0.9rem;
}

/* ===== CURRICULUM PAGE ===== */
.curriculum-section { padding: 80px 24px; }

.curriculum-tabs {
  display: flex;
  gap: 8px;
  margin: 40px 0;
  border-bottom: 2px solid var(--gray-light);
  overflow-x: auto;
  padding-bottom: 0;
}

.curr-tab {
  padding: 12px 24px;
  border: none;
  background: none;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.92rem;
  font-weight: 600;
  color: var(--gray);
  cursor: pointer;
  border-bottom: 2px solid transparent;
  margin-bottom: -2px;
  white-space: nowrap;
  transition: all 0.2s;
}

.curr-tab.active, .curr-tab:hover {
  color: var(--orange);
  border-bottom-color: var(--orange);
}

.curr-content { display: none; }
.curr-content.active { display: block; }

.curr-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.subject-card {
  background: var(--off-white);
  border-radius: 16px;
  overflow: hidden;
  border: 1px solid var(--gray-light);
}

.subject-header {
  padding: 20px 22px;
  display: flex;
  align-items: center;
  gap: 12px;
  border-bottom: 1px solid var(--gray-light);
}

.subject-emoji { font-size: 1.4rem; }

.subject-header h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1rem;
  font-weight: 700;
  color: var(--navy);
}

.subject-topics {
  padding: 16px 22px;
  list-style: none;
}

.subject-topics li {
  padding: 7px 0;
  color: var(--gray);
  font-size: 0.85rem;
  border-bottom: 1px solid var(--gray-light);
  display: flex;
  align-items: center;
  gap: 8px;
}

.subject-topics li:last-child { border-bottom: none; }

.subject-topics li::before {
  content: '→';
  color: var(--orange);
  font-size: 0.75rem;
  flex-shrink: 0;
}

/* ===== PROGRAMMES PAGE ===== */
.programmes-section { padding: 80px 24px; }

.prog-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 28px;
  margin-top: 48px;
}

.prog-card {
  background: var(--white);
  border-radius: 24px;
  border: 2px solid var(--gray-light);
  overflow: hidden;
  transition: all 0.3s;
}

.prog-card:hover {
  border-color: var(--orange);
  box-shadow: 0 16px 50px rgba(255,107,0,0.12);
  transform: translateY(-4px);
}

.prog-card.featured {
  border-color: var(--orange);
  position: relative;
}

.prog-featured-tag {
  position: absolute;
  top: 20px; right: 20px;
  background: var(--orange);
  color: white;
  font-size: 0.72rem;
  font-weight: 700;
  padding: 5px 12px;
  border-radius: 50px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.prog-top {
  background: var(--navy);
  padding: 32px 28px;
}

.prog-top h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1.25rem;
  font-weight: 800;
  color: var(--white);
  margin-bottom: 8px;
}

.prog-top p {
  color: rgba(255,255,255,0.55);
  font-size: 0.88rem;
  line-height: 1.6;
}

.prog-bottom { padding: 28px; }

.prog-features { list-style: none; margin-bottom: 24px; }

.prog-features li {
  padding: 8px 0;
  color: var(--text);
  font-size: 0.9rem;
  display: flex;
  align-items: center;
  gap: 10px;
  border-bottom: 1px solid var(--gray-light);
}

.prog-features li:last-child { border-bottom: none; }

.prog-features li::before {
  content: '✓';
  width: 20px; height: 20px;
  background: rgba(255,107,0,0.1);
  color: var(--orange);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.7rem;
  font-weight: 700;
  flex-shrink: 0;
}

.prog-btn {
  width: 100%;
  background: var(--navy);
  color: white;
  border: none;
  padding: 14px;
  border-radius: 12px;
  font-size: 0.92rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  font-family: 'DM Sans', sans-serif;
}

.prog-btn:hover { background: var(--orange); }
.prog-card.featured .prog-btn { background: var(--orange); }
.prog-card.featured .prog-btn:hover { background: var(--orange-light); }

/* ===== FEES/PRICING PAGE ===== */
.pricing-section { padding: 80px 24px; }

.pricing-toggle {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 14px;
  margin: 36px 0;
}

.toggle-label {
  font-weight: 600;
  color: var(--gray);
  font-size: 0.92rem;
}

.toggle-label.active { color: var(--navy); }

.toggle-switch {
  width: 52px; height: 28px;
  background: var(--orange);
  border-radius: 14px;
  position: relative;
  cursor: pointer;
}

.toggle-switch::after {
  content: '';
  width: 22px; height: 22px;
  background: white;
  border-radius: 50%;
  position: absolute;
  top: 3px; left: 3px;
  transition: left 0.2s;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 20px;
}

.price-card {
  background: var(--white);
  border-radius: 24px;
  border: 2px solid var(--gray-light);
  overflow: hidden;
  transition: all 0.3s;
  text-align: center;
}

.price-card:hover {
  border-color: var(--orange);
  box-shadow: 0 16px 50px rgba(255,107,0,0.1);
  transform: translateY(-4px);
}

.price-card.popular {
  border-color: var(--orange);
  transform: scale(1.04);
}

.price-card.popular:hover { transform: scale(1.04) translateY(-4px); }

.popular-tag {
  background: var(--orange);
  color: white;
  font-size: 0.75rem;
  font-weight: 700;
  padding: 8px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.price-top { padding: 32px 28px 24px; }

.price-top h3 {
  font-family: 'Sora', sans-serif;
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--navy);
  margin-bottom: 4px;
}

.price-top .subtitle {
  color: var(--gray);
  font-size: 0.82rem;
  margin-bottom: 20px;
}

.price-amount {
  font-family: 'Sora', sans-serif;
  font-size: 2.8rem;
  font-weight: 800;
  color: var(--navy);
  line-height: 1;
}

.price-amount span { font-size: 1.2rem; font-weight: 600; }
.price-period { color: var(--gray); font-size: 0.82rem; margin-top: 4px; }

.price-features {
  padding: 0 28px 28px;
  list-style: none;
  text-align: left;
}

.price-features li {
  padding: 9px 0;
  font-size: 0.88rem;
  color: var(--text);
  display: flex;
  align-items: center;
  gap: 10px;
  border-bottom: 1px solid var(--gray-light);
}

.price-features li:last-child { border-bottom: none; }

.price-features li::before {
  content: '✓';
  color: var(--orange);
  font-weight: 700;
  flex-shrink: 0;
}

.price-features li.no::before { content: '✗'; color: var(--gray); }
.price-features li.no { color: var(--gray); }

.price-btn-wrap { padding: 0 28px 28px; }

.price-btn {
  width: 100%;
  background: var(--navy);
  color: white;
  border: none;
  padding: 14px;
  border-radius: 12px;
  font-size: 0.92rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  font-family: 'DM Sans', sans-serif;
}

.price-btn:hover { background: var(--orange); }
.price-card.popular .price-btn { background: var(--orange); }
.price-card.popular .price-btn:hover { background: var(--orange-light); }

.faq-section {
  background: var(--off-white);
  padding: 80px 24px;
}

.faq-list {
  max-width: 720px;
  margin: 48px auto 0;
}

.faq-item {
  background: var(--white);
  border-radius: 14px;
  border: 1px solid var(--gray-light);
  margin-bottom: 12px;
  overflow: hidden;
}

.faq-q {
  padding: 18px 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  font-weight: 600;
  color: var(--navy);
  font-size: 0.95rem;
  gap: 12px;
}

.faq-arrow {
  color: var(--orange);
  font-size: 1.1rem;
  transition: transform 0.3s;
  flex-shrink: 0;
}

.faq-item.open .faq-arrow { transform: rotate(180deg); }

.faq-a {
  display: none;
  padding: 0 24px 18px;
  color: var(--gray);
  font-size: 0.9rem;
  line-height: 1.7;
}

.faq-item.open .faq-a { display: block; }

/* ===== FOOTER ===== */
footer {
  background: var(--navy);
  padding: 60px 24px 24px;
}

.footer-inner {
  max-width: 1200px;
  margin: 0 auto;
}

.footer-top {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 40px;
  margin-bottom: 48px;
}

.footer-brand .logo { font-size: 1.4rem; display: inline-block; margin-bottom: 12px; }

.footer-brand p {
  color: rgba(255,255,255,0.5);
  font-size: 0.88rem;
  line-height: 1.7;
  margin-bottom: 20px;
}

.social-links { display: flex; gap: 10px; }

.social-btn {
  width: 38px; height: 38px;
  background: rgba(255,255,255,0.07);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255,255,255,0.6);
  text-decoration: none;
  font-size: 0.85rem;
  transition: all 0.2s;
}

.social-btn:hover { background: var(--orange); color: white; }

.footer-col h4 {
  font-family: 'Sora', sans-serif;
  font-size: 0.9rem;
  font-weight: 700;
  color: var(--white);
  margin-bottom: 16px;
}

.footer-links { list-style: none; }

.footer-links li { margin-bottom: 9px; }

.footer-links a {
  color: rgba(255,255,255,0.5);
  text-decoration: none;
  font-size: 0.86rem;
  transition: color 0.2s;
  cursor: pointer;
}

.footer-links a:hover { color: var(--orange); }

.footer-bottom {
  border-top: 1px solid rgba(255,255,255,0.07);
  padding-top: 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
  flex-wrap: wrap;
}

.footer-bottom p {
  color: rgba(255,255,255,0.35);
  font-size: 0.82rem;
}

/* WhatsApp FAB */
.whatsapp-fab {
  position: fixed;
  bottom: 28px;
  right: 28px;
  width: 56px; height: 56px;
  background: #25D366;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.5rem;
  text-decoration: none;
  box-shadow: 0 4px 20px rgba(37,211,102,0.4);
  z-index: 999;
  transition: all 0.2s;
  animation: wiggle 3s ease-in-out infinite 5s;
}

.whatsapp-fab:hover {
  transform: scale(1.1);
  box-shadow: 0 8px 30px rgba(37,211,102,0.5);
}

@keyframes wiggle {
  0%, 100% { transform: rotate(0); }
  25% { transform: rotate(-10deg); }
  75% { transform: rotate(10deg); }
}

/* Mobile */
@media (max-width: 900px) {
  .nav-links { display: none; }
  .hamburger { display: flex; }
  
  .nav-links.open {
    display: flex;
    flex-direction: column;
    position: fixed;
    top: 70px; left: 0; right: 0;
    background: var(--navy);
    padding: 20px;
    gap: 4px;
    border-bottom: 1px solid rgba(255,255,255,0.08);
  }

  .hero-inner { grid-template-columns: 1fr; }
  .hero-visual { display: none; }
  .features-grid { grid-template-columns: 1fr; }
  .courses-grid { grid-template-columns: 1fr; }
  .toppers-grid { grid-template-columns: repeat(2,1fr); }
  .testimonials-grid { grid-template-columns: 1fr; }
  .contact-grid { grid-template-columns: 1fr; }
  .footer-top { grid-template-columns: 1fr 1fr; }
  .why-grid { grid-template-columns: 1fr; }
  .numbers-grid { grid-template-columns: repeat(2,1fr); }
  .curr-grid { grid-template-columns: 1fr; }
  .prog-grid { grid-template-columns: 1fr; }
  .pricing-grid { grid-template-columns: 1fr; }
  .price-card.popular { transform: none; }
  .form-row { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
  <div class="nav-inner">
    <a class="logo" onclick="showPage('home')">Edu<span>Luma</span></a>
    <ul class="nav-links" id="navLinks">
      <li><a onclick="showPage('home')" class="active" id="nav-home">Home</a></li>
      <li><a onclick="showPage('why-us')" id="nav-why-us">Why Us</a></li>
      <li><a onclick="showPage('curriculum')" id="nav-curriculum">Curriculum</a></li>
      <li><a onclick="showPage('programmes')" id="nav-programmes">Programmes</a></li>
      <li><a onclick="showPage('pricing')" id="nav-pricing">Fees</a></li>
      <li><a onclick="showPage('home'); setTimeout(()=>document.getElementById('contact').scrollIntoView({behavior:'smooth'}),100)" class="nav-cta">Enroll Now</a></li>
    </ul>
    <div class="hamburger" onclick="toggleNav()">
      <span></span><span></span><span></span>
    </div>
  </div>
</nav>

<!-- ===================== HOME PAGE ===================== -->
<div class="page active" id="page-home">

  <!-- Hero -->
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-grid"></div>
    <div class="hero-inner">
      <div class="hero-left">
        <div class="hero-badge">Admissions Open 2025–26</div>
        <h1>India's Premier <span class="highlight">IIT JEE</span> &amp; <span class="highlight">NEET</span> Coaching</h1>
        <p>EduLuma empowers aspirants with IITian faculty, personalised mentoring, and a results-driven approach — illuminating the path to your dream rank.</p>
        <div class="hero-btns">
          <button class="btn-primary" onclick="showPage('programmes')">Explore Courses</button>
          <button class="btn-secondary" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Book Free Demo</button>
        </div>
        <div class="hero-stats">
          <div class="stat-card"><div class="num">5000+</div><div class="label">Students Enrolled</div></div>
          <div class="stat-card"><div class="num">1200+</div><div class="label">IIT / NEET Selections</div></div>
          <div class="stat-card"><div class="num">12+</div><div class="label">Years of Excellence</div></div>
          <div class="stat-card"><div class="num">50+</div><div class="label">Expert Faculty</div></div>
        </div>
      </div>
      <div class="hero-visual">
        <div class="glow-orb orb1"></div>
        <div class="glow-orb orb2"></div>
        <div class="hero-card-stack">
          <div class="float-card main">
            <div class="luma-icon">💡</div>
            <h3>EduLuma Institute</h3>
            <p>Glow with Knowledge. Reach your Rank.</p>
          </div>
          <div class="float-card badge1">
            <div class="badge-icon">🏆</div>
            <div class="badge-text">AIR 47</div>
            <div class="badge-sub">JEE Advanced 2024</div>
          </div>
          <div class="float-card badge2">
            <div class="badge-icon">🩺</div>
            <div class="badge-text">700 / 720</div>
            <div class="badge-sub">NEET 2024 Topper</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Marquee -->
  <div class="marquee-bar">
    <div class="marquee-track">
      <span>Admissions Open 2025–26</span>
      <span>JEE Main Batch Starting Soon</span>
      <span>NEET 2025 Scholarship Test Every Sunday</span>
      <span>Free Demo Class Available</span>
      <span>IITian Faculty | Proven Results</span>
      <span>Admissions Open 2025–26</span>
      <span>JEE Main Batch Starting Soon</span>
      <span>NEET 2025 Scholarship Test Every Sunday</span>
      <span>Free Demo Class Available</span>
      <span>IITian Faculty | Proven Results</span>
    </div>
  </div>

  <!-- Features -->
  <section class="features-section">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label">Why EduLuma</div>
        <h2 class="section-title">Built Different. Built for Toppers.</h2>
        <p class="section-subtitle">Every element of EduLuma is designed with one goal — your selection.</p>
      </div>
      <div class="features-grid">
        <div class="feature-card">
          <div class="feature-icon">🎓</div>
          <h3>IITian Faculty</h3>
          <p>Learn from faculty who have cracked IIT and NEET themselves — bringing real exam insight to every class.</p>
        </div>
        <div class="feature-card">
          <div class="feature-icon">👥</div>
          <h3>Small Batch Sizes</h3>
          <p>Maximum 25 students per batch to ensure every student gets personal attention and timely doubt resolution.</p>
        </div>
        <div class="feature-card">
          <div class="feature-icon">📝</div>
          <h3>Daily Practice Tests</h3>
          <p>Daily DPPs, weekly chapter tests and monthly mock exams aligned to the exact JEE/NEET pattern.</p>
        </div>
        <div class="feature-card">
          <div class="feature-icon">📚</div>
          <h3>Premium Study Material</h3>
          <p>Comprehensive, Kota-standard printed modules updated yearly to reflect latest exam trends and syllabus.</p>
        </div>
        <div class="feature-card">
          <div class="feature-icon">🖥️</div>
          <h3>Online + Offline Classes</h3>
          <p>Flexible hybrid mode — attend live in class or from home via our learning portal with recorded lectures.</p>
        </div>
        <div class="feature-card">
          <div class="feature-icon">🧑‍💼</div>
          <h3>1-on-1 Mentorship</h3>
          <p>Dedicated mentors track every student's progress and provide personalised guidance and motivation.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Courses -->
  <section style="background:var(--white);padding:90px 24px;">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label">Our Courses</div>
        <h2 class="section-title">Choose Your Path to Success</h2>
        <p class="section-subtitle">Structured programmes designed for every stage of your preparation journey.</p>
      </div>
      <div class="courses-grid">
        <div class="course-card">
          <div class="course-top">
            <span class="course-emoji">⚙️</span>
            <span class="course-tag">Engineering</span>
            <h3>JEE Main</h3>
            <p>Complete preparation for JEE Main with concept clarity, problem solving and full mock tests.</p>
          </div>
          <div class="course-bottom">
            <div class="course-meta">
              <div class="meta-item"><span>📅</span><span>1 Year</span></div>
              <div class="meta-item"><span>👥</span><span>Batch of 25</span></div>
            </div>
            <button class="course-btn" onclick="showPage('programmes')">Know More →</button>
          </div>
        </div>
        <div class="course-card">
          <div class="course-top">
            <span class="course-emoji">🚀</span>
            <span class="course-tag">Elite</span>
            <h3>JEE Advanced</h3>
            <p>Advanced-level coaching for IIT aspirants with in-depth problem-solving and analytical skills.</p>
          </div>
          <div class="course-bottom">
            <div class="course-meta">
              <div class="meta-item"><span>📅</span><span>2 Years</span></div>
              <div class="meta-item"><span>👥</span><span>Batch of 20</span></div>
            </div>
            <button class="course-btn" onclick="showPage('programmes')">Know More →</button>
          </div>
        </div>
        <div class="course-card">
          <div class="course-top">
            <span class="course-emoji">🩺</span>
            <span class="course-tag">Medical</span>
            <h3>NEET UG</h3>
            <p>Comprehensive NEET coaching covering Physics, Chemistry and Biology with doctor-led faculty.</p>
          </div>
          <div class="course-bottom">
            <div class="course-meta">
              <div class="meta-item"><span>📅</span><span>1–2 Years</span></div>
              <div class="meta-item"><span>👥</span><span>Batch of 25</span></div>
            </div>
            <button class="course-btn" onclick="showPage('programmes')">Know More →</button>
          </div>
        </div>
        <div class="course-card">
          <div class="course-top">
            <span class="course-emoji">🌱</span>
            <span class="course-tag">Foundation</span>
            <h3>Class 8–10 Foundation</h3>
            <p>Build a strong science and math base early — the smartest head start for JEE/NEET.</p>
          </div>
          <div class="course-bottom">
            <div class="course-meta">
              <div class="meta-item"><span>📅</span><span>1 Year</span></div>
              <div class="meta-item"><span>👥</span><span>Batch of 30</span></div>
            </div>
            <button class="course-btn" onclick="showPage('programmes')">Know More →</button>
          </div>
        </div>
        <div class="course-card">
          <div class="course-top">
            <span class="course-emoji">🔄</span>
            <span class="course-tag">Repeater</span>
            <h3>Dropper Batch</h3>
            <p>Intensive one-year programme for students who want to improve their rank and crack their target exam.</p>
          </div>
          <div class="course-bottom">
            <div class="course-meta">
              <div class="meta-item"><span>📅</span><span>1 Year</span></div>
              <div class="meta-item"><span>👥</span><span>Batch of 20</span></div>
            </div>
            <button class="course-btn" onclick="showPage('programmes')">Know More →</button>
          </div>
        </div>
        <div class="course-card">
          <div class="course-top">
            <span class="course-emoji">⚡</span>
            <span class="course-tag">Short-Term</span>
            <h3>Crash Course</h3>
            <p>Rapid revision and test-readiness programme in the last 3 months before the exam.</p>
          </div>
          <div class="course-bottom">
            <div class="course-meta">
              <div class="meta-item"><span>📅</span><span>3 Months</span></div>
              <div class="meta-item"><span>👥</span><span>Batch of 30</span></div>
            </div>
            <button class="course-btn" onclick="showPage('programmes')">Know More →</button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Toppers -->
  <section class="toppers-section">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label">Our Toppers</div>
        <h2 class="section-title" style="color:white;">Our Students. Their Glory.</h2>
        <p class="section-subtitle" style="color:rgba(255,255,255,0.55);margin:0 auto;">Thousands of students have trusted EduLuma to illuminate their path to success.</p>
      </div>
      <div class="toppers-grid">
        <div class="topper-card">
          <div class="topper-avatar">AK</div>
          <h4>Arjun Kumar</h4>
          <div class="topper-exam">JEE Advanced 2024</div>
          <div class="topper-rank">AIR 47</div>
        </div>
        <div class="topper-card">
          <div class="topper-avatar">PS</div>
          <h4>Priya Sharma</h4>
          <div class="topper-exam">NEET 2024</div>
          <div class="topper-rank">700 / 720</div>
        </div>
        <div class="topper-card">
          <div class="topper-avatar">RV</div>
          <h4>Rahul Verma</h4>
          <div class="topper-exam">JEE Main 2024</div>
          <div class="topper-rank">99.7 %ile</div>
        </div>
        <div class="topper-card">
          <div class="topper-avatar">SN</div>
          <h4>Sneha Nair</h4>
          <div class="topper-exam">NEET 2024</div>
          <div class="topper-rank">AIR 312</div>
        </div>
      </div>
    </div>
  </section>

  <!-- Testimonials -->
  <section class="testimonials-section">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label">Testimonials</div>
        <h2 class="section-title">What Our Students Say</h2>
      </div>
      <div class="testimonials-grid">
        <div class="testimonial-card">
          <div class="stars">★★★★★</div>
          <p>"EduLuma completely changed my approach to JEE. The faculty breaks down the toughest concepts with such clarity. I never felt lost — even in Calculus and Electrochemistry!"</p>
          <div class="testimonial-author">
            <div class="author-avatar">AK</div>
            <div>
              <div class="author-name">Arjun Kumar</div>
              <div class="author-class">JEE Advanced — AIR 47</div>
            </div>
          </div>
        </div>
        <div class="testimonial-card">
          <div class="stars">★★★★★</div>
          <p>"The small batch size meant my doubts were always heard. The Biology faculty at EduLuma is exceptional — I scored 360/360 in Biology in NEET!"</p>
          <div class="testimonial-author">
            <div class="author-avatar">PS</div>
            <div>
              <div class="author-name">Priya Sharma</div>
              <div class="author-class">NEET 2024 — 700/720</div>
            </div>
          </div>
        </div>
        <div class="testimonial-card">
          <div class="stars">★★★★★</div>
          <p>"After a disappointing first attempt, the Dropper Batch at EduLuma helped me completely turn around. The mentors never gave up on me. I'm going to IIT Bombay!"</p>
          <div class="testimonial-author">
            <div class="author-avatar">RV</div>
            <div>
              <div class="author-name">Rahul Verma</div>
              <div class="author-class">JEE Main — 99.7 Percentile</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section class="contact-section" id="contact">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label">Contact Us</div>
        <h2 class="section-title">Start Your Journey Today</h2>
        <p class="section-subtitle">Reach out to book your free demo class or get answers to all your queries.</p>
      </div>
      <div class="contact-grid">
        <div>
          <div class="contact-info">
            <h3>We're Here to Help</h3>
            <p>Our counsellors are available Mon–Sat, 9am–7pm to guide you through the best programme for your goal.</p>
          </div>
          <div class="contact-items">
            <div class="contact-item">
              <div class="contact-item-icon">📍</div>
              <div class="contact-item-text">
                <strong>Address</strong>
                <span>EduLuma Institute, 3rd Floor, Knowledge Tower,<br>Uppal, Hyderabad – 500039</span>
              </div>
            </div>
            <div class="contact-item">
              <div class="contact-item-icon">📞</div>
              <div class="contact-item-text">
                <strong>Phone</strong>
                <span>+91 98765 43210 | +91 87654 32109</span>
              </div>
            </div>
            <div class="contact-item">
              <div class="contact-item-icon">✉️</div>
              <div class="contact-item-text">
                <strong>Email</strong>
                <span>admissions@eduluma.in</span>
              </div>
            </div>
            <div class="contact-item">
              <div class="contact-item-icon">🕐</div>
              <div class="contact-item-text">
                <strong>Office Hours</strong>
                <span>Monday – Saturday: 9:00 AM – 7:00 PM</span>
              </div>
            </div>
          </div>
        </div>
        <div class="contact-form">
          <h3>Book a Free Demo Class</h3>
          <div class="form-row">
            <div class="form-group">
              <label>Full Name</label>
              <input type="text" placeholder="Your name">
            </div>
            <div class="form-group">
              <label>Phone Number</label>
              <input type="tel" placeholder="+91 XXXXX XXXXX">
            </div>
          </div>
          <div class="form-group">
            <label>Email Address</label>
            <input type="email" placeholder="your@email.com">
          </div>
          <div class="form-row">
            <div class="form-group">
              <label>Class / Year</label>
              <select>
                <option value="">Select Class</option>
                <option>Class 8</option>
                <option>Class 9</option>
                <option>Class 10</option>
                <option>Class 11</option>
                <option>Class 12</option>
                <option>Dropper</option>
              </select>
            </div>
            <div class="form-group">
              <label>Target Exam</label>
              <select>
                <option value="">Select Exam</option>
                <option>JEE Main</option>
                <option>JEE Advanced</option>
                <option>NEET UG</option>
                <option>Foundation</option>
              </select>
            </div>
          </div>
          <div class="form-group">
            <label>Message (optional)</label>
            <textarea placeholder="Any specific questions or requirements..."></textarea>
          </div>
          <button class="form-submit" onclick="alert('Thank you! We will contact you within 24 hours. 🎉')">Submit Enquiry →</button>
        </div>
      </div>
    </div>
  </section>

</div>

<!-- ===================== WHY US PAGE ===================== -->
<div class="page" id="page-why-us">
  <div class="page-hero">
    <div class="section-label">Why EduLuma</div>
    <h1>The EduLuma Difference</h1>
    <p>Discover why thousands of JEE and NEET aspirants choose EduLuma as their coaching home.</p>
  </div>

  <section class="why-us-section">
    <div class="section-inner">
      <div class="why-grid">
        <div class="why-card"><div class="why-icon">🎓</div><div class="why-content"><h3>IITian & Doctor Faculty</h3><p>Our faculty members are alumni of IITs, NITs and top medical colleges — they've cracked the exams you're preparing for and teach with real insight.</p></div></div>
        <div class="why-card"><div class="why-icon">👥</div><div class="why-content"><h3>Small Batch Sizes (Max 25)</h3><p>We cap every batch at 25 students to ensure individualised attention. No student goes unnoticed at EduLuma.</p></div></div>
        <div class="why-card"><div class="why-icon">📊</div><div class="why-content"><h3>Performance Analytics</h3><p>Detailed weekly performance reports identify strengths, weaknesses and improvement areas — keeping both students and parents informed.</p></div></div>
        <div class="why-card"><div class="why-icon">🔄</div><div class="why-content"><h3>Revision-First Approach</h3><p>We ensure 3+ rounds of complete syllabus revision before your exam — because retention and speed come from repeated practice.</p></div></div>
        <div class="why-card"><div class="why-icon">🖥️</div><div class="why-content"><h3>Hybrid Learning Mode</h3><p>Attend live in class or access recorded lectures on our portal anytime — your preparation never stops even on holidays.</p></div></div>
        <div class="why-card"><div class="why-icon">💰</div><div class="why-content"><h3>Scholarships Available</h3><p>We believe talent should not be limited by finances. Merit-based scholarships of up to 90% are available through our scholarship test.</p></div></div>
        <div class="why-card"><div class="why-icon">🧑‍💼</div><div class="why-content"><h3>Dedicated Mentors</h3><p>Each student is assigned a personal mentor who tracks their academic journey, solves problems and keeps motivation high.</p></div></div>
        <div class="why-card"><div class="why-icon">📚</div><div class="why-content"><h3>Kota-Standard Study Material</h3><p>Our printed modules and DPPs are developed by experienced faculty — comprehensive, updated and aligned to exam patterns.</p></div></div>
      </div>
    </div>
  </section>

  <section class="numbers-section">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label" style="color:var(--gold);justify-content:center;">--</div>
        <h2 class="section-title" style="color:white;">Our Numbers Speak</h2>
      </div>
      <div class="numbers-grid">
        <div class="number-item"><div class="big-num">5000+</div><div class="num-label">Students Trained</div></div>
        <div class="number-item"><div class="big-num">1200+</div><div class="num-label">IIT / NEET Selections</div></div>
        <div class="number-item"><div class="big-num">12+</div><div class="num-label">Years Experience</div></div>
        <div class="number-item"><div class="big-num">95%</div><div class="num-label">Student Satisfaction</div></div>
      </div>
    </div>
  </section>
</div>

<!-- ===================== CURRICULUM PAGE ===================== -->
<div class="page" id="page-curriculum">
  <div class="page-hero">
    <div class="section-label">Curriculum</div>
    <h1>What You Will Learn</h1>
    <p>A comprehensive, exam-aligned curriculum built around the latest JEE and NEET syllabus — no topic left behind.</p>
  </div>

  <section class="curriculum-section">
    <div class="section-inner">
      <div class="curriculum-tabs">
        <button class="curr-tab active" onclick="switchTab('jee-main')">JEE Main</button>
        <button class="curr-tab" onclick="switchTab('jee-adv')">JEE Advanced</button>
        <button class="curr-tab" onclick="switchTab('neet')">NEET UG</button>
        <button class="curr-tab" onclick="switchTab('foundation')">Foundation</button>
      </div>

      <div class="curr-content active" id="curr-jee-main">
        <div class="curr-grid">
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">⚡</span><h3>Physics</h3></div>
            <ul class="subject-topics">
              <li>Mechanics & Laws of Motion</li>
              <li>Work, Energy & Power</li>
              <li>Electrostatics & Magnetism</li>
              <li>Optics & Modern Physics</li>
              <li>Waves & Oscillations</li>
              <li>Thermodynamics</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">🧪</span><h3>Chemistry</h3></div>
            <ul class="subject-topics">
              <li>Physical Chemistry — Mole Concept</li>
              <li>Organic Chemistry — Reactions</li>
              <li>Inorganic — Periodic Table & Bonding</li>
              <li>Electrochemistry & Solutions</li>
              <li>Chemical Kinetics</li>
              <li>Coordination Compounds</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">📐</span><h3>Mathematics</h3></div>
            <ul class="subject-topics">
              <li>Algebra — Quadratics & Sequences</li>
              <li>Calculus — Limits, Derivatives & Integration</li>
              <li>Coordinate Geometry</li>
              <li>Trigonometry</li>
              <li>Probability & Statistics</li>
              <li>Vectors & 3D Geometry</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="curr-content" id="curr-jee-adv">
        <div class="curr-grid">
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">⚡</span><h3>Advanced Physics</h3></div>
            <ul class="subject-topics">
              <li>Rotational Mechanics & Rigid Bodies</li>
              <li>Fluid Mechanics</li>
              <li>Advanced Electromagnetism</li>
              <li>Nuclear Physics & Radioactivity</li>
              <li>Ray & Wave Optics (Advanced)</li>
              <li>Semiconductor Devices</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">🧪</span><h3>Advanced Chemistry</h3></div>
            <ul class="subject-topics">
              <li>Reaction Mechanisms (Advanced Organic)</li>
              <li>Named Reactions & Synthesis</li>
              <li>Transition Metals & Complexes</li>
              <li>Isomerism & Stereochemistry</li>
              <li>Electrochemical Cells</li>
              <li>Qualitative Analysis</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">📐</span><h3>Advanced Mathematics</h3></div>
            <ul class="subject-topics">
              <li>Complex Numbers & Polynomials</li>
              <li>Advanced Integration Techniques</li>
              <li>Differential Equations</li>
              <li>Matrices & Determinants</li>
              <li>Permutations & Combinations</li>
              <li>Conics — Parabola, Ellipse, Hyperbola</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="curr-content" id="curr-neet">
        <div class="curr-grid">
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">🌿</span><h3>Biology</h3></div>
            <ul class="subject-topics">
              <li>Cell Biology & Biomolecules</li>
              <li>Plant Physiology</li>
              <li>Human Physiology</li>
              <li>Genetics & Evolution</li>
              <li>Ecology & Environment</li>
              <li>Biotechnology</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">⚡</span><h3>Physics (NEET)</h3></div>
            <ul class="subject-topics">
              <li>Motion & Laws of Motion</li>
              <li>Work & Energy</li>
              <li>Current Electricity</li>
              <li>Magnetism</li>
              <li>Optics</li>
              <li>Nuclear & Modern Physics</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">🧪</span><h3>Chemistry (NEET)</h3></div>
            <ul class="subject-topics">
              <li>Atomic Structure & Bonding</li>
              <li>States of Matter</li>
              <li>Biomolecules & Polymers</li>
              <li>Organic Chemistry Reactions</li>
              <li>Equilibrium & Thermodynamics</li>
              <li>Environmental Chemistry</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="curr-content" id="curr-foundation">
        <div class="curr-grid">
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">🔢</span><h3>Mathematics</h3></div>
            <ul class="subject-topics">
              <li>Number Systems & Arithmetic</li>
              <li>Algebra — Equations & Polynomials</li>
              <li>Geometry & Mensuration</li>
              <li>Statistics & Probability</li>
              <li>Trigonometry Basics</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">🌍</span><h3>Science</h3></div>
            <ul class="subject-topics">
              <li>Physics — Motion & Forces</li>
              <li>Chemistry — Atoms & Elements</li>
              <li>Biology — Life Processes</li>
              <li>Light, Sound & Electricity</li>
              <li>Natural Resources & Environment</li>
            </ul>
          </div>
          <div class="subject-card">
            <div class="subject-header"><span class="subject-emoji">🏆</span><h3>Olympiad & NTSE</h3></div>
            <ul class="subject-topics">
              <li>Mental Ability & Reasoning</li>
              <li>Quantitative Aptitude</li>
              <li>Science Olympiad Prep</li>
              <li>NTSE MAT & SAT</li>
              <li>Logical & Analytical Thinking</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ===================== PROGRAMMES PAGE ===================== -->
<div class="page" id="page-programmes">
  <div class="page-hero">
    <div class="section-label">Our Programmes</div>
    <h1>Find Your Perfect Programme</h1>
    <p>Whether you're just starting out or going for a second attempt — EduLuma has a programme built for you.</p>
  </div>

  <section class="programmes-section">
    <div class="section-inner">
      <div class="prog-grid">
        <div class="prog-card featured">
          <span class="prog-featured-tag">Most Popular</span>
          <div class="prog-top">
            <h3>🚀 JEE Main + Advanced (2 Year)</h3>
            <p>Complete integrated programme for Class 11 & 12 students targeting IITs and NITs.</p>
          </div>
          <div class="prog-bottom">
            <ul class="prog-features">
              <li>Class 11 + 12 Boards Coverage</li>
              <li>JEE Main & Advanced Full Syllabus</li>
              <li>Daily DPPs + Weekly Chapter Tests</li>
              <li>3 Full Rounds of Revision</li>
              <li>IITian Faculty (All Subjects)</li>
              <li>Printed Study Modules</li>
              <li>Online Portal Access</li>
              <li>Personal Mentor Assigned</li>
            </ul>
            <button class="prog-btn" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'});showPage('home')">Enroll Now →</button>
          </div>
        </div>

        <div class="prog-card">
          <div class="prog-top">
            <h3>🩺 NEET UG (2 Year)</h3>
            <p>Comprehensive NEET preparation for Class 11 & 12 students aspiring for MBBS/BDS.</p>
          </div>
          <div class="prog-bottom">
            <ul class="prog-features">
              <li>Physics, Chemistry & Biology</li>
              <li>NCERT Deep Dive + Advanced Topics</li>
              <li>Doctor-Led Biology Faculty</li>
              <li>Weekly NEET Pattern Tests</li>
              <li>Full Syllabus Revision Cycles</li>
              <li>Printed Study Material</li>
              <li>Online Portal Access</li>
            </ul>
            <button class="prog-btn" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'});showPage('home')">Enroll Now →</button>
          </div>
        </div>

        <div class="prog-card">
          <div class="prog-top">
            <h3>🌱 Foundation (Class 8–10)</h3>
            <p>The smartest head start — build solid Maths and Science fundamentals from Class 8.</p>
          </div>
          <div class="prog-bottom">
            <ul class="prog-features">
              <li>Mathematics & Science Foundation</li>
              <li>NTSE & Olympiad Preparation</li>
              <li>School Board Coverage (CBSE/State)</li>
              <li>Reasoning & Aptitude Training</li>
              <li>Monthly Assessment Tests</li>
              <li>Study Material Provided</li>
            </ul>
            <button class="prog-btn" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'});showPage('home')">Enroll Now →</button>
          </div>
        </div>

        <div class="prog-card">
          <div class="prog-top">
            <h3>🔄 Dropper Batch (1 Year)</h3>
            <p>Intensive programme for repeater students focused on rank improvement and exam mastery.</p>
          </div>
          <div class="prog-bottom">
            <ul class="prog-features">
              <li>Full Syllabus Intensive Revision</li>
              <li>Targeted Weak Area Coaching</li>
              <li>All India Mock Test Series</li>
              <li>Stress Management & Counselling</li>
              <li>Small Batch — Max 20 Students</li>
              <li>1-on-1 Weekly Mentor Sessions</li>
            </ul>
            <button class="prog-btn" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'});showPage('home')">Enroll Now →</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ===================== PRICING PAGE ===================== -->
<div class="page" id="page-pricing">
  <div class="page-hero">
    <div class="section-label">Fees & Pricing</div>
    <h1>Transparent. Affordable. Worth It.</h1>
    <p>No hidden fees. No surprises. Choose a plan that works for your goal and budget.</p>
  </div>

  <section class="pricing-section">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label">Pricing Plans</div>
        <h2 class="section-title">Simple, Transparent Fee Structure</h2>
        <p class="section-subtitle">All plans include study material, tests and portal access. Scholarships available.</p>
      </div>
      <div class="pricing-grid">
        <div class="price-card">
          <div class="price-top">
            <h3>Foundation</h3>
            <div class="subtitle">Class 8–10</div>
            <div class="price-amount"><span>₹</span>45,000</div>
            <div class="price-period">per year (incl. GST)</div>
          </div>
          <ul class="price-features">
            <li>Maths & Science Classes</li>
            <li>NTSE / Olympiad Prep</li>
            <li>Monthly Tests</li>
            <li>Study Material</li>
            <li>Online Portal Access</li>
            <li class="no">Personal Mentor</li>
            <li class="no">All India Test Series</li>
          </ul>
          <div class="price-btn-wrap">
            <button class="price-btn" onclick="showPage('home');setTimeout(()=>document.getElementById('contact').scrollIntoView({behavior:'smooth'}),100)">Get Started</button>
          </div>
        </div>

        <div class="price-card popular">
          <div class="popular-tag">⭐ Most Popular</div>
          <div class="price-top">
            <h3>JEE / NEET Full</h3>
            <div class="subtitle">Class 11–12 (2 Year)</div>
            <div class="price-amount"><span>₹</span>90,000</div>
            <div class="price-period">per year (incl. GST)</div>
          </div>
          <ul class="price-features">
            <li>All 3 Subjects Full Syllabus</li>
            <li>Board Exam Coverage</li>
            <li>Daily DPPs & Tests</li>
            <li>Premium Study Material</li>
            <li>Online + Offline Classes</li>
            <li>Personal Mentor</li>
            <li>All India Mock Test Series</li>
          </ul>
          <div class="price-btn-wrap">
            <button class="price-btn" onclick="showPage('home');setTimeout(()=>document.getElementById('contact').scrollIntoView({behavior:'smooth'}),100)">Enroll Now</button>
          </div>
        </div>

        <div class="price-card">
          <div class="price-top">
            <h3>Dropper Batch</h3>
            <div class="subtitle">Repeater (1 Year)</div>
            <div class="price-amount"><span>₹</span>75,000</div>
            <div class="price-period">per year (incl. GST)</div>
          </div>
          <ul class="price-features">
            <li>Intensive Revision Programme</li>
            <li>Weak Area Targeting</li>
            <li>Daily Tests & DPPs</li>
            <li>Study Material</li>
            <li>Online Portal Access</li>
            <li>Weekly 1-on-1 Mentor</li>
            <li>All India Test Series</li>
          </ul>
          <div class="price-btn-wrap">
            <button class="price-btn" onclick="showPage('home');setTimeout(()=>document.getElementById('contact').scrollIntoView({behavior:'smooth'}),100)">Get Started</button>
          </div>
        </div>
      </div>

      <div style="background:rgba(255,107,0,0.06);border:1.5px solid rgba(255,107,0,0.2);border-radius:20px;padding:28px 32px;margin-top:40px;display:flex;align-items:center;justify-content:space-between;gap:20px;flex-wrap:wrap;">
        <div>
          <div style="font-family:'Sora',sans-serif;font-size:1.1rem;font-weight:700;color:var(--navy);margin-bottom:6px;">🎓 Scholarship Test — Up to 90% Fee Waiver</div>
          <div style="color:var(--gray);font-size:0.9rem;">Every Sunday | Free to appear | Merit-based scholarships for deserving students</div>
        </div>
        <button class="btn-primary" onclick="showPage('home');setTimeout(()=>document.getElementById('contact').scrollIntoView({behavior:'smooth'}),100)">Register for Scholarship Test</button>
      </div>
    </div>
  </section>

  <section class="faq-section">
    <div class="section-inner">
      <div class="text-center">
        <div class="section-label">FAQs</div>
        <h2 class="section-title">Frequently Asked Questions</h2>
      </div>
      <div class="faq-list">
        <div class="faq-item">
          <div class="faq-q" onclick="toggleFaq(this)">Are there any hidden fees beyond the listed fee? <span class="faq-arrow">▾</span></div>
          <div class="faq-a">No. The fee listed covers tuition, printed study material, all tests and portal access. There are no hidden charges. Optional hostel and transport are available at separate cost.</div>
        </div>
        <div class="faq-item">
          <div class="faq-q" onclick="toggleFaq(this)">How can I apply for a scholarship? <span class="faq-arrow">▾</span></div>
          <div class="faq-a">Scholarship tests are held every Sunday at our centre. Register via our enquiry form or call us. Based on your score, you can receive 25%, 50%, 75% or 90% fee waiver.</div>
        </div>
        <div class="faq-item">
          <div class="faq-q" onclick="toggleFaq(this)">Is EMI or instalment payment available? <span class="faq-arrow">▾</span></div>
          <div class="faq-a">Yes. We offer quarterly and half-yearly instalment options. Speak to our admissions counsellor for a payment plan that suits your family.</div>
        </div>
        <div class="faq-item">
          <div class="faq-q" onclick="toggleFaq(this)">What is the refund policy? <span class="faq-arrow">▾</span></div>
          <div class="faq-a">If a student withdraws within the first 15 days of joining, 70% of the fee is refunded after deducting administrative charges. No refund is available after 15 days.</div>
        </div>
        <div class="faq-item">
          <div class="faq-q" onclick="toggleFaq(this)">Can I attend a demo class before enrolling? <span class="faq-arrow">▾</span></div>
          <div class="faq-a">Absolutely! We encourage every student to attend a free demo class before making a decision. Fill the enquiry form or call us to schedule your demo.</div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-top">
      <div class="footer-brand">
        <a class="logo" onclick="showPage('home')">Edu<span>Luma</span></a>
        <p>Illuminating the path to IIT and NEET for thousands of aspirants. Glow with Knowledge.</p>
        <div class="social-links">
          <a class="social-btn" href="#">f</a>
          <a class="social-btn" href="#">in</a>
          <a class="social-btn" href="#">yt</a>
          <a class="social-btn" href="#">ig</a>
        </div>
      </div>
      <div class="footer-col">
        <h4>Pages</h4>
        <ul class="footer-links">
          <li><a onclick="showPage('home')">Home</a></li>
          <li><a onclick="showPage('why-us')">Why Us</a></li>
          <li><a onclick="showPage('curriculum')">Curriculum</a></li>
          <li><a onclick="showPage('programmes')">Programmes</a></li>
          <li><a onclick="showPage('pricing')">Fees</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Courses</h4>
        <ul class="footer-links">
          <li><a onclick="showPage('programmes')">JEE Main</a></li>
          <li><a onclick="showPage('programmes')">JEE Advanced</a></li>
          <li><a onclick="showPage('programmes')">NEET UG</a></li>
          <li><a onclick="showPage('programmes')">Foundation</a></li>
          <li><a onclick="showPage('programmes')">Dropper Batch</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Contact</h4>
        <ul class="footer-links">
          <li><a>📍 Uppal, Hyderabad</a></li>
          <li><a>📞 +91 98765 43210</a></li>
          <li><a>✉️ admissions@eduluma.in</a></li>
          <li><a>🕐 Mon–Sat, 9am–7pm</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2025 EduLuma Institute. All rights reserved.</p>
      <p>Glow with Knowledge 💡</p>
    </div>
  </div>
</footer>

<!-- WhatsApp FAB -->
<a class="whatsapp-fab" href="https://wa.me/919876543210" target="_blank" title="Chat on WhatsApp">💬</a>

<script>
function showPage(name) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
  document.getElementById('page-' + name).classList.add('active');
  const navEl = document.getElementById('nav-' + name);
  if (navEl) navEl.classList.add('active');
  window.scrollTo({ top: 0, behavior: 'smooth' });
  // close mobile nav
  document.getElementById('navLinks').classList.remove('open');
}

function toggleNav() {
  document.getElementById('navLinks').classList.toggle('open');
}

function switchTab(id) {
  document.querySelectorAll('.curr-tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.curr-content').forEach(c => c.classList.remove('active'));
  document.getElementById('curr-' + id).classList.add('active');
  event.target.classList.add('active');
}

function toggleFaq(el) {
  el.closest('.faq-item').classList.toggle('open');
}
</script>
</body>
</html>
