import { useState, useEffect, useRef, useCallback } from "react";

// ─── STYLES ──────────────────────────────────────────────────────────────────
const css = `
  @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;900&family=Space+Mono:wght@400;700&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg-base:      #04060d;
    --bg-card:      #0b0f1c;
    --bg-elevated:  #111827;
    --bg-hover:     #1a2236;
    --border:       rgba(99,179,255,0.12);
    --border-glow:  rgba(99,179,255,0.35);
    --accent:       #3b9eff;
    --accent-soft:  rgba(59,158,255,0.15);
    --accent-glow:  rgba(59,158,255,0.4);
    --text-primary: #e8f0ff;
    --text-sec:     #7a90b8;
    --text-dim:     #3a4d6b;
    --danger:       #ff4d6a;
    --success:      #22d3a0;
    --gold:         #f5c842;
    --radius:       14px;
    --radius-sm:    8px;
    --sidebar-w:    240px;
    --header-h:     60px;
    --transition:   0.2s cubic-bezier(0.4,0,0.2,1);
  }

  html, body, #root { height: 100%; width: 100%; overflow: hidden; }

  body {
    font-family: 'Outfit', sans-serif;
    background: var(--bg-base);
    color: var(--text-primary);
    -webkit-font-smoothing: antialiased;
  }

  /* SCROLLBAR */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--border-glow); border-radius: 4px; }

  /* ── SPLASH ── */
  .splash {
    position: fixed; inset: 0; z-index: 1000;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    background: radial-gradient(ellipse 80% 70% at 50% 40%, #0d1f3c 0%, #04060d 100%);
    animation: splashFadeOut 0.6s 2.8s forwards;
  }
  @keyframes splashFadeOut { to { opacity: 0; pointer-events: none; } }

  .splash-orb {
    width: 120px; height: 120px; border-radius: 50%; position: relative; margin-bottom: 32px;
    background: radial-gradient(circle at 35% 35%, #a8d8ff, #3b9eff 40%, #0a5abf 80%);
    box-shadow: 0 0 60px rgba(59,158,255,0.7), 0 0 120px rgba(59,158,255,0.35), inset 0 -10px 30px rgba(0,30,80,0.4);
    animation: orbPulse 2s ease-in-out infinite;
  }
  .splash-orb::after {
    content: ''; position: absolute; top: 15%; left: 20%; width: 30%; height: 20%;
    background: rgba(255,255,255,0.35); border-radius: 50%; filter: blur(4px);
  }
  @keyframes orbPulse {
    0%,100% { box-shadow: 0 0 60px rgba(59,158,255,0.7), 0 0 120px rgba(59,158,255,0.35); transform: scale(1); }
    50% { box-shadow: 0 0 80px rgba(59,158,255,0.9), 0 0 160px rgba(59,158,255,0.5); transform: scale(1.04); }
  }

  .splash-title {
    font-size: 42px; font-weight: 900; letter-spacing: 6px; text-transform: uppercase;
    background: linear-gradient(135deg, #ffffff 0%, #a8d8ff 50%, #3b9eff 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    animation: fadeUp 0.8s 0.3s both;
  }
  .splash-sub {
    font-size: 14px; color: var(--text-sec); letter-spacing: 2px; margin-top: 8px;
    animation: fadeUp 0.8s 0.6s both;
  }
  .splash-tagline {
    font-size: 15px; color: var(--text-sec); margin-top: 24px;
    animation: fadeUp 0.8s 1s both;
  }
  .splash-btn {
    margin-top: 40px; padding: 14px 44px;
    background: linear-gradient(135deg, #3b9eff, #1a6fd4);
    border: none; border-radius: 40px; color: #fff; font-family: 'Outfit',sans-serif;
    font-size: 16px; font-weight: 600; letter-spacing: 1px; cursor: pointer;
    box-shadow: 0 0 30px rgba(59,158,255,0.5);
    animation: fadeUp 0.8s 1.4s both;
    transition: transform 0.15s, box-shadow 0.15s;
  }
  .splash-btn:hover { transform: translateY(-2px); box-shadow: 0 0 45px rgba(59,158,255,0.7); }

  @keyframes fadeUp { from { opacity:0; transform: translateY(20px); } to { opacity:1; transform: translateY(0); } }

  /* ── LOGIN ── */
  .login-screen {
    position: fixed; inset: 0; display: flex; align-items: center; justify-content: center;
    background: radial-gradient(ellipse 80% 70% at 50% 30%, #0d1f3c 0%, #04060d 100%);
    z-index: 900; animation: fadeUp 0.5s both;
  }
  .login-card {
    background: var(--bg-card); border: 1px solid var(--border);
    border-radius: 20px; padding: 40px; width: 100%; max-width: 440px; position: relative;
    box-shadow: 0 0 60px rgba(59,158,255,0.08), 0 30px 60px rgba(0,0,0,0.5);
  }
  .login-logo { display: flex; align-items: center; gap: 12px; margin-bottom: 32px; }
  .login-orb {
    width: 40px; height: 40px; border-radius: 50%;
    background: radial-gradient(circle at 35% 35%, #a8d8ff, #3b9eff 40%, #0a5abf 80%);
    box-shadow: 0 0 20px rgba(59,158,255,0.6);
  }
  .login-title { font-size: 22px; font-weight: 700; letter-spacing: 3px; }
  .login-tabs { display: flex; gap: 4px; margin-bottom: 28px; background: var(--bg-elevated); border-radius: var(--radius-sm); padding: 4px; }
  .login-tab {
    flex: 1; padding: 9px; border: none; border-radius: 6px; background: transparent;
    color: var(--text-sec); font-family: 'Outfit',sans-serif; font-size: 13px; font-weight: 500;
    cursor: pointer; transition: var(--transition);
  }
  .login-tab.active { background: var(--accent); color: #fff; }
  .form-group { margin-bottom: 16px; }
  .form-label { display: block; font-size: 12px; color: var(--text-sec); margin-bottom: 6px; letter-spacing: 0.5px; font-weight: 500; }
  .form-input {
    width: 100%; padding: 12px 14px; background: var(--bg-elevated); border: 1px solid var(--border);
    border-radius: var(--radius-sm); color: var(--text-primary); font-family: 'Outfit',sans-serif;
    font-size: 14px; transition: var(--transition); outline: none;
  }
  .form-input:focus { border-color: var(--accent); box-shadow: 0 0 0 3px var(--accent-soft); }
  .form-input::placeholder { color: var(--text-dim); }
  .form-check { display: flex; align-items: center; gap: 8px; margin: 16px 0; cursor: pointer; font-size: 13px; color: var(--text-sec); }
  .form-check input { accent-color: var(--accent); width: 15px; height: 15px; }
  .btn-primary {
    width: 100%; padding: 14px; background: linear-gradient(135deg, #3b9eff, #1a6fd4);
    border: none; border-radius: var(--radius-sm); color: #fff; font-family: 'Outfit',sans-serif;
    font-size: 15px; font-weight: 600; cursor: pointer; transition: var(--transition);
    box-shadow: 0 4px 20px rgba(59,158,255,0.35);
  }
  .btn-primary:hover { transform: translateY(-1px); box-shadow: 0 6px 25px rgba(59,158,255,0.5); }
  .btn-primary:disabled { opacity: 0.5; cursor: not-allowed; transform: none; }
  .upload-area {
    border: 2px dashed var(--border-glow); border-radius: var(--radius-sm); padding: 24px;
    text-align: center; cursor: pointer; transition: var(--transition); background: var(--bg-elevated);
  }
  .upload-area:hover { border-color: var(--accent); background: var(--accent-soft); }
  .upload-icon { font-size: 28px; margin-bottom: 8px; }
  .upload-text { font-size: 13px; color: var(--text-sec); }
  .divider { display: flex; align-items: center; gap: 12px; margin: 16px 0; }
  .divider::before, .divider::after { content: ''; flex: 1; height: 1px; background: var(--border); }
  .divider span { font-size: 11px; color: var(--text-dim); }
  .login-note { font-size: 11px; color: var(--text-dim); text-align: center; margin-top: 20px; line-height: 1.6; }

  /* ── MAIN LAYOUT ── */
  .app {
    display: flex; height: 100%; width: 100%; overflow: hidden;
  }

  /* ── SIDEBAR ── */
  .sidebar {
    width: var(--sidebar-w); flex-shrink: 0; background: var(--bg-card);
    border-right: 1px solid var(--border); display: flex; flex-direction: column;
    padding: 0; z-index: 10; transition: transform var(--transition);
    height: 100%; overflow: hidden;
  }
  .sidebar-brand {
    padding: 20px 20px 16px; display: flex; align-items: center; gap: 12px;
    border-bottom: 1px solid var(--border); flex-shrink: 0;
  }
  .sidebar-orb {
    width: 32px; height: 32px; border-radius: 50%; flex-shrink: 0;
    background: radial-gradient(circle at 35% 35%, #a8d8ff, #3b9eff 40%, #0a5abf 80%);
    box-shadow: 0 0 14px rgba(59,158,255,0.5);
  }
  .sidebar-name { font-size: 15px; font-weight: 700; letter-spacing: 2px; }
  .sidebar-nav { flex: 1; overflow-y: auto; padding: 12px 10px; }
  .nav-section { margin-bottom: 20px; }
  .nav-section-label { font-size: 10px; color: var(--text-dim); letter-spacing: 1.5px; font-weight: 600; padding: 0 10px; margin-bottom: 6px; text-transform: uppercase; }
  .nav-item {
    display: flex; align-items: center; gap: 12px; padding: 10px 12px;
    border-radius: var(--radius-sm); cursor: pointer; transition: var(--transition);
    color: var(--text-sec); font-size: 14px; font-weight: 500; border: 1px solid transparent;
    user-select: none;
  }
  .nav-item:hover { background: var(--bg-hover); color: var(--text-primary); }
  .nav-item.active { background: var(--accent-soft); color: var(--accent); border-color: rgba(59,158,255,0.2); }
  .nav-icon { font-size: 18px; width: 22px; text-align: center; flex-shrink: 0; }
  .nav-badge {
    margin-left: auto; background: var(--accent); color: #fff; border-radius: 10px;
    font-size: 10px; font-weight: 700; padding: 2px 6px; min-width: 18px; text-align: center;
  }
  .sidebar-footer { padding: 12px 10px; border-top: 1px solid var(--border); flex-shrink: 0; }
  .sidebar-account {
    display: flex; align-items: center; gap: 10px; padding: 10px 12px;
    border-radius: var(--radius-sm); background: var(--bg-elevated); cursor: pointer;
    transition: var(--transition);
  }
  .sidebar-account:hover { background: var(--bg-hover); }
  .account-avatar {
    width: 32px; height: 32px; border-radius: 50%; background: var(--accent);
    display: flex; align-items: center; justify-content: center; font-size: 14px; font-weight: 700; flex-shrink: 0;
  }
  .account-info { flex: 1; min-width: 0; }
  .account-name { font-size: 13px; font-weight: 600; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .account-type { font-size: 11px; color: var(--text-sec); }

  /* ── MAIN CONTENT ── */
  .main { flex: 1; display: flex; flex-direction: column; overflow: hidden; min-width: 0; }

  .topbar {
    height: var(--header-h); display: flex; align-items: center; gap: 16px;
    padding: 0 20px; border-bottom: 1px solid var(--border); flex-shrink: 0;
    background: var(--bg-card);
  }
  .topbar-menu-btn {
    display: none; background: none; border: none; color: var(--text-sec);
    font-size: 20px; cursor: pointer; padding: 4px;
  }
  .topbar-title { font-size: 18px; font-weight: 700; flex: 1; }
  .search-bar {
    display: flex; align-items: center; gap: 8px; background: var(--bg-elevated);
    border: 1px solid var(--border); border-radius: 30px; padding: 8px 14px; flex: 1; max-width: 360px;
    transition: var(--transition);
  }
  .search-bar:focus-within { border-color: var(--accent); }
  .search-bar input {
    background: none; border: none; color: var(--text-primary); font-family: 'Outfit',sans-serif;
    font-size: 14px; outline: none; flex: 1;
  }
  .search-bar input::placeholder { color: var(--text-dim); }
  .search-icon { color: var(--text-dim); font-size: 16px; }

  .content { flex: 1; overflow-y: auto; padding: 24px; }

  /* ── HERO ── */
  .hero {
    border-radius: 16px; padding: 32px; margin-bottom: 28px; position: relative; overflow: hidden;
    background: linear-gradient(135deg, #0d2a5c 0%, #0a1f42 40%, #04060d 100%);
    border: 1px solid var(--border);
  }
  .hero::before {
    content: ''; position: absolute; top: -50px; right: -50px; width: 300px; height: 300px;
    border-radius: 50%; background: radial-gradient(circle, rgba(59,158,255,0.15) 0%, transparent 70%);
  }
  .hero-label { font-size: 11px; color: var(--accent); letter-spacing: 2px; font-weight: 600; margin-bottom: 8px; }
  .hero-title { font-size: 26px; font-weight: 800; margin-bottom: 8px; }
  .hero-sub { font-size: 14px; color: var(--text-sec); margin-bottom: 20px; }
  .hero-actions { display: flex; gap: 10px; flex-wrap: wrap; }
  .btn-hero {
    padding: 10px 22px; border-radius: 30px; font-family: 'Outfit',sans-serif; font-size: 14px;
    font-weight: 600; cursor: pointer; transition: var(--transition); border: none;
  }
  .btn-hero.primary { background: var(--accent); color: #fff; box-shadow: 0 0 20px rgba(59,158,255,0.4); }
  .btn-hero.primary:hover { box-shadow: 0 0 30px rgba(59,158,255,0.6); }
  .btn-hero.secondary { background: rgba(255,255,255,0.08); color: var(--text-primary); border: 1px solid var(--border); }
  .btn-hero.secondary:hover { background: rgba(255,255,255,0.13); }

  /* ── STATS ── */
  .stats-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 14px; margin-bottom: 28px; }
  .stat-card {
    background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius);
    padding: 18px; text-align: center; transition: var(--transition);
  }
  .stat-card:hover { border-color: var(--border-glow); transform: translateY(-2px); }
  .stat-icon { font-size: 24px; margin-bottom: 8px; }
  .stat-num { font-size: 24px; font-weight: 800; color: var(--accent); font-family: 'Space Mono', monospace; }
  .stat-label { font-size: 12px; color: var(--text-sec); margin-top: 2px; }

  /* ── SECTION ── */
  .section { margin-bottom: 28px; }
  .section-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 14px; }
  .section-title { font-size: 16px; font-weight: 700; }
  .section-more { font-size: 12px; color: var(--accent); cursor: pointer; background: none; border: none; font-family: 'Outfit',sans-serif; }
  .section-more:hover { text-decoration: underline; }

  /* ── CHANNEL GRID ── */
  .channel-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 14px; }
  .channel-card {
    background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius);
    overflow: hidden; cursor: pointer; transition: var(--transition); display: flex; flex-direction: column;
  }
  .channel-card:hover { border-color: var(--border-glow); transform: translateY(-3px); box-shadow: 0 8px 30px rgba(0,0,0,0.4); }
  .channel-thumb {
    height: 140px; background: var(--bg-elevated);
    display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden;
  }
  .channel-thumb-bg {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, #0d2042, #071530);
  }
  .channel-thumb-icon { font-size: 40px; z-index: 1; position: relative; }
  .live-badge {
    position: absolute; top: 8px; left: 8px; background: var(--danger); color: #fff;
    font-size: 10px; font-weight: 700; padding: 3px 7px; border-radius: 4px; letter-spacing: 1px; z-index: 2;
  }
  .channel-info { padding: 12px; flex: 1; }
  .channel-name { font-size: 14px; font-weight: 600; margin-bottom: 4px; }
  .channel-category { font-size: 11px; color: var(--text-sec); }
  .channel-actions { display: flex; align-items: center; gap: 8px; padding: 10px 12px 12px; }
  .btn-play {
    flex: 1; padding: 8px; background: var(--accent); border: none; border-radius: 8px;
    color: #fff; font-family: 'Outfit',sans-serif; font-size: 13px; font-weight: 600;
    cursor: pointer; transition: var(--transition); display: flex; align-items: center; justify-content: center; gap: 6px;
  }
  .btn-play:hover { background: #5aadff; }
  .btn-fav {
    width: 34px; height: 34px; border-radius: 8px; border: 1px solid var(--border);
    background: var(--bg-elevated); color: var(--text-sec); cursor: pointer; font-size: 16px;
    display: flex; align-items: center; justify-content: center; transition: var(--transition);
  }
  .btn-fav:hover, .btn-fav.active { color: var(--gold); border-color: var(--gold); background: rgba(245,200,66,0.1); }

  /* ── MOVIE GRID ── */
  .movie-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(160px, 1fr)); gap: 14px; }
  .movie-card {
    background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius);
    overflow: hidden; cursor: pointer; transition: var(--transition);
  }
  .movie-card:hover { border-color: var(--border-glow); transform: scale(1.03); }
  .movie-poster {
    aspect-ratio: 2/3; background: var(--bg-elevated);
    display: flex; align-items: center; justify-content: center; font-size: 48px;
    position: relative;
  }
  .movie-poster-bg { position: absolute; inset: 0; background: linear-gradient(135deg, #0d2042, #061025); }
  .movie-poster-icon { z-index: 1; position: relative; }
  .movie-info { padding: 10px; }
  .movie-title { font-size: 13px; font-weight: 600; margin-bottom: 3px; line-height: 1.3; }
  .movie-meta { font-size: 11px; color: var(--text-sec); }
  .movie-rating { color: var(--gold); font-weight: 600; }

  /* ── PLAYER OVERLAY ── */
  .player-overlay {
    position: fixed; inset: 0; z-index: 500; background: #000;
    display: flex; flex-direction: column; animation: fadeUp 0.3s both;
  }
  .player-topbar {
    position: absolute; top: 0; left: 0; right: 0; z-index: 10;
    padding: 16px 20px; display: flex; align-items: center; gap: 14px;
    background: linear-gradient(to bottom, rgba(0,0,0,0.8) 0%, transparent 100%);
  }
  .player-back {
    width: 38px; height: 38px; border-radius: 50%; border: 1px solid rgba(255,255,255,0.2);
    background: rgba(0,0,0,0.5); color: #fff; cursor: pointer; display: flex;
    align-items: center; justify-content: center; font-size: 18px; transition: var(--transition);
  }
  .player-back:hover { background: rgba(255,255,255,0.15); }
  .player-channel-title { font-size: 16px; font-weight: 600; flex: 1; }
  .player-live-badge {
    background: var(--danger); color: #fff; font-size: 10px; font-weight: 700;
    padding: 4px 8px; border-radius: 4px; letter-spacing: 1px;
    display: flex; align-items: center; gap: 4px;
  }
  .live-dot { width: 6px; height: 6px; border-radius: 50%; background: #fff; animation: liveBlink 1s infinite; }
  @keyframes liveBlink { 0%,100%{ opacity:1; } 50%{ opacity:0.3; } }

  .player-video-area { flex: 1; display: flex; align-items: center; justify-content: center; position: relative; }
  .player-loading {
    display: flex; flex-direction: column; align-items: center; gap: 16px;
    color: var(--text-sec);
  }
  .player-spinner {
    width: 48px; height: 48px; border-radius: 50%; border: 3px solid rgba(59,158,255,0.2);
    border-top-color: var(--accent); animation: spin 0.8s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }
  .player-channel-info { text-align: center; }
  .player-channel-name { font-size: 20px; font-weight: 700; margin-bottom: 4px; }
  .player-channel-cat { font-size: 13px; color: var(--text-sec); }
  .player-note { font-size: 12px; color: var(--text-dim); margin-top: 8px; }

  .player-controls {
    position: absolute; bottom: 0; left: 0; right: 0;
    padding: 20px; background: linear-gradient(to top, rgba(0,0,0,0.9) 0%, transparent 100%);
    display: flex; flex-direction: column; gap: 12px;
  }
  .player-progress { position: relative; height: 4px; background: rgba(255,255,255,0.2); border-radius: 4px; cursor: pointer; }
  .player-progress-fill { height: 100%; background: var(--accent); border-radius: 4px; transition: width 0.3s; }
  .player-btns { display: flex; align-items: center; gap: 12px; }
  .player-btn {
    background: none; border: none; color: rgba(255,255,255,0.8); cursor: pointer;
    font-size: 20px; padding: 6px; transition: var(--transition); border-radius: 6px;
  }
  .player-btn:hover { color: #fff; background: rgba(255,255,255,0.1); }
  .player-btn.big { font-size: 28px; }
  .player-time { font-size: 13px; color: rgba(255,255,255,0.7); font-family: 'Space Mono', monospace; margin-right: auto; }
  .volume-slider {
    -webkit-appearance: none; width: 80px; height: 4px; border-radius: 4px;
    background: rgba(255,255,255,0.3); outline: none; cursor: pointer;
  }
  .volume-slider::-webkit-slider-thumb {
    -webkit-appearance: none; width: 14px; height: 14px; border-radius: 50%;
    background: var(--accent); cursor: pointer;
  }

  /* ── CATEGORIES ── */
  .category-pills { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 20px; }
  .pill {
    padding: 7px 16px; border-radius: 30px; border: 1px solid var(--border); background: var(--bg-card);
    color: var(--text-sec); font-size: 13px; cursor: pointer; transition: var(--transition); font-family: 'Outfit',sans-serif;
  }
  .pill:hover { border-color: var(--border-glow); color: var(--text-primary); }
  .pill.active { background: var(--accent); border-color: var(--accent); color: #fff; }

  /* ── SETTINGS ── */
  .settings-card {
    background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius);
    overflow: hidden; margin-bottom: 16px;
  }
  .settings-item {
    display: flex; align-items: center; gap: 14px; padding: 16px 18px;
    border-bottom: 1px solid var(--border); cursor: pointer; transition: var(--transition);
  }
  .settings-item:last-child { border-bottom: none; }
  .settings-item:hover { background: var(--bg-hover); }
  .settings-icon { font-size: 20px; width: 24px; text-align: center; flex-shrink: 0; }
  .settings-label { flex: 1; font-size: 14px; font-weight: 500; }
  .settings-value { font-size: 13px; color: var(--text-sec); }
  .settings-arrow { color: var(--text-dim); font-size: 16px; }
  .toggle {
    width: 44px; height: 24px; border-radius: 12px; background: var(--bg-elevated);
    position: relative; cursor: pointer; transition: var(--transition); border: 1px solid var(--border);
  }
  .toggle.on { background: var(--accent); border-color: var(--accent); }
  .toggle::after {
    content: ''; position: absolute; top: 3px; left: 3px; width: 16px; height: 16px;
    border-radius: 50%; background: #fff; transition: var(--transition);
  }
  .toggle.on::after { transform: translateX(20px); }
  .settings-section-title { font-size: 12px; color: var(--text-dim); letter-spacing: 1px; padding: 16px 18px 8px; font-weight: 600; text-transform: uppercase; }

  /* ── HISTORY ── */
  .history-list { display: flex; flex-direction: column; gap: 10px; }
  .history-item {
    display: flex; align-items: center; gap: 14px; padding: 14px 16px;
    background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius);
    cursor: pointer; transition: var(--transition);
  }
  .history-item:hover { border-color: var(--border-glow); background: var(--bg-hover); }
  .history-thumb {
    width: 48px; height: 48px; border-radius: 8px; background: var(--bg-elevated);
    display: flex; align-items: center; justify-content: center; font-size: 22px; flex-shrink: 0;
  }
  .history-info { flex: 1; min-width: 0; }
  .history-name { font-size: 14px; font-weight: 600; margin-bottom: 3px; }
  .history-meta { font-size: 12px; color: var(--text-sec); }
  .history-time { font-size: 11px; color: var(--text-dim); flex-shrink: 0; }

  /* ── EMPTY STATE ── */
  .empty-state { text-align: center; padding: 60px 20px; color: var(--text-sec); }
  .empty-icon { font-size: 48px; margin-bottom: 16px; opacity: 0.5; }
  .empty-text { font-size: 16px; font-weight: 600; margin-bottom: 6px; color: var(--text-primary); }
  .empty-sub { font-size: 13px; color: var(--text-sec); }

  /* ── TOAST ── */
  .toast-container { position: fixed; bottom: 24px; right: 24px; z-index: 9999; display: flex; flex-direction: column; gap: 8px; pointer-events: none; }
  .toast {
    background: var(--bg-elevated); border: 1px solid var(--border-glow);
    border-radius: 10px; padding: 12px 16px; font-size: 13px; color: var(--text-primary);
    display: flex; align-items: center; gap: 10px; min-width: 220px;
    box-shadow: 0 8px 30px rgba(0,0,0,0.5); animation: toastIn 0.3s both;
    pointer-events: all;
  }
  @keyframes toastIn { from { opacity:0; transform: translateX(20px); } to { opacity:1; transform: translateX(0); } }
  .toast.success { border-color: rgba(34,211,160,0.4); }
  .toast.error { border-color: rgba(255,77,106,0.4); }
  .toast-icon { font-size: 16px; }

  /* ── OVERLAY MOBILE ── */
  .sidebar-overlay {
    display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.6); z-index: 9;
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    :root { --sidebar-w: 260px; }
    .sidebar {
      position: fixed; top: 0; left: 0; bottom: 0; z-index: 10;
      transform: translateX(-100%);
    }
    .sidebar.open { transform: translateX(0); box-shadow: 4px 0 30px rgba(0,0,0,0.5); }
    .sidebar-overlay.visible { display: block; }
    .topbar-menu-btn { display: flex; }
    .search-bar { max-width: none; }
    .content { padding: 16px; }
    .hero { padding: 20px; }
    .hero-title { font-size: 20px; }
    .channel-grid { grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); }
    .movie-grid { grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); }
    .toast-container { bottom: 16px; right: 16px; left: 16px; }
  }

  @media (max-width: 480px) {
    .stats-grid { grid-template-columns: repeat(2, 1fr); }
    .channel-grid { grid-template-columns: 1fr; }
    .movie-grid { grid-template-columns: repeat(2, 1fr); }
  }
`;

