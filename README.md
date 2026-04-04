<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tiên Giới: Khởi Nguyên — Wiki</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+SC:wght@400;500;600;700&family=Ma+Shan+Zheng&family=Mulish:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --bg:        #F0EAE0;
  --bg-panel:  #E5DDD1;
  --bg-card:   #FAF5EE;
  --bg-card2:  #F2EBE0;
  --border:    #C8B89A;
  --border-2:  #B0976E;
  --accent:    #7A4E2A;
  --accent2:   #9B6235;
  --accent3:   #3E6B55;
  --gold:      #6B4E1C;
  --gold2:     #9E7B3F;
  --gold3:     #C4963A;
  --red:       #A03030;
  --green:     #2E6644;
  --blue:      #2A5070;
  --purple:    #5A3880;
  --text:      #2A1A08;
  --text-2:    #4A3418;
  --text-3:    #7A6040;
  --text-4:    #A8906A;
  --shadow-sm: 0 1px 4px rgba(60,30,10,.10);
  --shadow:    0 4px 18px rgba(60,30,10,.15);
  --shadow-lg: 0 8px 32px rgba(60,30,10,.20);
  --radius:    4px;
  --radius-lg: 8px;
  --sidebar-w: 236px;
  --pattern-color: rgba(100,60,20,.045);
}
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }
body {
  font-family: 'Mulish', 'Noto Serif SC', sans-serif;
  background: var(--bg);
  background-image:
    repeating-linear-gradient(0deg, var(--pattern-color) 0px, var(--pattern-color) 1px, transparent 1px, transparent 40px),
    repeating-linear-gradient(90deg, var(--pattern-color) 0px, var(--pattern-color) 1px, transparent 1px, transparent 40px);
  color: var(--text);
  min-height: 100vh;
  font-size: 14px;
  line-height: 1.6;
}
::-webkit-scrollbar { width: 5px; height: 5px; }
::-webkit-scrollbar-track { background: var(--bg-panel); }
::-webkit-scrollbar-thumb { background: var(--border-2); border-radius: 2px; }

/* ===== DECORATIVE PATTERNS ===== */
.jade-border {
  border: 1px solid var(--border);
  position: relative;
}
.jade-border::before, .jade-border::after {
  content: '';
  position: absolute;
  width: 8px; height: 8px;
  border-color: var(--gold3);
  border-style: solid;
}
.jade-border::before { top: -1px; left: -1px; border-width: 2px 0 0 2px; }
.jade-border::after  { bottom: -1px; right: -1px; border-width: 0 2px 2px 0; }

.section-ornament {
  display: flex; align-items: center; gap: 10px; margin-bottom: 14px;
}
.section-ornament::before, .section-ornament::after {
  content: '';
  flex: 1; height: 1px;
  background: linear-gradient(90deg, transparent, var(--border-2), transparent);
}

/* ===== SIDEBAR ===== */
#sidebar {
  position: fixed; left:0; top:0; width: var(--sidebar-w); height:100vh;
  background: var(--bg-panel);
  border-right: 1px solid var(--border);
  display: flex; flex-direction: column;
  z-index: 100;
}
#sidebar::after {
  content: '';
  position: absolute;
  top: 0; right: -1px; width: 3px; height: 100%;
  background: repeating-linear-gradient(180deg, var(--gold3) 0px, var(--gold3) 3px, transparent 3px, transparent 14px);
  opacity: .25;
}
.sidebar-logo {
  padding: 22px 18px 16px;
  border-bottom: 1px solid var(--border);
  background: var(--bg-card2);
  text-align: center;
}
.sidebar-logo-title {
  font-family: 'Noto Serif SC', 'Ma Shan Zheng', serif;
  font-size: 19px; font-weight: 700;
  color: var(--gold); line-height: 1.3;
  letter-spacing: 2px;
}
.sidebar-logo-deco {
  display: flex; align-items: center; justify-content: center; gap: 6px;
  margin: 6px 0 4px;
}
.sidebar-logo-deco span { width: 24px; height: 1px; background: var(--border-2); }
.sidebar-logo-sub {
  font-size: 10px; color: var(--text-3);
  letter-spacing: 3px; text-transform: uppercase;
  font-weight: 600;
}
nav { flex:1; overflow-y:auto; padding: 8px 0; }
.nav-section {
  padding: 12px 16px 3px;
  font-size: 9px; color: var(--text-4);
  text-transform: uppercase; letter-spacing: 3px; font-weight: 700;
  display: flex; align-items: center; gap: 6px;
}
.nav-section::after { content:''; flex:1; height:1px; background:var(--border); }
.nav-item {
  display: flex; align-items: center; gap: 8px;
  padding: 7px 18px; cursor: pointer;
  font-size: 12.5px; color: var(--text-2); font-weight: 500;
  transition: all .18s; position: relative;
  border-left: 2px solid transparent;
}
.nav-item:hover { color: var(--accent); background: rgba(122,78,42,.07); border-left-color: rgba(122,78,42,.4); }
.nav-item.active { color: var(--accent); background: rgba(122,78,42,.12); border-left-color: var(--accent); font-weight: 700; }
.sidebar-footer { padding: 12px 14px; border-top: 1px solid var(--border); display:flex; flex-direction:column; gap:7px; }
#editModeBtn {
  width:100%; padding: 8px 12px;
  border: 1px solid var(--border-2); background: var(--bg-card);
  color: var(--text-2); border-radius: var(--radius);
  cursor: pointer; font-size: 12px; font-family: 'Mulish', sans-serif;
  display: flex; align-items: center; justify-content: center; gap: 8px;
  transition: all .2s; font-weight: 600;
}
#editModeBtn:hover { border-color: var(--accent); color: var(--accent); }
#editModeBtn.active { background: var(--accent); color: #f5e8d5; border-color: var(--accent); }
.edit-dot { width:6px; height:6px; border-radius:50%; background: var(--text-4); flex-shrink:0; }
#editModeBtn.active .edit-dot { background: #ffd580; box-shadow: 0 0 5px #ffd580; }
#exportBtn2 {
  width:100%; padding: 6px 12px;
  border: 1px solid var(--border); background: transparent;
  color: var(--text-3); border-radius: var(--radius);
  cursor: pointer; font-size: 11px; font-family: 'Mulish', sans-serif;
  transition: all .2s; font-weight: 600;
}
#exportBtn2:hover { color: var(--gold); border-color: var(--gold); }

/* ===== MAIN ===== */
#main { margin-left: var(--sidebar-w); min-height: 100vh; }
#topbar {
  position: sticky; top:0; z-index:50;
  background: rgba(240,234,224,.93); backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--border);
  padding: 11px 30px; display: flex; align-items: center; justify-content: space-between;
}
.topbar-title {
  font-family: 'Noto Serif SC', serif;
  font-size: 15px; font-weight: 600; color: var(--gold); letter-spacing: 2px;
}
.topbar-deco { display: flex; gap: 4px; align-items: center; }
.topbar-deco span { width: 4px; height: 4px; background: var(--gold3); opacity: .5; transform: rotate(45deg); }

/* ===== PAGES ===== */
.page { display:none; padding: 28px 32px; }
.page.active { display:block; }
.page-header { margin-bottom: 24px; }
.page-title {
  font-family: 'Noto Serif SC', serif;
  font-size: 26px; font-weight: 700; color: var(--gold);
  letter-spacing: 2px;
}
.page-desc { color: var(--text-3); margin-top: 4px; font-size: 12px; }
.divider-title {
  display: flex; align-items: center; gap: 10px; margin: 6px 0 10px;
}
.divider-title::before { content: ''; width: 3px; height: 20px; background: var(--gold3); }
.divider-title::after {
  content: ''; flex:1; height:1px;
  background: linear-gradient(90deg, var(--border-2), transparent);
}

