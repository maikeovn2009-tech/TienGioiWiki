# TienGioiWiki
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tiên Giới: Khởi Nguyên — Wiki</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;0,700;1,400;1,600&family=Mulish:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --bg:        #F5EFEB;
  --bg-panel:  #EDE4DC;
  --bg-card:   #FFFFFF;
  --bg-card2:  #FAF6F3;
  --border:    #D9CEC5;
  --border-2:  #C8BAB0;
  --accent:    #8B5E3C;
  --accent2:   #A0522D;
  --accent3:   #5C8374;
  --gold:      #7A5C2E;
  --gold2:     #9E7B3F;
  --red:       #B94040;
  --green:     #3A7D5C;
  --text:      #2C1F14;
  --text-2:    #5C4A38;
  --text-3:    #8C7B6B;
  --text-4:    #AFA098;
  --shadow-sm: 0 1px 4px rgba(60,30,10,.08);
  --shadow:    0 4px 18px rgba(60,30,10,.12);
  --shadow-lg: 0 8px 32px rgba(60,30,10,.16);
  --radius:    8px;
  --radius-lg: 14px;
  --sidebar-w: 230px;
}
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }
body {
  font-family: 'Mulish', sans-serif;
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  font-size: 14px;
  line-height: 1.6;
}
::-webkit-scrollbar { width: 5px; height: 5px; }
::-webkit-scrollbar-track { background: var(--bg-panel); }
::-webkit-scrollbar-thumb { background: var(--border-2); border-radius: 3px; }

/* ===== SIDEBAR ===== */
#sidebar {
  position: fixed; left:0; top:0; width: var(--sidebar-w); height:100vh;
  background: var(--bg-panel);
  border-right: 1px solid var(--border);
  display: flex; flex-direction: column;
  z-index: 100;
  transition: transform .3s ease;
}
.sidebar-logo {
  padding: 24px 20px 18px;
  border-bottom: 1px solid var(--border);
}
.sidebar-logo-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px; font-weight: 700;
  color: var(--gold); line-height: 1.2;
  letter-spacing: .5px;
}
.sidebar-logo-sub {
  font-size: 11px; color: var(--text-3);
  letter-spacing: 1.5px; text-transform: uppercase;
  margin-top: 4px; font-weight: 600;
}

nav { flex:1; overflow-y:auto; padding: 10px 0; }
.nav-section {
  padding: 14px 16px 4px;
  font-size: 10px; color: var(--text-4);
  text-transform: uppercase; letter-spacing: 2px; font-weight: 700;
}
.nav-item {
  display: flex; align-items: center; gap: 8px;
  padding: 8px 20px; cursor: pointer;
  font-size: 13px; color: var(--text-2); font-weight: 500;
  transition: all .18s; position: relative;
  border-left: 2px solid transparent;
}
.nav-item:hover { color: var(--accent); background: rgba(139,94,60,.06); border-left-color: rgba(139,94,60,.3); }
.nav-item.active { color: var(--accent); background: rgba(139,94,60,.1); border-left-color: var(--accent); font-weight: 600; }

.sidebar-footer { padding: 14px 16px; border-top: 1px solid var(--border); display: flex; flex-direction: column; gap: 8px; }
#editModeBtn {
  width:100%; padding: 9px 14px;
  border: 1px solid var(--border-2); background: var(--bg-card);
  color: var(--text-2); border-radius: var(--radius);
  cursor: pointer; font-size: 12px; font-family: 'Mulish', sans-serif;
  display: flex; align-items: center; justify-content: center; gap: 8px;
  transition: all .2s; font-weight: 600;
}
#editModeBtn:hover { border-color: var(--accent); color: var(--accent); }
#editModeBtn.active { background: var(--accent); color: #fff; border-color: var(--accent); }
.edit-dot { width:7px; height:7px; border-radius:50%; background: var(--text-4); flex-shrink:0; }
#editModeBtn.active .edit-dot { background: #a3f0c8; box-shadow: 0 0 6px #4ade80; }
#exportBtn2 {
  width:100%; padding: 7px 14px;
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
  background: rgba(245,239,235,.92); backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--border);
  padding: 12px 32px; display: flex; align-items: center; justify-content: space-between;
}
.topbar-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 16px; font-weight: 600; color: var(--gold); letter-spacing: .5px;
}

/* ===== PAGES ===== */
.page { display:none; padding: 32px 36px; }
.page.active { display:block; }
.page-header { margin-bottom: 28px; }
.page-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 28px; font-weight: 700; color: var(--gold);
  letter-spacing: .5px;
}
.page-desc { color: var(--text-3); margin-top: 4px; font-size: 13px; }
.divider { width:50px; height:2px; background: linear-gradient(90deg, var(--gold), transparent); margin: 10px 0; border-radius:2px; }

/* ===== CARDS ===== */
.cards-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 14px; margin-bottom: 20px; }