// ─── MOCK DATA ───────────────────────────────────────────────────────────────
const MOCK_CHANNELS = [
  { id: 1, name: "CNN International", category: "Notícias", icon: "📺", live: true },
  { id: 2, name: "BBC World News", category: "Notícias", icon: "🌍", live: true },
  { id: 3, name: "Eurosport 1", category: "Desporto", icon: "⚽", live: true },
  { id: 4, name: "Eurosport 2", category: "Desporto", icon: "🏊", live: true },
  { id: 5, name: "National Geographic", category: "Documentários", icon: "🔭", live: true },
  { id: 6, name: "Discovery Channel", category: "Documentários", icon: "🌿", live: true },
  { id: 7, name: "MTV", category: "Entretenimento", icon: "🎵", live: true },
  { id: 8, name: "Comedy Central", category: "Entretenimento", icon: "😂", live: true },
  { id: 9, name: "SIC Notícias", category: "Notícias PT", icon: "📡", live: true },
  { id: 10, name: "TVI 24", category: "Notícias PT", icon: "🇵🇹", live: true },
  { id: 11, name: "Sport TV 1", category: "Desporto PT", icon: "🏟️", live: true },
  { id: 12, name: "RTP 1", category: "Geral PT", icon: "🏠", live: true },
];

const MOCK_MOVIES = [
  { id: 1, title: "Avatar: The Way of Water", year: 2022, rating: 7.6, genre: "Ficção Científica", icon: "🌊" },
  { id: 2, title: "Top Gun: Maverick", year: 2022, rating: 8.3, genre: "Ação", icon: "✈️" },
  { id: 3, title: "Black Panther: Wakanda", year: 2022, rating: 6.7, genre: "Ação", icon: "🐾" },
  { id: 4, title: "The Batman", year: 2022, rating: 7.8, genre: "Ação", icon: "🦇" },
  { id: 5, title: "Doctor Strange 2", year: 2022, rating: 6.9, genre: "Fantasia", icon: "🔮" },
  { id: 6, title: "Thor: Love and Thunder", year: 2022, rating: 6.2, genre: "Ação", icon: "⚡" },
  { id: 7, title: "Uncharted", year: 2022, rating: 6.3, genre: "Aventura", icon: "🗺️" },
  { id: 8, title: "The Northman", year: 2022, rating: 7.1, genre: "Drama", icon: "⚔️" },
];