/* ===== CARDS ===== */
.cards-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(148px, 1fr)); gap: 12px; margin-bottom: 18px; }
.char-card {
  background: var(--bg-card); border: 1px solid var(--border);
  cursor: pointer; transition: all .22s; position: relative; overflow: hidden;
}
.char-card::before {
  content: ''; position: absolute; top:0; left:0; right:0;
  height: 2px; background: linear-gradient(90deg, var(--gold3), var(--accent3), var(--gold3));
  opacity: 0; transition: opacity .2s;
}
.char-card:hover { border-color: var(--accent2); transform: translateY(-3px); box-shadow: var(--shadow); }
.char-card:hover::before { opacity: 1; }
.char-card-img {
  height: 128px; background: var(--bg-card2);
  display: flex; align-items: center; justify-content: center;
  overflow: hidden; position: relative;
}
.char-card-img img { width:100%; height:100%; object-fit:cover; }
.char-card-img .placeholder-text { font-size:11px; color:var(--text-4); font-style:italic; }
.char-rarity-bar { height: 2px; }
.rarity-5 { background: linear-gradient(90deg, #9B6B1A, #D4A82A, #9B6B1A); }
.rarity-4 { background: linear-gradient(90deg, #7056a8, #9b7de8, #7056a8); }
.rarity-3 { background: linear-gradient(90deg, #3868a8, #6899d8, #3868a8); }
.char-card-info { padding: 8px 10px; }
.char-card-name { font-size: 13px; font-weight: 700; color: var(--text); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; font-family: 'Noto Serif SC', serif; }
.char-card-meta { display: flex; align-items: center; gap: 5px; margin-top: 4px; flex-wrap: wrap; }
.char-element-tag {
  font-size: 10px; padding: 1px 7px; border-radius: 2px;
  border: 1px solid var(--border); color: var(--text-2); font-weight: 600;
  background: var(--bg-panel);
}
.char-stars { font-size: 10px; color: #9B6B1A; }
.char-stars.s4 { color: #6B4A9E; }

/* ===== FILTER BAR ===== */
.filter-bar { display:flex; gap:7px; flex-wrap:wrap; margin-bottom:16px; align-items:center; }
.filter-btn {
  padding: 5px 12px; background: var(--bg-card);
  border: 1px solid var(--border); color: var(--text-2);
  border-radius: 2px; cursor: pointer; font-size: 12px;
  font-family: 'Mulish', sans-serif; font-weight: 600;
  transition: all .18s;
}
.filter-btn:hover, .filter-btn.active { background: var(--accent); border-color: var(--accent); color: #f5e8d5; }
.search-box {
  padding: 6px 12px; background: var(--bg-card); border: 1px solid var(--border);
  color: var(--text); border-radius: 2px; font-size: 12px;
  font-family: 'Mulish', sans-serif; outline: none; min-width: 200px;
  transition: border-color .2s;
}
.search-box:focus { border-color: var(--accent); }
.search-box::placeholder { color: var(--text-4); }
.view-toggle { display:flex; gap:3px; }
.view-btn {
  padding: 5px 12px; background: var(--bg-card);
  border: 1px solid var(--border); color: var(--text-3);
  border-radius: 2px; cursor: pointer; font-size: 12px;
  font-family: 'Mulish', sans-serif; font-weight: 600; transition: all .18s;
}
.view-btn.active { background: var(--accent); border-color: var(--accent); color: #f5e8d5; }

/* ===== ADD BUTTON ===== */
.add-btn {
  display: inline-flex; align-items: center; gap: 5px;
  padding: 7px 16px; background: var(--accent); color: #f5e8d5;
  border: none; border-radius: var(--radius); cursor: pointer;
  font-size: 12px; font-family: 'Mulish', sans-serif; font-weight: 600;
  transition: all .2s; margin-bottom: 16px; box-shadow: var(--shadow-sm);
}
.add-btn:hover { background: var(--accent2); box-shadow: var(--shadow); }
.add-btn.hidden { display: none; }

/* ===== TABLE ===== */
.data-table { width:100%; border-collapse:collapse; background: var(--bg-card); overflow:hidden; box-shadow: var(--shadow-sm); border: 1px solid var(--border); }
.data-table th { text-align:left; padding:9px 12px; font-size:10px; color:var(--text-3); text-transform:uppercase; letter-spacing:1.5px; background:var(--bg-panel); border-bottom:1px solid var(--border); font-weight:700; }
.data-table td { padding:9px 12px; font-size:12.5px; border-bottom:1px solid var(--border); color:var(--text); }
.data-table tr:last-child td { border-bottom:none; }
.data-table tr:hover td { background: var(--bg-card2); cursor:pointer; }

/* ===== DETAIL PANEL ===== */
#detailOverlay { display:none; position:fixed; inset:0; z-index:200; background:rgba(30,18,5,.45); backdrop-filter:blur(3px); }
#detailPanel {
  display:none; position:fixed; top:0; right:0; height:100vh; width:680px;
  background: var(--bg); border-left: 2px solid var(--border);
  overflow-y:auto; z-index:201; box-shadow: var(--shadow-lg);
  animation: slideIn .3s ease;
}
#detailPanel::before {
  content: '';
  position: absolute; top:0; left:0; width:100%; height:100%;
  background-image:
    repeating-linear-gradient(0deg, var(--pattern-color) 0px, var(--pattern-color) 1px, transparent 1px, transparent 40px),
    repeating-linear-gradient(90deg, var(--pattern-color) 0px, var(--pattern-color) 1px, transparent 1px, transparent 40px);
  pointer-events: none; z-index:-1;
}
@keyframes slideIn { from{transform:translateX(30px);opacity:0} to{transform:translateX(0);opacity:1} }
.detail-close {
  position: sticky; top:0;
  background: rgba(240,234,224,.95); backdrop-filter:blur(8px);
  padding: 12px 20px; display:flex; align-items:center; justify-content:space-between;
  border-bottom: 1px solid var(--border); z-index:10;
}
.detail-close-title { font-family:'Noto Serif SC',serif; font-size:15px; color:var(--gold); font-weight:700; letter-spacing:1px; }
.detail-close-actions { display:flex; gap:7px; }
.close-btn {
  width:28px; height:28px; border-radius:2px;
  background:var(--bg-card); border:1px solid var(--border);
  color:var(--text-3); cursor:pointer; display:flex; align-items:center; justify-content:center;
  font-size:13px; transition:all .2s;
}
.close-btn:hover { border-color: var(--red); color:var(--red); }
.detail-content { padding: 20px 24px; }

/* ===== SECTION CARDS ===== */
.section-card {
  background: var(--bg-card); border: 1px solid var(--border);
  padding: 16px 18px; margin-bottom: 12px;
  position: relative;
}
.section-card::before, .section-card::after {
  content: ''; position:absolute; width:8px; height:8px;
  border-color: var(--gold3); border-style: solid;
}
.section-card::before { top:-1px; left:-1px; border-width:2px 0 0 2px; }
.section-card::after  { bottom:-1px; right:-1px; border-width:0 2px 2px 0; }

.section-title {
  font-family: 'Noto Serif SC', serif;
  font-size: 11px; font-weight: 700; text-transform: uppercase;
  letter-spacing: 3px; color: var(--accent); margin-bottom: 14px;
  padding-bottom: 8px; border-bottom: 1px solid var(--border);
  display: flex; align-items: center; gap: 8px;
}
.section-title::before {
  content: ''; display:inline-block; width:3px; height:14px;
  background: var(--gold3); flex-shrink:0;
}

.field-grid { display:grid; grid-template-columns:1fr 1fr; gap:10px; }
.field-grid.cols3 { grid-template-columns:1fr 1fr 1fr; }
.field-item { display:flex; flex-direction:column; gap:2px; }
.field-label { font-size:9px; color:var(--text-4); text-transform:uppercase; letter-spacing:1.5px; font-weight:700; }
.field-value { font-size:12.5px; color:var(--text); line-height:1.6; }
.field-value.empty { color:var(--text-4); font-style:italic; }
.field-full { margin-bottom:10px; }
.field-full:last-child { margin-bottom:0; }

.stat-row { display:flex; align-items:center; justify-content:space-between; padding:6px 0; border-bottom:1px solid var(--border); }
.stat-row:last-child { border-bottom:none; }
.stat-name { font-size:11.5px; color:var(--text-2); font-weight:500; }
.stat-val { font-size:12.5px; color:var(--text); font-weight:700; }

.skill-card { background:var(--bg-card2); border:1px solid var(--border); border-left:3px solid var(--accent); padding:12px 14px; margin-bottom:9px; }
.skill-type { font-size:9px; text-transform:uppercase; letter-spacing:2px; color:var(--accent3); margin-bottom:2px; font-weight:700; }
.skill-name { font-family:'Noto Serif SC',serif; font-size:15px; font-weight:700; color:var(--gold); margin-bottom:5px; }
.skill-desc { font-size:12px; color:var(--text-2); line-height:1.7; }

.constellation-grid { display:grid; grid-template-columns:1fr 1fr; gap:7px; }
.const-item { background:var(--bg-card2); border:1px solid var(--border); padding:10px 12px; }
.const-level { font-size:9px; color:var(--accent); font-weight:700; text-transform:uppercase; letter-spacing:1.5px; }
.const-desc { font-size:12px; color:var(--text-2); margin-top:4px; line-height:1.6; }

/* ===== MODAL ===== */
#modal { display:none; position:fixed; inset:0; z-index:300; background:rgba(30,18,5,.55); backdrop-filter:blur(5px); overflow-y:auto; padding:36px 18px; }
.modal-box {
  max-width:840px; margin:0 auto;
  background:var(--bg); border:1px solid var(--border-2);
  overflow:hidden;
  animation: slideIn .3s ease; box-shadow: var(--shadow-lg);
  position: relative;
}
.modal-box::before, .modal-box::after {
  content: ''; position:absolute; width:12px; height:12px;
  border-color: var(--gold3); border-style: solid; z-index:1;
}
.modal-box::before { top:-1px; left:-1px; border-width:3px 0 0 3px; }
.modal-box::after  { bottom:-1px; right:-1px; border-width:0 3px 3px 0; }
.modal-header {
  padding: 16px 22px; border-bottom:1px solid var(--border);
  display:flex; align-items:center; justify-content:space-between;
  background: var(--bg-panel);
}
.modal-title { font-family:'Noto Serif SC',serif; font-size:17px; color:var(--gold); font-weight:700; letter-spacing:1px; }
.modal-body { padding:22px; max-height:74vh; overflow-y:auto; }
.modal-footer { padding:12px 22px; border-top:1px solid var(--border); display:flex; justify-content:flex-end; gap:9px; background:var(--bg-panel); }

/* ===== FORMS ===== */
.form-section { margin-bottom:20px; }
.form-section-title {
  font-size:10px; text-transform:uppercase; letter-spacing:2.5px;
  color:var(--accent); font-weight:700; margin-bottom:11px;
  padding-bottom:6px; border-bottom:1px solid var(--border);
  display: flex; align-items: center; gap: 8px;
}
.form-section-title::before { content:''; display:inline-block; width:3px; height:12px; background:var(--gold3); flex-shrink:0; }
.form-grid { display:grid; grid-template-columns:1fr 1fr; gap:11px; }
.form-grid.cols3 { grid-template-columns:1fr 1fr 1fr; }
.form-group { display:flex; flex-direction:column; gap:4px; }
.form-group.full { grid-column:1/-1; }
.form-label { font-size:10.5px; color:var(--text-3); font-weight:700; letter-spacing:.3px; }
.form-input, .form-select, .form-textarea {
  background: var(--bg-card); border:1px solid var(--border);
  color: var(--text); border-radius:var(--radius);
  padding: 8px 11px; font-size:13px; font-family:'Mulish',sans-serif;
  outline:none; transition:border-color .2s; width:100%;
}
.form-input:focus, .form-select:focus, .form-textarea:focus { border-color:var(--accent); }
.form-select option { background: var(--bg-panel); color: var(--text); }
.form-textarea { min-height:76px; resize:vertical; }
.img-upload-wrap { position:relative; }
.img-preview {
  width:100%; height:110px; background:var(--bg-panel); border:1px dashed var(--border-2);
  border-radius:var(--radius); display:flex; align-items:center; justify-content:center;
  cursor:pointer; overflow:hidden; transition:border-color .2s;
  font-size:11px; color:var(--text-4); font-style:italic;
}
.img-preview:hover { border-color:var(--accent); }
.img-preview img { width:100%; height:100%; object-fit:cover; }
.img-upload-input { display:none; }

/* ===== BUTTONS ===== */
.btn { padding:7px 16px; border-radius:var(--radius); cursor:pointer; font-size:12.5px; font-family:'Mulish',sans-serif; font-weight:600; transition:all .2s; border:1px solid; }
.btn-primary { background:var(--accent); border-color:var(--accent); color:#f5e8d5; }
.btn-primary:hover { background:var(--accent2); border-color:var(--accent2); }
.btn-danger { background:rgba(160,48,48,.1); border-color:var(--red); color:var(--red); }
.btn-danger:hover { background:rgba(160,48,48,.2); }
.btn-ghost { background:transparent; border-color:var(--border); color:var(--text-3); }
.btn-ghost:hover { border-color:var(--border-2); color:var(--text-2); }

/* ===== HOME ===== */
.home-hero {
  background: var(--bg-card); border:1px solid var(--border);
  padding:32px 36px; margin-bottom:22px;
  position:relative; overflow:hidden;
}
.home-hero::before {
  content:''; position:absolute; inset:0;
  background-image:
    repeating-linear-gradient(0deg, var(--pattern-color) 0px, var(--pattern-color) 1px, transparent 1px, transparent 40px),
    repeating-linear-gradient(90deg, var(--pattern-color) 0px, var(--pattern-color) 1px, transparent 1px, transparent 40px);
  pointer-events:none;
}
.home-hero::after {
  content:''; position:absolute; top:0; left:0; right:0; height:3px;
  background: repeating-linear-gradient(90deg, var(--gold3) 0px, var(--gold3) 6px, transparent 6px, transparent 12px);
  opacity:.5;
}
.home-hero-title { font-family:'Noto Serif SC',serif; font-size:32px; font-weight:700; color:var(--gold); margin-bottom:7px; letter-spacing:2px; }
.home-hero-sub { color:var(--text-2); font-size:13px; max-width:500px; line-height:1.9; }
.home-stats { display:grid; grid-template-columns:repeat(4,1fr); gap:12px; margin-bottom:22px; }
.home-stat {
  background:var(--bg-card); border:1px solid var(--border);
  padding:16px 18px; text-align:center;
  transition:all .2s; position:relative; overflow:hidden;
}
.home-stat::before { content:''; position:absolute; bottom:0; left:0; right:0; height:2px; background:var(--gold3); opacity:0; transition:opacity .2s; }
.home-stat:hover { border-color:var(--accent); box-shadow:var(--shadow-sm); }
.home-stat:hover::before { opacity:.5; }
.home-stat-num { font-family:'Noto Serif SC',serif; font-size:28px; font-weight:700; color:var(--accent); }
.home-stat-label { font-size:10px; color:var(--text-3); text-transform:uppercase; letter-spacing:1.5px; margin-top:2px; font-weight:700; }
.home-sections { display:grid; grid-template-columns:repeat(3,1fr); gap:12px; }
.home-section-card {
  background:var(--bg-card); border:1px solid var(--border);
  padding:16px 18px; cursor:pointer;
  transition:all .22s; position:relative;
}
.home-section-card::before { content:''; position:absolute; left:0; top:0; bottom:0; width:2px; background:var(--gold3); opacity:0; transition:opacity .2s; }
.home-section-card:hover { border-color:var(--accent); transform:translateY(-2px); box-shadow:var(--shadow); }
.home-section-card:hover::before { opacity:1; }
.home-section-title { font-family:'Noto Serif SC',serif; font-size:15px; font-weight:700; color:var(--gold); margin-bottom:3px; }
.home-section-desc { font-size:11.5px; color:var(--text-3); }

/* ===== INFO SECTION ===== */
.info-section { background:var(--bg-card); border:1px solid var(--border); padding:18px; margin-bottom:14px; }
.info-section h3 { font-family:'Noto Serif SC',serif; font-size:16px; font-weight:700; color:var(--gold); margin-bottom:12px; letter-spacing:1px; }
.info-text { font-size:13px; color:var(--text-2); line-height:1.8; }
.info-table { width:100%; border-collapse:collapse; font-size:12.5px; margin-top:7px; }
.info-table th { padding:7px 11px; background:var(--bg-panel); color:var(--text-3); text-align:left; font-size:10px; text-transform:uppercase; letter-spacing:1.5px; border:1px solid var(--border); font-weight:700; }
.info-table td { padding:7px 11px; border:1px solid var(--border); color:var(--text-2); }
.info-table tr:hover td { background:var(--bg-card2); }

/* ===== REACTION ===== */
.reaction-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(240px,1fr)); gap:10px; }
.reaction-card { background:var(--bg-card); border:1px solid var(--border); padding:13px; transition:all .2s; cursor:default; }
.reaction-card:hover { border-color:var(--accent3); box-shadow:var(--shadow-sm); }
.reaction-name { font-family:'Noto Serif SC',serif; font-size:14px; font-weight:700; color:var(--gold); margin-bottom:2px; }
.reaction-trigger { font-size:10px; color:var(--accent3); margin-bottom:5px; font-weight:600; letter-spacing:.5px; }
.reaction-effect { font-size:11.5px; color:var(--text-2); line-height:1.65; }
.reaction-filter-bar { display:flex; gap:6px; flex-wrap:wrap; margin-bottom:16px; align-items:center; }

/* ===== GEO ===== */
.geo-continent { background:var(--bg-card); border:1px solid var(--border); margin-bottom:12px; overflow:hidden; }
.geo-continent-header { padding:12px 16px; display:flex; align-items:center; justify-content:space-between; cursor:pointer; background:var(--bg-panel); border-bottom:1px solid var(--border); }
.geo-continent-name { font-family:'Noto Serif SC',serif; font-size:16px; font-weight:700; color:var(--gold); letter-spacing:1px; }
.geo-forces { padding:13px 16px; }
.force-item { padding:9px 12px; background:var(--bg-card2); margin-bottom:7px; border:1px solid var(--border); border-left:3px solid var(--accent3); }
.force-name { font-size:13px; font-weight:700; color:var(--text); }
.force-desc { font-size:12px; color:var(--text-2); margin-top:3px; }

/* ===== ITEM CARD ===== */
.item-card { background:var(--bg-card); border:1px solid var(--border); cursor:pointer; transition:all .2s; overflow:hidden; }
.item-card:hover { border-color:var(--accent); transform:translateY(-2px); box-shadow:var(--shadow); }
.item-card-img { height:88px; background:var(--bg-card2); display:flex; align-items:center; justify-content:center; overflow:hidden; }
.item-card-img img { width:100%; height:100%; object-fit:cover; }
.item-card-img .placeholder-text { font-size:10px; color:var(--text-4); font-style:italic; }
.item-card-body { padding:9px 11px; }
.item-card-name { font-size:12.5px; font-weight:700; color:var(--text); }
.item-card-meta { font-size:10.5px; color:var(--text-3); margin-top:3px; display:flex; gap:4px; flex-wrap:wrap; }
/* Rarity badges - cấp */
.rarity-badge { display:inline-block; padding:1px 7px; border-radius:2px; font-size:10px; font-weight:700; }
.rarity-huang { background:rgba(180,140,40,.12); color:#7A5C1A; border:1px solid rgba(180,140,40,.4); }  /* Hoàng - trắng */
.rarity-xuan  { background:rgba(60,100,180,.12); color:#2A4E8A; border:1px solid rgba(60,100,180,.4); }  /* Huyền - lam */
.rarity-dia   { background:rgba(110,60,180,.12); color:#5A2E9A; border:1px solid rgba(110,60,180,.4); }  /* Địa - tím */
.rarity-thien { background:rgba(180,140,20,.18); color:#7A5800; border:1px solid rgba(180,140,20,.5); }  /* Thiên - vàng */
/* Phẩm badges */
.pham-ha     { background:rgba(140,140,140,.1); color:#5A5A5A; border:1px solid rgba(140,140,140,.3); }
.pham-trung  { background:rgba(60,140,80,.1); color:#2A6A3A; border:1px solid rgba(60,140,80,.3); }
.pham-thuong { background:rgba(60,80,180,.1); color:#2A3A8A; border:1px solid rgba(60,80,180,.3); }
.pham-cuc    { background:rgba(140,40,160,.1); color:#6A1A7A; border:1px solid rgba(140,40,160,.3); }

/* ===== TIMELINE ===== */
.timeline-wrap { position:relative; padding-left:28px; }
.timeline-wrap::before { content:''; position:absolute; left:8px; top:0; bottom:0; width:1px; background:repeating-linear-gradient(180deg,var(--border-2) 0,var(--border-2) 6px,transparent 6px,transparent 12px); }
.timeline-item { position:relative; margin-bottom:18px; }
.timeline-item::before { content:''; position:absolute; left:-22px; top:7px; width:8px; height:8px; background:var(--gold3); transform:rotate(45deg); border:1px solid var(--bg); }
.timeline-card { background:var(--bg-card); border:1px solid var(--border); padding:13px 15px; transition:all .2s; }
.timeline-card:hover { border-color:var(--accent); box-shadow:var(--shadow-sm); }
.timeline-year { font-size:10px; color:var(--accent); font-weight:700; text-transform:uppercase; letter-spacing:1.5px; margin-bottom:3px; }
.timeline-title { font-family:'Noto Serif SC',serif; font-size:15px; font-weight:700; color:var(--gold); margin-bottom:4px; }
.timeline-desc { font-size:11.5px; color:var(--text-2); line-height:1.7; }

/* ===== PASS MODAL ===== */
#passModal { display:none; position:fixed; inset:0; z-index:500; background:rgba(30,18,5,.65); backdrop-filter:blur(8px); align-items:center; justify-content:center; }
.pass-box { background:var(--bg); border:1px solid var(--border-2); padding:28px; width:320px; text-align:center; box-shadow:var(--shadow-lg); position:relative; }
.pass-box::before, .pass-box::after { content:''; position:absolute; width:10px; height:10px; border-color:var(--gold3); border-style:solid; }
.pass-box::before { top:-1px; left:-1px; border-width:2px 0 0 2px; }
.pass-box::after  { bottom:-1px; right:-1px; border-width:0 2px 2px 0; }
.pass-title { font-family:'Noto Serif SC',serif; font-size:19px; color:var(--gold); margin-bottom:5px; font-weight:700; letter-spacing:1px; }
.pass-desc { font-size:11px; color:var(--text-3); margin-bottom:18px; }
.pass-input { width:100%; text-align:center; letter-spacing:4px; font-size:15px; margin-bottom:14px; }
.pass-error { color:var(--red); font-size:11px; margin-bottom:7px; min-height:16px; }

/* ===== TOAST ===== */
.toast {
  position:fixed; bottom:22px; right:22px; z-index:999;
  padding:10px 16px; background:var(--bg-card); border:1px solid var(--border);
  font-size:12.5px; color:var(--text);
  box-shadow:var(--shadow); animation:toastIn .3s ease;
  display:flex; align-items:center; gap:9px; font-weight:500;
}
@keyframes toastIn { from{transform:translateY(20px);opacity:0} to{transform:translateY(0);opacity:1} }
.toast.success { border-color:var(--green); }
.toast.error { border-color:var(--red); }

/* ===== NAV BADGE ===== */
.nav-add-badge {
  margin-left:auto; font-size:9px; padding:1px 6px; border-radius:2px;
  background:rgba(122,78,42,.15); color:var(--accent); font-weight:700;
  display:none;
}
body.edit-mode .nav-add-badge { display:inline-block; }

/* ===== CHAR DETAIL HERO ===== */
.char-detail-hero {
  display:flex; gap:18px; margin-bottom:18px; align-items:flex-start;
  padding:18px; background:var(--bg-card); border:1px solid var(--border);
  position:relative; overflow:hidden;
}
.char-detail-hero::after { content:''; position:absolute; top:0; left:0; right:0; height:2px; background:linear-gradient(90deg,var(--gold3),var(--accent3),var(--gold3)); }
.char-detail-avatar {
  width:105px; height:105px;
  background:var(--bg-panel); border:1px solid var(--border);
  flex-shrink:0; overflow:hidden; display:flex; align-items:center; justify-content:center;
}
.char-detail-avatar img { width:100%; height:100%; object-fit:cover; }
.char-detail-avatar .placeholder-text { font-size:10px; color:var(--text-4); font-style:italic; text-align:center; padding:7px; }
.char-detail-name { font-family:'Noto Serif SC',serif; font-size:22px; font-weight:700; color:var(--text); line-height:1.2; letter-spacing:1px; }
.char-detail-title { font-size:12.5px; color:var(--text-3); margin-top:3px; font-style:italic; }
.char-detail-tags { display:flex; gap:5px; margin-top:9px; flex-wrap:wrap; align-items:center; }
.tag { font-size:10px; padding:2px 9px; border-radius:2px; border:1px solid var(--border); color:var(--text-2); background:var(--bg-panel); font-weight:600; }
.tag.gold { border-color:rgba(107,78,28,.4); color:var(--gold); background:rgba(107,78,28,.08); }

/* ===== EMPTY STATE ===== */
.empty-state { text-align:center; padding:55px; color:var(--text-4); }
.empty-state-title { font-size:13px; margin-top:10px; font-style:italic; }

/* ===== VOICE LINES ===== */
.voice-line { background:var(--bg-card2); border-left:3px solid var(--accent3); padding:9px 13px; margin-bottom:7px; }
.voice-label { font-size:9px; text-transform:uppercase; letter-spacing:1.5px; color:var(--accent3); font-weight:700; margin-bottom:2px; }
.voice-text { font-size:12.5px; color:var(--text); font-style:italic; line-height:1.65; }

/* ===== CHECKBOX GROUP ===== */
.checkbox-row { display:flex; flex-wrap:wrap; gap:6px; margin-top:4px; }
.checkbox-item { display:flex; align-items:center; gap:4px; cursor:pointer; }
.checkbox-item input { accent-color: var(--accent); cursor:pointer; }
.checkbox-item label { font-size:12px; color:var(--text-2); cursor:pointer; }

/* ===== STORY SECTION ===== */
.story-block { background:var(--bg-card2); border:1px solid var(--border); border-left:3px solid var(--gold3); padding:12px 14px; margin-bottom:9px; }
.story-block-title { font-size:10px; text-transform:uppercase; letter-spacing:2px; color:var(--gold); font-weight:700; margin-bottom:6px; }
.story-block-content { font-size:12.5px; color:var(--text-2); line-height:1.8; }

/* ===== RARITY COLORS ===== */
.weapon-5star { color:#9B6B1A; font-weight:700; }
.weapon-4star { color:#6B4A9E; font-weight:700; }
.weapon-3star { color:#2A5AA0; font-weight:700; }

/* ===== WEAPON GROUP BADGE ===== */
.weapon-group-tag { font-size:10px; padding:2px 8px; border-radius:2px; background:rgba(62,107,85,.12); color:var(--accent3); border:1px solid rgba(62,107,85,.3); font-weight:700; }
</style>
</head>
<body>

<!-- SIDEBAR -->
<div id="sidebar">
  <div class="sidebar-logo">
    <div class="sidebar-logo-title">仙界&nbsp;起源</div>
    <div class="sidebar-logo-deco"><span></span><span style="font-size:10px;color:var(--gold3);letter-spacing:2px">WIKI</span><span></span></div>
    <div class="sidebar-logo-sub">Tiên Giới Khởi Nguyên</div>
  </div>
  <nav id="nav">
    <div class="nav-section">Tổng quan</div>
    <div class="nav-item active" data-page="home">Trang chủ</div>

    <div class="nav-section">Nhân vật</div>
    <div class="nav-item" data-page="characters">Thư viện nhân vật <span class="nav-add-badge" onclick="event.stopPropagation();openCharModal()">+ Thêm</span></div>
    <div class="nav-item" data-page="char-info">Hệ tu &amp; Chỉ số</div>

    <div class="nav-section">Trang bị</div>
    <div class="nav-item" data-page="weapons">Pháp bảo trấn vật <span class="nav-add-badge" onclick="event.stopPropagation();openItemModal('weapon')">+ Thêm</span></div>
    <div class="nav-item" data-page="artifacts">Linh khí tùy thân <span class="nav-add-badge" onclick="event.stopPropagation();openItemModal('artifact')">+ Thêm</span></div>

    <div class="nav-section">Vật phẩm</div>
    <div class="nav-item" data-page="herbs">Thảo dược <span class="nav-add-badge" onclick="event.stopPropagation();openItemModal('herb')">+ Thêm</span></div>
    <div class="nav-item" data-page="minerals">Khoáng vật <span class="nav-add-badge" onclick="event.stopPropagation();openItemModal('mineral')">+ Thêm</span></div>
    <div class="nav-item" data-page="drops">Đồ rớt từ quái <span class="nav-add-badge" onclick="event.stopPropagation();openItemModal('drop')">+ Thêm</span></div>
    <div class="nav-item" data-page="pills">Đan dược <span class="nav-add-badge" onclick="event.stopPropagation();openItemModal('pill')">+ Thêm</span></div>

    <div class="nav-section">Cơ chế</div>
    <div class="nav-item" data-page="breakthrough">Đột phá cảnh giới</div>
    <div class="nav-item" data-page="reactions">Phản ứng nguyên tố</div>

    <div class="nav-section">Thế giới &amp; Lịch sử</div>
    <div class="nav-item" data-page="geography">Địa lý thế giới <span class="nav-add-badge" onclick="event.stopPropagation();openGeoModal()">+ Thêm</span></div>
    <div class="nav-item" data-page="timeline">Dòng thời gian <span class="nav-add-badge" onclick="event.stopPropagation();openTimelineModal()">+ Thêm</span></div>

    <div class="nav-section">Tùy chỉnh</div>
    <div class="nav-item" data-page="custom-sections">Nhánh tùy chỉnh</div>
  </nav>
  <div class="sidebar-footer">
    <button id="editModeBtn" onclick="toggleEditMode()">
      <span class="edit-dot"></span>
      <span id="editBtnText">Chế độ chỉnh sửa</span>
    </button>
    <button id="exportBtn2" onclick="exportHTML()">Xuất file HTML</button>
  </div>
</div>

<!-- MAIN -->
<div id="main">
  <div id="topbar">
    <span class="topbar-title" id="topbarTitle">Trang chủ</span>
    <div class="topbar-deco"><span></span><span></span><span></span></div>
  </div>

  <!-- HOME -->
  <div class="page active" id="page-home">
    <div class="home-hero">
      <div class="home-hero-title">Tiên Giới : Khởi Nguyên</div>
      <div class="home-hero-sub">Wiki nội bộ — lưu trữ nhân vật, trang bị, vật phẩm, cơ chế và địa lý của vũ trụ tu tiên đang được xây dựng.</div>
    </div>
    <div class="home-stats">
      <div class="home-stat"><div class="home-stat-num" id="stat-chars">0</div><div class="home-stat-label">Nhân vật</div></div>
      <div class="home-stat"><div class="home-stat-num" id="stat-weapons">0</div><div class="home-stat-label">Trang bị</div></div>
      <div class="home-stat"><div class="home-stat-num" id="stat-items">0</div><div class="home-stat-label">Vật phẩm</div></div>
      <div class="home-stat"><div class="home-stat-num" id="stat-events">0</div><div class="home-stat-label">Sự kiện</div></div>
    </div>
    <div class="home-sections">
      <div class="home-section-card" onclick="navigate('characters')"><div class="home-section-title">Thư viện nhân vật</div><div class="home-section-desc">Xem và quản lý tất cả nhân vật</div></div>
      <div class="home-section-card" onclick="navigate('reactions')"><div class="home-section-title">Phản ứng nguyên tố</div><div class="home-section-desc">11 hệ nguyên tố, tương sinh tương khắc</div></div>
      <div class="home-section-card" onclick="navigate('breakthrough')"><div class="home-section-title">Đột phá cảnh giới</div><div class="home-section-desc">7 cảnh giới từ Luyện Khí đến Đại Thừa</div></div>
      <div class="home-section-card" onclick="navigate('weapons')"><div class="home-section-title">Pháp bảo trấn vật</div><div class="home-section-desc">6 nhóm vũ khí, 5 cấp độ</div></div>
      <div class="home-section-card" onclick="navigate('geography')"><div class="home-section-title">Địa lý thế giới</div><div class="home-section-desc">Các lục địa và thế lực</div></div>
      <div class="home-section-card" onclick="navigate('timeline')"><div class="home-section-title">Dòng thời gian</div><div class="home-section-desc">Các sự kiện lịch sử cốt truyện</div></div>
    </div>
  </div>

  <!-- CHARACTERS -->
  <div class="page" id="page-characters">
    <div class="page-header">
      <div class="page-title">Thư viện nhân vật</div>
      <div class="divider-title"></div>
      <div class="page-desc">Tất cả nhân vật trong Tiên Giới: Khởi Nguyên</div>
    </div>
    <div class="filter-bar">
      <input class="search-box" type="text" placeholder="Tìm kiếm nhân vật..." id="charSearch" oninput="filterChars()">
      <button class="filter-btn active" data-filter="all" onclick="setCharFilter(this,'all')">Tất cả</button>
      <button class="filter-btn" data-filter="5" onclick="setCharFilter(this,'5')">5 sao</button>
      <button class="filter-btn" data-filter="4" onclick="setCharFilter(this,'4')">4 sao</button>
      <div class="view-toggle" style="margin-left:auto">
        <button class="view-btn active" onclick="setCharView('grid',this)">Grid</button>
        <button class="view-btn" onclick="setCharView('table',this)">Bảng</button>
      </div>
    </div>
    <button class="add-btn hidden" id="addCharBtn" onclick="openCharModal()">+ Thêm nhân vật</button>
    <div id="charGridView"><div class="cards-grid" id="charGrid"></div></div>
    <div id="charTableView" style="display:none">
      <table class="data-table">
        <thead><tr><th>Nhân vật</th><th>Sao</th><th>Nguyên tố</th><th>Hệ tu</th><th>Vũ khí</th><th>Cảnh giới</th><th>Patch</th></tr></thead>
        <tbody id="charTableBody"></tbody>
      </table>
    </div>
    <div id="charEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có nhân vật nào. Bật chế độ chỉnh sửa để thêm!</div></div>
  </div>

  <!-- CHAR INFO -->
  <div class="page" id="page-char-info">
    <div class="page-header"><div class="page-title">Hệ tu &amp; Chỉ số</div><div class="divider-title"></div></div>
    <div class="info-section">
      <h3>Hệ tu — Vai trò chiến đấu</h3>
      <table class="info-table">
        <thead><tr><th>Hệ tu</th><th>Vai trò</th><th>Mô tả</th></tr></thead>
        <tbody>
          <tr><td>Kiếm Tu</td><td style="color:#A03030">DPS</td><td>Công kích liên tục, sát thương cao, cận chiến</td></tr>
          <tr><td>Khí Tu</td><td style="color:#7A5C2E">Sub-DPS / Buff</td><td>Vận dụng linh khí, hiệu ứng nguyên tố</td></tr>
          <tr><td>Đan Tu</td><td style="color:#2E6644">Heal / Support</td><td>Luyện đan, hồi phục, tăng cường đồng đội</td></tr>
          <tr><td>Trận Tu</td><td style="color:#3E6B55">Support / CC</td><td>Bố trận pháp, kiểm soát vùng</td></tr>
          <tr><td>Thể Tu</td><td style="color:#5A3880">Tank / DPS</td><td>Luyện thân, phòng thủ cao, phản đòn</td></tr>
          <tr><td>Ma Tu</td><td style="color:#8B0000">DPS / Debuff</td><td>Tiêu hao sinh mệnh đổi lấy sức mạnh</td></tr>
          <tr><td>Thần Tu</td><td style="color:#6B4A9E">Sub-DPS / Buff</td><td>Thần thức, cổ pháp, biến hóa</td></tr>
          <tr><td>Ẩn Tu</td><td style="color:#4A3418">Assassin / Debuff</td><td>Tàng hình, ám sát, hạ gục mục tiêu đơn</td></tr>
        </tbody>
      </table>
    </div>
    <div class="info-section">
      <h3>Chỉ số thuộc tính (Level 99)</h3>
      <table class="info-table">
        <thead><tr><th>Chỉ số</th><th>Max 4 sao</th><th>Max 5 sao</th><th>Ghi chú</th></tr></thead>
        <tbody>
          <tr><td>Sinh mệnh linh đài (HP)</td><td>15,000</td><td>30,000</td><td>Tổng HP</td></tr>
          <tr><td>Linh lực cơ bản (ATK)</td><td>300</td><td>500</td><td>Sát thương vật lý & linh lực</td></tr>
          <tr><td>Thể phách trấn áp (DEF)</td><td>600</td><td>1,000</td><td>Giảm sát thương nhận vào</td></tr>
          <tr><td>Tỷ lệ bạo kích</td><td>5%</td><td>5%</td><td>Mặc định ~5%</td></tr>
          <tr><td>Sát thương bạo kích</td><td>50%</td><td>50%</td><td>Mặc định ~50%</td></tr>
          <tr><td>Tăng sát thương hệ</td><td>25%</td><td>30%</td><td>Theo linh căn đã chọn</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- WEAPONS -->
  <div class="page" id="page-weapons">
    <div class="page-header"><div class="page-title">Pháp bảo trấn vật</div><div class="divider-title"></div></div>
    <div class="filter-bar">
      <input class="search-box" type="text" placeholder="Tìm kiếm vũ khí..." id="weaponSearch" oninput="filterItems('weapon')">
      <button class="filter-btn active" data-wg="all" onclick="setWeaponGroupFilter(this,'all')">Tất cả</button>
      <button class="filter-btn" data-wg="KIẾM" onclick="setWeaponGroupFilter(this,'KIẾM')">Kiếm</button>
      <button class="filter-btn" data-wg="CUNG" onclick="setWeaponGroupFilter(this,'CUNG')">Cung</button>
      <button class="filter-btn" data-wg="PHÁP KHÍ" onclick="setWeaponGroupFilter(this,'PHÁP KHÍ')">Pháp khí</button>
      <button class="filter-btn" data-wg="VŨ KHÍ CÁN DÀI" onclick="setWeaponGroupFilter(this,'VŨ KHÍ CÁN DÀI')">Cán dài</button>
      <button class="filter-btn" data-wg="QUYỀN GIÁP" onclick="setWeaponGroupFilter(this,'QUYỀN GIÁP')">Quyền giáp</button>
      <button class="filter-btn" data-wg="LINH BẢO" onclick="setWeaponGroupFilter(this,'LINH BẢO')">Linh bảo</button>
    </div>
    <button class="add-btn hidden" id="addWeaponBtn" onclick="openItemModal('weapon')">+ Thêm vũ khí</button>
    <div class="cards-grid" id="weaponGrid"></div>
    <div id="weaponEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có vũ khí nào.</div></div>
    <div class="info-section" style="margin-top:22px">
      <h3>Phân loại vũ khí</h3>
      <table class="info-table">
        <thead><tr><th>Nhóm lớn</th><th>Nhóm nhỏ</th><th>Ghi chú</th></tr></thead>
        <tbody>
          <tr><td rowspan="3"><b>KIẾM</b></td><td>Kiếm đơn (Linh kiếm / Phi kiếm)</td><td>Linh hoạt, cân bằng tốc/sát thương</td></tr>
          <tr><td>Trọng kiếm (Đại kiếm)</td><td>Chậm nhưng sát thương cao, phá giáp tốt</td></tr>
          <tr><td>Song kiếm</td><td>Tốc độ cao, combo dày</td></tr>
          <tr><td rowspan="2"><b>CUNG</b></td><td>Trường cung</td><td>Tầm xa, sát thương ổn định</td></tr>
          <tr><td>Nỏ / Cơ quan nỏ</td><td>Liên xạ tốc độ cao</td></tr>
          <tr><td rowspan="5"><b>PHÁP KHÍ</b></td><td>Hồ lô / Bình linh</td><td>Trữ dược, hút linh khí</td></tr>
          <tr><td>Phất trần / Kiếm gỗ đào</td><td>Đạo gia, hỗ trợ & tẩy trừ</td></tr>
          <tr><td>Bút lông / Thư ấn</td><td>Vẽ bùa, triệu trận pháp</td></tr>
          <tr><td>Đạo ấn / Ngọc ấn</td><td>Khai ấn, phong ấn kẻ địch</td></tr>
          <tr><td>Chuông linh / Pháp tràng / Cổ Thư</td><td>Điều khiển âm ba, áp chế</td></tr>
          <tr><td rowspan="4"><b>VŨ KHÍ CÁN DÀI</b></td><td>Thương / Thiết kích / Giáo</td><td>Đâm xuyên, giữ khoảng cách</td></tr>
          <tr><td>Đại Đao</td><td>Sức chém mạnh</td></tr>
          <tr><td>Thiền trượng / Côn</td><td>Phật môn, mạnh mẽ, đẩy lui</td></tr>
          <tr><td>Đại phủ / Trượng thần</td><td>Phá giáp cực mạnh, chậm</td></tr>
          <tr><td rowspan="2"><b>QUYỀN GIÁP</b></td><td>Quyền giáp linh tinh</td><td>Cận chiến bùng nổ, tốc độ cao</td></tr>
          <tr><td>Vô vũ khí (Thể tu)</td><td>Luyện thể, đấm bằng linh lực</td></tr>
          <tr><td rowspan="3"><b>LINH BẢO</b> (đặc biệt)</td><td>Gương linh / Ngọc bội</td><td>Phòng thủ, phản chiếu</td></tr>
          <tr><td>Bài / Thẻ bài</td><td>Triệu hồi, ngẫu nhiên</td></tr>
          <tr><td>Nhạc khí linh</td><td>Điều khiển tình cảm & trạng thái</td></tr>
        </tbody>
      </table>
      <div style="margin-top:14px">
        <h3>Phân cấp</h3>
        <table class="info-table">
          <thead><tr><th>Cấp</th><th>Tên</th><th>Ghi chú</th></tr></thead>
          <tbody>
            <tr><td>1 sao</td><td>Phàm khí</td><td>Cấp thấp nhất</td></tr>
            <tr><td>2 sao</td><td>Linh khí</td><td>Có thể tự luyện</td></tr>
            <tr><td>3 sao</td><td>Địa khí</td><td>Có thể tự luyện</td></tr>
            <tr><td>4 sao</td><td>Tiên khí</td><td>Cần điều kiện đặc biệt</td></tr>
            <tr><td>5 sao</td><td style="color:var(--gold);font-weight:700">Thần khí</td><td>Hiếm nhất — Bản Mệnh Pháp Bảo</td></tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>

  <!-- ARTIFACTS -->
  <div class="page" id="page-artifacts">
    <div class="page-header"><div class="page-title">Linh khí tùy thân</div><div class="divider-title"></div></div>
    <button class="add-btn hidden" id="addArtifactBtn" onclick="openItemModal('artifact')">+ Thêm bộ linh khí</button>
    <div class="cards-grid" id="artifactGrid"></div>
    <div id="artifactEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có bộ linh khí nào.</div></div>
  </div>

  <!-- HERBS -->
  <div class="page" id="page-herbs">
    <div class="page-header"><div class="page-title">Thảo dược</div><div class="divider-title"></div></div>
    <button class="add-btn hidden" id="addHerbBtn" onclick="openItemModal('herb')">+ Thêm thảo dược</button>
    <div class="cards-grid" id="herbGrid"></div>
    <div id="herbEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có thảo dược nào.</div></div>
  </div>

  <!-- MINERALS -->
  <div class="page" id="page-minerals">
    <div class="page-header"><div class="page-title">Khoáng vật</div><div class="divider-title"></div></div>
    <button class="add-btn hidden" id="addMineralBtn" onclick="openItemModal('mineral')">+ Thêm khoáng vật</button>
    <div class="cards-grid" id="mineralGrid"></div>
    <div id="mineralEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có khoáng vật nào.</div></div>
  </div>

  <!-- DROPS -->
  <div class="page" id="page-drops">
    <div class="page-header"><div class="page-title">Đồ rớt từ quái</div><div class="divider-title"></div></div>
    <button class="add-btn hidden" id="addDropBtn" onclick="openItemModal('drop')">+ Thêm vật phẩm rớt</button>
    <div class="cards-grid" id="dropGrid"></div>
    <div id="dropEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có vật phẩm rớt nào.</div></div>
  </div>

  <!-- PILLS -->
  <div class="page" id="page-pills">
    <div class="page-header"><div class="page-title">Đan dược</div><div class="divider-title"></div></div>
    <button class="add-btn hidden" id="addPillBtn" onclick="openItemModal('pill')">+ Thêm đan dược</button>
    <div class="cards-grid" id="pillGrid"></div>
    <div id="pillEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có đan dược nào.</div></div>
  </div>

  <!-- BREAKTHROUGH -->
  <div class="page" id="page-breakthrough">
    <div class="page-header"><div class="page-title">Đột phá cảnh giới</div><div class="divider-title"></div></div>
    <div class="info-section">
      <h3>Cảnh giới &amp; Cấp độ</h3>
      <table class="info-table">
        <thead><tr><th>Cảnh giới</th><th>Cấp (Lv)</th><th>Đột phá tại</th></tr></thead>
        <tbody>
          <tr><td style="color:#2E6644;font-weight:700">Luyện Khí</td><td>1 → 20</td><td>Lv.20</td></tr>
          <tr><td style="color:#A03030;font-weight:700">Trúc Cơ</td><td>21 → 40</td><td>Lv.40</td></tr>
          <tr><td style="color:#6B4A9E;font-weight:700">Kết Đan</td><td>41 → 60</td><td>Lv.60</td></tr>
          <tr><td style="color:#2A5070;font-weight:700">Nguyên Anh</td><td>61 → 80</td><td>Lv.80</td></tr>
          <tr><td style="color:#7A5C2E;font-weight:700">Hóa Thần</td><td>81 → 90</td><td>Lv.90</td></tr>
          <tr><td style="color:#5A3880;font-weight:700">Luyện Hư</td><td>91 → 99</td><td>Lv.99</td></tr>
          <tr><td style="color:#9B6B1A;font-weight:700">Đại Thừa / Độ Kiếp</td><td>100+</td><td>—</td></tr>
        </tbody>
      </table>
    </div>
    <div class="info-section">
      <h3>Điều kiện đột phá</h3>
      <div class="info-text">Muốn đột phá cảnh giới cần 5 loại vật phẩm: Linh thạch, Đồ quái rơi, Đồ boss rơi, Kỳ trân dị bảo, và Đan đột phá (tỷ lệ thành công mặc định 30%). Nếu thất bại, không mất tài nguyên nhưng nhân vật bị thương do lôi kiếp — phải trị thương mới có thể thử lại.</div>
    </div>
  </div>

  <!-- REACTIONS -->
  <div class="page" id="page-reactions">
    <div class="page-header"><div class="page-title">Phản ứng nguyên tố</div><div class="divider-title"></div></div>
    <div class="info-section">
      <h3>Tương Sinh (Ngũ hành)</h3>
      <div class="info-text">Mộc sinh Hỏa → Hỏa sinh Thổ → Thổ sinh Kim → Kim sinh Thủy → Thủy sinh Mộc<br><span style="color:var(--text-3);font-size:11.5px">Hiệu ứng: Giảm 10% Giáp và Kháng Nguyên Tố của mục tiêu</span></div>
      <h3 style="margin-top:14px">Tương Khắc</h3>
      <div class="info-text">Mộc khắc Thổ → Thổ khắc Thủy → Thủy khắc Hỏa → Hỏa khắc Kim → Kim khắc Mộc<br><span style="color:var(--text-3);font-size:11.5px">Hiệu ứng: Nhân vật kích hoạt nhận +5% Tăng Sát Nguyên Tố</span></div>
    </div>

    <!-- Reaction filter -->
    <div style="margin-bottom:14px">
      <div style="font-size:10px;color:var(--text-4);letter-spacing:2px;text-transform:uppercase;margin-bottom:8px;font-weight:700">Tìm theo hệ nguyên tố</div>
      <div class="reaction-filter-bar" id="reactionFilterBar">
        <button class="filter-btn active" data-re="all" onclick="setReactionFilter(this,'all')">Tất cả</button>
        <button class="filter-btn" data-re="Kim" onclick="setReactionFilter(this,'Kim')">Kim</button>
        <button class="filter-btn" data-re="Mộc" onclick="setReactionFilter(this,'Mộc')">Mộc</button>
        <button class="filter-btn" data-re="Thủy" onclick="setReactionFilter(this,'Thủy')">Thủy</button>
        <button class="filter-btn" data-re="Hỏa" onclick="setReactionFilter(this,'Hỏa')">Hỏa</button>
        <button class="filter-btn" data-re="Thổ" onclick="setReactionFilter(this,'Thổ')">Thổ</button>
        <button class="filter-btn" data-re="Phong" onclick="setReactionFilter(this,'Phong')">Phong</button>
        <button class="filter-btn" data-re="Lôi" onclick="setReactionFilter(this,'Lôi')">Lôi</button>
        <button class="filter-btn" data-re="Băng" onclick="setReactionFilter(this,'Băng')">Băng</button>
        <button class="filter-btn" data-re="Độc" onclick="setReactionFilter(this,'Độc')">Độc</button>
        <button class="filter-btn" data-re="Quang" onclick="setReactionFilter(this,'Quang')">Quang</button>
        <button class="filter-btn" data-re="Ám" onclick="setReactionFilter(this,'Ám')">Ám</button>
      </div>
    </div>

    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:10px">
      <div style="font-size:10px;color:var(--text-4);letter-spacing:2px;text-transform:uppercase;font-weight:700">Danh sách phản ứng</div>
      <button class="add-btn hidden" id="addReactionBtn" onclick="openReactionModal()" style="margin:0;padding:5px 12px;font-size:11px">+ Thêm phản ứng</button>
    </div>
    <div class="reaction-grid" id="reactionGrid"></div>
  </div>

  <!-- GEOGRAPHY -->
  <div class="page" id="page-geography">
    <div class="page-header"><div class="page-title">Địa lý thế giới</div><div class="divider-title"></div></div>
    <button class="add-btn hidden" id="addGeoBtn" onclick="openGeoModal()">+ Thêm lục địa</button>
    <div id="geoList"></div>
    <div id="geoEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có lục địa nào.</div></div>
  </div>

  <!-- TIMELINE -->
  <div class="page" id="page-timeline">
    <div class="page-header"><div class="page-title">Dòng thời gian</div><div class="divider-title"></div><div class="page-desc">Lịch sử và các sự kiện quan trọng trong cốt truyện</div></div>
    <button class="add-btn hidden" id="addTimelineBtn" onclick="openTimelineModal()">+ Thêm sự kiện</button>
    <div id="timelineList"></div>
    <div id="timelineEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có sự kiện nào. Bật chế độ chỉnh sửa để thêm!</div></div>
  </div>

  <!-- CUSTOM SECTIONS -->
  <div class="page" id="page-custom-sections">
    <div class="page-header"><div class="page-title">Nhánh tùy chỉnh</div><div class="divider-title"></div><div class="page-desc">Thêm các nhánh lớn và mục nhỏ hoàn toàn tùy ý</div></div>
    <button class="add-btn hidden" id="addCustomSectionBtn" onclick="openCustomSectionModal()">+ Thêm nhánh mới</button>
    <div id="customSectionsList"></div>
    <div id="customSectionsEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có nhánh tùy chỉnh nào.</div></div>
  </div>
</div>

<!-- DETAIL OVERLAY -->
<div id="detailOverlay" onclick="closeDetail()"></div>
<div id="detailPanel">
  <div class="detail-close">
    <div class="detail-close-title" id="detailPanelTitle"></div>
    <div class="detail-close-actions">
      <button class="btn btn-danger hidden" id="detailDeleteBtn" style="padding:4px 11px;font-size:11px">Xóa</button>
      <button class="btn btn-primary hidden" id="detailEditBtn" style="padding:4px 11px;font-size:11px">Chỉnh sửa</button>
      <div class="close-btn" onclick="closeDetail()">✕</div>
    </div>
  </div>
  <div id="detailContent" class="detail-content"></div>
</div>

<!-- MODAL -->
<div id="modal">
  <div class="modal-box">
    <div class="modal-header">
      <div class="modal-title" id="modalTitle">Thêm mới</div>
      <div class="close-btn" onclick="closeModal()">✕</div>
    </div>
    <div class="modal-body" id="modalBody"></div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeModal()">Hủy</button>
      <button class="btn btn-primary" onclick="saveModal()">Lưu</button>
    </div>
  </div>
</div>

<!-- PASS MODAL -->
<div id="passModal" style="display:none;position:fixed;inset:0;z-index:500;background:rgba(30,18,5,.65);backdrop-filter:blur(8px);align-items:center;justify-content:center;">
  <div class="pass-box">
    <div class="pass-title">制御模式</div>
    <div class="pass-desc">Nhập mật khẩu để kích hoạt quyền chỉnh sửa nội dung</div>
    <input class="form-input pass-input" type="password" id="passInput" placeholder="••••••" onkeydown="if(event.key==='Enter')checkPass()">
    <div class="pass-error" id="passError"></div>
    <button class="btn btn-primary" style="width:100%;margin-bottom:7px" onclick="checkPass()">Xác nhận</button>
    <button class="btn btn-ghost" style="width:100%" onclick="closePassModal()">Hủy</button>
  </div>
</div>

<script>
// ===== WEAPON GROUPS =====
const WEAPON_GROUPS = {
  'KIẾM': ['Kiếm đơn (Linh kiếm)','Kiếm đơn (Phi kiếm)','Trọng kiếm (Đại kiếm)','Song kiếm'],
  'CUNG': ['Trường cung','Nỏ / Cơ quan nỏ'],
  'PHÁP KHÍ': ['Hồ lô / Bình linh','Phất trần / Kiếm gỗ đào','Bút lông / Thư ấn','Đạo ấn / Ngọc ấn','Chuông linh','Pháp tràng','Cổ Thư / Kinh Thư'],
  'VŨ KHÍ CÁN DÀI': ['Thương / Giáo','Thiết kích','Đại Đao','Thiền trượng / Côn','Đại phủ / Trượng thần'],
  'QUYỀN GIÁP': ['Quyền giáp linh tinh','Vô vũ khí (Thể tu)'],
  'LINH BẢO': ['Gương linh / Ngọc bội','Bài / Thẻ bài','Nhạc khí linh']
};

// ===== DB =====
let DB = JSON.parse(localStorage.getItem('tiengioi_db_v3') || 'null') || {
  characters:[], weapons:[], artifacts:[], herbs:[], minerals:[], drops:[], pills:[],
  geography:[], timeline:[], customSections:[], customReactions:[],
  pass: '1900100biet'
};
let editMode = false;
let currentPage = 'home';
let currentDetailItem = null;
let currentDetailType = null;
let charFilter = 'all';
let charView = 'grid';
let itemFilters = {};
let weaponGroupFilter = 'all';
let reactionElementFilter = 'all';
let modalType = null;
let modalEditItem = null;

function save() {
  localStorage.setItem('tiengioi_db_v3', JSON.stringify(DB));
  updateStats();
}

function updateStats() {
  document.getElementById('stat-chars').textContent = DB.characters.length;
  document.getElementById('stat-weapons').textContent = DB.weapons.length + DB.artifacts.length;
  document.getElementById('stat-items').textContent = DB.herbs.length + DB.minerals.length + DB.drops.length + DB.pills.length;
  document.getElementById('stat-events').textContent = DB.timeline.length;
}

// ===== NAVIGATION =====
function navigate(page) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
  const pg = document.getElementById('page-' + page);
  if (!pg) return;
  pg.classList.add('active');
  document.querySelector(`[data-page="${page}"]`)?.classList.add('active');
  currentPage = page;
  const titles = {
    home:'Trang chủ', characters:'Thư viện nhân vật', 'char-info':'Hệ tu & Chỉ số',
    weapons:'Pháp bảo trấn vật', artifacts:'Linh khí tùy thân',
    herbs:'Thảo dược', minerals:'Khoáng vật', drops:'Đồ rớt từ quái',
    pills:'Đan dược', breakthrough:'Đột phá cảnh giới', reactions:'Phản ứng nguyên tố',
    geography:'Địa lý thế giới', timeline:'Dòng thời gian', 'custom-sections':'Nhánh tùy chỉnh'
  };
  document.getElementById('topbarTitle').textContent = titles[page] || page;
  renderPage(page);
}
document.querySelectorAll('.nav-item').forEach(item => {
  item.addEventListener('click', () => navigate(item.dataset.page));
});

function renderPage(page) {
  if (page === 'characters') renderChars();
  else if (page === 'weapons') renderItems('weapon');
  else if (page === 'artifacts') renderItems('artifact');
  else if (page === 'herbs') renderItems('herb');
  else if (page === 'minerals') renderItems('mineral');
  else if (page === 'drops') renderItems('drop');
  else if (page === 'pills') renderItems('pill');
  else if (page === 'geography') renderGeo();
  else if (page === 'timeline') renderTimeline();
  else if (page === 'reactions') renderReactions();
  else if (page === 'custom-sections') renderCustomSections();
}

// ===== EDIT MODE =====
function toggleEditMode() {
  if (!editMode) {
    document.getElementById('passModal').style.display = 'flex';
    document.getElementById('passInput').value = '';
    document.getElementById('passError').textContent = '';
    setTimeout(() => document.getElementById('passInput').focus(), 100);
  } else {
    editMode = false;
    updateEditUI();
    showToast('Đã tắt chế độ chỉnh sửa', 'info');
  }
}
function checkPass() {
  const v = document.getElementById('passInput').value;
  if (v === DB.pass) {
    editMode = true;
    closePassModal();
    updateEditUI();
    showToast('Chế độ chỉnh sửa đã bật', 'success');
  } else {
    document.getElementById('passError').textContent = 'Mật khẩu không đúng!';
    document.getElementById('passInput').value = '';
  }
}
function closePassModal() { document.getElementById('passModal').style.display = 'none'; }
function updateEditUI() {
  const btn = document.getElementById('editModeBtn');
  btn.classList.toggle('active', editMode);
  document.getElementById('editBtnText').textContent = editMode ? 'Đang chỉnh sửa' : 'Chế độ chỉnh sửa';
  document.querySelectorAll('.add-btn').forEach(b => b.classList.toggle('hidden', !editMode));
  document.body.classList.toggle('edit-mode', editMode);
  if (currentDetailItem) {
    document.getElementById('detailEditBtn').classList.toggle('hidden', !editMode);
    document.getElementById('detailDeleteBtn').classList.toggle('hidden', !editMode);
  }
  renderPage(currentPage);
}

// ===== IMAGE UPLOAD =====
function handleImageUpload(file, callback) {
  const reader = new FileReader();
  reader.onload = e => callback(e.target.result);
  reader.readAsDataURL(file);
}
function makeImageUpload(id, currentSrc) {
  return `
    <div class="img-upload-wrap">
      <div class="img-preview" id="prev_${id}" onclick="document.getElementById('file_${id}').click()">
        ${currentSrc ? `<img src="${currentSrc}" id="previewImg_${id}">` : `<span class="placeholder-text">Nhấn để chọn ảnh</span>`}
      </div>
      <input type="file" accept="image/*" class="img-upload-input" id="file_${id}" onchange="previewUpload('${id}')">
      <input type="hidden" id="f_${id}" value="${currentSrc || ''}">
    </div>`;
}
function previewUpload(id) {
  const file = document.getElementById('file_' + id)?.files[0];
  if (!file) return;
  handleImageUpload(file, src => {
    document.getElementById('f_' + id).value = src;
    const prev = document.getElementById('prev_' + id);
    prev.innerHTML = `<img src="${src}">`;
  });
}

// ===== CHAR RENDER =====
const elementColors = {
  'Kim':'#8a8a8a','Mộc':'#2E6644','Thủy':'#2A5070','Hỏa':'#A03030',
  'Thổ':'#7A5C2E','Phong':'#3E6B55','Lôi':'#6B4A9E','Băng':'#2A6070',
  'Độc':'#4A6A1A','Ám':'#3A2060','Quang':'#9B6B1A'
};

function renderChars() {
  const q = (document.getElementById('charSearch')?.value || '').toLowerCase();
  let data = DB.characters.filter(c => {
    if (charFilter !== 'all' && String(c.stars) !== charFilter) return false;
    if (q && !c.name?.toLowerCase().includes(q) && !c.element?.toLowerCase().includes(q)) return false;
    return true;
  });
  const grid = document.getElementById('charGrid');
  const tbody = document.getElementById('charTableBody');
  const empty = document.getElementById('charEmpty');
  grid.innerHTML = ''; tbody.innerHTML = '';
  if (data.length === 0) { empty.style.display = 'block'; return; }
  empty.style.display = 'none';
  data.forEach(c => {
    const stars = c.stars==5?'★★★★★':c.stars==4?'★★★★':'★★★';
    const col = elementColors[c.element] || 'var(--accent)';
    const card = document.createElement('div');
    card.className = 'char-card'; card.onclick = () => openCharDetail(c);
    card.innerHTML = `
      <div class="char-card-img">
        ${c.image ? `<img src="${c.image}" alt="${c.name}">` : `<span class="placeholder-text">Chưa có ảnh</span>`}
      </div>
      <div class="rarity-bar ${c.stars==5?'rarity-5':c.stars==4?'rarity-4':'rarity-3'}"></div>
      <div class="char-card-info">
        <div class="char-card-name">${c.name||'???'}</div>
        <div class="char-card-meta">
          <span class="char-element-tag" style="color:${col};border-color:${col}55">${c.element||'?'}</span>
          <span class="char-stars ${c.stars==4?'s4':''}">${stars}</span>
        </div>
      </div>`;
    grid.appendChild(card);
    const tr = document.createElement('tr');
    tr.onclick = () => openCharDetail(c);
    tr.innerHTML = `<td><b>${c.name||'???'}</b>${c.title?` <span style="color:var(--text-3);font-size:11px;font-style:italic"> — ${c.title}</span>`:''}</td>
    <td><span style="color:${c.stars==5?'#9B6B1A':'#6B4A9E'}">${stars}</span></td>
    <td><span style="color:${col};font-weight:600">${c.element||'—'}</span></td>
    <td>${c.cultivation||'—'}</td><td>${c.weaponGroup?c.weaponGroup+(c.weaponSubtype?' / '+c.weaponSubtype:''):c.weaponSubtype||'—'}</td><td>${c.realm||'—'}</td><td>${c.patch||'—'}</td>`;
    tbody.appendChild(tr);
  });
}
function filterChars() { renderChars(); }
function setCharFilter(el, f) {
  document.querySelectorAll('#page-characters .filter-btn[data-filter]').forEach(b => b.classList.remove('active'));
  el.classList.add('active'); charFilter = f; renderChars();
}
function setCharView(v, el) {
  charView = v;
  document.querySelectorAll('.view-btn').forEach(b => b.classList.remove('active'));
  el.classList.add('active');
  document.getElementById('charGridView').style.display = v==='grid'?'block':'none';
  document.getElementById('charTableView').style.display = v==='table'?'block':'none';
}

// ===== ITEMS =====
const itemDB = {weapon:'weapons',artifact:'artifacts',herb:'herbs',mineral:'minerals',drop:'drops',pill:'pills'};

function renderItems(type) {
  const key = itemDB[type];
  const q = (document.getElementById(type+'Search')?.value||'').toLowerCase();
  const data = DB[key].filter(it => {
    if (type === 'weapon' && weaponGroupFilter !== 'all' && it.weaponGroup !== weaponGroupFilter) return false;
    if (q && !it.name?.toLowerCase().includes(q)) return false;
    return true;
  });
  const grid = document.getElementById(type+'Grid');
  const empty = document.getElementById(type+'Empty');
  if (!grid) return;
  grid.innerHTML = '';
  if (data.length===0) { empty.style.display='block'; return; }
  empty.style.display='none';
  data.forEach(it => {
    const card = document.createElement('div');
    card.className = 'item-card'; card.onclick = () => openItemDetail(it, type);
    const cap = getCapBadge(it.cap);
    const pham = getPhamBadge(it.pham);
    card.innerHTML = `
      <div class="item-card-img">
        ${it.image ? `<img src="${it.image}" alt="${it.name}">` : `<span class="placeholder-text">Chưa có ảnh</span>`}
      </div>
      <div class="item-card-body">
        <div class="item-card-name">${it.name||'???'}</div>
        <div class="item-card-meta">
          ${cap}${pham}
          ${it.weaponGroup?`<span class="weapon-group-tag">${it.weaponGroup}</span>`:''}
          ${it.weaponSubtype?`<span style="font-size:10px;color:var(--text-3)">${it.weaponSubtype}</span>`:''}
          ${it.rarity?`<span style="font-size:10px;color:var(--text-3)">${it.rarity}</span>`:''}
        </div>
      </div>`;
    grid.appendChild(card);
  });
}

function getCapBadge(cap) {
  if (!cap) return '';
  const map = {'Hoàng':'rarity-huang','Huyền':'rarity-xuan','Địa':'rarity-dia','Thiên':'rarity-thien'};
  return `<span class="rarity-badge ${map[cap]||''}">${cap}</span>`;
}
function getPhamBadge(pham) {
  if (!pham) return '';
  const map = {'Hạ phẩm':'pham-ha','Trung phẩm':'pham-trung','Thượng phẩm':'pham-thuong','Cực phẩm':'pham-cuc'};
  return `<span class="rarity-badge ${map[pham]||''}">${pham}</span>`;
}

function setWeaponGroupFilter(el, g) {
  document.querySelectorAll('#page-weapons .filter-btn[data-wg]').forEach(b => b.classList.remove('active'));
  el.classList.add('active'); weaponGroupFilter = g; renderItems('weapon');
}
function filterItems(type) { renderItems(type); }

// ===== REACTION FILTER =====
const defaultReactions = [
  {name:'Thiêu đốt',trigger:'Hỏa + Mộc',effect:'DOT — thiêu đốt sinh mệnh linh đài theo thời gian'},
  {name:'Sinh trưởng',trigger:'Mộc + Thủy',effect:'Hồi phục sinh mệnh linh đài theo thời gian'},
  {name:'Bốc hơi',trigger:'Thủy + Hỏa',effect:'Gây sát thương chuẩn theo % sinh mệnh linh đài mục tiêu'},
  {name:'Nóng chảy',trigger:'Hỏa + Kim',effect:'Giảm Phòng Ngự và Kháng Nguyên Tố mạnh trong thời gian ngắn'},
  {name:'Xói mòn',trigger:'Thổ + Thủy',effect:'Mỗi giây trừ HP và giảm Linh lực cơ bản mục tiêu'},
  {name:'Băng phong',trigger:'Thủy + Băng',effect:'Đóng băng cứng, bất động hoàn toàn'},
  {name:'Phá băng',trigger:'Băng + Kim',effect:'Gây thêm sát thương vật lý xuyên thấu và tổn thương nội tạng'},
  {name:'Tan chảy',trigger:'Băng + Hỏa',effect:'Gây sát thương chuẩn, xóa trạng thái Băng. Đang đóng băng nhận thêm x1.5'},
  {name:'Điện giải',trigger:'Lôi + Thủy',effect:'Chuỗi sét, giảm phòng thủ địch'},
  {name:'Khuếch tán',trigger:'Phong + bất kỳ (trừ Ám/Quang)',effect:'Lan rộng nguyên tố ra diện rộng'},
  {name:'Kết tinh',trigger:'Thổ + bất kỳ (trừ Ám/Quang)',effect:'Tạo khiên nguyên tố bảo hộ theo hệ'},
  {name:'Hư vô',trigger:'Ám/Quang + bất kỳ',effect:'Vô hiệu phản ứng, xóa trạng thái địch. KHÔNG thể kích ngược lại'},
];

function getAllReactions() {
  return [...defaultReactions, ...(DB.customReactions||[])];
}

function setReactionFilter(el, element) {
  document.querySelectorAll('#reactionFilterBar .filter-btn').forEach(b => b.classList.remove('active'));
  el.classList.add('active'); reactionElementFilter = element; renderReactions();
}

function renderReactions() {
  const grid = document.getElementById('reactionGrid');
  let all = getAllReactions();
  if (reactionElementFilter !== 'all') {
    all = all.filter(r => r.trigger.includes(reactionElementFilter));
  }
  grid.innerHTML = all.map((r, i) => `
    <div class="reaction-card">
      <div style="display:flex;justify-content:space-between;align-items:start">
        <div>
          <div class="reaction-name">${r.name}</div>
          <div class="reaction-trigger">${r.trigger}</div>
          <div class="reaction-effect">${r.effect}</div>
        </div>
        ${editMode && i >= defaultReactions.length ? `<button class="btn btn-danger" style="padding:2px 7px;font-size:10px;flex-shrink:0;margin-left:6px" onclick="deleteCustomReaction(${i - defaultReactions.length})">✕</button>` : ''}
      </div>
    </div>`).join('');
}
function deleteCustomReaction(i) { DB.customReactions.splice(i,1); save(); renderReactions(); }

function openReactionModal() {
  if(!editMode) return;
  modalType='reaction'; modalEditItem=null;
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent='Thêm phản ứng mới';
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section"><div class="form-section-title">Phản ứng nguyên tố</div>
    <div class="form-grid">
      <div class="form-group full"><label class="form-label">Tên phản ứng *</label><input class="form-input" id="f_name" placeholder="Ví dụ: Thiêu đốt"></div>
      <div class="form-group full"><label class="form-label">Điều kiện kích hoạt *</label><input class="form-input" id="f_trigger" placeholder="Ví dụ: Hỏa + Mộc"></div>
      <div class="form-group full"><label class="form-label">Hiệu ứng</label><textarea class="form-textarea" id="f_effect"></textarea></div>
    </div></div>`;
}

// ===== GEO =====
function renderGeo() {
  const list = document.getElementById('geoList');
  const empty = document.getElementById('geoEmpty');
  list.innerHTML = '';
  if (DB.geography.length===0) { empty.style.display='block'; return; }
  empty.style.display='none';
  DB.geography.forEach((g, gi) => {
    const div = document.createElement('div');
    div.className = 'geo-continent';
    div.innerHTML = `
      <div class="geo-continent-header" onclick="toggleGeo(${gi})">
        <div class="geo-continent-name">${g.name}</div>
        <div style="display:flex;gap:7px;align-items:center">
          ${editMode?`<button class="btn btn-primary" style="padding:3px 9px;font-size:10px" onclick="event.stopPropagation();addForce(${gi})">+ Thêm thế lực</button>
          <button class="btn btn-danger" style="padding:3px 9px;font-size:10px" onclick="event.stopPropagation();deleteGeo(${gi})">Xóa</button>`:''}
          <span id="geo-arrow-${gi}">▼</span>
        </div>
      </div>
      <div class="geo-forces" id="geo-forces-${gi}">
        ${g.desc?`<div class="info-text" style="margin-bottom:10px">${g.desc}</div>`:''}
        ${(g.forces||[]).map((f,fi) => `
          <div class="force-item">
            <div style="display:flex;justify-content:space-between;align-items:start">
              <div><div class="force-name">${f.name}</div><div class="force-desc">${f.desc||''}</div></div>
              ${editMode?`<button class="btn btn-danger" style="padding:2px 7px;font-size:10px" onclick="deleteForce(${gi},${fi})">✕</button>`:''}
            </div>
          </div>`).join('')}
        ${!(g.forces||[]).length?'<div style="color:var(--text-4);font-size:11px;font-style:italic">Chưa có thế lực nào.</div>':''}
      </div>`;
    list.appendChild(div);
  });
}
function toggleGeo(i) {
  const el = document.getElementById(`geo-forces-${i}`);
  const ar = document.getElementById(`geo-arrow-${i}`);
  const vis = el.style.display!=='none';
  el.style.display = vis?'none':'block';
  ar.textContent = vis?'▶':'▼';
}
function deleteGeo(i) { if(confirm('Xóa lục địa này?')){DB.geography.splice(i,1);save();renderGeo();} }
function addForce(gi) {
  const name=prompt('Tên thế lực:'); if(!name) return;
  const desc=prompt('Mô tả:')||'';
  DB.geography[gi].forces=DB.geography[gi].forces||[];
  DB.geography[gi].forces.push({name,desc});
  save(); renderGeo();
}
function deleteForce(gi,fi){DB.geography[gi].forces.splice(fi,1);save();renderGeo();}

// ===== TIMELINE =====
function renderTimeline() {
  const list = document.getElementById('timelineList');
  const empty = document.getElementById('timelineEmpty');
  list.innerHTML='';
  const sorted = [...DB.timeline].sort((a,b) => (a.year||'').localeCompare(b.year||''));
  if (sorted.length===0) { empty.style.display='block'; return; }
  empty.style.display='none';
  const wrap = document.createElement('div'); wrap.className='timeline-wrap';
  sorted.forEach((ev, i) => {
    const realIdx = DB.timeline.indexOf(ev);
    const div = document.createElement('div'); div.className='timeline-item';
    div.innerHTML = `
      <div class="timeline-card">
        <div class="timeline-year">${ev.year||'???'}</div>
        <div class="timeline-title">${ev.title||'Sự kiện'}</div>
        <div class="timeline-desc">${ev.desc||''}</div>
        ${ev.chars?`<div style="font-size:11px;color:var(--text-3);margin-top:5px">Nhân vật liên quan: ${ev.chars}</div>`:''}
        ${editMode?`<div style="margin-top:8px;display:flex;gap:5px">
          <button class="btn btn-ghost" style="padding:3px 9px;font-size:10px" onclick="openTimelineModal(${realIdx})">Sửa</button>
          <button class="btn btn-danger" style="padding:3px 9px;font-size:10px" onclick="deleteTimeline(${realIdx})">Xóa</button>
        </div>`:''}
      </div>`;
    wrap.appendChild(div);
  });
  list.appendChild(wrap);
}
function deleteTimeline(i){if(confirm('Xóa sự kiện?')){DB.timeline.splice(i,1);save();renderTimeline();}}

// ===== CUSTOM SECTIONS =====
function renderCustomSections() {
  const list = document.getElementById('customSectionsList');
  const empty = document.getElementById('customSectionsEmpty');
  list.innerHTML='';
  if (!DB.customSections.length) { empty.style.display='block'; return; }
  empty.style.display='none';
  DB.customSections.forEach((sec, si) => {
    const div = document.createElement('div');
    div.className = 'geo-continent';
    div.innerHTML = `
      <div class="geo-continent-header" onclick="toggleCustom(${si})">
        <div class="geo-continent-name">${sec.name}</div>
        <div style="display:flex;gap:7px;align-items:center">
          ${editMode?`<button class="btn btn-primary" style="padding:3px 9px;font-size:10px" onclick="event.stopPropagation();openCustomEntryModal(${si})">+ Thêm mục</button>
          <button class="btn btn-danger" style="padding:3px 9px;font-size:10px" onclick="event.stopPropagation();deleteCustomSection(${si})">Xóa nhánh</button>`:''}
          <span id="custom-arrow-${si}">▼</span>
        </div>
      </div>
      <div class="geo-forces" id="custom-body-${si}">
        ${sec.desc?`<div class="info-text" style="margin-bottom:10px">${sec.desc}</div>`:''}
        ${(sec.entries||[]).map((e,ei) => `
          <div class="force-item" style="cursor:pointer" onclick="openCustomEntryDetail(${si},${ei})">
            <div style="display:flex;justify-content:space-between;align-items:start">
              <div>
                <div class="force-name">${e.name}</div>
                <div class="force-desc">${e.summary||''}</div>
              </div>
              ${editMode?`<div style="display:flex;gap:4px">
                <button class="btn btn-ghost" style="padding:2px 7px;font-size:10px" onclick="event.stopPropagation();openCustomEntryModal(${si},${ei})">Sửa</button>
                <button class="btn btn-danger" style="padding:2px 7px;font-size:10px" onclick="event.stopPropagation();deleteCustomEntry(${si},${ei})">✕</button>
              </div>`:''}
            </div>
          </div>`).join('')}
        ${!(sec.entries||[]).length?'<div style="color:var(--text-4);font-size:11px;font-style:italic">Chưa có mục nào.</div>':''}
      </div>`;
    list.appendChild(div);
  });
}
function toggleCustom(i) {
  const el = document.getElementById(`custom-body-${i}`);
  const ar = document.getElementById(`custom-arrow-${i}`);
  const vis = el.style.display!=='none';
  el.style.display=vis?'none':'block';
  ar.textContent=vis?'▶':'▼';
}
function deleteCustomSection(i){if(confirm('Xóa toàn bộ nhánh này?')){DB.customSections.splice(i,1);save();renderCustomSections();}}
function deleteCustomEntry(si,ei){DB.customSections[si].entries.splice(ei,1);save();renderCustomSections();}
function openCustomEntryDetail(si,ei){
  const e = DB.customSections[si].entries[ei];
  const sec = DB.customSections[si];
  currentDetailItem = {_si:si,_ei:ei,...e}; currentDetailType='customEntry';
  document.getElementById('detailOverlay').style.display='block';
  document.getElementById('detailPanel').style.display='block';
  document.getElementById('detailPanelTitle').textContent=e.name;
  document.getElementById('detailEditBtn').classList.toggle('hidden',!editMode);
  document.getElementById('detailDeleteBtn').classList.toggle('hidden',!editMode);
  document.getElementById('detailEditBtn').onclick=()=>{closeDetail();openCustomEntryModal(si,ei);};
  document.getElementById('detailDeleteBtn').onclick=()=>{deleteCustomEntry(si,ei);closeDetail();renderCustomSections();};
  let html=`<div class="section-card">`;
  html+=`<div class="section-title">${sec.name} — Chi tiết</div>`;
  if(e.image) html+=`<div style="margin-bottom:12px"><img src="${e.image}" style="max-width:100%;border:1px solid var(--border)"></div>`;
  html+=`<div class="field-full"><div class="field-label">Tên</div><div class="field-value">${e.name}</div></div>`;
  if(e.summary) html+=`<div class="field-full"><div class="field-label">Tóm tắt</div><div class="field-value">${e.summary}</div></div>`;
  if(e.content) html+=`<div class="field-full"><div class="field-label">Nội dung chi tiết</div><div class="field-value" style="line-height:1.8">${e.content.replace(/\n/g,'<br>')}</div></div>`;
  html+=`</div>`;
  document.getElementById('detailContent').innerHTML=html;
}

// ===== DETAIL CHAR =====
function openCharDetail(c) {
  currentDetailItem=c; currentDetailType='character';
  document.getElementById('detailOverlay').style.display='block';
  document.getElementById('detailPanel').style.display='block';
  document.getElementById('detailPanelTitle').textContent=c.name||'Nhân vật';
  document.getElementById('detailEditBtn').classList.toggle('hidden',!editMode);
  document.getElementById('detailDeleteBtn').classList.toggle('hidden',!editMode);
  document.getElementById('detailEditBtn').onclick=()=>{closeDetail();openCharModal(c);};
  document.getElementById('detailDeleteBtn').onclick=()=>deleteChar(c);
  const col = elementColors[c.element]||'var(--accent)';
  const stars = c.stars==5?'★★★★★':c.stars==4?'★★★★':'★★★';
  let html = `
    <div class="char-detail-hero">
      <div class="char-detail-avatar">
        ${c.image?`<img src="${c.image}" alt="${c.name}">`:`<span class="placeholder-text">Chưa có ảnh</span>`}
      </div>
      <div style="flex:1">
        <div class="char-detail-name">${c.name||'???'}</div>
        ${c.title?`<div class="char-detail-title">${c.title}</div>`:''}
        ${c.realName?`<div style="font-size:11.5px;color:var(--text-3);margin-top:2px">Tên thật: ${c.realName}</div>`:''}
        ${c.alias?`<div style="font-size:11px;color:var(--text-4);margin-top:1px">Biệt danh: ${c.alias}</div>`:''}
        ${c.rank?`<div style="font-size:11px;color:var(--text-3);margin-top:1px">Chức vị: ${c.rank}</div>`:''}
        <div class="char-detail-tags">
          ${c.element?`<span class="tag" style="color:${col};border-color:${col}55">${c.element}</span>`:''}
          <span class="tag gold">${stars}</span>
          ${c.cultivation?`<span class="tag">${c.cultivation}</span>`:''}
          ${c.weaponGroup?`<span class="tag">${c.weaponGroup}</span>`:''}
          ${c.realm?`<span class="tag gold">${c.realm}</span>`:''}
          ${c.race?`<span class="tag">${c.race}</span>`:''}
          ${c.faction?`<span class="tag">${c.faction}</span>`:''}
          ${c.patch?`<span class="tag" style="font-size:9px;color:var(--text-4)">v${c.patch}</span>`:''}
        </div>
      </div>
    </div>`;

  // Basic info
  const basicFields = [
    ['Giới tính',c.gender],['Chủng tộc',c.race],['Gia tộc / Môn phái gốc',c.clan],
    ['Sư phụ / Tổ sư',c.master],['Thế giới / Đại lục',c.world],
    ['Tuổi thực',c.age],['Ngoại hình trông như',c.ageAppear?c.ageAppear+' tuổi':null],
    ['Quê quán / Nguồn gốc',c.hometown],['Màu tóc',c.hairColor],
    ['Đồng tử',c.eyeColor],['Chiều cao / Thể hình',c.height],
    ['Trang phục đặc trưng',c.clothing],['Ấn ký / Dấu hiệu',c.markings],
    ['Vật phẩm luôn mang theo',c.items],['Giọng nói',c.voiceType],['Phong thái',c.aura]
  ].filter(([,v])=>v);
  if(basicFields.length){
    html+=`<div class="section-card"><div class="section-title">Thông tin cơ bản</div><div class="field-grid">`;
    basicFields.forEach(([k,v])=>{ html+=`<div class="field-item"><div class="field-label">${k}</div><div class="field-value">${v}</div></div>`; });
    html+=`</div></div>`;
  }

  // Stats
  const statFields=[['Sinh mệnh linh đài (HP)',c.hp],['Linh lực cơ bản (ATK)',c.atk],['Thể phách trấn áp (DEF)',c.def],
    ['Nguyên tinh thông (EM)',c.em],['Nạp linh lực (%)',c.energyRecharge],
    ['Tỷ lệ bạo kích',c.crit],['Sát thương bạo kích',c.cdmg],
    ['Tăng sát thương hệ',c.eleDmg],['Tốc độ tụ linh / Tốc công',c.atkSpeed],
    ['Kháng nguyên tố',c.eleRes],['Thấu linh / Xuyên phòng',c.penetrate],
    ['Chỉ số chữa lành',c.heal],['Chỉ số đặc biệt',c.special]].filter(([,v])=>v);
  if(statFields.length){
    html+=`<div class="section-card"><div class="section-title">Chỉ số thuộc tính</div>`;
    statFields.forEach(([k,v])=>html+=`<div class="stat-row"><span class="stat-name">${k}</span><span class="stat-val">${v}</span></div>`);
    html+=`<div style="font-size:11px;color:var(--text-4);margin-top:8px;font-style:italic">Chỉ số cơ bản tăng theo cảnh giới. Ngoài HP/ATK/DEF, mỗi nhân vật có 1 chỉ số phụ đặc trưng.</div></div>`;
  }

  // Combat
  if(c.normalAtk||c.skillE||c.skillQ||c.passive1||c.passive2){
    html+=`<div class="section-card"><div class="section-title">Kỹ năng chiến đấu</div>`;
    if(c.normalAtk){
      html+=`<div class="skill-card"><div class="skill-type">Tấn công thường</div><div class="skill-name">${c.normalAtk}</div>`;
      const hits=['hit1','hit2','hit3','hit4','hit5'].filter(h=>c[h]);
      if(hits.length) html+=`<div class="skill-desc">${hits.map((h,i)=>`<b>Đòn ${i+1}:</b> ${c[h]}`).join('<br>')}</div>`;
      if(c.charged) html+=`<div class="skill-desc"><b>Trọng kích:</b> ${c.charged}</div>`;
      if(c.plunge) html+=`<div class="skill-desc"><b>Tấn công rơi:</b> ${c.plunge}</div>`;
      if(c.normalDesc) html+=`<div class="skill-desc" style="margin-top:4px">${c.normalDesc}</div>`;
      html+=`</div>`;
    }
    if(c.skillE){
      html+=`<div class="skill-card"><div class="skill-type">Kỹ năng chiến thuật (E)</div><div class="skill-name">${c.skillE}</div>`;
      if(c.skillEEffect) html+=`<div style="font-size:10px;color:var(--accent3);margin-bottom:3px">${c.skillEEffect}</div>`;
      if(c.skillECd) html+=`<div style="font-size:10.5px;color:var(--text-3)">CD: ${c.skillECd} | NL tạo ra: ${c.skillEEnergy||'—'}</div>`;
      if(c.skillEDesc) html+=`<div class="skill-desc" style="margin-top:4px">${c.skillEDesc}</div>`;
      html+=`</div>`;
    }
    if(c.skillQ){
      html+=`<div class="skill-card"><div class="skill-type">Đại thần thông (Q — Tuyệt kỹ)</div><div class="skill-name">${c.skillQ}</div>`;
      if(c.skillQCost) html+=`<div style="font-size:10.5px;color:var(--text-3)">NL yêu cầu: ${c.skillQCost} | CD: ${c.skillQCd||'—'} | Thời gian: ${c.skillQDur||'—'}</div>`;
      if(c.skillQDesc) html+=`<div class="skill-desc" style="margin-top:4px">${c.skillQDesc}</div>`;
      html+=`</div>`;
    }
    if(c.passive1||c.passive2||c.passive3){
      html+=`<div class="skill-card"><div class="skill-type">Bị động tu tiên</div>
      ${c.passive1?`<div class="skill-desc"><b>Lv.20:</b> ${c.passive1}</div>`:''}
      ${c.passive2?`<div class="skill-desc" style="margin-top:5px"><b>Lv.60:</b> ${c.passive2}</div>`:''}
      ${c.passive3?`<div class="skill-desc" style="margin-top:5px"><b>Ngoài chiến đấu:</b> ${c.passive3}</div>`:''}
      </div>`;
    }
    html+=`</div>`;
  }

  // Constellations
  const consts = [c.c1,c.c2,c.c3,c.c4,c.c5,c.c6].filter(Boolean);
  if(consts.length){
    html+=`<div class="section-card"><div class="section-title">Tinh tú đạo mạch (C1–C6)</div><div class="constellation-grid">`;
    [c.c1,c.c2,c.c3,c.c4,c.c5,c.c6].forEach((ct,i)=>{
      const conds=['Gacha lần 1','Gacha lần 2','Gacha lần 3','Gacha lần 4','Gacha lần 5','Gacha lần 6 — Tối thượng'];
      html+=`<div class="const-item"><div class="const-level">C${i+1} <span style="font-weight:400;opacity:.7">${conds[i]}</span></div><div class="const-desc">${ct||'—'}</div></div>`;
    });
    html+=`</div></div>`;
  }

  // Story of life
  if(c.mainStory||c.subStory1||c.storyArc||c.conflict||c.resolution){
    html+=`<div class="section-card"><div class="section-title">Câu chuyện cuộc đời</div>`;
    if(c.mainStory) html+=`<div class="story-block"><div class="story-block-title">Cốt truyện chính</div><div class="story-block-content">${c.mainStory.replace(/\n/g,'<br>')}</div></div>`;
    if(c.subStory1) html+=`<div class="story-block"><div class="story-block-title">Mẫu chuyện phụ 1</div><div class="story-block-content">${c.subStory1.replace(/\n/g,'<br>')}</div></div>`;
    if(c.subStory2) html+=`<div class="story-block"><div class="story-block-title">Mẫu chuyện phụ 2</div><div class="story-block-content">${c.subStory2.replace(/\n/g,'<br>')}</div></div>`;
    if(c.storyArc) html+=`<div class="story-block"><div class="story-block-title">Story Arc cá nhân</div><div class="story-block-content">${c.storyArc}</div></div>`;
    if(c.conflict) html+=`<div class="story-block"><div class="story-block-title">Xung đột / Đối thủ</div><div class="story-block-content">${c.conflict}</div></div>`;
    if(c.resolution) html+=`<div class="story-block"><div class="story-block-title">Kết cục / Resolution</div><div class="story-block-content">${c.resolution}</div></div>`;
    html+=`</div>`;
  }

  // Personality & Background
  if(c.background||c.personality||c.goal||c.secret||c.worldview||c.likes||c.dislikes||c.fear||c.food){
    html+=`<div class="section-card"><div class="section-title">Lý lịch &amp; Cá tính</div>`;
    if(c.background) html+=`<div class="field-full"><div class="field-label">Xuất thân / Gia tộc</div><div class="field-value" style="margin-top:4px;line-height:1.8">${c.background.replace(/\n/g,'<br>')}</div></div>`;
    if(c.personality) html+=`<div class="field-full"><div class="field-label">Tính cách</div><div class="field-value" style="margin-top:4px;line-height:1.8">${c.personality.replace(/\n/g,'<br>')}</div></div>`;
    if(c.worldview) html+=`<div class="field-full"><div class="field-label">Thế giới quan</div><div class="field-value" style="margin-top:4px;line-height:1.8">${c.worldview.replace(/\n/g,'<br>')}</div></div>`;
    const miniFields=[['Mục tiêu cốt lõi',c.goal],['Bí mật',c.secret],['Vết thương tâm lý',c.trauma],['Sở thích',c.likes],['Ghét / Kỵ húy',c.dislikes],['Sợ nhất',c.fear],['Món ăn yêu thích',c.food]].filter(([,v])=>v);
    if(miniFields.length){
      html+=`<div class="field-grid" style="margin-top:8px">`;
      miniFields.forEach(([k,v])=>html+=`<div class="field-item"><div class="field-label">${k}</div><div class="field-value">${v}</div></div>`);
      html+=`</div>`;
    }
    html+=`</div>`;
  }

  // Relationships
  if(c.relationships||c.trusted||c.enemy) html+=`<div class="section-card"><div class="section-title">Tuyến quan hệ</div>
    ${c.relationships?`<div class="field-full"><div class="field-label">Bảng quan hệ</div><div class="field-value" style="line-height:1.9;margin-top:4px">${c.relationships.replace(/\n/g,'<br>')}</div></div>`:''} 
    ${c.trusted?`<div class="field-full"><div class="field-label">Người tin tưởng nhất</div><div class="field-value">${c.trusted}</div></div>`:''}
    ${c.enemy?`<div class="field-full"><div class="field-label">Kẻ thù / Đối thủ truyền kiếp</div><div class="field-value">${c.enemy}</div></div>`:''}
    </div>`;

  // Voice lines
  if(c.voiceGreet||c.voiceIntro||c.voiceJoin||c.voiceBreakthrough||c.voiceLowHP||c.voiceDefeated||c.voiceSkillE||c.voiceSkillQ||c.voiceCrit||c.voiceSelf||c.voiceWorld||c.voiceKey){
    html+=`<div class="section-card"><div class="section-title">Thoại đặc trưng</div>`;
    const vl = [
      ['Chào hỏi lần đầu',c.voiceGreet],['Giới thiệu bản thân',c.voiceIntro],
      ['Khi thêm vào đội',c.voiceJoin],['Khi đột phá cảnh giới',c.voiceBreakthrough],
      ['Khi HP thấp',c.voiceLowHP],['Khi bị đánh bại',c.voiceDefeated],
      ['Khi dùng kỹ năng E',c.voiceSkillE],['Khi dùng tuyệt kỹ Q',c.voiceSkillQ],
      ['Khi bạo kích liên tiếp',c.voiceCrit],
      ['Về bản thân',c.voiceSelf],['Về thế giới / thời thế',c.voiceWorld],['Về nhân vật quan trọng nhất',c.voiceKey]
    ].filter(([,v])=>v);
    vl.forEach(([k,v])=>html+=`<div class="voice-line"><div class="voice-label">${k}</div><div class="voice-text">"${v}"</div></div>`);
    html+=`</div>`;
  }

  // Special ability + Ascension
  if(c.uniqueAbility||c.mat1||c.mat2||c.mat3||c.skillMat1||c.skillMat2||c.skillMat3){
    html+=`<div class="section-card"><div class="section-title">Thần thông &amp; Nguyên liệu</div>`;
    if(c.uniqueAbility) html+=`<div class="field-full"><div class="field-label">Thần thông bản mệnh: ${c.uniqueAbilityName||''}</div><div class="field-value" style="margin-top:4px">${c.uniqueAbility}</div></div>`;
    if(c.uniqueCondition) html+=`<div class="field-full"><div class="field-label">Điều kiện khai mở</div><div class="field-value">${c.uniqueCondition}</div></div>`;
    const matFields=[['Nguyên liệu quái rơi',c.mat1],['Nguyên liệu boss rơi',c.mat2],['Kỳ trân dị bảo',c.mat3],['Sách kỹ năng',c.skillMat1],['Boss vật liệu kỹ năng',c.skillMat2],['Nguyên liệu thường',c.skillMat3]].filter(([,v])=>v);
    if(matFields.length){html+=`<div class="field-grid" style="margin-top:8px">`;matFields.forEach(([k,v])=>html+=`<div class="field-item"><div class="field-label">${k}</div><div class="field-value">${v}</div></div>`);html+=`</div>`;}
    html+=`</div>`;
  }

  // Notes
  if(c.notes) html+=`<div class="section-card"><div class="section-title">Ghi chú thiết kế</div><div class="field-value" style="line-height:1.8">${c.notes.replace(/\n/g,'<br>')}</div></div>`;

  document.getElementById('detailContent').innerHTML=html;
}

// ===== ITEM DETAIL =====
function openItemDetail(it, type) {
  currentDetailItem=it; currentDetailType=type;
  document.getElementById('detailOverlay').style.display='block';
  document.getElementById('detailPanel').style.display='block';
  document.getElementById('detailPanelTitle').textContent=it.name||'???';
  document.getElementById('detailEditBtn').classList.toggle('hidden',!editMode);
  document.getElementById('detailDeleteBtn').classList.toggle('hidden',!editMode);
  document.getElementById('detailEditBtn').onclick=()=>{closeDetail();openItemModal(type,it);};
  document.getElementById('detailDeleteBtn').onclick=()=>{deleteItem(type,it);closeDetail();};
  const capBadge = getCapBadge(it.cap);
  const phamBadge = getPhamBadge(it.pham);
  let html=`<div style="display:flex;gap:15px;align-items:flex-start;margin-bottom:18px;padding:18px;background:var(--bg-card);border:1px solid var(--border)">
    <div style="width:85px;height:85px;background:var(--bg-panel);border:1px solid var(--border);overflow:hidden;flex-shrink:0;display:flex;align-items:center;justify-content:center">
      ${it.image?`<img src="${it.image}" style="width:100%;height:100%;object-fit:cover">`:`<span style="font-size:10px;color:var(--text-4);font-style:italic;text-align:center;padding:6px">Chưa có ảnh</span>`}
    </div>
    <div>
      <div style="font-family:'Noto Serif SC',serif;font-size:20px;font-weight:700;color:var(--text);letter-spacing:1px">${it.name||'???'}</div>
      <div style="margin-top:5px;display:flex;gap:5px;flex-wrap:wrap;align-items:center">
        ${capBadge}${phamBadge}
        ${it.weaponGroup?`<span class="weapon-group-tag">${it.weaponGroup}</span>`:''}
        ${it.weaponSubtype?`<span class="tag">${it.weaponSubtype}</span>`:''}
        ${it.rarity?`<span class="tag">${it.rarity}</span>`:''}
      </div>
    </div>
  </div>`;
  const fieldMap = [
    ['Chỉ số chính',it.mainStat],['Chỉ số phụ',it.subStat],['Kỹ năng vũ khí',it.skill],
    ['Tính chất dược liệu',it.herbNature],['Đặc điểm hình thái',it.herbShape],
    ['Nguồn gốc / Rớt từ',it.origin||it.dropFrom],['Có thể tìm ở',it.location],
    ['Công dụng',it.use],['Công dụng Y học',it.medicineUse],['Công dụng luyện đan',it.alchemyUse],
    ['Hiệu ứng 2 món',it.set2],['Hiệu ứng 4 món',it.set4],
    ['Mô tả / Lore',it.desc],['Ghi chú',it.notes]
  ].filter(([,v])=>v);
  if(fieldMap.length){
    html+=`<div class="section-card">`;
    fieldMap.forEach(([k,v])=>{html+=`<div class="field-full" style="margin-bottom:9px"><div class="field-label">${k}</div><div class="field-value" style="margin-top:3px;line-height:1.7">${v}</div></div>`;});
    html+=`</div>`;
  }
  document.getElementById('detailContent').innerHTML=html;
}

function closeDetail(){
  document.getElementById('detailOverlay').style.display='none';
  document.getElementById('detailPanel').style.display='none';
  currentDetailItem=null; currentDetailType=null;
}
function deleteChar(c){if(!confirm(`Xóa nhân vật "${c.name}"?`))return;DB.characters=DB.characters.filter(x=>x!==c);save();closeDetail();renderChars();}
function deleteItem(type,it){const key=itemDB[type];DB[key]=DB[key].filter(x=>x!==it);save();renderItems(type);}

// ===== WEAPON SUBTYPE SELECT =====
function updateWeaponSubtypes() {
  const grp = document.getElementById('f_weaponGroup')?.value||'';
  const sub = document.getElementById('f_weaponSubtype');
  if(!sub) return;
  const opts = WEAPON_GROUPS[grp]||[];
  sub.innerHTML=`<option value="">—</option>`+opts.map(o=>`<option>${o}</option>`).join('');
}

// ===== OPEN CHAR MODAL =====
function openCharModal(edit) {
  if(!editMode) return;
  modalType='character'; modalEditItem=edit||null;
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent=edit?'Chỉnh sửa nhân vật':'Thêm nhân vật mới';
  const c=edit||{};
  const now = new Date().toISOString().slice(0,10);
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section">
      <div class="form-section-title">01 — Hình ảnh</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Ảnh đại diện (1:1)</label>${makeImageUpload('image', c.image)}</div>
        <div class="form-group"><label class="form-label">Ảnh full body / banner</label>${makeImageUpload('banner', c.banner)}</div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">02 — Nhận dạng &amp; Danh hiệu</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Tên nhân vật *</label><input class="form-input" id="f_name" value="${c.name||''}"></div>
        <div class="form-group"><label class="form-label">Đạo hiệu / Danh hiệu</label><input class="form-input" id="f_title" value="${c.title||''}"></div>
        <div class="form-group"><label class="form-label">Tên thật</label><input class="form-input" id="f_realName" value="${c.realName||''}"></div>
        <div class="form-group"><label class="form-label">Biệt danh / Tục danh</label><input class="form-input" id="f_alias" value="${c.alias||''}"></div>
        <div class="form-group"><label class="form-label">Chức vị / Địa vị</label><input class="form-input" id="f_rank" value="${c.rank||''}"></div>
        <div class="form-group"><label class="form-label">Số sao</label>
          <select class="form-select" id="f_stars">
            <option value="5" ${c.stars==5||!c.stars?'selected':''}>5 sao</option>
            <option value="4" ${c.stars==4?'selected':''}>4 sao</option>
            <option value="3" ${c.stars==3?'selected':''}>3 sao</option>
          </select></div>
        <div class="form-group"><label class="form-label">Giới tính</label>
          <select class="form-select" id="f_gender">
            <option value="">—</option>
            ${['Nam','Nữ','Vô tướng','Biến hóa'].map(r=>`<option ${c.gender===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Chủng tộc</label>
          <select class="form-select" id="f_race">
            <option value="">—</option>
            ${['Nhân tộc','Yêu tộc','Tiên tộc','Ma tộc','Thần minh','Quỷ tộc','Thú tộc','Lai huyết','Thần thú','Cổ sinh vật'].map(r=>`<option ${c.race===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Gia tộc / Môn phái gốc</label><input class="form-input" id="f_clan" value="${c.clan||''}"></div>
        <div class="form-group"><label class="form-label">Thế giới / Đại lục</label><input class="form-input" id="f_world" value="${c.world||''}"></div>
        <div class="form-group"><label class="form-label">Quê quán / Nguồn gốc</label><input class="form-input" id="f_hometown" value="${c.hometown||''}"></div>
        <div class="form-group"><label class="form-label">Tuổi thực (niên kỷ tu luyện)</label><input class="form-input" id="f_age" value="${c.age||''}"></div>
        <div class="form-group"><label class="form-label">Ngoại hình trông như (tuổi)</label><input class="form-input" id="f_ageAppear" placeholder="Ví dụ: 20" value="${c.ageAppear||''}"></div>
        <div class="form-group"><label class="form-label">Patch / Phiên bản</label><input class="form-input" id="f_patch" value="${c.patch||''}"></div>
        <div class="form-group"><label class="form-label">Ngày tạo</label><input class="form-input" type="date" id="f_createdAt" value="${c.createdAt||now}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">03 — Ngoại hình chi tiết</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Màu / Kiểu tóc</label><input class="form-input" id="f_hairColor" value="${c.hairColor||''}"></div>
        <div class="form-group"><label class="form-label">Đồng tử (màu, hình dạng)</label><input class="form-input" id="f_eyeColor" value="${c.eyeColor||''}"></div>
        <div class="form-group"><label class="form-label">Chiều cao / Thể hình</label><input class="form-input" id="f_height" value="${c.height||''}"></div>
        <div class="form-group"><label class="form-label">Trang phục đặc trưng</label><input class="form-input" id="f_clothing" value="${c.clothing||''}"></div>
        <div class="form-group"><label class="form-label">Ấn ký / Dấu hiệu trên cơ thể</label><input class="form-input" id="f_markings" value="${c.markings||''}"></div>
        <div class="form-group"><label class="form-label">Vật phẩm luôn mang theo</label><input class="form-input" id="f_items" value="${c.items||''}"></div>
        <div class="form-group"><label class="form-label">Giọng nói</label><input class="form-input" id="f_voiceType" value="${c.voiceType||''}"></div>
        <div class="form-group"><label class="form-label">Phong thái / Khí chất</label><input class="form-input" id="f_aura" value="${c.aura||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">04 — Linh căn &amp; Hệ nguyên tố</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Hệ nguyên tố (linh căn chính)</label>
          <select class="form-select" id="f_element">
            <option value="">—</option>
            ${['Kim','Mộc','Thủy','Hỏa','Thổ','Phong','Lôi','Băng','Độc','Quang','Ám'].map(e=>`<option ${c.element===e?'selected':''}>${e}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Màu sắc nguyên tố</label><input class="form-input" id="f_elementColor" value="${c.elementColor||''}"></div>
        <div class="form-group full"><label class="form-label">Hình dạng đặc trưng khi thi triển</label><input class="form-input" id="f_elementShape" value="${c.elementShape||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">05 — Môn phái &amp; Hệ tu</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Hệ tu chính</label>
          <select class="form-select" id="f_cultivation">
            <option value="">—</option>
            ${['Kiếm Tu','Khí Tu','Đan Tu','Trận Tu','Thể Tu','Ma Tu','Thần Tu','Ẩn Tu'].map(ct=>`<option ${c.cultivation===ct?'selected':''}>${ct}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Tên môn phái / Tổ chức</label><input class="form-input" id="f_faction" value="${c.faction||''}"></div>
        <div class="form-group"><label class="form-label">Sư phụ / Tổ sư</label><input class="form-input" id="f_master" value="${c.master||''}"></div>
        <div class="form-group"><label class="form-label">Pháp môn bí truyền</label><input class="form-input" id="f_secretArt" value="${c.secretArt||''}"></div>
        <div class="form-group"><label class="form-label">Vai trò chiến đấu</label>
          <select class="form-select" id="f_role">
            <option value="">—</option>
            ${['DPS','Sub-DPS','Support','Heal','Tank','Buff','Debuff','CC','Assassin'].map(r=>`<option ${c.role===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group full"><label class="form-label">Phong cách / Mô tả chiến đấu</label><textarea class="form-textarea" style="min-height:55px" id="f_fightStyle">${c.fightStyle||''}</textarea></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">06 — Pháp bảo &amp; Vũ khí</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Nhóm vũ khí lớn</label>
          <select class="form-select" id="f_weaponGroup" onchange="updateWeaponSubtypes()">
            <option value="">—</option>
            ${Object.keys(WEAPON_GROUPS).map(g=>`<option ${c.weaponGroup===g?'selected':''}>${g}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Loại vũ khí cụ thể</label>
          <select class="form-select" id="f_weaponSubtype">
            <option value="">—</option>
            ${(WEAPON_GROUPS[c.weaponGroup]||[]).map(s=>`<option ${c.weaponSubtype===s?'selected':''}>${s}</option>`).join('')}
          </select></div>
        <div class="form-group full"><label class="form-label">Tên pháp bảo trấn vật</label><input class="form-input" id="f_weaponName" value="${c.weaponName||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">07 — Cảnh giới &amp; Chỉ số</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Cảnh giới hiện tại</label>
          <select class="form-select" id="f_realm">
            <option value="">—</option>
            ${['Luyện Khí','Trúc Cơ','Kết Đan','Nguyên Anh','Hóa Thần','Luyện Hư','Đại Thừa','Độ Kiếp'].map(r=>`<option ${c.realm===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Chỉ số phụ đặc trưng (tăng theo cảnh giới)</label>
          <select class="form-select" id="f_bonusStat">
            <option value="">—</option>
            ${['Nguyên tinh thông (EM)','Nạp linh lực (%)','Tỷ lệ bạo kích (CRIT%)','Sát thương bạo kích (CDMG%)','HP%','ATK%','DEF%'].map(r=>`<option ${c.bonusStat===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
      </div>
      <div class="form-grid cols3" style="margin-top:10px">
        <div class="form-group"><label class="form-label">HP</label><input class="form-input" id="f_hp" value="${c.hp||''}"></div>
        <div class="form-group"><label class="form-label">ATK</label><input class="form-input" id="f_atk" value="${c.atk||''}"></div>
        <div class="form-group"><label class="form-label">DEF</label><input class="form-input" id="f_def" value="${c.def||''}"></div>
        <div class="form-group"><label class="form-label">Nguyên tinh thông (EM)</label><input class="form-input" id="f_em" value="${c.em||''}"></div>
        <div class="form-group"><label class="form-label">Nạp linh lực (%)</label><input class="form-input" id="f_energyRecharge" value="${c.energyRecharge||''}"></div>
        <div class="form-group"><label class="form-label">Tỷ lệ bạo kích</label><input class="form-input" id="f_crit" placeholder="5%" value="${c.crit||''}"></div>
        <div class="form-group"><label class="form-label">Sát thương bạo kích</label><input class="form-input" id="f_cdmg" placeholder="50%" value="${c.cdmg||''}"></div>
        <div class="form-group"><label class="form-label">Tăng sát thương hệ (%)</label><input class="form-input" id="f_eleDmg" value="${c.eleDmg||''}"></div>
        <div class="form-group"><label class="form-label">Tốc độ tụ linh / Tốc công</label><input class="form-input" id="f_atkSpeed" value="${c.atkSpeed||''}"></div>
        <div class="form-group"><label class="form-label">Kháng nguyên tố (%)</label><input class="form-input" id="f_eleRes" value="${c.eleRes||''}"></div>
        <div class="form-group"><label class="form-label">Thấu linh / Xuyên phòng (%)</label><input class="form-input" id="f_penetrate" value="${c.penetrate||''}"></div>
        <div class="form-group"><label class="form-label">Chỉ số chữa lành (%)</label><input class="form-input" id="f_heal" value="${c.heal||''}"></div>
        <div class="form-group"><label class="form-label">Chỉ số đặc biệt riêng</label><input class="form-input" id="f_special" value="${c.special||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">08 — Kỹ năng chiến đấu</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Tên chuỗi tấn công thường</label><input class="form-input" id="f_normalAtk" value="${c.normalAtk||''}"></div>
        <div class="form-group"><label class="form-label">Đòn 1</label><input class="form-input" id="f_hit1" value="${c.hit1||''}"></div>
        <div class="form-group"><label class="form-label">Đòn 2</label><input class="form-input" id="f_hit2" value="${c.hit2||''}"></div>
        <div class="form-group"><label class="form-label">Đòn 3</label><input class="form-input" id="f_hit3" value="${c.hit3||''}"></div>
        <div class="form-group"><label class="form-label">Đòn 4</label><input class="form-input" id="f_hit4" value="${c.hit4||''}"></div>
        <div class="form-group"><label class="form-label">Đòn 5 (kết chuỗi)</label><input class="form-input" id="f_hit5" value="${c.hit5||''}"></div>
        <div class="form-group"><label class="form-label">Trọng kích (Charged)</label><input class="form-input" id="f_charged" value="${c.charged||''}"></div>
        <div class="form-group"><label class="form-label">Tấn công rơi (Plunge)</label><input class="form-input" id="f_plunge" value="${c.plunge||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả thêm chuỗi đánh</label><textarea class="form-textarea" style="min-height:55px" id="f_normalDesc">${c.normalDesc||''}</textarea></div>
      </div>
      <div style="margin-top:14px;padding-top:12px;border-top:1px solid var(--border)">
        <div class="form-grid">
          <div class="form-group"><label class="form-label">Tên kỹ năng E</label><input class="form-input" id="f_skillE" value="${c.skillE||''}"></div>
          <div class="form-group"><label class="form-label">Hiệu ứng E</label>
            <select class="form-select" id="f_skillEEffect">
              <option value="">—</option>
              ${['Sát thương hệ','Khiên','Dịch chuyển','Triệu hồi','Buff','Trap','Heal','CC'].map(e=>`<option ${c.skillEEffect===e?'selected':''}>${e}</option>`).join('')}
            </select></div>
          <div class="form-group"><label class="form-label">Cooldown E</label><input class="form-input" id="f_skillECd" value="${c.skillECd||''}"></div>
          <div class="form-group"><label class="form-label">NL tạo ra (E)</label><input class="form-input" id="f_skillEEnergy" value="${c.skillEEnergy||''}"></div>
          <div class="form-group full"><label class="form-label">Mô tả kỹ năng E</label><textarea class="form-textarea" id="f_skillEDesc">${c.skillEDesc||''}</textarea></div>
        </div>
      </div>
      <div style="margin-top:12px;padding-top:12px;border-top:1px solid var(--border)">
        <div class="form-grid">
          <div class="form-group"><label class="form-label">Tên tuyệt kỹ Q</label><input class="form-input" id="f_skillQ" value="${c.skillQ||''}"></div>
          <div class="form-group"><label class="form-label">NL yêu cầu (Q)</label><input class="form-input" id="f_skillQCost" value="${c.skillQCost||''}"></div>
          <div class="form-group"><label class="form-label">Cooldown Q</label><input class="form-input" id="f_skillQCd" value="${c.skillQCd||''}"></div>
          <div class="form-group"><label class="form-label">Thời gian hiệu ứng Q</label><input class="form-input" id="f_skillQDur" value="${c.skillQDur||''}"></div>
          <div class="form-group full"><label class="form-label">Mô tả tuyệt kỹ Q</label><textarea class="form-textarea" id="f_skillQDesc">${c.skillQDesc||''}</textarea></div>
        </div>
      </div>
      <div style="margin-top:12px;padding-top:12px;border-top:1px solid var(--border)">
        <div class="form-grid">
          <div class="form-group full"><label class="form-label">Bị động 1 — mở Lv.20</label><textarea class="form-textarea" style="min-height:55px" id="f_passive1">${c.passive1||''}</textarea></div>
          <div class="form-group full"><label class="form-label">Bị động 2 — mở Lv.60</label><textarea class="form-textarea" style="min-height:55px" id="f_passive2">${c.passive2||''}</textarea></div>
          <div class="form-group full"><label class="form-label">Bị động 3 — ngoài chiến đấu</label><textarea class="form-textarea" style="min-height:55px" id="f_passive3">${c.passive3||''}</textarea></div>
        </div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">09 — Tinh tú đạo mạch (C1–C6)</div>
      <div class="form-grid">
        ${[1,2,3,4,5,6].map(i=>`<div class="form-group"><label class="form-label">C${i} ${['(Gacha lần 1)','(Gacha lần 2)','(E+3, Gacha 3)','(Gacha lần 4)','(Q+3, Gacha 5)','(Tối thượng)'][i-1]}</label><textarea class="form-textarea" style="min-height:60px" id="f_c${i}">${c['c'+i]||''}</textarea></div>`).join('')}
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">10 — Câu chuyện cuộc đời</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Cốt truyện chính</label><textarea class="form-textarea" style="min-height:100px" id="f_mainStory">${c.mainStory||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Mẫu chuyện phụ 1</label><textarea class="form-textarea" style="min-height:80px" id="f_subStory1">${c.subStory1||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Mẫu chuyện phụ 2</label><textarea class="form-textarea" style="min-height:80px" id="f_subStory2">${c.subStory2||''}</textarea></div>
        <div class="form-group"><label class="form-label">Story Arc cá nhân</label><input class="form-input" id="f_storyArc" value="${c.storyArc||''}"></div>
        <div class="form-group"><label class="form-label">Điểm xung đột / Đối thủ</label><input class="form-input" id="f_conflict" value="${c.conflict||''}"></div>
        <div class="form-group full"><label class="form-label">Kết cục / Resolution</label><input class="form-input" id="f_resolution" value="${c.resolution||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">11 — Lý lịch &amp; Cá tính</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Xuất thân / Gia tộc (lý lịch)</label><textarea class="form-textarea" style="min-height:90px" id="f_background">${c.background||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Tính cách</label><textarea class="form-textarea" style="min-height:70px" id="f_personality">${c.personality||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Thế giới quan / Triết lý sống</label><textarea class="form-textarea" style="min-height:70px" id="f_worldview">${c.worldview||''}</textarea></div>
        <div class="form-group"><label class="form-label">Mục tiêu cốt lõi</label><input class="form-input" id="f_goal" value="${c.goal||''}"></div>
        <div class="form-group"><label class="form-label">Bí mật chưa ai biết</label><input class="form-input" id="f_secret" value="${c.secret||''}"></div>
        <div class="form-group"><label class="form-label">Vết thương tâm lý / Biến cố</label><input class="form-input" id="f_trauma" value="${c.trauma||''}"></div>
        <div class="form-group"><label class="form-label">Sở thích</label><input class="form-input" id="f_likes" value="${c.likes||''}"></div>
        <div class="form-group"><label class="form-label">Ghét / Kỵ húy</label><input class="form-input" id="f_dislikes" value="${c.dislikes||''}"></div>
        <div class="form-group"><label class="form-label">Sợ điều gì nhất</label><input class="form-input" id="f_fear" value="${c.fear||''}"></div>
        <div class="form-group"><label class="form-label">Món ăn yêu thích (buff nấu)</label><input class="form-input" id="f_food" value="${c.food||''}"></div>
        <div class="form-group full"><label class="form-label">Tuyến quan hệ nhân vật</label><textarea class="form-textarea" style="min-height:80px" id="f_relationships" placeholder="Ví dụ: [Tên] — Sư phụ, mối quan hệ... (mỗi người 1 dòng)">${c.relationships||''}</textarea></div>
        <div class="form-group"><label class="form-label">Người tin tưởng nhất</label><input class="form-input" id="f_trusted" value="${c.trusted||''}"></div>
        <div class="form-group"><label class="form-label">Kẻ thù / Đối thủ truyền kiếp</label><input class="form-input" id="f_enemy" value="${c.enemy||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">12 — Thoại đặc trưng (Voice Lines)</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Chào hỏi lần đầu</label><input class="form-input" id="f_voiceGreet" value="${c.voiceGreet||''}"></div>
        <div class="form-group full"><label class="form-label">Giới thiệu bản thân</label><input class="form-input" id="f_voiceIntro" value="${c.voiceIntro||''}"></div>
        <div class="form-group full"><label class="form-label">Khi thêm vào đội</label><input class="form-input" id="f_voiceJoin" value="${c.voiceJoin||''}"></div>
        <div class="form-group full"><label class="form-label">Khi đột phá cảnh giới</label><input class="form-input" id="f_voiceBreakthrough" value="${c.voiceBreakthrough||''}"></div>
        <div class="form-group full"><label class="form-label">Khi HP thấp</label><input class="form-input" id="f_voiceLowHP" value="${c.voiceLowHP||''}"></div>
        <div class="form-group full"><label class="form-label">Khi bị đánh bại</label><input class="form-input" id="f_voiceDefeated" value="${c.voiceDefeated||''}"></div>
        <div class="form-group full"><label class="form-label">Khi dùng kỹ năng E</label><input class="form-input" id="f_voiceSkillE" value="${c.voiceSkillE||''}"></div>
        <div class="form-group full"><label class="form-label">Khi dùng tuyệt kỹ Q</label><input class="form-input" id="f_voiceSkillQ" value="${c.voiceSkillQ||''}"></div>
        <div class="form-group full"><label class="form-label">Khi bạo kích liên tiếp</label><input class="form-input" id="f_voiceCrit" value="${c.voiceCrit||''}"></div>
        <div class="form-group full"><label class="form-label">Về bản thân</label><input class="form-input" id="f_voiceSelf" value="${c.voiceSelf||''}"></div>
        <div class="form-group full"><label class="form-label">Về thế giới / thời thế</label><input class="form-input" id="f_voiceWorld" value="${c.voiceWorld||''}"></div>
        <div class="form-group full"><label class="form-label">Về nhân vật quan trọng nhất</label><input class="form-input" id="f_voiceKey" value="${c.voiceKey||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">13 — Thần thông &amp; Nguyên liệu đột phá</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Tên thần thông bản mệnh</label><input class="form-input" id="f_uniqueAbilityName" value="${c.uniqueAbilityName||''}"></div>
        <div class="form-group"><label class="form-label">Điều kiện khai mở</label><input class="form-input" id="f_uniqueCondition" value="${c.uniqueCondition||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả thần thông</label><textarea class="form-textarea" style="min-height:60px" id="f_uniqueAbility">${c.uniqueAbility||''}</textarea></div>
        <div class="form-group"><label class="form-label">① Nguyên liệu quái rơi</label><input class="form-input" id="f_mat1" value="${c.mat1||''}"></div>
        <div class="form-group"><label class="form-label">② Nguyên liệu boss rơi</label><input class="form-input" id="f_mat2" value="${c.mat2||''}"></div>
        <div class="form-group"><label class="form-label">③ Kỳ trân dị bảo</label><input class="form-input" id="f_mat3" value="${c.mat3||''}"></div>
        <div class="form-group"><label class="form-label">① Sách kỹ năng</label><input class="form-input" id="f_skillMat1" value="${c.skillMat1||''}"></div>
        <div class="form-group"><label class="form-label">② Boss vật liệu kỹ năng</label><input class="form-input" id="f_skillMat2" value="${c.skillMat2||''}"></div>
        <div class="form-group"><label class="form-label">③ Nguyên liệu thường</label><input class="form-input" id="f_skillMat3" value="${c.skillMat3||''}"></div>
        <div class="form-group full"><label class="form-label">Linh khí tùy thân — Bộ 1 (4 món)</label><input class="form-input" id="f_artifactSet1" value="${c.artifactSet1||''}"></div>
        <div class="form-group full"><label class="form-label">Linh khí tùy thân — Bộ 2 (2+2 món)</label><input class="form-input" id="f_artifactSet2" value="${c.artifactSet2||''}"></div>
        <div class="form-group full"><label class="form-label">Ghi chú thiết kế tự do</label><textarea class="form-textarea" id="f_notes">${c.notes||''}</textarea></div>
      </div>
    </div>`;
}

// ===== OPEN ITEM MODAL =====
function openItemModal(type, edit) {
  if(!editMode) return;
  modalType=type; modalEditItem=edit||null;
  const typeNames={weapon:'Vũ khí',artifact:'Bộ linh khí',herb:'Thảo dược',mineral:'Khoáng vật',drop:'Vật phẩm rớt',pill:'Đan dược'};
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent=(edit?'Chỉnh sửa':'Thêm')+' '+typeNames[type];
  const it=edit||{};

  const capOpts = ['Hoàng','Huyền','Địa','Thiên'].map(r=>`<option ${it.cap===r?'selected':''}>${r}</option>`).join('');
  const phamOpts = ['Hạ phẩm','Trung phẩm','Thượng phẩm','Cực phẩm'].map(r=>`<option ${it.pham===r?'selected':''}>${r}</option>`).join('');

  let body=`
    <div class="form-section"><div class="form-section-title">Hình ảnh</div>
      <div class="form-group">${makeImageUpload('image', it.image)}</div>
    </div>
    <div class="form-section"><div class="form-section-title">Thông tin cơ bản</div>
    <div class="form-grid">
      <div class="form-group full"><label class="form-label">Tên *</label><input class="form-input" id="f_name" value="${it.name||''}"></div>
      <div class="form-group"><label class="form-label">Cấp (Hoàng/Huyền/Địa/Thiên)</label>
        <select class="form-select" id="f_cap"><option value="">—</option>${capOpts}</select></div>
      <div class="form-group"><label class="form-label">Phẩm (Hạ/Trung/Thượng/Cực)</label>
        <select class="form-select" id="f_pham"><option value="">—</option>${phamOpts}</select></div>`;

  if(type==='weapon'){
    body+=`<div class="form-group"><label class="form-label">Nhóm vũ khí</label>
        <select class="form-select" id="f_weaponGroup" onchange="updateItemWeaponSubtypes()">
          <option value="">—</option>
          ${Object.keys(WEAPON_GROUPS).map(g=>`<option ${it.weaponGroup===g?'selected':''}>${g}</option>`).join('')}
        </select></div>
      <div class="form-group"><label class="form-label">Loại cụ thể</label>
        <select class="form-select" id="f_weaponSubtype">
          <option value="">—</option>
          ${(WEAPON_GROUPS[it.weaponGroup]||[]).map(s=>`<option ${it.weaponSubtype===s?'selected':''}>${s}</option>`).join('')}
        </select></div>
      <div class="form-group"><label class="form-label">Cấp độ vũ khí</label>
        <select class="form-select" id="f_rarity">
          <option value="">—</option>
          ${['Phàm khí','Linh khí','Địa khí','Tiên khí','Thần khí'].map(r=>`<option ${it.rarity===r?'selected':''}>${r}</option>`).join('')}
        </select></div>
      <div class="form-group"><label class="form-label">Chỉ số chính</label><input class="form-input" id="f_mainStat" value="${it.mainStat||''}"></div>
      <div class="form-group"><label class="form-label">Chỉ số phụ</label>
        <select class="form-select" id="f_subStat">
          <option value="">—</option>
          ${['CRIT%','CDMG%','ATK%','EM','Nạp linh lực','DEF%','HP%'].map(s=>`<option ${it.subStat===s?'selected':''}>${s}</option>`).join('')}
        </select></div>
      <div class="form-group full"><label class="form-label">Kỹ năng vũ khí</label><textarea class="form-textarea" id="f_skill">${it.skill||''}</textarea></div>`;
  }
  if(type==='artifact'){
    body+=`<div class="form-group full"><label class="form-label">Hiệu ứng bộ 2 món</label><textarea class="form-textarea" id="f_set2">${it.set2||''}</textarea></div>
      <div class="form-group full"><label class="form-label">Hiệu ứng bộ 4 món</label><textarea class="form-textarea" id="f_set4">${it.set4||''}</textarea></div>`;
  }
  if(['herb','mineral','drop'].includes(type)){
    body+=`<div class="form-group full"><label class="form-label">Tính chất dược liệu</label><input class="form-input" id="f_herbNature" value="${it.herbNature||''}"></div>
      <div class="form-group full"><label class="form-label">Đặc điểm hình thái</label><input class="form-input" id="f_herbShape" value="${it.herbShape||''}"></div>
      <div class="form-group full"><label class="form-label">Nguồn gốc / Rớt từ</label><input class="form-input" id="f_origin" value="${it.origin||it.dropFrom||''}"></div>
      <div class="form-group full"><label class="form-label">Có thể tìm ở</label><input class="form-input" id="f_location" value="${it.location||''}"></div>
      <div class="form-group full"><label class="form-label">Công dụng chung</label><textarea class="form-textarea" id="f_use">${it.use||''}</textarea></div>`;
    if(type==='herb') body+=`<div class="form-group full"><label class="form-label">Công dụng Y học</label><textarea class="form-textarea" id="f_medicineUse">${it.medicineUse||''}</textarea></div>
      <div class="form-group full"><label class="form-label">Công dụng luyện đan</label><textarea class="form-textarea" id="f_alchemyUse">${it.alchemyUse||''}</textarea></div>`;
  }
  if(type==='pill') body+=`<div class="form-group full"><label class="form-label">Công thức / Nguyên liệu</label><textarea class="form-textarea" id="f_use">${it.use||''}</textarea></div>`;
  body+=`<div class="form-group full"><label class="form-label">Mô tả / Lore</label><textarea class="form-textarea" id="f_desc">${it.desc||''}</textarea></div>
    <div class="form-group full"><label class="form-label">Ghi chú</label><textarea class="form-textarea" id="f_notes">${it.notes||''}</textarea></div>
    </div></div>`;
  document.getElementById('modalBody').innerHTML=body;
}

function updateItemWeaponSubtypes() {
  const grp = document.getElementById('f_weaponGroup')?.value||'';
  const sub = document.getElementById('f_weaponSubtype');
  if(!sub) return;
  const opts = WEAPON_GROUPS[grp]||[];
  sub.innerHTML=`<option value="">—</option>`+opts.map(o=>`<option>${o}</option>`).join('');
}

function openGeoModal() {
  if(!editMode) return;
  modalType='geo'; modalEditItem=null;
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent='Thêm lục địa mới';
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section"><div class="form-section-title">Thông tin lục địa</div>
    <div class="form-grid">
      <div class="form-group full"><label class="form-label">Tên lục địa *</label><input class="form-input" id="f_name" placeholder="Ví dụ: Lục địa Tiên Nguyên"></div>
      <div class="form-group full"><label class="form-label">Mô tả tổng quan</label><textarea class="form-textarea" id="f_desc"></textarea></div>
    </div></div>`;
}

function openTimelineModal(editIdx) {
  if(!editMode) return;
  const edit = editIdx!==undefined ? DB.timeline[editIdx] : null;
  modalType='timeline'; modalEditItem=edit!==null&&edit!==undefined?{item:edit,idx:editIdx}:null;
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent=edit?'Chỉnh sửa sự kiện':'Thêm sự kiện mới';
  const ev=edit||{};
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section"><div class="form-section-title">Thông tin sự kiện</div>
    <div class="form-grid">
      <div class="form-group"><label class="form-label">Năm / Mốc thời gian *</label><input class="form-input" id="f_year" placeholder="Ví dụ: Năm 0, Kỷ nguyên thứ nhất..." value="${ev.year||''}"></div>
      <div class="form-group"><label class="form-label">Tên sự kiện *</label><input class="form-input" id="f_name" value="${ev.title||''}"></div>
      <div class="form-group full"><label class="form-label">Mô tả chi tiết</label><textarea class="form-textarea" style="min-height:110px" id="f_desc">${ev.desc||''}</textarea></div>
      <div class="form-group full"><label class="form-label">Nhân vật liên quan</label><input class="form-input" id="f_chars" placeholder="Ví dụ: Khải Viễn, Tiểu Bạch..." value="${ev.chars||''}"></div>
      <div class="form-group full"><label class="form-label">Ghi chú</label><input class="form-input" id="f_notes" value="${ev.notes||''}"></div>
    </div></div>`;
}

function openCustomSectionModal() {
  if(!editMode) return;
  modalType='customSection'; modalEditItem=null;
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent='Thêm nhánh mới';
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section"><div class="form-section-title">Tên nhánh</div>
    <div class="form-grid">
      <div class="form-group full"><label class="form-label">Tên nhánh *</label><input class="form-input" id="f_name" placeholder="Ví dụ: Bản đồ chiến trường, Thú cưỡi..."></div>
      <div class="form-group full"><label class="form-label">Mô tả nhánh</label><textarea class="form-textarea" id="f_desc"></textarea></div>
    </div></div>`;
}

function openCustomEntryModal(si, ei) {
  if(!editMode) return;
  const edit = ei!==undefined ? DB.customSections[si].entries[ei] : null;
  modalType='customEntry'; modalEditItem=edit?{si,ei,item:edit}:{si};
  document.getElementById('modal').style.display='block';
  const secName=DB.customSections[si].name;
  document.getElementById('modalTitle').textContent=(edit?'Chỉnh sửa':'Thêm')+' mục vào "'+secName+'"';
  const e=edit||{};
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section"><div class="form-section-title">Hình ảnh (tùy chọn)</div>
      <div class="form-group">${makeImageUpload('image', e.image)}</div>
    </div>
    <div class="form-section"><div class="form-section-title">Nội dung</div>
    <div class="form-grid">
      <div class="form-group full"><label class="form-label">Tên *</label><input class="form-input" id="f_name" value="${e.name||''}"></div>
      <div class="form-group full"><label class="form-label">Tóm tắt ngắn</label><input class="form-input" id="f_summary" value="${e.summary||''}"></div>
      <div class="form-group full"><label class="form-label">Nội dung chi tiết</label><textarea class="form-textarea" style="min-height:150px" id="f_content">${e.content||''}</textarea></div>
      <div class="form-group full"><label class="form-label">Ghi chú</label><input class="form-input" id="f_notes" value="${e.notes||''}"></div>
    </div></div>`;
}

// ===== SAVE MODAL =====
function saveModal() {
  const name = document.getElementById('f_name')?.value?.trim();
  if(!name && modalType!=='timeline') { showToast('Vui lòng nhập tên!','error'); return; }

  if(modalType==='character'){
    const c = modalEditItem || {};
    ['name','title','realName','alias','rank','gender','race','clan','world','hometown','age','ageAppear','patch','createdAt',
     'hairColor','eyeColor','height','clothing','markings','items','voiceType','aura',
     'element','elementColor','elementShape','cultivation','faction','master','secretArt','role','fightStyle',
     'weaponGroup','weaponSubtype','weaponName','realm','bonusStat',
     'hp','atk','def','em','energyRecharge','crit','cdmg','eleDmg','atkSpeed','eleRes','penetrate','heal','special',
     'normalAtk','hit1','hit2','hit3','hit4','hit5','charged','plunge','normalDesc',
     'skillE','skillEEffect','skillECd','skillEEnergy','skillEDesc',
     'skillQ','skillQCost','skillQCd','skillQDur','skillQDesc',
     'passive1','passive2','passive3',
     'c1','c2','c3','c4','c5','c6',
     'mainStory','subStory1','subStory2','storyArc','conflict','resolution',
     'background','personality','worldview','goal','secret','trauma','likes','dislikes','fear','food','relationships','trusted','enemy',
     'voiceGreet','voiceIntro','voiceJoin','voiceBreakthrough','voiceLowHP','voiceDefeated',
     'voiceSkillE','voiceSkillQ','voiceCrit','voiceSelf','voiceWorld','voiceKey',
     'uniqueAbilityName','uniqueCondition','uniqueAbility',
     'mat1','mat2','mat3','skillMat1','skillMat2','skillMat3',
     'artifactSet1','artifactSet2','notes','image','banner'
    ].forEach(f=>{const el=document.getElementById('f_'+f);if(el)c[f]=el.value;});
    c.stars=parseInt(document.getElementById('f_stars')?.value||'5');
    if(!modalEditItem) DB.characters.push(c);
    save(); closeModal(); renderChars();

  } else if(modalType==='reaction'){
    DB.customReactions=DB.customReactions||[];
    DB.customReactions.push({
      name:document.getElementById('f_name')?.value||'',
      trigger:document.getElementById('f_trigger')?.value||'',
      effect:document.getElementById('f_effect')?.value||''
    });
    save(); closeModal(); renderReactions();
    return;

  } else if(modalType==='geo'){
    DB.geography.push({name,desc:document.getElementById('f_desc')?.value||'',forces:[]});
    save(); closeModal(); renderGeo();

  } else if(modalType==='timeline'){
    const ev = modalEditItem?.item || {};
    ev.year = document.getElementById('f_year')?.value||'';
    ev.title = document.getElementById('f_name')?.value||'';
    ev.desc = document.getElementById('f_desc')?.value||'';
    ev.chars = document.getElementById('f_chars')?.value||'';
    ev.notes = document.getElementById('f_notes')?.value||'';
    if(!ev.title){showToast('Vui lòng nhập tên sự kiện!','error');return;}
    if(!modalEditItem) DB.timeline.push(ev);
    save(); closeModal(); renderTimeline();

  } else if(modalType==='customSection'){
    DB.customSections.push({name,desc:document.getElementById('f_desc')?.value||'',entries:[]});
    save(); closeModal(); renderCustomSections();

  } else if(modalType==='customEntry'){
    const {si,ei,item} = modalEditItem||{si:modalEditItem?.si};
    const e = item||{};
    e.name = document.getElementById('f_name')?.value||'';
    e.summary = document.getElementById('f_summary')?.value||'';
    e.content = document.getElementById('f_content')?.value||'';
    e.notes = document.getElementById('f_notes')?.value||'';
    e.image = document.getElementById('f_image')?.value||'';
    if(!e.name){showToast('Vui lòng nhập tên!','error');return;}
    const targetSi = modalEditItem?.si;
    DB.customSections[targetSi].entries = DB.customSections[targetSi].entries||[];
    if(ei===undefined) DB.customSections[targetSi].entries.push(e);
    save(); closeModal(); renderCustomSections();

  } else {
    const key = itemDB[modalType];
    const it = modalEditItem || {};
    ['name','cap','pham','rarity','weaponGroup','weaponSubtype','mainStat','subStat','skill','herbNature','herbShape','desc','origin','use','medicineUse','alchemyUse','location','dropFrom','set2','set4','notes','image'].forEach(f=>{
      const el=document.getElementById('f_'+f);if(el)it[f]=el.value;
    });
    if(!modalEditItem) DB[key].push(it);
    save(); closeModal(); renderItems(modalType);
  }
  showToast('Đã lưu thành công!','success');
}

function closeModal(){
  document.getElementById('modal').style.display='none';
  modalType=null; modalEditItem=null;
}
document.getElementById('modal').addEventListener('click',function(e){if(e.target===this)closeModal();});

// ===== EXPORT =====
function exportHTML(){
  const script=`<script>window.__EXPORT_DB__=${JSON.stringify(DB)};<\/script>`;
  const html=document.documentElement.outerHTML.replace('<head>','<head>'+script);
  const a=document.createElement('a');
  a.href=URL.createObjectURL(new Blob([html],{type:'text/html'}));
  a.download='tiengioi-wiki.html'; a.click();
  showToast('Đã xuất file HTML!','success');
}

// ===== TOAST =====
function showToast(msg, type='info'){
  const t=document.createElement('div');
  t.className=`toast ${type}`;
  t.textContent=msg;
  document.body.appendChild(t);
  setTimeout(()=>t.remove(),3000);
}

// ===== INIT =====
if(window.__EXPORT_DB__){DB=window.__EXPORT_DB__;save();}
// Migrate old DB
if(localStorage.getItem('tiengioi_db_v2')){
  const old=JSON.parse(localStorage.getItem('tiengioi_db_v2'));
  if(old && !DB.characters.length) {
    DB.characters=old.characters||[];
    DB.weapons=old.weapons||[];
    DB.artifacts=old.artifacts||[];
    DB.herbs=old.herbs||[];
    DB.minerals=old.minerals||[];
    DB.drops=old.drops||[];
    DB.pills=old.pills||[];
    DB.geography=old.geography||[];
    DB.timeline=old.timeline||[];
    DB.customSections=old.customSections||[];
    save();
  }
}
updateStats();
renderReactions();
</script>
</body>
</html>