.char-card {
  background: var(--bg-card); border: 1px solid var(--border);
  border-radius: var(--radius-lg); overflow: hidden; cursor: pointer;
  transition: all .22s; position: relative;
}
.char-card:hover { border-color: var(--accent2); transform: translateY(-3px); box-shadow: var(--shadow); }
.char-card-img {
  height: 130px; background: var(--bg-card2);
  display: flex; align-items: center; justify-content: center;
  overflow: hidden; position: relative;
}
.char-card-img img { width:100%; height:100%; object-fit:cover; }
.char-card-img .placeholder-text {
  font-size: 11px; color: var(--text-4); font-style: italic;
}
.char-rarity-bar { height: 3px; }
.rarity-5 { background: linear-gradient(90deg, #c9a227, #e8c97a); }
.rarity-4 { background: linear-gradient(90deg, #8b72be, #a78bfa); }
.rarity-3 { background: linear-gradient(90deg, #5a8fd8, #7cb9e8); }
.char-card-info { padding: 10px 12px; }
.char-card-name { font-size: 13px; font-weight: 700; color: var(--text); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.char-card-meta { display: flex; align-items: center; gap: 6px; margin-top: 4px; flex-wrap: wrap; }
.char-element-tag {
  font-size: 10px; padding: 2px 8px; border-radius: 20px;
  border: 1px solid var(--border); color: var(--text-2); font-weight: 600;
  background: var(--bg-panel);
}
.char-stars { font-size: 10px; color: #b8860b; }
.char-stars.s4 { color: #7B68EE; }

/* ===== FILTER BAR ===== */
.filter-bar { display:flex; gap:8px; flex-wrap:wrap; margin-bottom:18px; align-items:center; }
.filter-btn {
  padding: 6px 14px; background: var(--bg-card);
  border: 1px solid var(--border); color: var(--text-2);
  border-radius: 20px; cursor: pointer; font-size: 12px;
  font-family: 'Mulish', sans-serif; font-weight: 600;
  transition: all .18s;
}
.filter-btn:hover, .filter-btn.active { background: var(--accent); border-color: var(--accent); color: #fff; }
.search-box {
  padding: 7px 14px; background: var(--bg-card); border: 1px solid var(--border);
  color: var(--text); border-radius: 20px; font-size: 12px;
  font-family: 'Mulish', sans-serif; outline: none; min-width: 200px;
  transition: border-color .2s;
}
.search-box:focus { border-color: var(--accent); }
.search-box::placeholder { color: var(--text-4); }

/* ===== VIEW TOGGLE ===== */
.view-toggle { display:flex; gap:4px; }
.view-btn {
  padding: 6px 14px; background: var(--bg-card);
  border: 1px solid var(--border); color: var(--text-3);
  border-radius: 8px; cursor: pointer; font-size: 12px;
  font-family: 'Mulish', sans-serif; font-weight: 600; transition: all .18s;
}
.view-btn.active { background: var(--accent); border-color: var(--accent); color: #fff; }

/* ===== ADD BUTTON ===== */
.add-btn {
  display: inline-flex; align-items: center; gap: 6px;
  padding: 8px 18px; background: var(--accent); color: #fff;
  border: none; border-radius: var(--radius); cursor: pointer;
  font-size: 13px; font-family: 'Mulish', sans-serif; font-weight: 600;
  transition: all .2s; margin-bottom: 18px; box-shadow: var(--shadow-sm);
}
.add-btn:hover { background: var(--accent2); box-shadow: var(--shadow); }
.add-btn.hidden { display: none; }

/* ===== TABLE ===== */
.data-table { width:100%; border-collapse:collapse; background: var(--bg-card); border-radius: var(--radius-lg); overflow:hidden; box-shadow: var(--shadow-sm); }
.data-table th { text-align:left; padding:10px 14px; font-size:11px; color:var(--text-3); text-transform:uppercase; letter-spacing:1px; background:var(--bg-panel); border-bottom:1px solid var(--border); font-weight:700; }
.data-table td { padding:10px 14px; font-size:13px; border-bottom:1px solid var(--border); color:var(--text); }
.data-table tr:last-child td { border-bottom:none; }
.data-table tr:hover td { background: var(--bg-card2); cursor:pointer; }

/* ===== DETAIL PANEL ===== */
#detailOverlay { display:none; position:fixed; inset:0; z-index:200; background:rgba(44,31,20,.4); backdrop-filter:blur(3px); }
#detailPanel {
  display:none; position:fixed; top:0; right:0; height:100vh; width:700px;
  background: var(--bg); border-left: 1px solid var(--border);
  overflow-y:auto; z-index:201; box-shadow: var(--shadow-lg);
  animation: slideIn .3s ease;
}
@keyframes slideIn { from{transform:translateX(30px);opacity:0} to{transform:translateX(0);opacity:1} }
.detail-close {
  position: sticky; top:0;
  background: rgba(245,239,235,.95); backdrop-filter:blur(8px);
  padding: 14px 22px; display:flex; align-items:center; justify-content:space-between;
  border-bottom: 1px solid var(--border); z-index:10;
}
.detail-close-title { font-family:'Cormorant Garamond',serif; font-size:15px; color:var(--gold); font-weight:600; }
.detail-close-actions { display:flex; gap:8px; }
.close-btn {
  width:30px; height:30px; border-radius:50%;
  background:var(--bg-card); border:1px solid var(--border);
  color:var(--text-3); cursor:pointer; display:flex; align-items:center; justify-content:center;
  font-size:14px; transition:all .2s;
}
.close-btn:hover { border-color: var(--red); color:var(--red); }
.detail-content { padding: 24px 28px; }

/* ===== SECTION CARDS ===== */
.section-card {
  background: var(--bg-card); border: 1px solid var(--border);
  border-radius: var(--radius-lg); padding: 18px 20px; margin-bottom: 14px;
}
.section-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 13px; font-weight: 700; text-transform: uppercase;
  letter-spacing: 2px; color: var(--accent); margin-bottom: 14px;
  padding-bottom: 8px; border-bottom: 1px solid var(--border);
}

.field-grid { display:grid; grid-template-columns:1fr 1fr; gap:12px; }
.field-grid.cols3 { grid-template-columns:1fr 1fr 1fr; }
.field-item { display:flex; flex-direction:column; gap:3px; }
.field-label { font-size:10px; color:var(--text-4); text-transform:uppercase; letter-spacing:1px; font-weight:700; }
.field-value { font-size:13px; color:var(--text); line-height:1.6; }
.field-value.empty { color:var(--text-4); font-style:italic; }
.field-full { margin-bottom:12px; }
.field-full:last-child { margin-bottom:0; }

.stat-row { display:flex; align-items:center; justify-content:space-between; padding:7px 0; border-bottom:1px solid var(--border); }
.stat-row:last-child { border-bottom:none; }
.stat-name { font-size:12px; color:var(--text-2); font-weight:500; }
.stat-val { font-size:13px; color:var(--text); font-weight:700; }

.skill-card { background:var(--bg-card2); border:1px solid var(--border); border-radius:var(--radius); padding:14px; margin-bottom:10px; }
.skill-type { font-size:10px; text-transform:uppercase; letter-spacing:1.5px; color:var(--accent3); margin-bottom:3px; font-weight:700; }
.skill-name { font-family:'Cormorant Garamond',serif; font-size:16px; font-weight:700; color:var(--gold); margin-bottom:6px; }
.skill-desc { font-size:12px; color:var(--text-2); line-height:1.7; }

.constellation-grid { display:grid; grid-template-columns:1fr 1fr; gap:8px; }
.const-item { background:var(--bg-card2); border:1px solid var(--border); border-radius:8px; padding:12px; }
.const-level { font-size:10px; color:var(--accent); font-weight:700; text-transform:uppercase; letter-spacing:1px; }
.const-desc { font-size:12px; color:var(--text-2); margin-top:4px; line-height:1.6; }

/* ===== MODAL ===== */
#modal { display:none; position:fixed; inset:0; z-index:300; background:rgba(44,31,20,.5); backdrop-filter:blur(5px); overflow-y:auto; padding:40px 20px; }
.modal-box {
  max-width:820px; margin:0 auto;
  background:var(--bg); border:1px solid var(--border);
  border-radius: var(--radius-lg); overflow:hidden;
  animation: slideIn .3s ease; box-shadow: var(--shadow-lg);
}
.modal-header {
  padding: 18px 24px; border-bottom:1px solid var(--border);
  display:flex; align-items:center; justify-content:space-between;
  background: var(--bg-panel);
}
.modal-title { font-family:'Cormorant Garamond',serif; font-size:18px; color:var(--gold); font-weight:700; }
.modal-body { padding:24px; max-height:72vh; overflow-y:auto; }
.modal-footer { padding:14px 24px; border-top:1px solid var(--border); display:flex; justify-content:flex-end; gap:10px; background:var(--bg-panel); }

/* ===== FORMS ===== */
.form-section { margin-bottom:22px; }
.form-section-title {
  font-size:11px; text-transform:uppercase; letter-spacing:2px;
  color:var(--accent); font-weight:700; margin-bottom:12px;
  padding-bottom:6px; border-bottom:1px solid var(--border);
}
.form-grid { display:grid; grid-template-columns:1fr 1fr; gap:12px; }
.form-grid.cols3 { grid-template-columns:1fr 1fr 1fr; }
.form-group { display:flex; flex-direction:column; gap:5px; }
.form-group.full { grid-column:1/-1; }
.form-label { font-size:11px; color:var(--text-3); font-weight:700; letter-spacing:.5px; }
.form-input, .form-select, .form-textarea {
  background: var(--bg-card); border:1px solid var(--border);
  color: var(--text); border-radius:var(--radius);
  padding: 9px 12px; font-size:13px; font-family:'Mulish',sans-serif;
  outline:none; transition:border-color .2s; width:100%;
}
.form-input:focus, .form-select:focus, .form-textarea:focus { border-color:var(--accent); }
.form-select option { background: var(--bg-panel); color: var(--text); }
.form-textarea { min-height:80px; resize:vertical; }
.img-upload-wrap { position:relative; }
.img-preview {
  width:100%; height:120px; background:var(--bg-panel); border:1px dashed var(--border-2);
  border-radius:var(--radius); display:flex; align-items:center; justify-content:center;
  cursor:pointer; overflow:hidden; transition:border-color .2s;
  font-size:12px; color:var(--text-4); font-style:italic;
}
.img-preview:hover { border-color:var(--accent); }
.img-preview img { width:100%; height:100%; object-fit:cover; }
.img-upload-input { display:none; }

/* ===== BUTTONS ===== */
.btn { padding:8px 18px; border-radius:var(--radius); cursor:pointer; font-size:13px; font-family:'Mulish',sans-serif; font-weight:600; transition:all .2s; border:1px solid; }
.btn-primary { background:var(--accent); border-color:var(--accent); color:#fff; }
.btn-primary:hover { background:var(--accent2); border-color:var(--accent2); }
.btn-danger { background:rgba(185,64,64,.1); border-color:var(--red); color:var(--red); }
.btn-danger:hover { background:rgba(185,64,64,.2); }
.btn-ghost { background:transparent; border-color:var(--border); color:var(--text-3); }
.btn-ghost:hover { border-color:var(--border-2); color:var(--text-2); }

/* ===== HOME ===== */
.home-hero {
  background: var(--bg-card); border:1px solid var(--border);
  border-radius:var(--radius-lg); padding:36px 40px; margin-bottom:24px;
  position:relative; overflow:hidden;
}
.home-hero::before {
  content:''; position:absolute; inset:0;
  background: linear-gradient(135deg, rgba(139,94,60,.04), rgba(92,131,116,.04));
  pointer-events:none;
}
.home-hero-title { font-family:'Cormorant Garamond',serif; font-size:34px; font-weight:700; color:var(--gold); margin-bottom:8px; }
.home-hero-sub { color:var(--text-2); font-size:14px; max-width:500px; line-height:1.8; }
.home-stats { display:grid; grid-template-columns:repeat(4,1fr); gap:14px; margin-bottom:24px; }
.home-stat {
  background:var(--bg-card); border:1px solid var(--border);
  border-radius:var(--radius-lg); padding:18px 20px; text-align:center;
  transition:all .2s;
}
.home-stat:hover { border-color:var(--accent); box-shadow:var(--shadow-sm); }
.home-stat-num { font-family:'Cormorant Garamond',serif; font-size:30px; font-weight:700; color:var(--accent); }
.home-stat-label { font-size:11px; color:var(--text-3); text-transform:uppercase; letter-spacing:1px; margin-top:2px; font-weight:700; }
.home-sections { display:grid; grid-template-columns:repeat(3,1fr); gap:14px; }
.home-section-card {
  background:var(--bg-card); border:1px solid var(--border);
  border-radius:var(--radius-lg); padding:18px 20px; cursor:pointer;
  transition:all .22s;
}
.home-section-card:hover { border-color:var(--accent); transform:translateY(-2px); box-shadow:var(--shadow); }
.home-section-title { font-family:'Cormorant Garamond',serif; font-size:16px; font-weight:700; color:var(--gold); margin-bottom:4px; }
.home-section-desc { font-size:12px; color:var(--text-3); }

/* ===== INFO SECTION ===== */
.info-section { background:var(--bg-card); border:1px solid var(--border); border-radius:var(--radius-lg); padding:20px; margin-bottom:16px; }
.info-section h3 { font-family:'Cormorant Garamond',serif; font-size:17px; font-weight:700; color:var(--gold); margin-bottom:14px; }
.info-text { font-size:13px; color:var(--text-2); line-height:1.8; }
.info-table { width:100%; border-collapse:collapse; font-size:13px; margin-top:8px; }
.info-table th { padding:8px 12px; background:var(--bg-panel); color:var(--text-3); text-align:left; font-size:11px; text-transform:uppercase; letter-spacing:1px; border:1px solid var(--border); font-weight:700; }
.info-table td { padding:8px 12px; border:1px solid var(--border); color:var(--text-2); }
.info-table tr:hover td { background:var(--bg-card2); }

/* ===== REACTION ===== */
.reaction-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(240px,1fr)); gap:12px; }
.reaction-card { background:var(--bg-card); border:1px solid var(--border); border-radius:var(--radius); padding:14px; }
.reaction-name { font-family:'Cormorant Garamond',serif; font-size:15px; font-weight:700; color:var(--gold); margin-bottom:3px; }
.reaction-trigger { font-size:11px; color:var(--accent3); margin-bottom:6px; font-weight:600; }
.reaction-effect { font-size:12px; color:var(--text-2); line-height:1.6; }

/* ===== GEO ===== */
.geo-continent { background:var(--bg-card); border:1px solid var(--border); border-radius:var(--radius-lg); margin-bottom:14px; overflow:hidden; }
.geo-continent-header { padding:14px 18px; display:flex; align-items:center; justify-content:space-between; cursor:pointer; background:var(--bg-panel); }
.geo-continent-name { font-family:'Cormorant Garamond',serif; font-size:17px; font-weight:700; color:var(--gold); }
.geo-forces { padding:14px 18px; }
.force-item { padding:10px 14px; background:var(--bg-card2); border-radius:8px; margin-bottom:8px; border:1px solid var(--border); }
.force-name { font-size:13px; font-weight:700; color:var(--text); }
.force-desc { font-size:12px; color:var(--text-2); margin-top:3px; }

/* ===== ITEM CARD ===== */
.item-card { background:var(--bg-card); border:1px solid var(--border); border-radius:var(--radius-lg); padding:0; cursor:pointer; transition:all .2s; overflow:hidden; }
.item-card:hover { border-color:var(--accent); transform:translateY(-2px); box-shadow:var(--shadow); }
.item-card-img { height:90px; background:var(--bg-card2); display:flex; align-items:center; justify-content:center; overflow:hidden; }
.item-card-img img { width:100%; height:100%; object-fit:cover; }
.item-card-img .placeholder-text { font-size:11px; color:var(--text-4); font-style:italic; }
.item-card-body { padding:10px 12px; }
.item-card-name { font-size:13px; font-weight:700; color:var(--text); }
.item-card-meta { font-size:11px; color:var(--text-3); margin-top:3px; }
.rarity-badge { display:inline-block; padding:2px 8px; border-radius:10px; font-size:10px; font-weight:700; }
.rarity-5star { background:rgba(201,162,39,.15); color:#7A5C2E; border:1px solid rgba(201,162,39,.4); }
.rarity-4star { background:rgba(139,114,190,.15); color:#5a3d8a; border:1px solid rgba(139,114,190,.4); }
.rarity-3star { background:rgba(90,143,216,.15); color:#2a5aa0; border:1px solid rgba(90,143,216,.4); }

/* ===== TIMELINE ===== */
.timeline-wrap { position:relative; padding-left:30px; }
.timeline-wrap::before { content:''; position:absolute; left:10px; top:0; bottom:0; width:2px; background:var(--border); }
.timeline-item { position:relative; margin-bottom:20px; }
.timeline-item::before { content:''; position:absolute; left:-24px; top:6px; width:10px; height:10px; border-radius:50%; background:var(--accent); border:2px solid var(--bg); box-shadow:0 0 0 2px var(--accent); }
.timeline-card { background:var(--bg-card); border:1px solid var(--border); border-radius:var(--radius); padding:14px 16px; transition:all .2s; }
.timeline-card:hover { border-color:var(--accent); box-shadow:var(--shadow-sm); }
.timeline-year { font-size:11px; color:var(--accent); font-weight:700; text-transform:uppercase; letter-spacing:1px; margin-bottom:3px; }
.timeline-title { font-family:'Cormorant Garamond',serif; font-size:16px; font-weight:700; color:var(--gold); margin-bottom:5px; }
.timeline-desc { font-size:12px; color:var(--text-2); line-height:1.7; }

/* ===== PASS MODAL ===== */
#passModal { display:none; position:fixed; inset:0; z-index:500; background:rgba(44,31,20,.6); backdrop-filter:blur(8px); align-items:center; justify-content:center; }
.pass-box { background:var(--bg); border:1px solid var(--border); border-radius:var(--radius-lg); padding:32px; width:340px; text-align:center; box-shadow:var(--shadow-lg); }
.pass-title { font-family:'Cormorant Garamond',serif; font-size:20px; color:var(--gold); margin-bottom:6px; font-weight:700; }
.pass-desc { font-size:12px; color:var(--text-3); margin-bottom:20px; }
.pass-input { width:100%; text-align:center; letter-spacing:4px; font-size:16px; margin-bottom:16px; }
.pass-error { color:var(--red); font-size:12px; margin-bottom:8px; min-height:18px; }

/* ===== TOAST ===== */
.toast {
  position:fixed; bottom:24px; right:24px; z-index:999;
  padding:11px 18px; background:var(--bg-card); border:1px solid var(--border);
  border-radius:var(--radius); font-size:13px; color:var(--text);
  box-shadow:var(--shadow); animation:toastIn .3s ease;
  display:flex; align-items:center; gap:10px; font-weight:500;
}
@keyframes toastIn { from{transform:translateY(20px);opacity:0} to{transform:translateY(0);opacity:1} }
.toast.success { border-color:var(--green); }
.toast.error { border-color:var(--red); }

/* ===== NAV BADGE ===== */
.nav-add-badge {
  margin-left:auto; font-size:10px; padding:1px 7px; border-radius:10px;
  background:rgba(139,94,60,.15); color:var(--accent); font-weight:700;
  display:none;
}
body.edit-mode .nav-add-badge { display:inline-block; }

/* ===== CHAR DETAIL HERO ===== */
.char-detail-hero {
  display:flex; gap:20px; margin-bottom:22px; align-items:flex-start;
  padding: 20px; background:var(--bg-card); border:1px solid var(--border);
  border-radius:var(--radius-lg);
}
.char-detail-avatar {
  width:110px; height:110px; border-radius:12px;
  background:var(--bg-panel); border:1px solid var(--border);
  flex-shrink:0; overflow:hidden; display:flex; align-items:center; justify-content:center;
}
.char-detail-avatar img { width:100%; height:100%; object-fit:cover; }
.char-detail-avatar .placeholder-text { font-size:11px; color:var(--text-4); font-style:italic; text-align:center; padding:8px; }
.char-detail-name { font-family:'Cormorant Garamond',serif; font-size:24px; font-weight:700; color:var(--text); line-height:1.2; }
.char-detail-title { font-size:13px; color:var(--text-3); margin-top:3px; font-style:italic; }
.char-detail-tags { display:flex; gap:6px; margin-top:10px; flex-wrap:wrap; align-items:center; }
.tag { font-size:11px; padding:3px 10px; border-radius:20px; border:1px solid var(--border); color:var(--text-2); background:var(--bg-panel); font-weight:600; }
.tag.gold { border-color:rgba(122,92,46,.4); color:var(--gold); background:rgba(122,92,46,.08); }

/* ===== EMPTY STATE ===== */
.empty-state { text-align:center; padding:60px; color:var(--text-4); }
.empty-state-title { font-size:14px; margin-top:12px; font-style:italic; }

/* ===== VOICE LINES ===== */
.voice-line { background:var(--bg-card2); border-left:3px solid var(--accent3); border-radius:0 var(--radius) var(--radius) 0; padding:10px 14px; margin-bottom:8px; }
.voice-label { font-size:10px; text-transform:uppercase; letter-spacing:1px; color:var(--accent3); font-weight:700; margin-bottom:3px; }
.voice-text { font-size:13px; color:var(--text); font-style:italic; line-height:1.6; }
</style>
</head>
<body>

<!-- SIDEBAR -->
<div id="sidebar">
  <div class="sidebar-logo">
    <div class="sidebar-logo-title">Tiên Giới<br>Khởi Nguyên</div>
    <div class="sidebar-logo-sub">Wiki Lore Database</div>
  </div>
  <nav id="nav">
    <div class="nav-section">Tổng quan</div>
    <div class="nav-item active" data-page="home">Trang chủ</div>

    <div class="nav-section">Nhân vật</div>
    <div class="nav-item" data-page="characters">Thư viện nhân vật <span class="nav-add-badge" onclick="event.stopPropagation();openCharModal()">+ Thêm</span></div>
    <div class="nav-item" data-page="char-info">Hệ tu & Chỉ số</div>

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

    <div class="nav-section">Thế giới & Lịch sử</div>
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
  </div>

  <!-- HOME -->
  <div class="page active" id="page-home">
    <div class="home-hero">
      <div class="home-hero-title">Tiên Giới: Khởi Nguyên</div>
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
      <div class="home-section-card" onclick="navigate('weapons')"><div class="home-section-title">Pháp bảo trấn vật</div><div class="home-section-desc">5 cấp độ vũ khí</div></div>
      <div class="home-section-card" onclick="navigate('geography')"><div class="home-section-title">Địa lý thế giới</div><div class="home-section-desc">Các lục địa và thế lực</div></div>
      <div class="home-section-card" onclick="navigate('timeline')"><div class="home-section-title">Dòng thời gian</div><div class="home-section-desc">Các sự kiện lịch sử cốt truyện</div></div>
    </div>
  </div>

  <!-- CHARACTERS -->
  <div class="page" id="page-characters">
    <div class="page-header">
      <div class="page-title">Thư viện nhân vật</div>
      <div class="divider"></div>
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
        <thead><tr><th>Nhân vật</th><th>Sao</th><th>Nguyên tố</th><th>Hệ tu</th><th>Vũ khí</th><th>Cảnh giới</th></tr></thead>
        <tbody id="charTableBody"></tbody>
      </table>
    </div>
    <div id="charEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có nhân vật nào. Bật chế độ chỉnh sửa để thêm!</div></div>
  </div>

  <!-- CHAR INFO -->
  <div class="page" id="page-char-info">
    <div class="page-header"><div class="page-title">Hệ tu & Chỉ số</div><div class="divider"></div></div>
    <div class="info-section">
      <h3>Hệ tu — Vai trò chiến đấu</h3>
      <table class="info-table">
        <thead><tr><th>Hệ tu</th><th>Vai trò</th><th>Mô tả</th></tr></thead>
        <tbody>
          <tr><td>Kiếm Tu</td><td style="color:#B94040">DPS</td><td>Công kích liên tục, sát thương cao, cận chiến</td></tr>
          <tr><td>Khí Tu</td><td style="color:#7A5C2E">Sub-DPS / Buff</td><td>Vận dụng linh khí, hiệu ứng nguyên tố</td></tr>
          <tr><td>Đan Tu</td><td style="color:#3A7D5C">Heal / Support</td><td>Luyện đan, hồi phục, tăng cường đồng đội</td></tr>
          <tr><td>Trận Tu</td><td style="color:#5C8374">Support / CC</td><td>Bố trận pháp, kiểm soát vùng</td></tr>
          <tr><td>Thể Tu</td><td style="color:#5a3d8a">Tank / DPS</td><td>Luyện thân, phòng thủ cao, phản đòn</td></tr>
          <tr><td>Ma Tu</td><td style="color:#8B0000">DPS / Debuff</td><td>Tiêu hao sinh mệnh đổi lấy sức mạnh</td></tr>
          <tr><td>Thần Tu</td><td style="color:#7B68EE">Sub-DPS / Buff</td><td>Thần thức, cổ pháp, biến hóa</td></tr>
          <tr><td>Ẩn Tu</td><td style="color:#5C4A38">Assassin / Debuff</td><td>Tàng hình, ám sát, hạ gục mục tiêu đơn</td></tr>
        </tbody>
      </table>
    </div>
    <div class="info-section">
      <h3>Chỉ số thuộc tính cơ bản (Level 99)</h3>
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
    <div class="page-header"><div class="page-title">Pháp bảo trấn vật</div><div class="divider"></div></div>
    <div class="filter-bar">
      <input class="search-box" type="text" placeholder="Tìm kiếm vũ khí..." id="weaponSearch" oninput="filterItems('weapon')">
      <button class="filter-btn active" data-filter="all" onclick="setItemFilter(this,'weapon','all')">Tất cả</button>
      <button class="filter-btn" onclick="setItemFilter(this,'weapon','Thần khí')">Thần khí</button>
      <button class="filter-btn" onclick="setItemFilter(this,'weapon','Tiên khí')">Tiên khí</button>
      <button class="filter-btn" onclick="setItemFilter(this,'weapon','Địa khí')">Địa khí</button>
    </div>
    <button class="add-btn hidden" id="addWeaponBtn" onclick="openItemModal('weapon')">+ Thêm vũ khí</button>
    <div class="cards-grid" id="weaponGrid"></div>
    <div id="weaponEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có vũ khí nào.</div></div>
    <div class="info-section" style="margin-top:24px">
      <h3>Phân cấp vũ khí</h3>
      <table class="info-table">
        <thead><tr><th>Cấp</th><th>Tên</th><th>Ghi chú</th></tr></thead>
        <tbody>
          <tr><td>1 sao</td><td>Phàm khí</td><td>Cấp thấp nhất</td></tr>
          <tr><td>2 sao</td><td>Linh khí</td><td>Có thể tự luyện</td></tr>
          <tr><td>3 sao</td><td>Địa khí</td><td>Có thể tự luyện</td></tr>
          <tr><td>4 sao</td><td>Tiên khí</td><td>Cần điều kiện đặc biệt</td></tr>
          <tr><td>5 sao</td><td style="color:var(--gold);font-weight:700">Thần khí</td><td>Hiếm nhất, Bản Mệnh Pháp Bảo</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- ARTIFACTS -->
  <div class="page" id="page-artifacts">
    <div class="page-header"><div class="page-title">Linh khí tùy thân</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addArtifactBtn" onclick="openItemModal('artifact')">+ Thêm bộ linh khí</button>
    <div class="cards-grid" id="artifactGrid"></div>
    <div id="artifactEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có bộ linh khí nào.</div></div>
  </div>

  <!-- HERBS -->
  <div class="page" id="page-herbs">
    <div class="page-header"><div class="page-title">Thảo dược</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addHerbBtn" onclick="openItemModal('herb')">+ Thêm thảo dược</button>
    <div class="cards-grid" id="herbGrid"></div>
    <div id="herbEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có thảo dược nào.</div></div>
  </div>

  <!-- MINERALS -->
  <div class="page" id="page-minerals">
    <div class="page-header"><div class="page-title">Khoáng vật</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addMineralBtn" onclick="openItemModal('mineral')">+ Thêm khoáng vật</button>
    <div class="cards-grid" id="mineralGrid"></div>
    <div id="mineralEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có khoáng vật nào.</div></div>
  </div>

  <!-- DROPS -->
  <div class="page" id="page-drops">
    <div class="page-header"><div class="page-title">Đồ rớt từ quái</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addDropBtn" onclick="openItemModal('drop')">+ Thêm vật phẩm rớt</button>
    <div class="cards-grid" id="dropGrid"></div>
    <div id="dropEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có vật phẩm rớt nào.</div></div>
  </div>

  <!-- PILLS -->
  <div class="page" id="page-pills">
    <div class="page-header"><div class="page-title">Đan dược</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addPillBtn" onclick="openItemModal('pill')">+ Thêm đan dược</button>
    <div class="cards-grid" id="pillGrid"></div>
    <div id="pillEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có đan dược nào.</div></div>
  </div>

  <!-- BREAKTHROUGH -->
  <div class="page" id="page-breakthrough">
    <div class="page-header"><div class="page-title">Đột phá cảnh giới</div><div class="divider"></div></div>
    <div class="info-section">
      <h3>Cảnh giới & Cấp độ</h3>
      <table class="info-table">
        <thead><tr><th>Cảnh giới</th><th>Cấp (Lv)</th><th>Đột phá tại</th></tr></thead>
        <tbody>
          <tr><td style="color:#3A7D5C;font-weight:700">Luyện Khí</td><td>1 → 20</td><td>Lv.20</td></tr>
          <tr><td style="color:#B94040;font-weight:700">Trúc Cơ</td><td>21 → 40</td><td>Lv.40</td></tr>
          <tr><td style="color:#7B68EE;font-weight:700">Kết Đan</td><td>41 → 60</td><td>Lv.60</td></tr>
          <tr><td style="color:#2a5aa0;font-weight:700">Nguyên Anh</td><td>61 → 80</td><td>Lv.80</td></tr>
          <tr><td style="color:#7A5C2E;font-weight:700">Hóa Thần</td><td>81 → 90</td><td>Lv.90</td></tr>
          <tr><td style="color:#5a3d8a;font-weight:700">Luyện Hư</td><td>91 → 99</td><td>Lv.99</td></tr>
          <tr><td style="color:#B8860B;font-weight:700">Đại Thừa / Độ Kiếp</td><td>100+</td><td>—</td></tr>
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
    <div class="page-header"><div class="page-title">Phản ứng nguyên tố</div><div class="divider"></div></div>
    <div class="info-section">
      <h3>Tương Sinh (Ngũ hành)</h3>
      <div class="info-text">Mộc sinh Hỏa → Hỏa sinh Thổ → Thổ sinh Kim → Kim sinh Thủy → Thủy sinh Mộc<br><span style="color:var(--text-3);font-size:12px">Hiệu ứng: Giảm 10% Giáp và Kháng Nguyên Tố của mục tiêu</span></div>
      <h3 style="margin-top:16px">Tương Khắc</h3>
      <div class="info-text">Mộc khắc Thổ → Thổ khắc Thủy → Thủy khắc Hỏa → Hỏa khắc Kim → Kim khắc Mộc<br><span style="color:var(--text-3);font-size:12px">Hiệu ứng: Nhân vật kích hoạt nhận +5% Tăng Sát Nguyên Tố</span></div>
    </div>
    <div class="reaction-grid" id="reactionGrid"></div>
  </div>

  <!-- GEOGRAPHY -->
  <div class="page" id="page-geography">
    <div class="page-header"><div class="page-title">Địa lý thế giới</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addGeoBtn" onclick="openGeoModal()">+ Thêm lục địa</button>
    <div id="geoList"></div>
    <div id="geoEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có lục địa nào.</div></div>
  </div>

  <!-- TIMELINE -->
  <div class="page" id="page-timeline">
    <div class="page-header"><div class="page-title">Dòng thời gian</div><div class="divider"></div><div class="page-desc">Lịch sử và các sự kiện quan trọng trong cốt truyện</div></div>
    <button class="add-btn hidden" id="addTimelineBtn" onclick="openTimelineModal()">+ Thêm sự kiện</button>
    <div id="timelineList"></div>
    <div id="timelineEmpty" class="empty-state" style="display:none"><div class="empty-state-title">Chưa có sự kiện nào. Bật chế độ chỉnh sửa để thêm!</div></div>
  </div>

  <!-- CUSTOM SECTIONS -->
  <div class="page" id="page-custom-sections">
    <div class="page-header"><div class="page-title">Nhánh tùy chỉnh</div><div class="divider"></div><div class="page-desc">Thêm các nhánh lớn và mục nhỏ hoàn toàn tùy ý</div></div>
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
      <button class="btn btn-danger hidden" id="detailDeleteBtn" style="padding:5px 12px;font-size:12px">Xóa</button>
      <button class="btn btn-primary hidden" id="detailEditBtn" style="padding:5px 12px;font-size:12px">Chỉnh sửa</button>
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
<div id="passModal" style="display:none;position:fixed;inset:0;z-index:500;background:rgba(44,31,20,.6);backdrop-filter:blur(8px);align-items:center;justify-content:center;">
  <div class="pass-box">
    <div class="pass-title">Chế độ chỉnh sửa</div>
    <div class="pass-desc">Nhập mật khẩu để kích hoạt quyền chỉnh sửa nội dung</div>
    <input class="form-input pass-input" type="password" id="passInput" placeholder="••••••" onkeydown="if(event.key==='Enter')checkPass()">
    <div class="pass-error" id="passError"></div>
    <button class="btn btn-primary" style="width:100%;margin-bottom:8px" onclick="checkPass()">Xác nhận</button>
    <button class="btn btn-ghost" style="width:100%" onclick="closePassModal()">Hủy</button>
  </div>
</div>

<script>
// ===== DB =====
let DB = JSON.parse(localStorage.getItem('tiengioi_db_v2') || 'null') || {
  characters:[], weapons:[], artifacts:[], herbs:[], minerals:[], drops:[], pills:[],
  geography:[], timeline:[], customSections:[],
  pass: '1900100biet'
};
let editMode = false;
let currentPage = 'home';
let currentDetailItem = null;
let currentDetailType = null;
let charFilter = 'all';
let charView = 'grid';
let itemFilters = {};
let modalType = null;
let modalEditItem = null;

function save() {
  localStorage.setItem('tiengioi_db_v2', JSON.stringify(DB));
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
  'Kim':'#8a8a8a','Mộc':'#3A7D5C','Thủy':'#2a5aa0','Hỏa':'#B94040',
  'Thổ':'#7A5C2E','Phong':'#5C8374','Lôi':'#7B68EE','Băng':'#4a90a0',
  'Độc':'#6a8a2a','Ám':'#4a3080','Quang':'#B8860B'
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
    // Grid
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
    // Table
    const tr = document.createElement('tr');
    tr.onclick = () => openCharDetail(c);
    tr.innerHTML = `<td><b>${c.name||'???'}</b>${c.title?` <span style="color:var(--text-3);font-size:11px;font-style:italic"> — ${c.title}</span>`:''}</td>
    <td><span style="color:${c.stars==5?'#b8860b':'#7B68EE'}">${stars}</span></td>
    <td><span style="color:${col};font-weight:600">${c.element||'—'}</span></td>
    <td>${c.cultivation||'—'}</td><td>${c.weaponType||'—'}</td><td>${c.realm||'—'}</td>`;
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
  const f = itemFilters[type] || 'all';
  const q = (document.getElementById(type+'Search')?.value||'').toLowerCase();
  const data = DB[key].filter(it => {
    if (f!=='all' && it.rarity!==f) return false;
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
    const stars = it.stars==5?'rarity-5star':it.stars==4?'rarity-4star':'rarity-3star';
    card.innerHTML = `
      <div class="item-card-img">
        ${it.image ? `<img src="${it.image}" alt="${it.name}">` : `<span class="placeholder-text">Chưa có ảnh</span>`}
      </div>
      <div class="item-card-body">
        <div class="item-card-name">${it.name||'???'}</div>
        <div class="item-card-meta">${it.rarity?`<span class="rarity-badge ${stars}">${it.rarity}</span>`:''} ${it.subtype||''}</div>
      </div>`;
    grid.appendChild(card);
  });
}
function setItemFilter(el, type, f) {
  const mapPage = {weapon:'weapons',artifact:'artifacts',herb:'herbs',mineral:'minerals',drop:'drops',pill:'pills'};
  document.querySelectorAll(`#page-${mapPage[type]} .filter-btn`).forEach(b => b.classList.remove('active'));
  el.classList.add('active'); itemFilters[type]=f; renderItems(type);
}
function filterItems(type) { renderItems(type); }

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
        <div style="display:flex;gap:8px;align-items:center">
          ${editMode?`<button class="btn btn-primary" style="padding:4px 10px;font-size:11px" onclick="event.stopPropagation();addForce(${gi})">+ Thêm thế lực</button>
          <button class="btn btn-danger" style="padding:4px 10px;font-size:11px" onclick="event.stopPropagation();deleteGeo(${gi})">Xóa</button>`:''}
          <span id="geo-arrow-${gi}">▼</span>
        </div>
      </div>
      <div class="geo-forces" id="geo-forces-${gi}">
        ${g.desc?`<div class="info-text" style="margin-bottom:12px">${g.desc}</div>`:''}
        ${(g.forces||[]).map((f,fi) => `
          <div class="force-item">
            <div style="display:flex;justify-content:space-between;align-items:start">
              <div><div class="force-name">${f.name}</div><div class="force-desc">${f.desc||''}</div></div>
              ${editMode?`<button class="btn btn-danger" style="padding:2px 8px;font-size:11px" onclick="deleteForce(${gi},${fi})">✕</button>`:''}
            </div>
          </div>`).join('')}
        ${!(g.forces||[]).length?'<div style="color:var(--text-4);font-size:12px;font-style:italic">Chưa có thế lực nào.</div>':''}
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
    const div = document.createElement('div'); div.className='timeline-item';
    div.innerHTML = `
      <div class="timeline-card">
        <div class="timeline-year">${ev.year||'???'}</div>
        <div class="timeline-title">${ev.title||'Sự kiện'}</div>
        <div class="timeline-desc">${ev.desc||''}</div>
        ${editMode?`<div style="margin-top:8px;display:flex;gap:6px">
          <button class="btn btn-ghost" style="padding:4px 10px;font-size:11px" onclick="openTimelineModal(${i})">Sửa</button>
          <button class="btn btn-danger" style="padding:4px 10px;font-size:11px" onclick="deleteTimeline(${i})">Xóa</button>
        </div>`:''}
      </div>`;
    wrap.appendChild(div);
  });
  list.appendChild(wrap);
}
function deleteTimeline(i){if(confirm('Xóa sự kiện?')){DB.timeline.splice(i,1);save();renderTimeline();}}

// ===== REACTIONS =====
const reactions = [
  {name:'Thiêu đốt',trigger:'Hỏa + Mộc',effect:'DOT — thiêu đốt sinh mệnh linh đài theo thời gian'},
  {name:'Sinh trưởng',trigger:'Mộc + Thủy',effect:'Hồi phục sinh mệnh linh đài theo thời gian'},
  {name:'Bốc hơi',trigger:'Thủy + Hỏa',effect:'Gây sát thương chuẩn theo % sinh mệnh linh đài mục tiêu'},
  {name:'Nóng chảy',trigger:'Hỏa + Kim',effect:'Giảm Phòng Ngự và Kháng Nguyên Tố mạnh trong thời gian ngắn'},
  {name:'Xói mòn',trigger:'Thổ + Thủy',effect:'Mỗi giây trừ HP và giảm Linh lực cơ bản mục tiêu'},
  {name:'Băng phong',trigger:'Thủy + Băng',effect:'Đóng băng cứng, bất động hoàn toàn'},
  {name:'Phá băng',trigger:'Băng + Kim',effect:'Gây thêm sát thương vật lý xuyên thấu và tổn thương nội tạng'},
  {name:'Tan chảy',trigger:'Băng + Hỏa',effect:'Gây sát thương chuẩn, xóa trạng thái Băng. Đang đóng băng nhận thêm ×1.5'},
  {name:'Điện giải',trigger:'Lôi + Thủy',effect:'Chuỗi sét, giảm phòng thủ địch'},
  {name:'Khuếch tán',trigger:'Phong + bất kỳ (trừ Ám/Quang)',effect:'Lan rộng nguyên tố ra diện rộng'},
  {name:'Kết tinh',trigger:'Thổ + bất kỳ (trừ Ám/Quang)',effect:'Tạo khiên nguyên tố bảo hộ theo hệ'},
  {name:'Hư vô',trigger:'Ám/Quang + bất kỳ',effect:'Vô hiệu phản ứng, xóa trạng thái địch. KHÔNG thể kích ngược lại'},
];
function renderReactions(){
  document.getElementById('reactionGrid').innerHTML=reactions.map(r=>`
    <div class="reaction-card">
      <div class="reaction-name">${r.name}</div>
      <div class="reaction-trigger">${r.trigger}</div>
      <div class="reaction-effect">${r.effect}</div>
    </div>`).join('');
}

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
        <div style="display:flex;gap:8px;align-items:center">
          ${editMode?`<button class="btn btn-primary" style="padding:4px 10px;font-size:11px" onclick="event.stopPropagation();openCustomEntryModal(${si})">+ Thêm mục</button>
          <button class="btn btn-danger" style="padding:4px 10px;font-size:11px" onclick="event.stopPropagation();deleteCustomSection(${si})">Xóa nhánh</button>`:''}
          <span id="custom-arrow-${si}">▼</span>
        </div>
      </div>
      <div class="geo-forces" id="custom-body-${si}">
        ${sec.desc?`<div class="info-text" style="margin-bottom:12px">${sec.desc}</div>`:''}
        ${(sec.entries||[]).map((e,ei) => `
          <div class="force-item" style="cursor:pointer" onclick="openCustomEntryDetail(${si},${ei})">
            <div style="display:flex;justify-content:space-between;align-items:start">
              <div>
                <div class="force-name">${e.name}</div>
                <div class="force-desc">${e.summary||''}</div>
              </div>
              ${editMode?`<div style="display:flex;gap:4px">
                <button class="btn btn-ghost" style="padding:2px 8px;font-size:11px" onclick="event.stopPropagation();openCustomEntryModal(${si},${ei})">Sửa</button>
                <button class="btn btn-danger" style="padding:2px 8px;font-size:11px" onclick="event.stopPropagation();deleteCustomEntry(${si},${ei})">✕</button>
              </div>`:''}
            </div>
          </div>`).join('')}
        ${!(sec.entries||[]).length?'<div style="color:var(--text-4);font-size:12px;font-style:italic">Chưa có mục nào.</div>':''}
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
  if(e.image) html+=`<div style="margin-bottom:14px"><img src="${e.image}" style="max-width:100%;border-radius:var(--radius);border:1px solid var(--border)"></div>`;
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
        ${c.realName?`<div style="font-size:12px;color:var(--text-3);margin-top:2px">Tên thật: ${c.realName}</div>`:''}
        <div class="char-detail-tags">
          ${c.element?`<span class="tag" style="color:${col};border-color:${col}55">${c.element}</span>`:''}
          <span class="tag gold">${stars}</span>
          ${c.cultivation?`<span class="tag">${c.cultivation}</span>`:''}
          ${c.weaponType?`<span class="tag">${c.weaponType}</span>`:''}
          ${c.realm?`<span class="tag gold">${c.realm}</span>`:''}
          ${c.race?`<span class="tag">${c.race}</span>`:''}
          ${c.faction?`<span class="tag">${c.faction}</span>`:''}
        </div>
      </div>
    </div>`;

  // Basic info
  const basicFields = [
    ['Giới tính',c.gender],['Chủng tộc',c.race],['Môn phái',c.faction],
    ['Tuổi thực',c.age],['Ngoại hình',c.ageAppear?c.ageAppear+' tuổi':null],
    ['Quê quán',c.hometown],['Đặc điểm ngoại hình',c.appearance]
  ].filter(([,v])=>v);
  if(basicFields.length){
    html+=`<div class="section-card"><div class="section-title">Thông tin cơ bản</div><div class="field-grid">`;
    basicFields.forEach(([k,v])=>{ html+=`<div class="field-item"><div class="field-label">${k}</div><div class="field-value">${v}</div></div>`; });
    html+=`</div></div>`;
  }

  // Stats
  if(c.hp||c.atk||c.def||c.em||c.crit||c.cdmg||c.special){
    html+=`<div class="section-card"><div class="section-title">Chỉ số thuộc tính</div>`;
    if(c.hp) html+=`<div class="stat-row"><span class="stat-name">Sinh mệnh linh đài (HP)</span><span class="stat-val">${c.hp}</span></div>`;
    if(c.atk) html+=`<div class="stat-row"><span class="stat-name">Linh lực cơ bản (ATK)</span><span class="stat-val">${c.atk}</span></div>`;
    if(c.def) html+=`<div class="stat-row"><span class="stat-name">Thể phách trấn áp (DEF)</span><span class="stat-val">${c.def}</span></div>`;
    if(c.em) html+=`<div class="stat-row"><span class="stat-name">Nguyên tinh thông (EM)</span><span class="stat-val">${c.em}</span></div>`;
    if(c.crit) html+=`<div class="stat-row"><span class="stat-name">Tỷ lệ bạo kích</span><span class="stat-val">${c.crit}</span></div>`;
    if(c.cdmg) html+=`<div class="stat-row"><span class="stat-name">Sát thương bạo kích</span><span class="stat-val">${c.cdmg}</span></div>`;
    if(c.special) html+=`<div class="stat-row"><span class="stat-name">Chỉ số đặc biệt</span><span class="stat-val">${c.special}</span></div>`;
    html+=`</div>`;
  }

  // Skills
  if(c.normalAtk||c.skillE||c.skillQ||c.passive1||c.passive2){
    html+=`<div class="section-card"><div class="section-title">Kỹ năng chiến đấu</div>`;
    if(c.normalAtk) html+=`<div class="skill-card"><div class="skill-type">Tấn công thường</div><div class="skill-name">${c.normalAtk}</div>${c.normalDesc?`<div class="skill-desc">${c.normalDesc}</div>`:''}</div>`;
    if(c.skillE) html+=`<div class="skill-card"><div class="skill-type">Kỹ năng chiến thuật (E)</div><div class="skill-name">${c.skillE}</div>${c.skillEDesc?`<div class="skill-desc">${c.skillEDesc}</div>`:''}</div>`;
    if(c.skillQ) html+=`<div class="skill-card"><div class="skill-type">Đại thần thông (Q)</div><div class="skill-name">${c.skillQ}</div>${c.skillQDesc?`<div class="skill-desc">${c.skillQDesc}</div>`:''}</div>`;
    if(c.passive1||c.passive2) html+=`<div class="skill-card"><div class="skill-type">Bị động</div>${c.passive1?`<div class="skill-desc" style="margin-bottom:5px"><b>Lv.20:</b> ${c.passive1}</div>`:''}${c.passive2?`<div class="skill-desc" style="margin-bottom:5px"><b>Lv.60:</b> ${c.passive2}</div>`:''}${c.passive3?`<div class="skill-desc"><b>Khác:</b> ${c.passive3}</div>`:''}</div>`;
    html+=`</div>`;
  }

  // Constellations
  const consts = [c.c1,c.c2,c.c3,c.c4,c.c5,c.c6].filter(Boolean);
  if(consts.length){
    html+=`<div class="section-card"><div class="section-title">Tinh tú đạo mạch</div><div class="constellation-grid">`;
    [c.c1,c.c2,c.c3,c.c4,c.c5,c.c6].forEach((ct,i)=>{
      html+=`<div class="const-item"><div class="const-level">C${i+1}</div><div class="const-desc">${ct||'—'}</div></div>`;
    });
    html+=`</div></div>`;
  }

  // Story
  if(c.background||c.personality||c.goal||c.secret||c.worldview){
    html+=`<div class="section-card"><div class="section-title">Lý lịch & Cá tính</div>`;
    if(c.background) html+=`<div class="field-full"><div class="field-label">Xuất thân / Lý lịch</div><div class="field-value" style="margin-top:4px;line-height:1.8">${c.background.replace(/\n/g,'<br>')}</div></div>`;
    if(c.personality) html+=`<div class="field-full"><div class="field-label">Tính cách</div><div class="field-value" style="margin-top:4px;line-height:1.8">${c.personality.replace(/\n/g,'<br>')}</div></div>`;
    if(c.worldview) html+=`<div class="field-full"><div class="field-label">Thế giới quan / Triết lý</div><div class="field-value" style="margin-top:4px;line-height:1.8">${c.worldview.replace(/\n/g,'<br>')}</div></div>`;
    if(c.goal) html+=`<div class="field-full"><div class="field-label">Mục tiêu cốt lõi</div><div class="field-value" style="margin-top:4px">${c.goal}</div></div>`;
    if(c.secret) html+=`<div class="field-full"><div class="field-label">Bí mật</div><div class="field-value" style="margin-top:4px">${c.secret}</div></div>`;
    if(c.trauma) html+=`<div class="field-full"><div class="field-label">Vết thương tâm lý / Ám ảnh</div><div class="field-value" style="margin-top:4px">${c.trauma}</div></div>`;
    html+=`</div>`;
  }

  // Relationships
  if(c.relationships) html+=`<div class="section-card"><div class="section-title">Mối quan hệ</div><div class="field-value" style="line-height:1.9">${c.relationships.replace(/\n/g,'<br>')}</div></div>`;

  // Voice lines
  if(c.voiceGreet||c.voiceSkillE||c.voiceSkillQ||c.voiceBattle||c.voiceIdle){
    html+=`<div class="section-card"><div class="section-title">Thoại đặc trưng</div>`;
    if(c.voiceGreet) html+=`<div class="voice-line"><div class="voice-label">Chào hỏi lần đầu</div><div class="voice-text">"${c.voiceGreet}"</div></div>`;
    if(c.voiceSkillE) html+=`<div class="voice-line"><div class="voice-label">Khi dùng kỹ năng E</div><div class="voice-text">"${c.voiceSkillE}"</div></div>`;
    if(c.voiceSkillQ) html+=`<div class="voice-line"><div class="voice-label">Khi dùng tuyệt kỹ Q</div><div class="voice-text">"${c.voiceSkillQ}"</div></div>`;
    if(c.voiceBattle) html+=`<div class="voice-line"><div class="voice-label">Trong chiến đấu</div><div class="voice-text">"${c.voiceBattle}"</div></div>`;
    if(c.voiceIdle) html+=`<div class="voice-line"><div class="voice-label">Nhàn rỗi</div><div class="voice-text">"${c.voiceIdle}"</div></div>`;
    html+=`</div>`;
  }

  // Design notes
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
  const stars = it.stars==5?'rarity-5star':it.stars==4?'rarity-4star':'rarity-3star';
  let html=`<div style="display:flex;gap:16px;align-items:flex-start;margin-bottom:20px;padding:20px;background:var(--bg-card);border:1px solid var(--border);border-radius:var(--radius-lg)">
    <div style="width:90px;height:90px;border-radius:10px;background:var(--bg-panel);border:1px solid var(--border);overflow:hidden;flex-shrink:0;display:flex;align-items:center;justify-content:center">
      ${it.image?`<img src="${it.image}" style="width:100%;height:100%;object-fit:cover">`:`<span style="font-size:11px;color:var(--text-4);font-style:italic;text-align:center;padding:8px">Chưa có ảnh</span>`}
    </div>
    <div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:22px;font-weight:700;color:var(--text)">${it.name||'???'}</div>
      <div style="margin-top:6px;display:flex;gap:6px;flex-wrap:wrap">
        ${it.rarity?`<span class="rarity-badge ${stars}">${it.rarity}</span>`:''}
        ${it.subtype?`<span class="tag">${it.subtype}</span>`:''}
      </div>
    </div>
  </div>`;
  const fieldMap = [
    ['Chỉ số chính',it.mainStat],['Chỉ số phụ',it.subStat],['Kỹ năng vũ khí',it.skill],
    ['Nguồn gốc',it.origin],['Có thể tìm ở',it.location],
    ['Công dụng',it.use],['Công dụng luyện đan',it.alchemyUse],
    ['Rớt từ',it.dropFrom||it.origin],
    ['Hiệu ứng 2 món',it.set2],['Hiệu ứng 4 món',it.set4],
    ['Mô tả',it.desc],['Ghi chú',it.notes]
  ].filter(([,v])=>v);
  if(fieldMap.length){
    html+=`<div class="section-card">`;
    fieldMap.forEach(([k,v])=>{html+=`<div class="field-full" style="margin-bottom:10px"><div class="field-label">${k}</div><div class="field-value" style="margin-top:3px;line-height:1.7">${v}</div></div>`;});
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

// ===== MODALS =====
function openCharModal(edit) {
  if(!editMode) return;
  modalType='character'; modalEditItem=edit||null;
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent=edit?'Chỉnh sửa nhân vật':'Thêm nhân vật mới';
  const c=edit||{};
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section">
      <div class="form-section-title">01 — Hình ảnh</div>
      <div class="form-grid">
        <div class="form-group">
          <label class="form-label">Ảnh đại diện (1:1)</label>
          ${makeImageUpload('image', c.image)}
        </div>
        <div class="form-group">
          <label class="form-label">Ảnh banner / full body</label>
          ${makeImageUpload('banner', c.banner)}
        </div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">02 — Nhận dạng & Danh hiệu</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Tên nhân vật *</label><input class="form-input" id="f_name" value="${c.name||''}"></div>
        <div class="form-group"><label class="form-label">Đạo hiệu / Danh hiệu</label><input class="form-input" id="f_title" value="${c.title||''}"></div>
        <div class="form-group"><label class="form-label">Tên thật</label><input class="form-input" id="f_realName" value="${c.realName||''}"></div>
        <div class="form-group"><label class="form-label">Số sao</label>
          <select class="form-select" id="f_stars">
            <option value="5" ${c.stars==5||!c.stars?'selected':''}>5 sao</option>
            <option value="4" ${c.stars==4?'selected':''}>4 sao</option>
            <option value="3" ${c.stars==3?'selected':''}>3 sao</option>
          </select></div>
        <div class="form-group"><label class="form-label">Giới tính</label>
          <select class="form-select" id="f_gender">
            <option value="">—</option>
            <option value="Nam" ${c.gender==='Nam'?'selected':''}>Nam</option>
            <option value="Nữ" ${c.gender==='Nữ'?'selected':''}>Nữ</option>
            <option value="Vô tướng" ${c.gender==='Vô tướng'?'selected':''}>Vô tướng</option>
          </select></div>
        <div class="form-group"><label class="form-label">Chủng tộc</label>
          <select class="form-select" id="f_race">
            <option value="">—</option>
            ${['Nhân tộc','Yêu tộc','Tiên tộc','Ma tộc','Thần minh','Quỷ tộc','Thú tộc','Lai huyết','Thần thú','Cổ sinh vật'].map(r=>`<option ${c.race===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Tuổi thực</label><input class="form-input" id="f_age" value="${c.age||''}"></div>
        <div class="form-group"><label class="form-label">Ngoại hình trông như... tuổi</label><input class="form-input" id="f_ageAppear" placeholder="Ví dụ: 20" value="${c.ageAppear||''}"></div>
        <div class="form-group"><label class="form-label">Quê quán / Nguồn gốc</label><input class="form-input" id="f_hometown" value="${c.hometown||''}"></div>
        <div class="form-group full"><label class="form-label">Đặc điểm ngoại hình</label><textarea class="form-textarea" style="min-height:60px" id="f_appearance">${c.appearance||''}</textarea></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">03 — Linh căn & Hệ tu</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Hệ nguyên tố</label>
          <select class="form-select" id="f_element">
            <option value="">—</option>
            ${['Kim','Mộc','Thủy','Hỏa','Thổ','Phong','Lôi','Băng','Độc','Quang','Ám'].map(e=>`<option ${c.element===e?'selected':''}>${e}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Hệ tu</label>
          <select class="form-select" id="f_cultivation">
            <option value="">—</option>
            ${['Kiếm Tu','Khí Tu','Đan Tu','Trận Tu','Thể Tu','Ma Tu','Thần Tu','Ẩn Tu'].map(ct=>`<option ${c.cultivation===ct?'selected':''}>${ct}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Loại vũ khí</label>
          <select class="form-select" id="f_weaponType">
            <option value="">—</option>
            ${['Kiếm','Trọng kiếm','Song kiếm','Cung','Nỏ','Pháp khí','Thương','Đại Đao','Quyền giáp','Linh bảo','Phất trần','Bút lông','Chuông linh'].map(w=>`<option ${c.weaponType===w?'selected':''}>${w}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Môn phái / Lực lượng</label><input class="form-input" id="f_faction" value="${c.faction||''}"></div>
        <div class="form-group"><label class="form-label">Cảnh giới hiện tại</label>
          <select class="form-select" id="f_realm">
            <option value="">—</option>
            ${['Luyện Khí','Trúc Cơ','Kết Đan','Nguyên Anh','Hóa Thần','Luyện Hư','Đại Thừa','Độ Kiếp'].map(r=>`<option ${c.realm===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Vai trò chiến đấu</label>
          <select class="form-select" id="f_role">
            <option value="">—</option>
            ${['DPS','Sub-DPS','Support','Heal','Tank','Buff','Debuff','CC','Assassin'].map(r=>`<option ${c.role===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group full"><label class="form-label">Mô tả chiến đấu / Phong cách</label><textarea class="form-textarea" style="min-height:60px" id="f_fightStyle">${c.fightStyle||''}</textarea></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">04 — Chỉ số thuộc tính</div>
      <div class="form-grid cols3">
        <div class="form-group"><label class="form-label">HP</label><input class="form-input" id="f_hp" value="${c.hp||''}"></div>
        <div class="form-group"><label class="form-label">ATK</label><input class="form-input" id="f_atk" value="${c.atk||''}"></div>
        <div class="form-group"><label class="form-label">DEF</label><input class="form-input" id="f_def" value="${c.def||''}"></div>
        <div class="form-group"><label class="form-label">Nguyên tinh thông (EM)</label><input class="form-input" id="f_em" value="${c.em||''}"></div>
        <div class="form-group"><label class="form-label">Tỷ lệ bạo kích</label><input class="form-input" id="f_crit" placeholder="Ví dụ: 5%" value="${c.crit||''}"></div>
        <div class="form-group"><label class="form-label">Sát thương bạo kích</label><input class="form-input" id="f_cdmg" placeholder="Ví dụ: 50%" value="${c.cdmg||''}"></div>
        <div class="form-group full"><label class="form-label">Chỉ số đặc biệt (nếu có)</label><input class="form-input" id="f_special" value="${c.special||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">05 — Kỹ năng chiến đấu</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Tên chuỗi tấn công thường</label><input class="form-input" id="f_normalAtk" value="${c.normalAtk||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả tấn công thường</label><textarea class="form-textarea" id="f_normalDesc">${c.normalDesc||''}</textarea></div>
        <div class="form-group"><label class="form-label">Tên kỹ năng E</label><input class="form-input" id="f_skillE" value="${c.skillE||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả kỹ năng E</label><textarea class="form-textarea" id="f_skillEDesc">${c.skillEDesc||''}</textarea></div>
        <div class="form-group"><label class="form-label">Tên tuyệt kỹ Q</label><input class="form-input" id="f_skillQ" value="${c.skillQ||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả tuyệt kỹ Q</label><textarea class="form-textarea" id="f_skillQDesc">${c.skillQDesc||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Bị động 1 (Lv.20)</label><textarea class="form-textarea" style="min-height:60px" id="f_passive1">${c.passive1||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Bị động 2 (Lv.60)</label><textarea class="form-textarea" style="min-height:60px" id="f_passive2">${c.passive2||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Bị động 3 (Khác)</label><textarea class="form-textarea" style="min-height:60px" id="f_passive3">${c.passive3||''}</textarea></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">06 — Tinh tú đạo mạch (C1–C6)</div>
      <div class="form-grid">
        ${[1,2,3,4,5,6].map(i=>`<div class="form-group"><label class="form-label">Tinh tú C${i}</label><textarea class="form-textarea" style="min-height:60px" id="f_c${i}">${c['c'+i]||''}</textarea></div>`).join('')}
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">07 — Lý lịch & Cá tính</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Lý lịch / Xuất thân</label><textarea class="form-textarea" style="min-height:100px" id="f_background">${c.background||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Tính cách</label><textarea class="form-textarea" style="min-height:80px" id="f_personality">${c.personality||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Thế giới quan / Triết lý sống</label><textarea class="form-textarea" style="min-height:80px" id="f_worldview">${c.worldview||''}</textarea></div>
        <div class="form-group"><label class="form-label">Mục tiêu cốt lõi</label><input class="form-input" id="f_goal" value="${c.goal||''}"></div>
        <div class="form-group"><label class="form-label">Bí mật</label><input class="form-input" id="f_secret" value="${c.secret||''}"></div>
        <div class="form-group full"><label class="form-label">Vết thương tâm lý / Ám ảnh</label><input class="form-input" id="f_trauma" value="${c.trauma||''}"></div>
        <div class="form-group full"><label class="form-label">Mối quan hệ quan trọng</label><textarea class="form-textarea" style="min-height:80px" id="f_relationships" placeholder="Ví dụ: [Tên nhân vật] — Sư phụ, mối quan hệ...">${c.relationships||''}</textarea></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">08 — Thoại đặc trưng</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Chào hỏi lần đầu</label><input class="form-input" id="f_voiceGreet" value="${c.voiceGreet||''}"></div>
        <div class="form-group full"><label class="form-label">Khi dùng kỹ năng E</label><input class="form-input" id="f_voiceSkillE" value="${c.voiceSkillE||''}"></div>
        <div class="form-group full"><label class="form-label">Khi dùng tuyệt kỹ Q</label><input class="form-input" id="f_voiceSkillQ" value="${c.voiceSkillQ||''}"></div>
        <div class="form-group full"><label class="form-label">Trong chiến đấu</label><input class="form-input" id="f_voiceBattle" value="${c.voiceBattle||''}"></div>
        <div class="form-group full"><label class="form-label">Thoại nhàn rỗi</label><input class="form-input" id="f_voiceIdle" value="${c.voiceIdle||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">09 — Nguyên liệu đột phá & Ghi chú</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Nguyên liệu quái rơi</label><input class="form-input" id="f_mat1" value="${c.mat1||''}"></div>
        <div class="form-group"><label class="form-label">Nguyên liệu boss rơi</label><input class="form-input" id="f_mat2" value="${c.mat2||''}"></div>
        <div class="form-group"><label class="form-label">Kỳ trân dị bảo</label><input class="form-input" id="f_mat3" value="${c.mat3||''}"></div>
        <div class="form-group"><label class="form-label">Sách kỹ năng</label><input class="form-input" id="f_mat4" value="${c.mat4||''}"></div>
        <div class="form-group full"><label class="form-label">Ghi chú thiết kế tự do</label><textarea class="form-textarea" id="f_notes">${c.notes||''}</textarea></div>
      </div>
    </div>`;
}

function openItemModal(type, edit) {
  if(!editMode) return;
  modalType=type; modalEditItem=edit||null;
  const typeNames={weapon:'Vũ khí',artifact:'Bộ linh khí',herb:'Thảo dược',mineral:'Khoáng vật',drop:'Vật phẩm rớt',pill:'Đan dược'};
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent=(edit?'Chỉnh sửa':'Thêm')+' '+typeNames[type];
  const it=edit||{};
  let body=`
    <div class="form-section">
      <div class="form-section-title">Hình ảnh</div>
      <div class="form-group">${makeImageUpload('image', it.image)}</div>
    </div>
    <div class="form-section">
      <div class="form-section-title">Thông tin cơ bản</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Tên *</label><input class="form-input" id="f_name" value="${it.name||''}"></div>
        <div class="form-group"><label class="form-label">Phẩm / Cấp</label>
          <select class="form-select" id="f_rarity">
            <option value="">—</option>`;
  if(type==='weapon'){
    ['Phàm khí','Linh khí','Địa khí','Tiên khí','Thần khí'].forEach(r=>{body+=`<option ${it.rarity===r?'selected':''}>${r}</option>`;});
  } else {
    ['Hoàng','Huyền','Địa','Thiên'].forEach(r=>{body+=`<option ${it.rarity===r?'selected':''}>${r}</option>`;});
  }
  body+=`</select></div>`;
  if(type==='weapon'){
    const wTypes=['Kiếm đơn','Trọng kiếm','Song kiếm','Trường cung','Nỏ','Hồ lô','Phất trần','Bút lông','Đạo ấn','Chuông linh','Cổ Thư','Thương','Đại Đao','Thiền trượng','Quyền giáp','Gương linh'];
    body+=`<div class="form-group"><label class="form-label">Loại</label><select class="form-select" id="f_subtype"><option value="">—</option>${wTypes.map(w=>`<option ${it.subtype===w?'selected':''}>${w}</option>`).join('')}</select></div>`;
    body+=`<div class="form-group"><label class="form-label">Chỉ số chính</label><input class="form-input" id="f_mainStat" value="${it.mainStat||''}"></div>`;
    body+=`<div class="form-group"><label class="form-label">Chỉ số phụ</label><input class="form-input" id="f_subStat" value="${it.subStat||''}"></div>`;
    body+=`<div class="form-group full"><label class="form-label">Kỹ năng vũ khí</label><textarea class="form-textarea" id="f_skill">${it.skill||''}</textarea></div>`;
  }
  body+=`<div class="form-group full"><label class="form-label">Mô tả / Lore</label><textarea class="form-textarea" id="f_desc">${it.desc||''}</textarea></div>`;
  if(['herb','mineral','drop'].includes(type)){
    body+=`<div class="form-group full"><label class="form-label">Nguồn gốc / Rớt từ</label><input class="form-input" id="f_origin" value="${it.origin||it.dropFrom||''}"></div>`;
    body+=`<div class="form-group full"><label class="form-label">Có thể tìm ở</label><input class="form-input" id="f_location" value="${it.location||''}"></div>`;
    body+=`<div class="form-group full"><label class="form-label">Công dụng</label><textarea class="form-textarea" id="f_use">${it.use||''}</textarea></div>`;
    if(type==='herb') body+=`<div class="form-group full"><label class="form-label">Công dụng luyện đan</label><textarea class="form-textarea" id="f_alchemyUse">${it.alchemyUse||''}</textarea></div>`;
  }
  if(type==='pill') body+=`<div class="form-group full"><label class="form-label">Công thức / Nguyên liệu</label><textarea class="form-textarea" id="f_use">${it.use||''}</textarea></div>`;
  if(type==='artifact'){
    body+=`<div class="form-group full"><label class="form-label">Hiệu ứng bộ 2 món</label><textarea class="form-textarea" id="f_set2">${it.set2||''}</textarea></div>`;
    body+=`<div class="form-group full"><label class="form-label">Hiệu ứng bộ 4 món</label><textarea class="form-textarea" id="f_set4">${it.set4||''}</textarea></div>`;
  }
  body+=`<div class="form-group full"><label class="form-label">Ghi chú</label><textarea class="form-textarea" id="f_notes">${it.notes||''}</textarea></div>`;
  body+=`</div></div>`;
  document.getElementById('modalBody').innerHTML=body;
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
  modalType='timeline'; modalEditItem=edit!==null?{item:edit,idx:editIdx}:null;
  document.getElementById('modal').style.display='block';
  document.getElementById('modalTitle').textContent=edit?'Chỉnh sửa sự kiện':'Thêm sự kiện mới';
  const ev=edit||{};
  document.getElementById('modalBody').innerHTML=`
    <div class="form-section"><div class="form-section-title">Thông tin sự kiện</div>
    <div class="form-grid">
      <div class="form-group"><label class="form-label">Năm / Mốc thời gian *</label><input class="form-input" id="f_year" placeholder="Ví dụ: Năm 0, Kỷ nguyên thứ nhất..." value="${ev.year||''}"></div>
      <div class="form-group"><label class="form-label">Tên sự kiện *</label><input class="form-input" id="f_name" value="${ev.title||''}"></div>
      <div class="form-group full"><label class="form-label">Mô tả chi tiết</label><textarea class="form-textarea" style="min-height:120px" id="f_desc">${ev.desc||''}</textarea></div>
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
      <div class="form-group full"><label class="form-label">Tên nhánh *</label><input class="form-input" id="f_name" placeholder="Ví dụ: Bản đồ chiến trường, Thú cưỡi, Ký ức đặc biệt..."></div>
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
    <div class="form-section">
      <div class="form-section-title">Hình ảnh (tùy chọn)</div>
      <div class="form-group">${makeImageUpload('image', e.image)}</div>
    </div>
    <div class="form-section"><div class="form-section-title">Nội dung</div>
    <div class="form-grid">
      <div class="form-group full"><label class="form-label">Tên *</label><input class="form-input" id="f_name" value="${e.name||''}"></div>
      <div class="form-group full"><label class="form-label">Tóm tắt ngắn</label><input class="form-input" id="f_summary" value="${e.summary||''}"></div>
      <div class="form-group full"><label class="form-label">Nội dung chi tiết</label><textarea class="form-textarea" style="min-height:160px" id="f_content">${e.content||''}</textarea></div>
      <div class="form-group full"><label class="form-label">Ghi chú</label><input class="form-input" id="f_notes" value="${e.notes||''}"></div>
    </div></div>`;
}

function saveModal() {
  const name = document.getElementById('f_name')?.value?.trim();
  if(!name && modalType!=='timeline') { showToast('Vui lòng nhập tên!','error'); return; }
  
  if(modalType==='character'){
    const c = modalEditItem || {};
    ['name','title','realName','gender','race','element','cultivation','weaponType','faction','realm','role','fightStyle','age','ageAppear','hometown','appearance',
     'hp','atk','def','em','crit','cdmg','special',
     'normalAtk','normalDesc','skillE','skillEDesc','skillQ','skillQDesc','passive1','passive2','passive3',
     'c1','c2','c3','c4','c5','c6',
     'background','personality','worldview','goal','secret','trauma','relationships',
     'voiceGreet','voiceSkillE','voiceSkillQ','voiceBattle','voiceIdle',
     'mat1','mat2','mat3','mat4','notes','image','banner'
    ].forEach(f=>{const el=document.getElementById('f_'+f);if(el)c[f]=el.value;});
    c.stars=parseInt(document.getElementById('f_stars')?.value||'5');
    if(!modalEditItem) DB.characters.push(c);
    save(); closeModal(); renderChars();

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
    ['name','rarity','subtype','mainStat','subStat','skill','desc','origin','use','alchemyUse','location','dropFrom','set2','set4','notes','image'].forEach(f=>{
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
updateStats();
renderReactions();
</script>
</body>
</html>