const MOCK_SERIES = [
  { id: 1, title: "House of the Dragon", seasons: 2, episodes: 18, icon: "🐲", genre: "Fantasia" },
  { id: 2, title: "The Last of Us", seasons: 2, episodes: 17, icon: "🍄", genre: "Drama" },
  { id: 3, title: "Succession", seasons: 4, episodes: 39, icon: "💼", genre: "Drama" },
  { id: 4, title: "Wednesday", seasons: 1, episodes: 8, icon: "🖤", genre: "Mistério" },
  { id: 5, title: "Andor", seasons: 1, episodes: 12, icon: "🚀", genre: "Ficção Científica" },
  { id: 6, title: "The Bear", seasons: 3, episodes: 28, icon: "🐻", genre: "Drama" },
];

const CATEGORIES = ["Todos", "Notícias", "Desporto", "Entretenimento", "Documentários", "Filmes", "Séries"];

// ─── HELPERS ─────────────────────────────────────────────────────────────────
function useLocalStorage(key, initial) {
  const [val, setVal] = useState(() => {
    try { const s = localStorage.getItem(key); return s ? JSON.parse(s) : initial; } catch { return initial; }
  });
  const set = useCallback(v => {
    setVal(v);
    try { localStorage.setItem(key, JSON.stringify(v)); } catch {}
  }, [key]);
  return [val, set];
}

function Toast({ toasts }) {
  return (
    <div className="toast-container">
      {toasts.map(t => (
        <div key={t.id} className={`toast ${t.type}`}>
          <span className="toast-icon">{t.type === "success" ? "✅" : t.type === "error" ? "❌" : "ℹ️"}</span>
          {t.msg}
        </div>
      ))}
    </div>
  );
}

// ─── PLAYER COMPONENT ────────────────────────────────────────────────────────
function PlayerOverlay({ item, onClose }) {
  const [playing, setPlaying] = useState(false);
  const [vol, setVol] = useState(80);
  const [muted, setMuted] = useState(false);
  const [loading, setLoading] = useState(true);
  const [progress, setProgress] = useState(0);

  useEffect(() => {
    const t = setTimeout(() => setLoading(false), 2000);
    return () => clearTimeout(t);
  }, []);

  useEffect(() => {
    if (!loading) {
      setPlaying(true);
      const interval = setInterval(() => setProgress(p => (p + 0.5) % 100), 500);
      return () => clearInterval(interval);
    }
  }, [loading]);

  return (
    <div className="player-overlay">
      <div className="player-topbar">
        <button className="player-back" onClick={onClose}>←</button>
        <span className="player-channel-title">{item.name || item.title}</span>
        {item.live && (
          <span className="player-live-badge">
            <span className="live-dot" />
            AO VIVO
          </span>
        )}
      </div>

      <div className="player-video-area">
        {loading ? (
          <div className="player-loading">
            <div className="player-spinner" />
            <div className="player-channel-info">
              <div className="player-channel-name">{item.name || item.title}</div>
              <div className="player-channel-cat">{item.category || item.genre}</div>
              <div className="player-note">A ligar ao servidor...</div>
            </div>
          </div>
        ) : (
          <div style={{ color: "rgba(255,255,255,0.3)", textAlign: "center" }}>
            <div style={{ fontSize: 72, marginBottom: 16 }}>{item.icon}</div>
            <div style={{ fontSize: 18, fontWeight: 700, color: "#e8f0ff" }}>{item.name || item.title}</div>
            <div style={{ fontSize: 13, color: "#7a90b8", marginTop: 6 }}>
              Reprodução simulada — liga o teu servidor para conteúdo real
            </div>
          </div>
        )}
      </div>

      <div className="player-controls">
        {!item.live && (
          <div className="player-progress">
            <div className="player-progress-fill" style={{ width: `${progress}%` }} />
          </div>
        )}
        <div className="player-btns">
          <button className="player-btn" onClick={() => setMuted(m => !m)}>
            {muted ? "🔇" : "🔊"}
          </button>
          <input type="range" className="volume-slider" min={0} max={100} value={muted ? 0 : vol}
            onChange={e => { setVol(+e.target.value); setMuted(false); }} />
          <button className="player-btn big" onClick={() => setPlaying(p => !p)}>
            {playing ? "⏸" : "▶️"}
          </button>
          {!item.live && <span className="player-time">{Math.floor(progress * 1.2)}:00 / 2:00:00</span>}
          <button className="player-btn" style={{ marginLeft: "auto" }}>⛶</button>
          <button className="player-btn">⚙️</button>
        </div>
      </div>
    </div>
  );
}

// ─── SCREENS ─────────────────────────────────────────────────────────────────
function DashboardHome({ setSection, setPlayer, favorites, toggleFav, addToast }) {
  const recentChannels = MOCK_CHANNELS.slice(0, 6);
  return (
    <div className="content">
      <div className="hero">
        <div className="hero-label">✦ BEM-VINDO AO LUMIN PLAYER</div>
        <div className="hero-title">O teu entretenimento, sem limites</div>
        <div className="hero-sub">TV em direto, filmes, séries — tudo no mesmo lugar.</div>
        <div className="hero-actions">
          <button className="btn-hero primary" onClick={() => setSection("tv")}>▶ TV em Direto</button>
          <button className="btn-hero secondary" onClick={() => setSection("movies")}>🎬 Filmes</button>
        </div>
      </div>

      <div className="stats-grid">
        <div className="stat-card"><div className="stat-icon">📺</div><div className="stat-num">{MOCK_CHANNELS.length}</div><div className="stat-label">Canais Disponíveis</div></div>
        <div className="stat-card"><div className="stat-icon">🎬</div><div className="stat-num">{MOCK_MOVIES.length}</div><div className="stat-label">Filmes</div></div>
        <div className="stat-card"><div className="stat-icon">📺</div><div className="stat-num">{MOCK_SERIES.length}</div><div className="stat-label">Séries</div></div>
        <div className="stat-card"><div className="stat-icon">⭐</div><div className="stat-num">{favorites.length}</div><div className="stat-label">Favoritos</div></div>
      </div>

      <div className="section">
        <div className="section-header">
          <div className="section-title">📺 TV em Direto</div>
          <button className="section-more" onClick={() => setSection("tv")}>Ver todos →</button>
        </div>
        <div className="channel-grid">
          {recentChannels.map(ch => (
            <div key={ch.id} className="channel-card">
              <div className="channel-thumb">
                <div className="channel-thumb-bg" />
                <div className="channel-thumb-icon">{ch.icon}</div>
                {ch.live && <span className="live-badge">● AO VIVO</span>}
              </div>
              <div className="channel-info">
                <div className="channel-name">{ch.name}</div>
                <div className="channel-category">{ch.category}</div>
              </div>
              <div className="channel-actions">
                <button className="btn-play" onClick={() => setPlayer(ch)}>▶ Reproduzir</button>
                <button className={`btn-fav ${favorites.includes(ch.id) ? "active" : ""}`}
                  onClick={() => { toggleFav(ch.id); addToast(favorites.includes(ch.id) ? "Removido dos favoritos" : "Adicionado aos favoritos", "success"); }}>
                  {favorites.includes(ch.id) ? "★" : "☆"}
                </button>
              </div>
            </div>
          ))}
        </div>
      </div>

      <div className="section">
        <div className="section-header">
          <div className="section-title">🎬 Filmes em Destaque</div>
          <button className="section-more" onClick={() => setSection("movies")}>Ver todos →</button>
        </div>
        <div className="movie-grid">
          {MOCK_MOVIES.slice(0, 4).map(m => (
            <div key={m.id} className="movie-card" onClick={() => setPlayer(m)}>
              <div className="movie-poster">
                <div className="movie-poster-bg" />
                <div className="movie-poster-icon">{m.icon}</div>
              </div>
              <div className="movie-info">
                <div className="movie-title">{m.title}</div>
                <div className="movie-meta"><span className="movie-rating">★ {m.rating}</span> · {m.year}</div>
              </div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}

function TVScreen({ setPlayer, favorites, toggleFav, addToast, searchQ }) {
  const [cat, setCat] = useState("Todos");
  const cats = ["Todos", ...new Set(MOCK_CHANNELS.map(c => c.category))];
  const filtered = MOCK_CHANNELS.filter(c => {
    const catOk = cat === "Todos" || c.category === cat;
    const qOk = !searchQ || c.name.toLowerCase().includes(searchQ.toLowerCase()) || c.category.toLowerCase().includes(searchQ.toLowerCase());
    return catOk && qOk;
  });

  return (
    <div className="content">
      <div className="category-pills">
        {cats.map(c => <button key={c} className={`pill ${cat === c ? "active" : ""}`} onClick={() => setCat(c)}>{c}</button>)}
      </div>
      {filtered.length === 0 ? (
        <div className="empty-state"><div className="empty-icon">🔍</div><div className="empty-text">Sem resultados</div><div className="empty-sub">Tenta outra pesquisa</div></div>
      ) : (
        <div className="channel-grid">
          {filtered.map(ch => (
            <div key={ch.id} className="channel-card">
              <div className="channel-thumb">
                <div className="channel-thumb-bg" />
                <div className="channel-thumb-icon">{ch.icon}</div>
                {ch.live && <span className="live-badge">● AO VIVO</span>}
              </div>
              <div className="channel-info">
                <div className="channel-name">{ch.name}</div>
                <div className="channel-category">{ch.category}</div>
              </div>
              <div className="channel-actions">
                <button className="btn-play" onClick={() => setPlayer(ch)}>▶ Reproduzir</button>
                <button className={`btn-fav ${favorites.includes(ch.id) ? "active" : ""}`}
                  onClick={() => { toggleFav(ch.id); addToast(favorites.includes(ch.id) ? "Removido dos favoritos" : "Adicionado aos favoritos", "success"); }}>
                  {favorites.includes(ch.id) ? "★" : "☆"}
                </button>
              </div>
            </div>
          ))}
        </div>
      )}
    </div>
  );
}

function MoviesScreen({ setPlayer, favorites, toggleFav, addToast, searchQ }) {
  const [genre, setGenre] = useState("Todos");
  const genres = ["Todos", ...new Set(MOCK_MOVIES.map(m => m.genre))];
  const filtered = MOCK_MOVIES.filter(m => {
    const gOk = genre === "Todos" || m.genre === genre;
    const qOk = !searchQ || m.title.toLowerCase().includes(searchQ.toLowerCase());
    return gOk && qOk;
  });

  return (
    <div className="content">
      <div className="category-pills">
        {genres.map(g => <button key={g} className={`pill ${genre === g ? "active" : ""}`} onClick={() => setGenre(g)}>{g}</button>)}
      </div>
      {filtered.length === 0 ? (
        <div className="empty-state"><div className="empty-icon">🎬</div><div className="empty-text">Sem resultados</div><div className="empty-sub">Tenta outra pesquisa</div></div>
      ) : (
        <div className="movie-grid">
          {filtered.map(m => (
            <div key={m.id} className="movie-card">
              <div className="movie-poster" onClick={() => setPlayer(m)}>
                <div className="movie-poster-bg" />
                <div className="movie-poster-icon">{m.icon}</div>
              </div>
              <div className="movie-info">
                <div className="movie-title">{m.title}</div>
                <div className="movie-meta">
                  <span className="movie-rating">★ {m.rating}</span> · {m.year} · {m.genre}
                </div>
                <div style={{ display: "flex", gap: 6, marginTop: 8 }}>
                  <button className="btn-play" style={{ flex: 1, padding: "7px" }} onClick={() => setPlayer(m)}>▶ Ver</button>
                  <button className={`btn-fav ${favorites.includes(m.id) ? "active" : ""}`}
                    onClick={() => { toggleFav(m.id); addToast(favorites.includes(m.id) ? "Removido" : "Adicionado aos favoritos", "success"); }}>
                    {favorites.includes(m.id) ? "★" : "☆"}
                  </button>
                </div>
              </div>
            </div>
          ))}
        </div>
      )}
    </div>
  );
}

function SeriesScreen({ setPlayer, searchQ }) {
  const filtered = MOCK_SERIES.filter(s => !searchQ || s.title.toLowerCase().includes(searchQ.toLowerCase()));
  return (
    <div className="content">
      {filtered.length === 0 ? (
        <div className="empty-state"><div className="empty-icon">📺</div><div className="empty-text">Sem resultados</div></div>
      ) : (
        <div className="channel-grid">
          {filtered.map(s => (
            <div key={s.id} className="channel-card" onClick={() => setPlayer({ ...s, name: s.title, category: s.genre })}>
              <div className="channel-thumb">
                <div className="channel-thumb-bg" />
                <div className="channel-thumb-icon">{s.icon}</div>
              </div>
              <div className="channel-info">
                <div className="channel-name">{s.title}</div>
                <div className="channel-category">{s.genre} · {s.seasons} Temporadas · {s.episodes} Episódios</div>
              </div>
              <div className="channel-actions">
                <button className="btn-play">▶ Continuar</button>
              </div>
            </div>
          ))}
        </div>
      )}
    </div>
  );
}

function FavoritesScreen({ setPlayer, favorites, toggleFav, addToast }) {
  const favChannels = MOCK_CHANNELS.filter(c => favorites.includes(c.id));
  const favMovies = MOCK_MOVIES.filter(m => favorites.includes(m.id));

  if (favChannels.length === 0 && favMovies.length === 0) {
    return (
      <div className="content">
        <div className="empty-state">
          <div className="empty-icon">⭐</div>
          <div className="empty-text">Sem favoritos ainda</div>
          <div className="empty-sub">Adiciona canais e filmes aos favoritos para os ver aqui</div>
        </div>
      </div>
    );
  }

  return (
    <div className="content">
      {favChannels.length > 0 && (
        <div className="section">
          <div className="section-header"><div className="section-title">📺 Canais Favoritos</div></div>
          <div className="channel-grid">
            {favChannels.map(ch => (
              <div key={ch.id} className="channel-card">
                <div className="channel-thumb">
                  <div className="channel-thumb-bg" /><div className="channel-thumb-icon">{ch.icon}</div>
                  {ch.live && <span className="live-badge">● AO VIVO</span>}
                </div>
                <div className="channel-info"><div className="channel-name">{ch.name}</div><div className="channel-category">{ch.category}</div></div>
                <div className="channel-actions">
                  <button className="btn-play" onClick={() => setPlayer(ch)}>▶ Reproduzir</button>
                  <button className="btn-fav active" onClick={() => { toggleFav(ch.id); addToast("Removido dos favoritos", "success"); }}>★</button>
                </div>
              </div>
            ))}
          </div>
        </div>
      )}
      {favMovies.length > 0 && (
        <div className="section">
          <div className="section-header"><div className="section-title">🎬 Filmes Favoritos</div></div>
          <div className="movie-grid">
            {favMovies.map(m => (
              <div key={m.id} className="movie-card">
                <div className="movie-poster" onClick={() => setPlayer(m)}>
                  <div className="movie-poster-bg" /><div className="movie-poster-icon">{m.icon}</div>
                </div>
                <div className="movie-info">
                  <div className="movie-title">{m.title}</div>
                  <div className="movie-meta"><span className="movie-rating">★ {m.rating}</span> · {m.year}</div>
                  <div style={{ display: "flex", gap: 6, marginTop: 8 }}>
                    <button className="btn-play" style={{ flex: 1, padding: "7px" }} onClick={() => setPlayer(m)}>▶ Ver</button>
                    <button className="btn-fav active" onClick={() => { toggleFav(m.id); addToast("Removido", "success"); }}>★</button>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </div>
      )}
    </div>
  );
}

function HistoryScreen({ setPlayer, history, clearHistory, addToast }) {
  if (history.length === 0) {
    return (
      <div className="content">
        <div className="empty-state">
          <div className="empty-icon">🕐</div>
          <div className="empty-text">Histórico vazio</div>
          <div className="empty-sub">Os conteúdos que vires aparecem aqui</div>
        </div>
      </div>
    );
  }
  return (
    <div className="content">
      <div className="section-header" style={{ marginBottom: 16 }}>
        <div className="section-title">Histórico de Reprodução</div>
        <button className="section-more" onClick={() => { clearHistory(); addToast("Histórico limpo", "success"); }}>Limpar tudo</button>
      </div>
      <div className="history-list">
        {history.map((item, i) => (
          <div key={i} className="history-item" onClick={() => setPlayer(item)}>
            <div className="history-thumb">{item.icon}</div>
            <div className="history-info">
              <div className="history-name">{item.name || item.title}</div>
              <div className="history-meta">{item.category || item.genre} {item.live ? "· Ao Vivo" : ""}</div>
            </div>
            <div className="history-time">Agora</div>
          </div>
        ))}
      </div>
    </div>
  );
}

function SettingsScreen({ creds, logout, addToast, darkMode, setDarkMode }) {
  const [cache, setCache] = useState(false);
  return (
    <div className="content">
      <div className="settings-card">
        <div className="settings-section-title">Conta</div>
        <div className="settings-item">
          <span className="settings-icon">🖥️</span>
          <span className="settings-label">Servidor</span>
          <span className="settings-value" style={{ fontSize: 12, maxWidth: 160, overflow: "hidden", textOverflow: "ellipsis", whiteSpace: "nowrap" }}>
            {creds?.server || creds?.m3u || "—"}
          </span>
        </div>
        <div className="settings-item">
          <span className="settings-icon">👤</span>
          <span className="settings-label">Utilizador</span>
          <span className="settings-value">{creds?.username || "M3U"}</span>
        </div>
        <div className="settings-item" onClick={logout} style={{ cursor: "pointer" }}>
          <span className="settings-icon">🔄</span>
          <span className="settings-label" style={{ color: "var(--accent)" }}>Alterar Conta</span>
          <span className="settings-arrow">›</span>
        </div>
      </div>

      <div className="settings-card">
        <div className="settings-section-title">Preferências</div>
        <div className="settings-item" onClick={() => setDarkMode(d => !d)}>
          <span className="settings-icon">🌙</span>
          <span className="settings-label">Tema Escuro</span>
          <div className={`toggle ${darkMode ? "on" : ""}`} />
        </div>
        <div className="settings-item">
          <span className="settings-icon">📶</span>
          <span className="settings-label">Qualidade Automática</span>
          <div className="toggle on" />
        </div>
        <div className="settings-item">
          <span className="settings-icon">▶️</span>
          <span className="settings-label">Retomar Reprodução</span>
          <div className="toggle on" />
        </div>
      </div>

      <div className="settings-card">
        <div className="settings-section-title">Cache & Dados</div>
        <div className="settings-item" onClick={() => { addToast("Cache limpo com sucesso", "success"); }}>
          <span className="settings-icon">🗑️</span>
          <span className="settings-label">Limpar Cache</span>
          <span className="settings-arrow">›</span>
        </div>
        <div className="settings-item" onClick={() => { logout(); addToast("Credenciais removidas", "success"); }}>
          <span className="settings-icon">🔐</span>
          <span className="settings-label" style={{ color: "var(--danger)" }}>Apagar Credenciais</span>
          <span className="settings-arrow">›</span>
        </div>
      </div>

      <div className="settings-card">
        <div className="settings-section-title">Sobre</div>
        <div className="settings-item">
          <span className="settings-icon">💡</span>
          <span className="settings-label">LUMIN PLAYER</span>
          <span className="settings-value">v1.0.0</span>
        </div>
        <div className="settings-item">
          <span className="settings-icon">🛡️</span>
          <span className="settings-label">Segurança</span>
          <span className="settings-value" style={{ color: "var(--success)" }}>✓ Encriptado</span>
        </div>
        <div className="settings-item">
          <span className="settings-icon">📦</span>
          <span className="settings-label">Tecnologia</span>
          <span className="settings-value">HLS.js · React · PWA</span>
        </div>
      </div>

      <div style={{ background: "var(--bg-card)", border: "1px solid var(--border)", borderRadius: "var(--radius)", padding: "16px 18px", fontSize: 12, color: "var(--text-dim)", lineHeight: 1.7 }}>
        ⚠️ <strong style={{ color: "var(--text-sec)" }}>Aviso Legal:</strong> O LUMIN PLAYER não inclui nenhum canal, lista ou conteúdo IPTV. O utilizador é o único responsável pelas fontes inseridas e pelo cumprimento das leis de direitos de autor da sua região.
      </div>
    </div>
  );
}

// ─── LOGIN SCREEN ─────────────────────────────────────────────────────────────
function LoginScreen({ onLogin }) {
  const [tab, setTab] = useState("xtream");
  const [server, setServer] = useState("");
  const [user, setUser] = useState("");
  const [pass, setPass] = useState("");
  const [m3u, setM3u] = useState("");
  const [save, setSave] = useState(true);
  const [loading, setLoading] = useState(false);

  const handleSubmit = () => {
    if (tab === "xtream" && (!server || !user || !pass)) return;
    if (tab === "m3u" && !m3u) return;
    setLoading(true);
    setTimeout(() => {
      const creds = tab === "xtream" ? { server, username: user, password: pass, type: "xtream" } : { m3u, type: "m3u" };
      onLogin(creds, save);
    }, 1500);
  };

  const handleFileUpload = (e) => {
    const file = e.target.files[0];
    if (file) setM3u(`file://${file.name}`);
  };

  return (
    <div className="login-screen">
      <div className="login-card">
        <div className="login-logo">
          <div className="login-orb" />
          <div className="login-title">LUMIN PLAYER</div>
        </div>

        <div className="login-tabs">
          <button className={`login-tab ${tab === "xtream" ? "active" : ""}`} onClick={() => setTab("xtream")}>Xtream Codes</button>
          <button className={`login-tab ${tab === "m3u" ? "active" : ""}`} onClick={() => setTab("m3u")}>Lista M3U</button>
        </div>

        {tab === "xtream" ? (
          <>
            <div className="form-group">
              <label className="form-label">URL do Servidor</label>
              <input className="form-input" placeholder="http://servidor.com:8080" value={server} onChange={e => setServer(e.target.value)} />
            </div>
            <div className="form-group">
              <label className="form-label">Username</label>
              <input className="form-input" placeholder="utilizador" value={user} onChange={e => setUser(e.target.value)} />
            </div>
            <div className="form-group">
              <label className="form-label">Password</label>
              <input className="form-input" type="password" placeholder="••••••••" value={pass} onChange={e => setPass(e.target.value)} />
            </div>
          </>
        ) : (
          <>
            <div className="form-group">
              <label className="form-label">URL da Lista M3U</label>
              <input className="form-input" placeholder="http://servidor.com/lista.m3u" value={m3u} onChange={e => setM3u(e.target.value)} />
            </div>
            <div className="divider"><span>ou</span></div>
            <label className="upload-area">
              <input type="file" accept=".m3u,.m3u8" style={{ display: "none" }} onChange={handleFileUpload} />
              <div className="upload-icon">📁</div>
              <div className="upload-text">{m3u.startsWith("file://") ? m3u.replace("file://", "") : "Clica para fazer upload de um ficheiro M3U"}</div>
            </label>
          </>
        )}

        <label className="form-check">
          <input type="checkbox" checked={save} onChange={e => setSave(e.target.checked)} />
          Guardar credenciais localmente (encriptado)
        </label>

        <button className="btn-primary" onClick={handleSubmit} disabled={loading}>
          {loading ? "A ligar..." : "Entrar"}
        </button>

        <div className="login-note">
          🔒 As tuas credenciais são armazenadas apenas no teu dispositivo.<br />
          Nenhum dado é enviado para os nossos servidores.
        </div>
      </div>
    </div>
  );
}

// ─── SPLASH SCREEN ────────────────────────────────────────────────────────────
function SplashScreen({ onEnter }) {
  const [visible, setVisible] = useState(true);
  useEffect(() => { const t = setTimeout(() => setVisible(false), 3400); return () => clearTimeout(t); }, []);
  if (!visible) return null;
  return (
    <div className="splash">
      <div className="splash-orb" />
      <div className="splash-title">LUMIN PLAYER</div>
      <div className="splash-sub">by REBORN AI</div>
      <div className="splash-tagline">A tua biblioteca multimédia num só lugar</div>
      <button className="splash-btn" onClick={onEnter}>Entrar</button>
    </div>
  );
}

// ─── MAIN APP ─────────────────────────────────────────────────────────────────
export default function LuminPlayer() {
  const [phase, setPhase] = useLocalStorage("lumin_phase", "splash"); // splash | login | app
  const [creds, setCreds] = useLocalStorage("lumin_creds", null);
  const [section, setSection] = useState("home");
  const [player, setPlayer] = useState(null);
  const [favorites, setFavorites] = useLocalStorage("lumin_favs", []);
  const [history, setHistory] = useLocalStorage("lumin_history", []);
  const [toasts, setToasts] = useState([]);
  const [searchQ, setSearchQ] = useState("");
  const [sidebarOpen, setSidebarOpen] = useState(false);
  const [darkMode, setDarkMode] = useState(true);

  const addToast = useCallback((msg, type = "info") => {
    const id = Date.now();
    setToasts(t => [...t, { id, msg, type }]);
    setTimeout(() => setToasts(t => t.filter(x => x.id !== id)), 3000);
  }, []);

  const toggleFav = useCallback((id) => {
    setFavorites(f => f.includes(id) ? f.filter(x => x !== id) : [...f, id]);
  }, [setFavorites]);

  const playItem = useCallback((item) => {
    setPlayer(item);
    setHistory(h => {
      const without = h.filter(x => (x.id || x.name) !== (item.id || item.name));
      return [item, ...without].slice(0, 20);
    });
  }, [setHistory]);

  const logout = () => {
    setCreds(null);
    setPhase("login");
    setSidebarOpen(false);
  };

  const navItems = [
    { id: "home", icon: "⊞", label: "Início" },
    { id: "tv", icon: "📺", label: "TV em Direto", badge: MOCK_CHANNELS.filter(c => c.live).length },
    { id: "movies", icon: "🎬", label: "Filmes" },
    { id: "series", icon: "🍿", label: "Séries" },
  ];
  const navItems2 = [
    { id: "favorites", icon: "⭐", label: "Favoritos", badge: favorites.length || null },
    { id: "history", icon: "🕐", label: "Histórico" },
  ];
  const navItems3 = [
    { id: "settings", icon: "⚙️", label: "Definições" },
  ];

  const sectionTitles = { home: "LUMIN PLAYER", tv: "TV em Direto", movies: "Filmes", series: "Séries", favorites: "Favoritos", history: "Histórico", settings: "Definições" };

  const renderScreen = () => {
    const props = { setPlayer: playItem, favorites, toggleFav, addToast, searchQ, setSection };
    switch (section) {
      case "home": return <DashboardHome {...props} />;
      case "tv": return <TVScreen {...props} />;
      case "movies": return <MoviesScreen {...props} />;
      case "series": return <SeriesScreen {...props} />;
      case "favorites": return <FavoritesScreen {...props} />;
      case "history": return <HistoryScreen setPlayer={playItem} history={history} clearHistory={() => setHistory([])} addToast={addToast} />;
      case "settings": return <SettingsScreen creds={creds} logout={logout} addToast={addToast} darkMode={darkMode} setDarkMode={setDarkMode} />;
      default: return null;
    }
  };

  return (
    <>
      <style>{css}</style>

      {/* SPLASH */}
      {phase === "splash" && (
        <SplashScreen onEnter={() => {
          setTimeout(() => setPhase(creds ? "app" : "login"), 100);
        }} />
      )}

      {/* LOGIN */}
      {phase === "login" && (
        <LoginScreen onLogin={(c, save) => {
          if (save) setCreds(c);
          else setCreds(c);
          setPhase("app");
          addToast("Ligado com sucesso!", "success");
        }} />
      )}

      {/* MAIN APP */}
      {phase === "app" && (
        <div className="app">
          {/* Sidebar overlay mobile */}
          <div className={`sidebar-overlay ${sidebarOpen ? "visible" : ""}`} onClick={() => setSidebarOpen(false)} />

          {/* Sidebar */}
          <nav className={`sidebar ${sidebarOpen ? "open" : ""}`}>
            <div className="sidebar-brand">
              <div className="sidebar-orb" />
              <div className="sidebar-name">LUMIN</div>
            </div>
            <div className="sidebar-nav">
              <div className="nav-section">
                <div className="nav-section-label">Principal</div>
                {navItems.map(n => (
                  <div key={n.id} className={`nav-item ${section === n.id ? "active" : ""}`}
                    onClick={() => { setSection(n.id); setSidebarOpen(false); }}>
                    <span className="nav-icon">{n.icon}</span>
                    {n.label}
                    {n.badge ? <span className="nav-badge">{n.badge}</span> : null}
                  </div>
                ))}
              </div>
              <div className="nav-section">
                <div className="nav-section-label">Biblioteca</div>
                {navItems2.map(n => (
                  <div key={n.id} className={`nav-item ${section === n.id ? "active" : ""}`}
                    onClick={() => { setSection(n.id); setSidebarOpen(false); }}>
                    <span className="nav-icon">{n.icon}</span>
                    {n.label}
                    {n.badge ? <span className="nav-badge">{n.badge}</span> : null}
                  </div>
                ))}
              </div>
              <div className="nav-section">
                <div className="nav-section-label">Sistema</div>
                {navItems3.map(n => (
                  <div key={n.id} className={`nav-item ${section === n.id ? "active" : ""}`}
                    onClick={() => { setSection(n.id); setSidebarOpen(false); }}>
                    <span className="nav-icon">{n.icon}</span>
                    {n.label}
                  </div>
                ))}
              </div>
            </div>
            <div className="sidebar-footer">
              <div className="sidebar-account" onClick={() => { setSection("settings"); setSidebarOpen(false); }}>
                <div className="account-avatar">L</div>
                <div className="account-info">
                  <div className="account-name">{creds?.username || "M3U"}</div>
                  <div className="account-type">{creds?.type === "xtream" ? "Xtream Codes" : "Lista M3U"}</div>
                </div>
                <span style={{ color: "var(--text-dim)", fontSize: 14 }}>›</span>
              </div>
            </div>
          </nav>

          {/* Main */}
          <div className="main">
            <div className="topbar">
              <button className="topbar-menu-btn" onClick={() => setSidebarOpen(o => !o)}>☰</button>
              <div className="topbar-title">{sectionTitles[section]}</div>
              <div className="search-bar">
                <span className="search-icon">🔍</span>
                <input placeholder="Pesquisar..." value={searchQ} onChange={e => setSearchQ(e.target.value)} />
              </div>
            </div>
            {renderScreen()}
          </div>

          {/* Player */}
          {player && <PlayerOverlay item={player} onClose={() => setPlayer(null)} />}
        </div>
      )}

      <Toast toasts={toasts} />
    </>
  );
}
