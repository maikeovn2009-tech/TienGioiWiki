# TienGioiWiki
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tiên Giới: Khởi Nguyên — Wiki</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+SC:wght@400;600;700&family=Be+Vietnam+Pro:wght@300;400;500;600;700&family=Cinzel:wght@400;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --bg-deep: #07080f;
  --bg-main: #0c0e1a;
  --bg-panel: #111428;
  --bg-card: #161932;
  --bg-card-hover: #1d2040;
  --border: #2a2f52;
  --border-glow: #4a5ab0;
  --accent: #6e8cff;
  --accent2: #a78bfa;
  --accent3: #38bdf8;
  --gold: #e8c97a;
  --gold2: #f5dfa0;
  --text-primary: #e8eaf6;
  --text-secondary: #8892bb;
  --text-muted: #4a5080;
  --star5: #e8c97a;
  --star4: #a78bfa;
  --red: #f87171;
  --green: #4ade80;
  --radius: 10px;
  --radius-lg: 16px;
  --shadow: 0 4px 24px rgba(0,0,0,0.5);
  --glow: 0 0 20px rgba(110,140,255,0.15);
}
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'Be Vietnam Pro',sans-serif;background:var(--bg-deep);color:var(--text-primary);min-height:100vh;overflow-x:hidden;}

/* SCROLLBAR */
::-webkit-scrollbar{width:6px;height:6px;}
::-webkit-scrollbar-track{background:var(--bg-main);}
::-webkit-scrollbar-thumb{background:var(--border-glow);border-radius:3px;}

/* SIDEBAR */
#sidebar{
  position:fixed;left:0;top:0;height:100vh;width:240px;
  background:linear-gradient(180deg,#0d0f1e 0%,#0a0c18 100%);
  border-right:1px solid var(--border);
  display:flex;flex-direction:column;z-index:100;
  transition:transform .3s ease;
}
.sidebar-logo{
  padding:24px 20px 16px;
  border-bottom:1px solid var(--border);
}
.sidebar-logo .logo-title{
  font-family:'Cinzel',serif;
  font-size:13px;letter-spacing:2px;
  color:var(--gold);text-transform:uppercase;
  line-height:1.4;
}
.sidebar-logo .logo-sub{
  font-size:10px;color:var(--text-muted);
  letter-spacing:1px;margin-top:2px;
}
.sidebar-logo .logo-icon{
  font-size:28px;margin-bottom:8px;
  filter:drop-shadow(0 0 8px rgba(232,201,122,0.5));
}
nav{flex:1;overflow-y:auto;padding:12px 0;}
.nav-section{padding:8px 16px 4px;font-size:10px;color:var(--text-muted);text-transform:uppercase;letter-spacing:2px;font-weight:600;}
.nav-item{
  display:flex;align-items:center;gap:10px;
  padding:9px 20px;cursor:pointer;
  font-size:13px;color:var(--text-secondary);
  transition:all .2s;position:relative;
  border-left:2px solid transparent;
}
.nav-item:hover{color:var(--text-primary);background:rgba(110,140,255,0.06);border-left-color:var(--accent);}
.nav-item.active{color:var(--accent);background:rgba(110,140,255,0.1);border-left-color:var(--accent);}
.nav-item .icon{width:18px;text-align:center;font-size:14px;}
.nav-sub{padding-left:48px;}
.nav-sub .nav-item{padding:6px 12px;font-size:12px;}

/* SIDEBAR FOOTER */
.sidebar-footer{padding:16px;border-top:1px solid var(--border);}
#editModeBtn{
  width:100%;padding:9px 14px;border:1px solid var(--border-glow);
  background:transparent;color:var(--accent);border-radius:var(--radius);
  cursor:pointer;font-size:12px;font-family:'Be Vietnam Pro',sans-serif;
  display:flex;align-items:center;gap:8px;justify-content:center;
  transition:all .2s;
}
#editModeBtn:hover{background:rgba(110,140,255,0.15);}
#editModeBtn.active{background:rgba(110,140,255,0.2);border-color:var(--accent);color:#fff;}
.edit-dot{width:7px;height:7px;border-radius:50%;background:var(--text-muted);}
#editModeBtn.active .edit-dot{background:#4ade80;box-shadow:0 0 6px #4ade80;}

/* MAIN */
#main{margin-left:240px;min-height:100vh;}
#topbar{
  position:sticky;top:0;z-index:50;
  background:rgba(12,14,26,0.9);backdrop-filter:blur(12px);
  border-bottom:1px solid var(--border);
  padding:12px 32px;display:flex;align-items:center;justify-content:space-between;
}
.topbar-title{font-family:'Cinzel',serif;font-size:14px;color:var(--gold);letter-spacing:1px;}
.topbar-right{display:flex;align-items:center;gap:12px;}
#exportBtn{
  padding:7px 16px;background:rgba(232,201,122,0.1);
  border:1px solid rgba(232,201,122,0.3);color:var(--gold);
  border-radius:var(--radius);cursor:pointer;font-size:12px;
  font-family:'Be Vietnam Pro',sans-serif;transition:all .2s;
}
#exportBtn:hover{background:rgba(232,201,122,0.2);}

/* PAGE */
.page{display:none;padding:32px;}
.page.active{display:block;}
.page-header{margin-bottom:28px;}
.page-title{
  font-family:'Cinzel',serif;font-size:26px;
  color:var(--gold);letter-spacing:1px;
  display:flex;align-items:center;gap:12px;
}
.page-desc{color:var(--text-secondary);margin-top:6px;font-size:13px;}
.divider{width:60px;height:2px;background:linear-gradient(90deg,var(--gold),transparent);margin:12px 0;}

/* CARDS GRID */
.cards-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:16px;margin-bottom:24px;}
.char-card{
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--radius-lg);overflow:hidden;cursor:pointer;
  transition:all .25s;position:relative;
}
.char-card:hover{border-color:var(--border-glow);transform:translateY(-3px);box-shadow:var(--glow);}
.char-card-img{
  height:120px;background:linear-gradient(135deg,#1a1f3a,#0f1228);
  display:flex;align-items:center;justify-content:center;
  font-size:48px;position:relative;overflow:hidden;
}
.char-card-img img{width:100%;height:100%;object-fit:cover;}
.char-card-img .no-img{color:var(--text-muted);}
.char-rarity-bar{height:3px;}
.rarity-5{background:linear-gradient(90deg,var(--star5),#f5a623);}
.rarity-4{background:linear-gradient(90deg,var(--star4),#818cf8);}
.rarity-3{background:linear-gradient(90deg,#60a5fa,#3b82f6);}
.char-card-info{padding:10px 12px;}
.char-card-name{font-size:13px;font-weight:600;color:var(--text-primary);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.char-card-meta{display:flex;align-items:center;gap:6px;margin-top:4px;}
.char-element-tag{
  font-size:10px;padding:2px 7px;border-radius:20px;
  background:rgba(110,140,255,0.15);color:var(--accent);border:1px solid rgba(110,140,255,0.3);
}
.char-stars{color:var(--star5);font-size:10px;letter-spacing:-1px;}
.char-stars.s4{color:var(--star4);}

/* VIEW TOGGLE */
.view-toggle{display:flex;gap:4px;margin-bottom:16px;}
.view-btn{
  padding:7px 14px;background:transparent;
  border:1px solid var(--border);color:var(--text-secondary);
  border-radius:8px;cursor:pointer;font-size:12px;
  font-family:'Be Vietnam Pro',sans-serif;transition:all .2s;
}
.view-btn.active{background:rgba(110,140,255,0.15);border-color:var(--accent);color:var(--accent);}

/* TABLE VIEW */
.data-table{width:100%;border-collapse:collapse;}
.data-table th{
  text-align:left;padding:10px 14px;font-size:11px;
  color:var(--text-muted);text-transform:uppercase;letter-spacing:1px;
  background:var(--bg-panel);border-bottom:1px solid var(--border);font-weight:600;
}
.data-table td{padding:10px 14px;font-size:13px;border-bottom:1px solid rgba(42,47,82,0.5);}
.data-table tr:hover td{background:rgba(110,140,255,0.05);}
.data-table tr{cursor:pointer;}

/* FILTER BAR */
.filter-bar{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:20px;align-items:center;}
.filter-btn{
  padding:6px 14px;background:var(--bg-card);
  border:1px solid var(--border);color:var(--text-secondary);
  border-radius:20px;cursor:pointer;font-size:12px;
  font-family:'Be Vietnam Pro',sans-serif;transition:all .2s;
}
.filter-btn:hover,.filter-btn.active{background:rgba(110,140,255,0.15);border-color:var(--accent);color:var(--accent);}
.search-box{
  padding:7px 14px;background:var(--bg-card);border:1px solid var(--border);
  color:var(--text-primary);border-radius:20px;font-size:12px;
  font-family:'Be Vietnam Pro',sans-serif;outline:none;min-width:200px;
  transition:border-color .2s;
}
.search-box:focus{border-color:var(--accent);}
.search-box::placeholder{color:var(--text-muted);}

/* ADD BUTTON */
.add-btn{
  display:inline-flex;align-items:center;gap:8px;
  padding:9px 20px;background:linear-gradient(135deg,rgba(110,140,255,0.2),rgba(167,139,250,0.2));
  border:1px solid var(--accent);color:var(--accent);
  border-radius:var(--radius);cursor:pointer;font-size:13px;
  font-family:'Be Vietnam Pro',sans-serif;font-weight:500;
  transition:all .2s;margin-bottom:20px;
}
.add-btn:hover{background:linear-gradient(135deg,rgba(110,140,255,0.35),rgba(167,139,250,0.35));box-shadow:0 0 15px rgba(110,140,255,0.3);}
.add-btn.hidden{display:none;}

/* DETAIL VIEW */
#detailOverlay{
  display:none;position:fixed;inset:0;z-index:200;
  background:rgba(0,0,0,0.7);backdrop-filter:blur(4px);
  animation:fadeIn .2s ease;
}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
#detailPanel{
  position:fixed;top:0;right:0;height:100vh;width:720px;
  background:var(--bg-main);border-left:1px solid var(--border);
  overflow-y:auto;z-index:201;
  animation:slideIn .3s ease;
}
@keyframes slideIn{from{transform:translateX(40px);opacity:0}to{transform:translateX(0);opacity:1}}
.detail-close{
  position:sticky;top:0;background:rgba(12,14,26,0.95);
  padding:16px 24px;display:flex;align-items:center;justify-content:space-between;
  border-bottom:1px solid var(--border);z-index:10;
}
.close-btn{
  width:32px;height:32px;border-radius:50%;
  background:var(--bg-card);border:1px solid var(--border);
  color:var(--text-secondary);cursor:pointer;display:flex;align-items:center;justify-content:center;
  font-size:16px;transition:all .2s;
}
.close-btn:hover{border-color:var(--red);color:var(--red);}
.detail-content{padding:24px;}

/* SECTION CARD */
.section-card{
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--radius-lg);padding:20px;margin-bottom:16px;
}
.section-title{
  font-size:12px;text-transform:uppercase;letter-spacing:2px;
  color:var(--accent2);font-weight:600;margin-bottom:14px;
  display:flex;align-items:center;gap:8px;
}
.section-title::before{content:'';width:3px;height:14px;background:var(--accent2);border-radius:2px;}

/* FIELD DISPLAY */
.field-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.field-grid.cols3{grid-template-columns:1fr 1fr 1fr;}
.field-item{display:flex;flex-direction:column;gap:3px;}
.field-label{font-size:10px;color:var(--text-muted);text-transform:uppercase;letter-spacing:1px;}
.field-value{font-size:13px;color:var(--text-primary);}
.field-value.empty{color:var(--text-muted);font-style:italic;}
.field-full{margin-bottom:10px;}

/* STAT TABLE */
.stat-row{display:flex;align-items:center;justify-content:space-between;padding:7px 0;border-bottom:1px solid rgba(42,47,82,0.4);}
.stat-row:last-child{border-bottom:none;}
.stat-name{font-size:12px;color:var(--text-secondary);display:flex;align-items:center;gap:6px;}
.stat-val{font-size:13px;color:var(--text-primary);font-weight:500;}

/* REALM TABLE */
.realm-table{width:100%;border-collapse:collapse;font-size:12px;}
.realm-table th{padding:8px 10px;background:rgba(26,31,58,0.8);color:var(--text-muted);text-align:left;font-size:10px;text-transform:uppercase;letter-spacing:1px;}
.realm-table td{padding:8px 10px;border-bottom:1px solid rgba(42,47,82,0.4);color:var(--text-secondary);}
.realm-table tr.current td{color:var(--gold);background:rgba(232,201,122,0.05);}
.realm-badge{display:inline-flex;align-items:center;gap:5px;}

/* SKILL CARD */
.skill-card{background:rgba(26,31,58,0.6);border:1px solid rgba(42,47,82,0.8);border-radius:10px;padding:14px;margin-bottom:10px;}
.skill-type{font-size:10px;text-transform:uppercase;letter-spacing:1px;color:var(--accent);margin-bottom:4px;}
.skill-name{font-size:14px;font-weight:600;margin-bottom:6px;}
.skill-desc{font-size:12px;color:var(--text-secondary);line-height:1.6;}

/* RELATIONSHIP TABLE */
.rel-table{width:100%;border-collapse:collapse;font-size:13px;}
.rel-table td{padding:8px 10px;border-bottom:1px solid rgba(42,47,82,0.4);}
.rel-name{color:var(--accent3);font-weight:500;}
.rel-type{color:var(--accent2);font-size:11px;}

/* CONSTELLATION */
.constellation-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;}
.const-item{background:rgba(26,31,58,0.6);border:1px solid rgba(42,47,82,0.8);border-radius:8px;padding:12px;}
.const-level{font-size:10px;color:var(--accent2);font-weight:600;text-transform:uppercase;letter-spacing:1px;}
.const-desc{font-size:12px;color:var(--text-secondary);margin-top:4px;}

/* MODAL */
#modal{display:none;position:fixed;inset:0;z-index:300;background:rgba(0,0,0,0.8);backdrop-filter:blur(6px);overflow-y:auto;padding:40px 20px;}
.modal-box{
  max-width:800px;margin:0 auto;
  background:var(--bg-main);border:1px solid var(--border);
  border-radius:var(--radius-lg);overflow:hidden;
  animation:slideIn .3s ease;
}
.modal-header{
  padding:20px 24px;border-bottom:1px solid var(--border);
  display:flex;align-items:center;justify-content:space-between;
  background:var(--bg-panel);
}
.modal-title{font-family:'Cinzel',serif;font-size:16px;color:var(--gold);}
.modal-body{padding:24px;max-height:70vh;overflow-y:auto;}
.modal-footer{padding:16px 24px;border-top:1px solid var(--border);display:flex;justify-content:flex-end;gap:10px;}

/* FORM ELEMENTS */
.form-section{margin-bottom:20px;}
.form-section-title{
  font-size:11px;text-transform:uppercase;letter-spacing:2px;
  color:var(--accent2);font-weight:600;margin-bottom:12px;padding-bottom:6px;
  border-bottom:1px solid rgba(42,47,82,0.6);
}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.form-grid.cols3{grid-template-columns:1fr 1fr 1fr;}
.form-group{display:flex;flex-direction:column;gap:5px;}
.form-group.full{grid-column:1/-1;}
.form-label{font-size:11px;color:var(--text-muted);text-transform:uppercase;letter-spacing:0.5px;}
.form-input,.form-select,.form-textarea{
  background:var(--bg-card);border:1px solid var(--border);
  color:var(--text-primary);border-radius:8px;
  padding:9px 12px;font-size:13px;font-family:'Be Vietnam Pro',sans-serif;
  outline:none;transition:border-color .2s;width:100%;
}
.form-input:focus,.form-select:focus,.form-textarea:focus{border-color:var(--accent);}
.form-select option{background:var(--bg-panel);}
.form-textarea{min-height:80px;resize:vertical;}
.form-checkbox-group{display:flex;flex-wrap:wrap;gap:8px;margin-top:4px;}
.form-checkbox-label{
  display:flex;align-items:center;gap:6px;cursor:pointer;
  font-size:12px;color:var(--text-secondary);
  padding:4px 10px;background:var(--bg-card);border:1px solid var(--border);
  border-radius:20px;transition:all .2s;
}
.form-checkbox-label:hover{border-color:var(--accent);color:var(--text-primary);}
.form-checkbox-label input[type=checkbox]{accent-color:var(--accent);}
.form-checkbox-label input[type=radio]{accent-color:var(--accent);}

/* BUTTONS */
.btn{
  padding:9px 20px;border-radius:var(--radius);cursor:pointer;
  font-size:13px;font-family:'Be Vietnam Pro',sans-serif;font-weight:500;
  transition:all .2s;border:1px solid;
}
.btn-primary{background:linear-gradient(135deg,rgba(110,140,255,0.3),rgba(167,139,250,0.3));border-color:var(--accent);color:var(--accent);}
.btn-primary:hover{background:linear-gradient(135deg,rgba(110,140,255,0.5),rgba(167,139,250,0.5));}
.btn-danger{background:rgba(248,113,113,0.1);border-color:var(--red);color:var(--red);}
.btn-danger:hover{background:rgba(248,113,113,0.2);}
.btn-ghost{background:transparent;border-color:var(--border);color:var(--text-secondary);}
.btn-ghost:hover{border-color:var(--text-secondary);color:var(--text-primary);}

/* HOME PAGE */
.home-hero{
  background:linear-gradient(135deg,rgba(110,140,255,0.08),rgba(167,139,250,0.05));
  border:1px solid var(--border);border-radius:var(--radius-lg);
  padding:40px;margin-bottom:28px;position:relative;overflow:hidden;
}
.home-hero::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse at 80% 50%,rgba(110,140,255,0.08),transparent 70%);
  pointer-events:none;
}
.home-hero-title{font-family:'Cinzel',serif;font-size:32px;color:var(--gold);margin-bottom:8px;}
.home-hero-sub{color:var(--text-secondary);font-size:14px;max-width:500px;line-height:1.7;}
.home-stats{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;margin-bottom:28px;}
.home-stat{
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--radius-lg);padding:20px;text-align:center;
}
.home-stat-num{font-size:28px;font-weight:700;color:var(--accent);font-family:'Cinzel',serif;}
.home-stat-label{font-size:11px;color:var(--text-muted);text-transform:uppercase;letter-spacing:1px;margin-top:4px;}
.home-sections{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;}
.home-section-card{
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--radius-lg);padding:20px;cursor:pointer;
  transition:all .25s;display:flex;align-items:flex-start;gap:14px;
}
.home-section-card:hover{border-color:var(--border-glow);transform:translateY(-2px);box-shadow:var(--glow);}
.home-section-icon{font-size:24px;width:44px;height:44px;display:flex;align-items:center;justify-content:center;background:rgba(110,140,255,0.1);border-radius:10px;}
.home-section-title{font-size:14px;font-weight:600;margin-bottom:4px;}
.home-section-desc{font-size:12px;color:var(--text-muted);}

/* REACTION TABLE */
.reaction-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:12px;}
.reaction-card{background:var(--bg-card);border:1px solid var(--border);border-radius:var(--radius);padding:14px;}
.reaction-name{font-size:13px;font-weight:600;margin-bottom:4px;color:var(--gold);}
.reaction-trigger{font-size:11px;color:var(--accent2);margin-bottom:6px;}
.reaction-effect{font-size:12px;color:var(--text-secondary);line-height:1.5;}

/* ELEMENT TAGS */
.elem-kim{color:#c0c0c0;} .elem-moc{color:#4ade80;} .elem-thuy{color:#38bdf8;}
.elem-hoa{color:#f87171;} .elem-tho{color:#a16207;} .elem-phong{color:#86efac;}
.elem-loi{color:#818cf8;} .elem-bang{color:#bae6fd;} .elem-doc{color:#a3e635;}
.elem-am{color:#6366f1;} .elem-quang{color:#fbbf24;}
.elem-tag{
  display:inline-block;padding:2px 8px;border-radius:12px;font-size:11px;
  background:rgba(255,255,255,0.07);margin-right:4px;
}

/* GEOGRAPHY */
.geo-continent{background:var(--bg-card);border:1px solid var(--border);border-radius:var(--radius-lg);margin-bottom:16px;overflow:hidden;}
.geo-continent-header{padding:16px 20px;display:flex;align-items:center;justify-content:space-between;cursor:pointer;background:rgba(26,31,58,0.5);}
.geo-continent-name{font-size:15px;font-weight:600;color:var(--gold);}
.geo-forces{padding:16px 20px;}
.force-item{padding:10px 14px;background:rgba(26,31,58,0.4);border-radius:8px;margin-bottom:8px;border:1px solid rgba(42,47,82,0.5);}
.force-name{font-size:13px;font-weight:500;color:var(--text-primary);}
.force-desc{font-size:12px;color:var(--text-secondary);margin-top:3px;}

/* RESPONSIVE */
@media(max-width:900px){
  #sidebar{transform:translateX(-100%);}
  #sidebar.open{transform:translateX(0);}
  #main{margin-left:0;}
}

/* TOAST */
.toast{
  position:fixed;bottom:24px;right:24px;z-index:999;
  padding:12px 20px;background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--radius);font-size:13px;color:var(--text-primary);
  box-shadow:var(--shadow);animation:toastIn .3s ease;
  display:flex;align-items:center;gap:10px;
}
@keyframes toastIn{from{transform:translateY(20px);opacity:0}to{transform:translateY(0);opacity:1}}
.toast.success{border-color:var(--green);}
.toast.error{border-color:var(--red);}

/* PASS MODAL */
#passModal{display:none;position:fixed;inset:0;z-index:500;background:rgba(0,0,0,0.85);backdrop-filter:blur(8px);display:none;align-items:center;justify-content:center;}
.pass-box{
  background:var(--bg-main);border:1px solid var(--border);
  border-radius:var(--radius-lg);padding:32px;width:340px;text-align:center;
  animation:slideIn .3s ease;
}
.pass-icon{font-size:40px;margin-bottom:12px;filter:drop-shadow(0 0 8px rgba(110,140,255,0.4));}
.pass-title{font-family:'Cinzel',serif;font-size:16px;color:var(--gold);margin-bottom:8px;}
.pass-desc{font-size:12px;color:var(--text-muted);margin-bottom:20px;}
.pass-input{width:100%;text-align:center;letter-spacing:4px;font-size:16px;margin-bottom:16px;}
.pass-error{color:var(--red);font-size:12px;margin-bottom:8px;min-height:18px;}

/* REALM BADGE COLORS */
.realm-luyen-khi{color:#86efac;} .realm-truc-co{color:#f87171;}
.realm-ket-dan{color:#a78bfa;} .realm-nguyen-anh{color:#38bdf8;}
.realm-hoa-than{color:#fbbf24;} .realm-luyen-hu{color:#818cf8;}
.realm-dai-thua{color:#e8c97a;}

/* GENERIC INFO PAGE */
.info-section{background:var(--bg-card);border:1px solid var(--border);border-radius:var(--radius-lg);padding:20px;margin-bottom:16px;}
.info-section h3{font-family:'Cinzel',serif;font-size:15px;color:var(--gold);margin-bottom:14px;}
.info-text{font-size:13px;color:var(--text-secondary);line-height:1.8;}
.info-table{width:100%;border-collapse:collapse;font-size:13px;margin-top:8px;}
.info-table th{padding:8px 12px;background:rgba(26,31,58,0.8);color:var(--text-muted);text-align:left;font-size:11px;text-transform:uppercase;letter-spacing:1px;border:1px solid rgba(42,47,82,0.5);}
.info-table td{padding:8px 12px;border:1px solid rgba(42,47,82,0.4);color:var(--text-secondary);}
.info-table tr:hover td{background:rgba(110,140,255,0.05);}

/* EDIT INLINE */
.editable-field{position:relative;}
.editable-field:hover .edit-icon{opacity:1;}
.edit-icon{position:absolute;right:0;top:50%;transform:translateY(-50%);opacity:0;transition:opacity .2s;cursor:pointer;font-size:12px;color:var(--accent);}
.edit-mode .editable-block{cursor:pointer;border-radius:4px;transition:background .2s;outline:1px dashed transparent;}
.edit-mode .editable-block:hover{background:rgba(110,140,255,0.08);outline-color:var(--border-glow);}

/* ITEM CARDS */
.item-card{background:var(--bg-card);border:1px solid var(--border);border-radius:var(--radius);padding:14px;cursor:pointer;transition:all .2s;}
.item-card:hover{border-color:var(--border-glow);transform:translateY(-2px);}
.item-card-icon{font-size:32px;margin-bottom:8px;}
.item-card-name{font-size:13px;font-weight:600;}
.item-card-meta{font-size:11px;color:var(--text-muted);margin-top:3px;}
.rarity-badge{display:inline-block;padding:2px 8px;border-radius:10px;font-size:10px;font-weight:600;}
.rarity-hoanh{background:rgba(156,163,175,0.15);color:#9ca3af;border:1px solid rgba(156,163,175,0.3);}
.rarity-huyen{background:rgba(96,165,250,0.15);color:#60a5fa;border:1px solid rgba(96,165,250,0.3);}
.rarity-dia{background:rgba(167,139,250,0.15);color:#a78bfa;border:1px solid rgba(167,139,250,0.3);}
.rarity-thien{background:rgba(232,201,122,0.15);color:#e8c97a;border:1px solid rgba(232,201,122,0.3);}
</style>
</head>
<body>

<!-- SIDEBAR -->
<div id="sidebar">
  <div class="sidebar-logo">
    <div class="logo-icon">☯</div>
    <div class="logo-title">Tiên Giới<br>Khởi Nguyên</div>
    <div class="logo-sub">Wiki · Lore Database</div>
  </div>
  <nav id="nav">
    <div class="nav-section">Tổng quan</div>
    <div class="nav-item active" data-page="home"><span class="icon">🏠</span> Trang chủ</div>

    <div class="nav-section">Nhân vật</div>
    <div class="nav-item" data-page="characters"><span class="icon">⚔️</span> Thư viện nhân vật</div>
    <div class="nav-item" data-page="char-info"><span class="icon">📊</span> Thông tin hệ tu</div>

    <div class="nav-section">Trang bị</div>
    <div class="nav-item" data-page="weapons"><span class="icon">🗡️</span> Pháp bảo trấn vật</div>
    <div class="nav-item" data-page="artifacts"><span class="icon">💎</span> Linh khí tùy thân</div>

    <div class="nav-section">Vật phẩm</div>
    <div class="nav-item" data-page="herbs"><span class="icon">🌿</span> Thảo dược</div>
    <div class="nav-item" data-page="minerals"><span class="icon">⛏️</span> Khoáng vật</div>
    <div class="nav-item" data-page="drops"><span class="icon">👾</span> Đồ rớt từ quái</div>
    <div class="nav-item" data-page="pills"><span class="icon">⚗️</span> Đan dược</div>

    <div class="nav-section">Cơ chế</div>
    <div class="nav-item" data-page="breakthrough"><span class="icon">🌀</span> Cơ chế đột phá</div>
    <div class="nav-item" data-page="reactions"><span class="icon">⚡</span> Phản ứng nguyên tố</div>

    <div class="nav-section">Thế giới</div>
    <div class="nav-item" data-page="geography"><span class="icon">🗺️</span> Địa lý</div>
  </nav>
  <div class="sidebar-footer">
    <button id="editModeBtn" onclick="toggleEditMode()">
      <span class="edit-dot"></span>
      <span id="editBtnText">Chế độ chỉnh sửa</span>
    </button>
  </div>
</div>

<!-- MAIN -->
<div id="main">
  <div id="topbar">
    <span class="topbar-title" id="topbarTitle">Trang chủ</span>
    <div class="topbar-right">
      <button id="exportBtn" onclick="exportHTML()">⬇ Xuất HTML</button>
    </div>
  </div>

  <!-- HOME PAGE -->
  <div class="page active" id="page-home">
    <div class="home-hero">
      <div class="home-hero-title">Tiên Giới: Khởi Nguyên</div>
      <div class="home-hero-sub">Wiki nội bộ cho thế giới tu tiên — lưu trữ nhân vật, trang bị, vật phẩm, cơ chế và địa lý của vũ trụ đang được xây dựng.</div>
    </div>
    <div class="home-stats">
      <div class="home-stat"><div class="home-stat-num" id="stat-chars">0</div><div class="home-stat-label">Nhân vật</div></div>
      <div class="home-stat"><div class="home-stat-num" id="stat-weapons">0</div><div class="home-stat-label">Vũ khí</div></div>
      <div class="home-stat"><div class="home-stat-num" id="stat-items">0</div><div class="home-stat-label">Vật phẩm</div></div>
      <div class="home-stat"><div class="home-stat-num" id="stat-places">0</div><div class="home-stat-label">Lục địa</div></div>
    </div>
    <div class="home-sections">
      <div class="home-section-card" onclick="navigate('characters')"><div class="home-section-icon">⚔️</div><div><div class="home-section-title">Thư viện nhân vật</div><div class="home-section-desc">Xem và quản lý tất cả nhân vật trong game</div></div></div>
      <div class="home-section-card" onclick="navigate('reactions')"><div class="home-section-icon">⚡</div><div><div class="home-section-title">Phản ứng nguyên tố</div><div class="home-section-desc">11 hệ nguyên tố, tương sinh tương khắc</div></div></div>
      <div class="home-section-card" onclick="navigate('breakthrough')"><div class="home-section-icon">🌀</div><div><div class="home-section-title">Cơ chế đột phá</div><div class="home-section-desc">7 cảnh giới từ Luyện Khí đến Đại Thừa</div></div></div>
      <div class="home-section-card" onclick="navigate('weapons')"><div class="home-section-icon">🗡️</div><div><div class="home-section-title">Pháp bảo trấn vật</div><div class="home-section-desc">Vũ khí 5 cấp độ từ Phàm khí đến Thần khí</div></div></div>
      <div class="home-section-card" onclick="navigate('geography')"><div class="home-section-icon">🗺️</div><div><div class="home-section-title">Địa lý thế giới</div><div class="home-section-desc">Các lục địa và thế lực trong thế giới</div></div></div>
      <div class="home-section-card" onclick="navigate('char-info')"><div class="home-section-icon">📊</div><div><div class="home-section-title">Hệ tu & Vai trò</div><div class="home-section-desc">8 hệ tu với các vai trò chiến đấu khác nhau</div></div></div>
    </div>
  </div>

  <!-- CHARACTERS PAGE -->
  <div class="page" id="page-characters">
    <div class="page-header">
      <div class="page-title">⚔️ Thư viện nhân vật</div>
      <div class="divider"></div>
      <div class="page-desc">Tất cả nhân vật trong Tiên Giới: Khởi Nguyên</div>
    </div>
    <div class="filter-bar">
      <input class="search-box" type="text" placeholder="🔍  Tìm kiếm nhân vật..." id="charSearch" oninput="filterChars()">
      <button class="filter-btn active" data-filter="all" onclick="setCharFilter(this,'all')">Tất cả</button>
      <button class="filter-btn" data-filter="5" onclick="setCharFilter(this,'5')">★ 5 sao</button>
      <button class="filter-btn" data-filter="4" onclick="setCharFilter(this,'4')">★ 4 sao</button>
      <div class="view-toggle" style="margin-left:auto;margin-bottom:0">
        <button class="view-btn active" onclick="setCharView('grid',this)">▦ Grid</button>
        <button class="view-btn" onclick="setCharView('table',this)">☰ Bảng</button>
      </div>
    </div>
    <button class="add-btn hidden" id="addCharBtn" onclick="openCharModal()">＋ Thêm nhân vật</button>
    <div id="charGridView"><div class="cards-grid" id="charGrid"></div></div>
    <div id="charTableView" style="display:none">
      <table class="data-table">
        <thead><tr><th>Nhân vật</th><th>Sao</th><th>Hệ nguyên tố</th><th>Hệ tu</th><th>Vũ khí</th><th>Cảnh giới</th></tr></thead>
        <tbody id="charTableBody"></tbody>
      </table>
    </div>
    <div id="charEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)">
      <div style="font-size:48px;margin-bottom:12px">👤</div>
      <div>Chưa có nhân vật nào. Bật chế độ chỉnh sửa để thêm!</div>
    </div>
  </div>

  <!-- CHAR INFO PAGE -->
  <div class="page" id="page-char-info">
    <div class="page-header">
      <div class="page-title">📊 Hệ tu & Chỉ số</div>
      <div class="divider"></div>
    </div>
    <div class="info-section">
      <h3>⚙️ Hệ tu — Vai trò chiến đấu</h3>
      <table class="info-table">
        <thead><tr><th>Hệ tu</th><th>Vai trò</th><th>Mô tả</th></tr></thead>
        <tbody>
          <tr><td>Kiếm Tu</td><td><span style="color:#f87171">DPS</span></td><td>Công kích liên tục, sát thương cao, cận chiến</td></tr>
          <tr><td>Khí Tu</td><td><span style="color:#fbbf24">Sub-DPS / Buff</span></td><td>Vận dụng linh khí, hiệu ứng nguyên tố, linh hoạt</td></tr>
          <tr><td>Đan Tu</td><td><span style="color:#4ade80">Heal / Support</span></td><td>Luyện đan, hồi phục, tăng cường đồng đội</td></tr>
          <tr><td>Trận Tu</td><td><span style="color:#38bdf8">Support / CC</span></td><td>Bố trận pháp, kiểm soát vùng, buff khu vực</td></tr>
          <tr><td>Thể Tu</td><td><span style="color:#a78bfa">Tank / DPS</span></td><td>Luyện thân, phòng thủ cao, phản đòn mạnh</td></tr>
          <tr><td>Ma Tu</td><td><span style="color:#6366f1">DPS / Debuff</span></td><td>Tiêu hao sinh mệnh bản thân đổi lấy sức mạnh</td></tr>
          <tr><td>Thần Tu</td><td><span style="color:#818cf8">Sub-DPS / Buff</span></td><td>Thần thức, cổ pháp, biến hóa khôn lường</td></tr>
          <tr><td>Ẩn Tu</td><td><span style="color:#9ca3af">Assassin / Debuff</span></td><td>Tàng hình, ám sát, hạ gục mục tiêu đơn</td></tr>
        </tbody>
      </table>
    </div>
    <div class="info-section">
      <h3>📈 Chỉ số thuộc tính cơ bản (Level 99)</h3>
      <table class="info-table">
        <thead><tr><th>Chỉ số</th><th>Max ★★★★</th><th>Max ★★★★★</th><th>Ghi chú</th></tr></thead>
        <tbody>
          <tr><td>❤️ Sinh mệnh linh đài (HP)</td><td>15,000</td><td>30,000</td><td>Tổng HP nhân vật</td></tr>
          <tr><td>⚔️ Linh lực cơ bản (ATK)</td><td>300</td><td>500</td><td>Sát thương vật lý & linh lực</td></tr>
          <tr><td>🛡️ Thể phách trấn áp (DEF)</td><td>600</td><td>1,000</td><td>Giảm sát thương nhận vào</td></tr>
          <tr><td>🌀 Nguyên tinh thông (EM)</td><td>0</td><td>0</td><td>Tăng hiệu quả phản ứng nguyên tố</td></tr>
          <tr><td>⚡ Nạp linh lực</td><td>100%</td><td>110%</td><td>Tốc độ hồi phục Chân Nguyên</td></tr>
          <tr><td>🎯 Tỷ lệ bạo kích (CRIT%)</td><td>5%</td><td>5%</td><td>Mặc định ~5%</td></tr>
          <tr><td>💥 Sát thương bạo kích (CDMG%)</td><td>50%</td><td>50%</td><td>Mặc định ~50%</td></tr>
          <tr><td>🌊 Tăng sát thương hệ</td><td>25%</td><td>30%</td><td>Theo linh căn đã chọn</td></tr>
          <tr><td>🌿 Chỉ số chữa lành</td><td>22.7%</td><td>35%</td><td>Chỉ nhân vật Heal dùng</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- WEAPONS PAGE -->
  <div class="page" id="page-weapons">
    <div class="page-header">
      <div class="page-title">🗡️ Pháp bảo trấn vật</div>
      <div class="divider"></div>
    </div>
    <div class="filter-bar">
      <input class="search-box" type="text" placeholder="🔍  Tìm kiếm vũ khí..." id="weaponSearch" oninput="filterItems('weapon')">
      <button class="filter-btn active" data-filter="all" onclick="setItemFilter(this,'weapon','all')">Tất cả</button>
      <button class="filter-btn" onclick="setItemFilter(this,'weapon','Thần khí')">★★★★★ Thần khí</button>
      <button class="filter-btn" onclick="setItemFilter(this,'weapon','Tiên khí')">★★★★ Tiên khí</button>
      <button class="filter-btn" onclick="setItemFilter(this,'weapon','Địa khí')">★★★ Địa khí</button>
    </div>
    <button class="add-btn hidden" id="addWeaponBtn" onclick="openItemModal('weapon')">＋ Thêm vũ khí</button>
    <div class="cards-grid" id="weaponGrid"></div>
    <div id="weaponEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)"><div style="font-size:48px;margin-bottom:12px">🗡️</div><div>Chưa có vũ khí nào.</div></div>
    <div class="info-section" style="margin-top:24px">
      <h3>📋 Phân cấp vũ khí</h3>
      <table class="info-table">
        <thead><tr><th>Cấp sao</th><th>Tên gọi</th><th>Ghi chú</th></tr></thead>
        <tbody>
          <tr><td>⭐</td><td>Phàm khí</td><td>Cấp thấp nhất, phổ thông</td></tr>
          <tr><td>⭐⭐</td><td>Linh khí</td><td>Có thể tự luyện/trao đổi</td></tr>
          <tr><td>⭐⭐⭐</td><td>Địa khí</td><td>Có thể tự luyện/trao đổi</td></tr>
          <tr><td>⭐⭐⭐⭐</td><td>Tiên khí</td><td>Cần điều kiện đặc biệt</td></tr>
          <tr><td>⭐⭐⭐⭐⭐</td><td><span style="color:var(--gold)">Thần khí</span></td><td>Hiếm nhất, Bản Mệnh Pháp Bảo</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- ARTIFACTS PAGE -->
  <div class="page" id="page-artifacts">
    <div class="page-header">
      <div class="page-title">💎 Linh khí tùy thân</div>
      <div class="divider"></div>
    </div>
    <button class="add-btn hidden" id="addArtifactBtn" onclick="openItemModal('artifact')">＋ Thêm bộ linh khí</button>
    <div class="cards-grid" id="artifactGrid"></div>
    <div id="artifactEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)"><div style="font-size:48px;margin-bottom:12px">💎</div><div>Chưa có bộ linh khí nào.</div></div>
  </div>

  <!-- HERBS PAGE -->
  <div class="page" id="page-herbs">
    <div class="page-header"><div class="page-title">🌿 Thảo dược</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addHerbBtn" onclick="openItemModal('herb')">＋ Thêm thảo dược</button>
    <div class="cards-grid" id="herbGrid"></div>
    <div id="herbEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)"><div style="font-size:48px;margin-bottom:12px">🌿</div><div>Chưa có thảo dược nào.</div></div>
  </div>

  <!-- MINERALS PAGE -->
  <div class="page" id="page-minerals">
    <div class="page-header"><div class="page-title">⛏️ Khoáng vật</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addMineralBtn" onclick="openItemModal('mineral')">＋ Thêm khoáng vật</button>
    <div class="cards-grid" id="mineralGrid"></div>
    <div id="mineralEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)"><div style="font-size:48px;margin-bottom:12px">⛏️</div><div>Chưa có khoáng vật nào.</div></div>
  </div>

  <!-- DROPS PAGE -->
  <div class="page" id="page-drops">
    <div class="page-header"><div class="page-title">👾 Đồ rớt từ quái</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addDropBtn" onclick="openItemModal('drop')">＋ Thêm vật phẩm rớt</button>
    <div class="cards-grid" id="dropGrid"></div>
    <div id="dropEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)"><div style="font-size:48px;margin-bottom:12px">👾</div><div>Chưa có vật phẩm rớt nào.</div></div>
  </div>

  <!-- PILLS PAGE -->
  <div class="page" id="page-pills">
    <div class="page-header"><div class="page-title">⚗️ Đan dược</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addPillBtn" onclick="openItemModal('pill')">＋ Thêm đan dược</button>
    <div class="cards-grid" id="pillGrid"></div>
    <div id="pillEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)"><div style="font-size:48px;margin-bottom:12px">⚗️</div><div>Chưa có đan dược nào.</div></div>
  </div>

  <!-- BREAKTHROUGH PAGE -->
  <div class="page" id="page-breakthrough">
    <div class="page-header"><div class="page-title">🌀 Cơ chế đột phá</div><div class="divider"></div></div>
    <div class="info-section">
      <h3>📊 Cảnh giới & Cấp độ</h3>
      <table class="info-table">
        <thead><tr><th>Cảnh giới</th><th>Cấp (Lv)</th><th>Đột phá</th></tr></thead>
        <tbody>
          <tr><td><span class="realm-luyen-khi">🌱 Luyện Khí</span></td><td>1 → 20</td><td>Lv.20</td></tr>
          <tr><td><span class="realm-truc-co">🔥 Trúc Cơ</span></td><td>21 → 40</td><td>Lv.40</td></tr>
          <tr><td><span class="realm-ket-dan">💎 Kết Đan</span></td><td>41 → 60</td><td>Lv.60</td></tr>
          <tr><td><span class="realm-nguyen-anh">👁️ Nguyên Anh</span></td><td>61 → 80</td><td>Lv.80</td></tr>
          <tr><td><span class="realm-hoa-than">⚡ Hóa Thần</span></td><td>81 → 90</td><td>Lv.90</td></tr>
          <tr><td><span class="realm-luyen-hu">🌀 Luyện Hư</span></td><td>91 → 99</td><td>Lv.99</td></tr>
          <tr><td><span class="realm-dai-thua">☀️ Đại Thừa / Độ Kiếp</span></td><td>100+</td><td>—</td></tr>
        </tbody>
      </table>
    </div>
    <div class="info-section">
      <h3>🔑 Điều kiện đột phá (Lv.1 → 99)</h3>
      <div class="info-text">Muốn đột phá cảnh giới cần 5 loại vật phẩm:</div>
      <div style="display:grid;grid-template-columns:repeat(5,1fr);gap:12px;margin-top:14px;">
        <div style="background:rgba(26,31,58,0.6);border:1px solid var(--border);border-radius:8px;padding:12px;text-align:center;">
          <div style="font-size:24px;margin-bottom:6px">💰</div><div style="font-size:12px;color:var(--gold);font-weight:600">Linh thạch</div><div style="font-size:11px;color:var(--text-muted);margin-top:3px">Tùy cấp độ</div>
        </div>
        <div style="background:rgba(26,31,58,0.6);border:1px solid var(--border);border-radius:8px;padding:12px;text-align:center;">
          <div style="font-size:24px;margin-bottom:6px">👾</div><div style="font-size:12px;color:var(--text-primary);font-weight:600">Đồ quái rơi</div><div style="font-size:11px;color:var(--text-muted);margin-top:3px">Tùy nhân vật</div>
        </div>
        <div style="background:rgba(26,31,58,0.6);border:1px solid var(--border);border-radius:8px;padding:12px;text-align:center;">
          <div style="font-size:24px;margin-bottom:6px">🐉</div><div style="font-size:12px;color:var(--text-primary);font-weight:600">Đồ boss rơi</div><div style="font-size:11px;color:var(--text-muted);margin-top:3px">Tùy nhân vật</div>
        </div>
        <div style="background:rgba(26,31,58,0.6);border:1px solid var(--border);border-radius:8px;padding:12px;text-align:center;">
          <div style="font-size:24px;margin-bottom:6px">✨</div><div style="font-size:12px;color:var(--text-primary);font-weight:600">Kỳ trân dị bảo</div><div style="font-size:11px;color:var(--text-muted);margin-top:3px">Tùy nhân vật</div>
        </div>
        <div style="background:rgba(26,31,58,0.6);border:1px solid var(--border);border-radius:8px;padding:12px;text-align:center;">
          <div style="font-size:24px;margin-bottom:6px">⚗️</div><div style="font-size:12px;color:var(--text-primary);font-weight:600">Đan đột phá</div><div style="font-size:11px;color:var(--text-muted);margin-top:3px">Tỷ lệ 30% mặc định</div>
        </div>
      </div>
      <div class="info-text" style="margin-top:14px;font-size:12px;color:var(--text-muted)">※ Nếu đột phá thất bại, không mất tài nguyên. Nhân vật bị thương do lôi kiếp — phải trị thương mới có thể thử lại.</div>
    </div>
  </div>

  <!-- REACTIONS PAGE -->
  <div class="page" id="page-reactions">
    <div class="page-header"><div class="page-title">⚡ Phản ứng nguyên tố</div><div class="divider"></div></div>
    <div class="info-section">
      <h3>🌊 Tương Sinh (Ngũ hành)</h3>
      <div class="info-text" style="margin-bottom:12px">Mộc sinh Hỏa → Hỏa sinh Thổ → Thổ sinh Kim → Kim sinh Thủy → Thủy sinh Mộc<br><span style="color:var(--text-muted);font-size:12px">Hiệu ứng: Giảm 10% Giáp và Kháng Nguyên Tố của mục tiêu</span></div>
      <h3 style="margin-top:16px">⚔️ Tương Khắc</h3>
      <div class="info-text" style="margin-bottom:12px">Mộc khắc Thổ → Thổ khắc Thủy → Thủy khắc Hỏa → Hỏa khắc Kim → Kim khắc Mộc<br><span style="color:var(--text-muted);font-size:12px">Hiệu ứng: Nhân vật kích hoạt nhận +5% Tăng Sát Nguyên Tố</span></div>
    </div>
    <div class="reaction-grid" id="reactionGrid"></div>
  </div>

  <!-- GEOGRAPHY PAGE -->
  <div class="page" id="page-geography">
    <div class="page-header"><div class="page-title">🗺️ Địa lý thế giới</div><div class="divider"></div></div>
    <button class="add-btn hidden" id="addGeoBtn" onclick="openGeoModal()">＋ Thêm lục địa</button>
    <div id="geoList"></div>
    <div id="geoEmpty" style="display:none;text-align:center;padding:60px;color:var(--text-muted)"><div style="font-size:48px;margin-bottom:12px">🗺️</div><div>Chưa có lục địa nào.</div></div>
  </div>
</div>

<!-- DETAIL OVERLAY -->
<div id="detailOverlay" onclick="closeDetail()"></div>
<div id="detailPanel">
  <div class="detail-close">
    <div id="detailPanelTitle" style="font-family:'Cinzel',serif;font-size:14px;color:var(--gold)"></div>
    <div style="display:flex;gap:8px">
      <button class="btn btn-danger hidden" id="detailDeleteBtn" style="padding:6px 14px;font-size:12px">🗑 Xóa</button>
      <button class="btn btn-primary hidden" id="detailEditBtn" style="padding:6px 14px;font-size:12px">✏️ Chỉnh sửa</button>
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
      <button class="btn btn-primary" id="modalSaveBtn" onclick="saveModal()">💾 Lưu</button>
    </div>
  </div>
</div>

<!-- PASS MODAL -->
<div id="passModal" style="display:none;position:fixed;inset:0;z-index:500;background:rgba(0,0,0,0.85);backdrop-filter:blur(8px);align-items:center;justify-content:center;">
  <div class="pass-box">
    <div class="pass-icon">🔐</div>
    <div class="pass-title">Chế độ chỉnh sửa</div>
    <div class="pass-desc">Nhập mật khẩu để kích hoạt quyền chỉnh sửa nội dung</div>
    <input class="form-input pass-input" type="password" id="passInput" placeholder="••••••" onkeydown="if(event.key==='Enter')checkPass()">
    <div class="pass-error" id="passError"></div>
    <button class="btn btn-primary" style="width:100%" onclick="checkPass()">Xác nhận</button>
    <button class="btn btn-ghost" style="width:100%;margin-top:8px" onclick="closePassModal()">Hủy</button>
    <div style="margin-top:16px;font-size:10px;color:var(--text-muted)">Mật khẩu mặc định: <code style="background:rgba(255,255,255,0.05);padding:2px 6px;border-radius:4px">tiengioi2025</code></div>
  </div>
</div>

<script>
// ===== STATE =====
let DB = JSON.parse(localStorage.getItem('tiengioi_db') || 'null') || {
  characters: [],
  weapons: [],
  artifacts: [],
  herbs: [],
  minerals: [],
  drops: [],
  pills: [],
  geography: [],
  pass: 'tiengioi2025'
};
let editMode = false;
let currentPage = 'home';
let currentModal = null;
let currentDetailItem = null;
let currentDetailType = null;
let charFilter = 'all';
let charView = 'grid';
let itemFilters = {};

function save() {
  localStorage.setItem('tiengioi_db', JSON.stringify(DB));
  updateStats();
}

function updateStats() {
  document.getElementById('stat-chars').textContent = DB.characters.length;
  document.getElementById('stat-weapons').textContent = DB.weapons.length;
  document.getElementById('stat-items').textContent = DB.herbs.length + DB.minerals.length + DB.drops.length + DB.pills.length;
  document.getElementById('stat-places').textContent = DB.geography.length;
}

// ===== NAVIGATION =====
function navigate(page) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
  document.getElementById('page-' + page).classList.add('active');
  document.querySelector(`[data-page="${page}"]`)?.classList.add('active');
  currentPage = page;
  const titles = {
    home: 'Trang chủ', characters: 'Thư viện nhân vật', 'char-info': 'Hệ tu & Chỉ số',
    weapons: 'Pháp bảo trấn vật', artifacts: 'Linh khí tùy thân',
    herbs: 'Thảo dược', minerals: 'Khoáng vật', drops: 'Đồ rớt từ quái',
    pills: 'Đan dược', breakthrough: 'Cơ chế đột phá', reactions: 'Phản ứng nguyên tố',
    geography: 'Địa lý thế giới'
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
  else if (page === 'reactions') renderReactions();
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
    showToast('✓ Chế độ chỉnh sửa đã bật', 'success');
  } else {
    document.getElementById('passError').textContent = 'Mật khẩu không đúng!';
    document.getElementById('passInput').value = '';
  }
}
function closePassModal() {
  document.getElementById('passModal').style.display = 'none';
}
function updateEditUI() {
  const btn = document.getElementById('editModeBtn');
  const txt = document.getElementById('editBtnText');
  btn.classList.toggle('active', editMode);
  txt.textContent = editMode ? 'Đang chỉnh sửa ✓' : 'Chế độ chỉnh sửa';
  document.querySelectorAll('.add-btn').forEach(b => b.classList.toggle('hidden', !editMode));
  if (currentDetailItem) {
    document.getElementById('detailEditBtn').classList.toggle('hidden', !editMode);
    document.getElementById('detailDeleteBtn').classList.toggle('hidden', !editMode);
  }
  renderPage(currentPage);
}

// ===== CHAR RENDER =====
const elementColors = {
  'Kim':'#c0c0c0','Mộc':'#4ade80','Thủy':'#38bdf8','Hỏa':'#f87171',
  'Thổ':'#a16207','Phong':'#86efac','Lôi':'#818cf8','Băng':'#bae6fd',
  'Độc':'#a3e635','Ám':'#6366f1','Quang':'#fbbf24'
};
const elementEmoji = {
  'Kim':'⚙️','Mộc':'🌿','Thủy':'💧','Hỏa':'🔥','Thổ':'⛰️',
  'Phong':'💨','Lôi':'⚡','Băng':'❄️','Độc':'☠️','Ám':'🌑','Quang':'☀️'
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
  grid.innerHTML = '';
  tbody.innerHTML = '';
  if (data.length === 0) { empty.style.display = 'block'; return; }
  empty.style.display = 'none';
  data.forEach(c => {
    const stars = c.stars == 5 ? '★★★★★' : c.stars == 4 ? '★★★★' : '★★★';
    const col = elementColors[c.element] || 'var(--accent)';
    const emoji = elementEmoji[c.element] || '✨';
    // Grid card
    const card = document.createElement('div');
    card.className = 'char-card'; card.onclick = () => openCharDetail(c);
    card.innerHTML = `
      <div class="char-card-img" style="background:linear-gradient(135deg,${col}22,#0f1228)">
        ${c.image ? `<img src="${c.image}" alt="${c.name}">` : `<span style="font-size:42px">${emoji}</span>`}
      </div>
      <div class="rarity-bar ${c.stars==5?'rarity-5':c.stars==4?'rarity-4':'rarity-3'}"></div>
      <div class="char-card-info">
        <div class="char-card-name">${c.name || '???'}</div>
        <div class="char-card-meta">
          <span class="char-element-tag" style="color:${col};border-color:${col}44;background:${col}15">${c.element||'?'}</span>
          <span class="char-stars ${c.stars==4?'s4':''}">${stars}</span>
        </div>
      </div>`;
    grid.appendChild(card);
    // Table row
    const tr = document.createElement('tr');
    tr.onclick = () => openCharDetail(c);
    tr.innerHTML = `<td><b>${c.name||'???'}</b>${c.title?` <span style="color:var(--text-muted);font-size:11px">— ${c.title}</span>`:''}
    </td><td><span class="${c.stars==5?'':'s4'}" style="color:${c.stars==5?'var(--star5)':'var(--star4)'}">${stars}</span>
    </td><td><span style="color:${col}">${emoji} ${c.element||'—'}</span>
    </td><td>${c.cultivation||'—'}</td><td>${c.weaponType||'—'}</td><td>${c.realm||'—'}</td>`;
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
  document.getElementById('charGridView').style.display = v === 'grid' ? 'block' : 'none';
  document.getElementById('charTableView').style.display = v === 'table' ? 'block' : 'none';
}

// ===== ITEMS RENDER =====
const itemIcons = {weapon:'🗡️',artifact:'💎',herb:'🌿',mineral:'⛏️',drop:'👾',pill:'⚗️'};
const itemDB = {weapon:'weapons',artifact:'artifacts',herb:'herbs',mineral:'minerals',drop:'drops',pill:'pills'};
const rarityMap = {'Phàm khí':'hoanh','Linh khí':'huyen','Địa khí':'dia','Tiên khí':'thien','Thần khí':'thien','Hoàng':'hoanh','Huyền':'huyen','Địa':'dia','Thiên':'thien'};

function renderItems(type) {
  const key = itemDB[type];
  const f = itemFilters[type] || 'all';
  const data = DB[key].filter(it => f === 'all' || it.rarity === f);
  const grid = document.getElementById(type + 'Grid');
  const empty = document.getElementById(type + 'Empty');
  if (!grid) return;
  grid.innerHTML = '';
  if (data.length === 0) { empty.style.display = 'block'; return; }
  empty.style.display = 'none';
  data.forEach(it => {
    const card = document.createElement('div');
    card.className = 'item-card'; card.onclick = () => openItemDetail(it, type);
    const rc = rarityMap[it.rarity] || 'huyen';
    card.innerHTML = `
      <div class="item-card-icon">${it.image || itemIcons[type]}</div>
      <div class="item-card-name">${it.name||'???'}</div>
      <div class="item-card-meta">
        ${it.rarity?`<span class="rarity-badge rarity-${rc}">${it.rarity}</span>`:''}
        ${it.subtype?` ${it.subtype}`:''}
      </div>`;
    grid.appendChild(card);
  });
}
function setItemFilter(el, type, f) {
  const page = document.getElementById('page-' + {weapon:'weapons',artifact:'artifacts',herb:'herbs',mineral:'minerals',drop:'drops',pill:'pills'}[type]);
  page?.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  el.classList.add('active'); itemFilters[type] = f; renderItems(type);
}
function filterItems(type) { renderItems(type); }

// ===== GEO RENDER =====
function renderGeo() {
  const list = document.getElementById('geoList');
  const empty = document.getElementById('geoEmpty');
  list.innerHTML = '';
  if (DB.geography.length === 0) { empty.style.display = 'block'; return; }
  empty.style.display = 'none';
  DB.geography.forEach((g, gi) => {
    const div = document.createElement('div');
    div.className = 'geo-continent';
    div.innerHTML = `
      <div class="geo-continent-header" onclick="toggleGeo(${gi})">
        <div class="geo-continent-name">🏔️ ${g.name}</div>
        <div style="display:flex;gap:8px;align-items:center">
          ${editMode ? `<button class="btn btn-primary" style="padding:5px 12px;font-size:11px" onclick="event.stopPropagation();addForce(${gi})">+ Thêm thế lực</button>
          <button class="btn btn-danger" style="padding:5px 12px;font-size:11px" onclick="event.stopPropagation();deleteGeo(${gi})">🗑</button>` : ''}
          <span id="geo-arrow-${gi}">▼</span>
        </div>
      </div>
      <div class="geo-forces" id="geo-forces-${gi}">
        ${g.desc ? `<div class="info-text" style="margin-bottom:12px">${g.desc}</div>` : ''}
        ${(g.forces||[]).map((f,fi) => `
          <div class="force-item">
            <div style="display:flex;justify-content:space-between;align-items:start">
              <div>
                <div class="force-name">${f.name}</div>
                <div class="force-desc">${f.desc||''}</div>
              </div>
              ${editMode ? `<button class="btn btn-danger" style="padding:3px 8px;font-size:11px" onclick="deleteForce(${gi},${fi})">✕</button>` : ''}
            </div>
          </div>`).join('')}
        ${(g.forces||[]).length === 0 ? '<div style="color:var(--text-muted);font-size:13px;font-style:italic">Chưa có thế lực nào.</div>' : ''}
      </div>`;
    list.appendChild(div);
  });
}
function toggleGeo(i) {
  const el = document.getElementById(`geo-forces-${i}`);
  const ar = document.getElementById(`geo-arrow-${i}`);
  const vis = el.style.display !== 'none';
  el.style.display = vis ? 'none' : 'block';
  ar.textContent = vis ? '▶' : '▼';
}
function deleteGeo(i) {
  if (confirm('Xóa lục địa này?')) { DB.geography.splice(i, 1); save(); renderGeo(); }
}
function addForce(gi) {
  const name = prompt('Tên thế lực:'); if (!name) return;
  const desc = prompt('Mô tả:') || '';
  DB.geography[gi].forces = DB.geography[gi].forces || [];
  DB.geography[gi].forces.push({name, desc});
  save(); renderGeo();
}
function deleteForce(gi, fi) {
  DB.geography[gi].forces.splice(fi, 1); save(); renderGeo();
}

// ===== REACTIONS RENDER =====
const reactions = [
  {name:'Thiêu đốt',trigger:'🔥 Hỏa + 🌿 Mộc',effect:'DOT — thiêu đốt sinh mệnh linh đài theo thời gian'},
  {name:'Sinh trưởng',trigger:'🌿 Mộc + 💧 Thủy',effect:'Hồi phục sinh mệnh linh đài theo thời gian'},
  {name:'Bốc hơi',trigger:'💧 Thủy + 🔥 Hỏa',effect:'Gây sát thương chuẩn theo % sinh mệnh linh đài của mục tiêu'},
  {name:'Nóng chảy',trigger:'🔥 Hỏa + ⚙️ Kim',effect:'Giảm Phòng Ngự và Kháng Nguyên Tố mạnh trong thời gian ngắn'},
  {name:'Xói mòn',trigger:'⛰️ Thổ + 💧 Thủy',effect:'Ăn mòn — mỗi giây trừ HP và giảm dần Linh lực cơ bản của mục tiêu'},
  {name:'Băng phong',trigger:'💧 Thủy + ❄️ Băng',effect:'Đóng băng cứng, bất động hoàn toàn'},
  {name:'Phá băng',trigger:'❄️ Băng + ⚙️ Kim',effect:'Phá băng, gây thêm sát thương vật lý xuyên thấu và tổn thương nội tạng'},
  {name:'Tan chảy',trigger:'❄️ Băng + 🔥 Hỏa',effect:'Gây sát thương chuẩn, xóa trạng thái Băng. Nếu đang đóng băng nhận thêm ×1.5 sát thương'},
  {name:'Điện giải',trigger:'⚡ Lôi + 💧 Thủy',effect:'Chuỗi sét, giảm phòng thủ địch'},
  {name:'Khuếch tán',trigger:'💨 Phong + bất kỳ (trừ Ám/Quang)',effect:'Lan rộng nguyên tố ra diện rộng'},
  {name:'Kết tinh',trigger:'⛰️ Thổ + bất kỳ (trừ Ám/Quang)',effect:'Tạo khiên nguyên tố bảo hộ theo hệ'},
  {name:'Hư vô',trigger:'🌑 Ám/☀️ Quang + bất kỳ',effect:'Vô hiệu phản ứng, xóa trạng thái địch (buff/debuff tương ứng). KHÔNG thể kích ngược lại'},
];
function renderReactions() {
  const grid = document.getElementById('reactionGrid');
  grid.innerHTML = reactions.map(r => `
    <div class="reaction-card">
      <div class="reaction-name">${r.name}</div>
      <div class="reaction-trigger">${r.trigger}</div>
      <div class="reaction-effect">${r.effect}</div>
    </div>`).join('');
}

// ===== DETAIL PANEL =====
function openCharDetail(c) {
  currentDetailItem = c; currentDetailType = 'character';
  document.getElementById('detailOverlay').style.display = 'block';
  document.getElementById('detailPanel').style.display = 'block';
  document.getElementById('detailPanelTitle').textContent = c.name || 'Nhân vật';
  document.getElementById('detailEditBtn').classList.toggle('hidden', !editMode);
  document.getElementById('detailDeleteBtn').classList.toggle('hidden', !editMode);
  document.getElementById('detailEditBtn').onclick = () => { closeDetail(); openCharModal(c); };
  document.getElementById('detailDeleteBtn').onclick = () => deleteChar(c);
  const stars = c.stars==5?'★★★★★':c.stars==4?'★★★★':'★★★';
  const col = elementColors[c.element] || 'var(--accent)';
  const emoji = elementEmoji[c.element] || '✨';
  let html = `
    <div style="display:flex;gap:20px;margin-bottom:20px;align-items:flex-start">
      <div style="width:100px;height:100px;border-radius:12px;background:linear-gradient(135deg,${col}33,#0f1228);display:flex;align-items:center;justify-content:center;font-size:48px;flex-shrink:0;border:1px solid ${col}44">
        ${c.image?`<img src="${c.image}" style="width:100%;height:100%;object-fit:cover;border-radius:12px">`:`${emoji}`}
      </div>
      <div>
        <div style="font-family:'Cinzel',serif;font-size:22px;color:var(--text-primary)">${c.name||'???'}</div>
        ${c.title?`<div style="color:var(--text-muted);font-size:13px;margin-top:2px">${c.title}</div>`:''}
        ${c.realName?`<div style="color:var(--text-secondary);font-size:12px;margin-top:2px">Tên thật: ${c.realName}</div>`:''}
        <div style="display:flex;gap:8px;margin-top:8px;flex-wrap:wrap">
          <span style="color:${col};font-size:13px">${emoji} ${c.element||'?'}</span>
          <span style="color:${c.stars==5?'var(--star5)':'var(--star4)'}">${stars}</span>
          ${c.cultivation?`<span style="color:var(--accent2);font-size:12px">${c.cultivation}</span>`:''}
          ${c.weaponType?`<span style="color:var(--text-muted);font-size:12px">🗡️ ${c.weaponType}</span>`:''}
        </div>
      </div>
    </div>`;
  // Basic info
  if (c.gender||c.race||c.faction||c.realm||c.age) {
    html += `<div class="section-card"><div class="section-title">Thông tin cơ bản</div>
    <div class="field-grid">
      ${c.gender?`<div class="field-item"><div class="field-label">Giới tính</div><div class="field-value">${c.gender}</div></div>`:''}
      ${c.race?`<div class="field-item"><div class="field-label">Chủng tộc</div><div class="field-value">${c.race}</div></div>`:''}
      ${c.faction?`<div class="field-item"><div class="field-label">Môn phái</div><div class="field-value">${c.faction}</div></div>`:''}
      ${c.realm?`<div class="field-item"><div class="field-label">Cảnh giới</div><div class="field-value">${c.realm}</div></div>`:''}
      ${c.age?`<div class="field-item"><div class="field-label">Tuổi (thực)</div><div class="field-value">${c.age}</div></div>`:''}
      ${c.ageAppear?`<div class="field-item"><div class="field-label">Trông như</div><div class="field-value">${c.ageAppear} tuổi</div></div>`:''}
    </div></div>`;
  }
  // Stats
  if (c.hp||c.atk||c.def) {
    html += `<div class="section-card"><div class="section-title">Chỉ số thuộc tính</div>
    ${c.hp?`<div class="stat-row"><span class="stat-name">❤️ Sinh mệnh linh đài (HP)</span><span class="stat-val">${c.hp}</span></div>`:''}
    ${c.atk?`<div class="stat-row"><span class="stat-name">⚔️ Linh lực cơ bản (ATK)</span><span class="stat-val">${c.atk}</span></div>`:''}
    ${c.def?`<div class="stat-row"><span class="stat-name">🛡️ Thể phách trấn áp (DEF)</span><span class="stat-val">${c.def}</span></div>`:''}
    ${c.em?`<div class="stat-row"><span class="stat-name">🌀 Nguyên tinh thông (EM)</span><span class="stat-val">${c.em}</span></div>`:''}
    ${c.crit?`<div class="stat-row"><span class="stat-name">🎯 Tỷ lệ bạo kích</span><span class="stat-val">${c.crit}</span></div>`:''}
    ${c.cdmg?`<div class="stat-row"><span class="stat-name">💥 Sát thương bạo kích</span><span class="stat-val">${c.cdmg}</span></div>`:''}
    ${c.special?`<div class="stat-row"><span class="stat-name">⭐ Chỉ số đặc biệt</span><span class="stat-val">${c.special}</span></div>`:''}
    </div>`;
  }
  // Skills
  if (c.skillE||c.skillQ||c.normalAtk) {
    html += `<div class="section-card"><div class="section-title">Kỹ năng chiến đấu</div>`;
    if (c.normalAtk) html += `<div class="skill-card"><div class="skill-type">Tấn công thường</div><div class="skill-name">${c.normalAtk}</div>${c.normalDesc?`<div class="skill-desc">${c.normalDesc}</div>`:''}</div>`;
    if (c.skillE) html += `<div class="skill-card"><div class="skill-type">Kỹ năng chiến thuật (E)</div><div class="skill-name">${c.skillE}</div>${c.skillEDesc?`<div class="skill-desc">${c.skillEDesc}</div>`:''}</div>`;
    if (c.skillQ) html += `<div class="skill-card"><div class="skill-type">Đại thần thông (Q)</div><div class="skill-name">${c.skillQ}</div>${c.skillQDesc?`<div class="skill-desc">${c.skillQDesc}</div>`:''}</div>`;
    if (c.passive1||c.passive2) html += `<div class="skill-card"><div class="skill-type">Bị động</div>${c.passive1?`<div class="skill-desc" style="margin-bottom:4px"><b>Lv.20:</b> ${c.passive1}</div>`:''}${c.passive2?`<div class="skill-desc"><b>Lv.60:</b> ${c.passive2}</div>`:''}</div>`;
    html += `</div>`;
  }
  // Constellations
  const consts = [c.c1,c.c2,c.c3,c.c4,c.c5,c.c6].filter(Boolean);
  if (consts.length) {
    html += `<div class="section-card"><div class="section-title">Tinh tú đạo mạch</div><div class="constellation-grid">`;
    [c.c1,c.c2,c.c3,c.c4,c.c5,c.c6].forEach((ct,i) => {
      html += `<div class="const-item"><div class="const-level">C${i+1}</div><div class="const-desc">${ct||'—'}</div></div>`;
    });
    html += `</div></div>`;
  }
  // Story
  if (c.background||c.personality||c.goal) {
    html += `<div class="section-card"><div class="section-title">Lý lịch & Cá tính</div>`;
    if (c.background) html += `<div class="field-full"><div class="field-label">Xuất thân / Lý lịch</div><div class="field-value" style="margin-top:4px;line-height:1.7">${c.background}</div></div>`;
    if (c.personality) html += `<div class="field-full"><div class="field-label">Tính cách</div><div class="field-value" style="margin-top:4px;line-height:1.7">${c.personality}</div></div>`;
    if (c.goal) html += `<div class="field-full"><div class="field-label">Mục tiêu cốt lõi</div><div class="field-value" style="margin-top:4px">${c.goal}</div></div>`;
    if (c.secret) html += `<div class="field-full"><div class="field-label">Bí mật</div><div class="field-value" style="margin-top:4px">${c.secret}</div></div>`;
    html += `</div>`;
  }
  // Voice lines
  if (c.voiceGreet||c.voiceSkillE||c.voiceSkillQ) {
    html += `<div class="section-card"><div class="section-title">Thoại đặc trưng</div>`;
    if (c.voiceGreet) html += `<div class="field-full" style="margin-bottom:8px"><div class="field-label">Chào hỏi lần đầu</div><div class="field-value" style="margin-top:4px;font-style:italic;color:var(--accent3)">"${c.voiceGreet}"</div></div>`;
    if (c.voiceSkillE) html += `<div class="field-full" style="margin-bottom:8px"><div class="field-label">Khi dùng kỹ năng E</div><div class="field-value" style="margin-top:4px;font-style:italic;color:var(--accent3)">"${c.voiceSkillE}"</div></div>`;
    if (c.voiceSkillQ) html += `<div class="field-full" style="margin-bottom:8px"><div class="field-label">Khi dùng tuyệt kỹ Q</div><div class="field-value" style="margin-top:4px;font-style:italic;color:var(--accent3)">"${c.voiceSkillQ}"</div></div>`;
    html += `</div>`;
  }
  // Notes
  if (c.notes) html += `<div class="section-card"><div class="section-title">Ghi chú thiết kế</div><div class="field-value" style="line-height:1.8">${c.notes}</div></div>`;
  document.getElementById('detailContent').innerHTML = html;
}

function openItemDetail(it, type) {
  currentDetailItem = it; currentDetailType = type;
  document.getElementById('detailOverlay').style.display = 'block';
  document.getElementById('detailPanel').style.display = 'block';
  document.getElementById('detailPanelTitle').textContent = it.name || '???';
  document.getElementById('detailEditBtn').classList.toggle('hidden', !editMode);
  document.getElementById('detailDeleteBtn').classList.toggle('hidden', !editMode);
  document.getElementById('detailEditBtn').onclick = () => { closeDetail(); openItemModal(type, it); };
  document.getElementById('detailDeleteBtn').onclick = () => { deleteItem(type, it); closeDetail(); };
  const icon = it.image || itemIcons[type];
  const rc = rarityMap[it.rarity] || 'huyen';
  let html = `
    <div style="display:flex;gap:16px;align-items:center;margin-bottom:20px">
      <div style="font-size:48px">${icon}</div>
      <div>
        <div style="font-family:'Cinzel',serif;font-size:20px">${it.name||'???'}</div>
        ${it.rarity?`<span class="rarity-badge rarity-${rc}" style="margin-top:6px;display:inline-block">${it.rarity}</span>`:''}
        ${it.subtype?`<span style="color:var(--text-muted);font-size:12px;margin-left:8px">${it.subtype}</span>`:''}
      </div>
    </div>`;
  const fields = [
    ['Phân cấp',it.rarity],['Loại',it.subtype],['Tính chất',it.property],
    ['Nguồn gốc',it.origin],['Công dụng (Y học)',it.medUse],
    ['Công dụng (Luyện đan)',it.alchemyUse],['Công dụng',it.use],
    ['Đặc điểm hình thái',it.appearance],['Có thể tìm ở',it.location],
    ['Chỉ số chính',it.mainStat],['Chỉ số phụ',it.subStat],
    ['Kỹ năng',it.skill],['Rớt từ',it.dropFrom],
    ['Mô tả',it.desc],['Ghi chú',it.notes]
  ].filter(([,v])=>v);
  if (fields.length) {
    html += `<div class="section-card">`;
    fields.forEach(([k,v]) => { html += `<div class="field-full" style="margin-bottom:10px"><div class="field-label">${k}</div><div class="field-value" style="margin-top:3px;line-height:1.7">${v}</div></div>`; });
    html += `</div>`;
  }
  document.getElementById('detailContent').innerHTML = html;
}

function closeDetail() {
  document.getElementById('detailOverlay').style.display = 'none';
  document.getElementById('detailPanel').style.display = 'none';
  currentDetailItem = null; currentDetailType = null;
}
function deleteChar(c) {
  if (!confirm(`Xóa nhân vật "${c.name}"?`)) return;
  DB.characters = DB.characters.filter(x => x !== c);
  save(); closeDetail(); renderChars();
}
function deleteItem(type, it) {
  const key = itemDB[type];
  DB[key] = DB[key].filter(x => x !== it);
  save(); renderItems(type);
}

// ===== MODALS =====
let modalType = null;
let modalEditItem = null;
function openCharModal(edit) {
  if (!editMode) return;
  modalType = 'character'; modalEditItem = edit || null;
  document.getElementById('modal').style.display = 'block';
  document.getElementById('modalTitle').textContent = edit ? '✏️ Chỉnh sửa nhân vật' : '＋ Thêm nhân vật mới';
  const c = edit || {};
  document.getElementById('modalBody').innerHTML = `
    <div class="form-section">
      <div class="form-section-title">01 — Nhận dạng & Danh hiệu</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Tên nhân vật *</label><input class="form-input" id="f_name" value="${c.name||''}"></div>
        <div class="form-group"><label class="form-label">Đạo hiệu / Danh hiệu</label><input class="form-input" id="f_title" value="${c.title||''}"></div>
        <div class="form-group"><label class="form-label">Tên thật</label><input class="form-input" id="f_realName" value="${c.realName||''}"></div>
        <div class="form-group"><label class="form-label">Số sao</label>
          <select class="form-select" id="f_stars">
            <option value="5" ${c.stars==5?'selected':''}>★★★★★ (5 sao)</option>
            <option value="4" ${c.stars==4?'selected':''}>★★★★ (4 sao)</option>
            <option value="3" ${c.stars==3?'selected':''}>★★★ (3 sao)</option>
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
            ${['Nhân tộc','Yêu tộc','Tiên tộc','Ma tộc','Thần minh','Lai huyết'].map(r=>`<option ${c.race===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">02 — Linh căn & Hệ tu</div>
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
            ${['Kiếm','Trọng kiếm','Song kiếm','Cung','Nỏ','Pháp khí','Thương','Đại Đao','Quyền giáp','Linh bảo'].map(w=>`<option ${c.weaponType===w?'selected':''}>${w}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Môn phái</label><input class="form-input" id="f_faction" value="${c.faction||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">03 — Cảnh giới & Chỉ số</div>
      <div class="form-grid cols3">
        <div class="form-group"><label class="form-label">Cảnh giới hiện tại</label>
          <select class="form-select" id="f_realm">
            <option value="">—</option>
            ${['🌱 Luyện Khí','🔥 Trúc Cơ','💎 Kết Đan','👁️ Nguyên Anh','⚡ Hóa Thần','🌀 Luyện Hư','☀️ Đại Thừa'].map(r=>`<option ${c.realm===r?'selected':''}>${r}</option>`).join('')}
          </select></div>
        <div class="form-group"><label class="form-label">Tuổi thực</label><input class="form-input" id="f_age" value="${c.age||''}"></div>
        <div class="form-group"><label class="form-label">Ngoại hình tuổi</label><input class="form-input" id="f_ageAppear" placeholder="Trông như X tuổi" value="${c.ageAppear||''}"></div>
        <div class="form-group"><label class="form-label">HP</label><input class="form-input" id="f_hp" value="${c.hp||''}"></div>
        <div class="form-group"><label class="form-label">ATK</label><input class="form-input" id="f_atk" value="${c.atk||''}"></div>
        <div class="form-group"><label class="form-label">DEF</label><input class="form-input" id="f_def" value="${c.def||''}"></div>
        <div class="form-group"><label class="form-label">CRIT%</label><input class="form-input" id="f_crit" value="${c.crit||''}"></div>
        <div class="form-group"><label class="form-label">CDMG%</label><input class="form-input" id="f_cdmg" value="${c.cdmg||''}"></div>
        <div class="form-group"><label class="form-label">Chỉ số đặc biệt</label><input class="form-input" id="f_special" value="${c.special||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">04 — Kỹ năng chiến đấu</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Tên chuỗi đánh thường</label><input class="form-input" id="f_normalAtk" value="${c.normalAtk||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả tấn công thường</label><textarea class="form-textarea" id="f_normalDesc">${c.normalDesc||''}</textarea></div>
        <div class="form-group"><label class="form-label">Tên kỹ năng E</label><input class="form-input" id="f_skillE" value="${c.skillE||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả kỹ năng E</label><textarea class="form-textarea" id="f_skillEDesc">${c.skillEDesc||''}</textarea></div>
        <div class="form-group"><label class="form-label">Tên tuyệt kỹ Q</label><input class="form-input" id="f_skillQ" value="${c.skillQ||''}"></div>
        <div class="form-group full"><label class="form-label">Mô tả tuyệt kỹ Q</label><textarea class="form-textarea" id="f_skillQDesc">${c.skillQDesc||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Bị động 1 (Lv.20)</label><textarea class="form-textarea" style="min-height:60px" id="f_passive1">${c.passive1||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Bị động 2 (Lv.60)</label><textarea class="form-textarea" style="min-height:60px" id="f_passive2">${c.passive2||''}</textarea></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">05 — Tinh tú đạo mạch (C1–C6)</div>
      <div class="form-grid">
        ${[1,2,3,4,5,6].map(i=>`<div class="form-group"><label class="form-label">C${i}</label><textarea class="form-textarea" style="min-height:60px" id="f_c${i}">${c['c'+i]||''}</textarea></div>`).join('')}
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">06 — Lý lịch & Cá tính</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Lý lịch / Xuất thân</label><textarea class="form-textarea" id="f_background">${c.background||''}</textarea></div>
        <div class="form-group full"><label class="form-label">Tính cách</label><textarea class="form-textarea" id="f_personality">${c.personality||''}</textarea></div>
        <div class="form-group"><label class="form-label">Mục tiêu cốt lõi</label><input class="form-input" id="f_goal" value="${c.goal||''}"></div>
        <div class="form-group"><label class="form-label">Bí mật</label><input class="form-input" id="f_secret" value="${c.secret||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">07 — Thoại đặc trưng</div>
      <div class="form-grid">
        <div class="form-group full"><label class="form-label">Chào hỏi lần đầu</label><input class="form-input" id="f_voiceGreet" value="${c.voiceGreet||''}"></div>
        <div class="form-group full"><label class="form-label">Khi dùng kỹ năng E</label><input class="form-input" id="f_voiceSkillE" value="${c.voiceSkillE||''}"></div>
        <div class="form-group full"><label class="form-label">Khi dùng tuyệt kỹ Q</label><input class="form-input" id="f_voiceSkillQ" value="${c.voiceSkillQ||''}"></div>
      </div>
    </div>
    <div class="form-section">
      <div class="form-section-title">08 — Nguyên liệu & Ghi chú</div>
      <div class="form-grid">
        <div class="form-group"><label class="form-label">Nguyên liệu quái rơi</label><input class="form-input" id="f_mat1" value="${c.mat1||''}"></div>
        <div class="form-group"><label class="form-label">Nguyên liệu boss rơi</label><input class="form-input" id="f_mat2" value="${c.mat2||''}"></div>
        <div class="form-group"><label class="form-label">Kỳ trân dị bảo</label><input class="form-input" id="f_mat3" value="${c.mat3||''}"></div>
        <div class="form-group"><label class="form-label">Sách kỹ năng</label><input class="form-input" id="f_mat4" value="${c.mat4||''}"></div>
        <div class="form-group full"><label class="form-label">Ghi chú thiết kế tự do</label><textarea class="form-textarea" id="f_notes">${c.notes||''}</textarea></div>
        <div class="form-group full"><label class="form-label">URL hình ảnh (tùy chọn)</label><input class="form-input" id="f_image" placeholder="https://..." value="${c.image||''}"></div>
      </div>
    </div>`;
}

function openItemModal(type, edit) {
  if (!editMode) return;
  modalType = type; modalEditItem = edit || null;
  const typeNames = {weapon:'Vũ khí',artifact:'Bộ linh khí',herb:'Thảo dược',mineral:'Khoáng vật',drop:'Vật phẩm rớt',pill:'Đan dược'};
  document.getElementById('modal').style.display = 'block';
  document.getElementById('modalTitle').textContent = (edit?'✏️ Chỉnh sửa':'＋ Thêm') + ' ' + typeNames[type];
  const it = edit || {};
  let body = `<div class="form-section"><div class="form-section-title">Thông tin cơ bản</div><div class="form-grid">
    <div class="form-group"><label class="form-label">Tên *</label><input class="form-input" id="f_name" value="${it.name||''}"></div>
    <div class="form-group"><label class="form-label">Emoji / Icon</label><input class="form-input" id="f_image" value="${it.image||''}" placeholder="Ví dụ: 🗡️"></div>
    <div class="form-group"><label class="form-label">Phân cấp / Phẩm</label>
      <select class="form-select" id="f_rarity">
        <option value="">—</option>`;
  if (type === 'weapon') {
    ['Phàm khí','Linh khí','Địa khí','Tiên khí','Thần khí'].forEach(r=>{ body+=`<option ${it.rarity===r?'selected':''}>${r}</option>`; });
  } else {
    ['Hoàng','Huyền','Địa','Thiên'].forEach(r=>{ body+=`<option ${it.rarity===r?'selected':''}>${r}</option>`; });
  }
  body += `</select></div>`;
  if (type === 'weapon') {
    const wTypes = ['Kiếm đơn','Trọng kiếm','Song kiếm','Trường cung','Nỏ','Hồ lô','Phất trần','Bút lông','Đạo ấn','Chuông linh','Cổ Thư','Thương','Đại Đao','Thiền trượng','Quyền giáp','Gương linh'];
    body += `<div class="form-group"><label class="form-label">Loại vũ khí</label><select class="form-select" id="f_subtype"><option value="">—</option>${wTypes.map(w=>`<option ${it.subtype===w?'selected':''}>${w}</option>`).join('')}</select></div>`;
    body += `<div class="form-group"><label class="form-label">Chỉ số chính</label><input class="form-input" id="f_mainStat" value="${it.mainStat||'ATK'}"></div>`;
    body += `<div class="form-group"><label class="form-label">Chỉ số phụ</label><input class="form-input" id="f_subStat" value="${it.subStat||''}"></div>`;
    body += `<div class="form-group full"><label class="form-label">Kỹ năng vũ khí</label><textarea class="form-textarea" id="f_skill">${it.skill||''}</textarea></div>`;
  }
  body += `<div class="form-group full"><label class="form-label">Mô tả</label><textarea class="form-textarea" id="f_desc">${it.desc||''}</textarea></div>`;
  if (['herb','mineral','drop'].includes(type)) {
    body += `<div class="form-group full"><label class="form-label">Nguồn gốc / Rớt từ</label><input class="form-input" id="f_origin" value="${it.origin||it.dropFrom||''}"></div>`;
    body += `<div class="form-group full"><label class="form-label">Công dụng</label><textarea class="form-textarea" id="f_use">${it.use||''}</textarea></div>`;
    if (type === 'herb') {
      body += `<div class="form-group full"><label class="form-label">Công dụng luyện đan</label><textarea class="form-textarea" id="f_alchemyUse">${it.alchemyUse||''}</textarea></div>`;
    }
    body += `<div class="form-group full"><label class="form-label">Có thể tìm ở</label><input class="form-input" id="f_location" value="${it.location||''}"></div>`;
  }
  if (type === 'pill') {
    body += `<div class="form-group full"><label class="form-label">Công thức / Nguyên liệu</label><textarea class="form-textarea" id="f_use">${it.use||''}</textarea></div>`;
  }
  if (type === 'artifact') {
    body += `<div class="form-group full"><label class="form-label">Hiệu ứng bộ 2 món</label><textarea class="form-textarea" id="f_set2">${it.set2||''}</textarea></div>`;
    body += `<div class="form-group full"><label class="form-label">Hiệu ứng bộ 4 món</label><textarea class="form-textarea" id="f_set4">${it.set4||''}</textarea></div>`;
  }
  body += `<div class="form-group full"><label class="form-label">Ghi chú</label><textarea class="form-textarea" id="f_notes">${it.notes||''}</textarea></div>`;
  body += `</div></div>`;
  document.getElementById('modalBody').innerHTML = body;
}

function openGeoModal() {
  if (!editMode) return;
  modalType = 'geo'; modalEditItem = null;
  document.getElementById('modal').style.display = 'block';
  document.getElementById('modalTitle').textContent = '＋ Thêm lục địa mới';
  document.getElementById('modalBody').innerHTML = `
    <div class="form-section"><div class="form-section-title">Thông tin lục địa</div>
    <div class="form-grid">
      <div class="form-group full"><label class="form-label">Tên lục địa *</label><input class="form-input" id="f_name" placeholder="Ví dụ: Lục địa Tiên Nguyên"></div>
      <div class="form-group full"><label class="form-label">Mô tả</label><textarea class="form-textarea" id="f_desc" placeholder="Mô tả về lục địa này..."></textarea></div>
    </div></div>`;
}

function saveModal() {
  const name = document.getElementById('f_name')?.value?.trim();
  if (!name) { showToast('Vui lòng nhập tên!', 'error'); return; }
  if (modalType === 'character') {
    const c = modalEditItem || {};
    const fields = ['name','title','realName','gender','race','element','cultivation','weaponType','faction','realm','age','ageAppear','hp','atk','def','em','crit','cdmg','special','normalAtk','normalDesc','skillE','skillEDesc','skillQ','skillQDesc','passive1','passive2','c1','c2','c3','c4','c5','c6','background','personality','goal','secret','voiceGreet','voiceSkillE','voiceSkillQ','mat1','mat2','mat3','mat4','notes','image'];
    fields.forEach(f => { const el=document.getElementById('f_'+f); if(el) c[f]=el.value; });
    c.stars = parseInt(document.getElementById('f_stars')?.value || '5');
    if (!modalEditItem) DB.characters.push(c);
    save(); closeModal(); renderChars();
  } else if (modalType === 'geo') {
    DB.geography.push({name,desc:document.getElementById('f_desc')?.value||'',forces:[]});
    save(); closeModal(); renderGeo();
  } else {
    const key = itemDB[modalType];
    const it = modalEditItem || {};
    ['name','image','rarity','subtype','mainStat','subStat','skill','desc','origin','use','alchemyUse','location','dropFrom','set2','set4','notes'].forEach(f=>{
      const el=document.getElementById('f_'+f); if(el) it[f]=el.value;
    });
    if (!modalEditItem) DB[key].push(it);
    save(); closeModal(); renderItems(modalType);
  }
  showToast('✓ Đã lưu thành công!', 'success');
}

function closeModal() {
  document.getElementById('modal').style.display = 'none';
  modalType = null; modalEditItem = null;
}
document.getElementById('modal').addEventListener('click', function(e){ if(e.target===this) closeModal(); });

// ===== EXPORT =====
function exportHTML() {
  const data = JSON.stringify(DB);
  const blob = document.documentElement.outerHTML.replace(
    /localStorage\.getItem\('tiengioi_db'\) \|\| 'null'\) \|\| \{/,
    `null) || `+data+`; // EXPORTED DATA\nif(false && {`
  );
  // Simple export with embedded data
  const exportContent = document.documentElement.outerHTML;
  const script = `<script>window.__EXPORT_DB__=${data};<\/script>`;
  const final = exportContent.replace('<head>', '<head>' + script);
  const a = document.createElement('a');
  a.href = URL.createObjectURL(new Blob([final], {type:'text/html'}));
  a.download = 'tiengioi-wiki.html';
  a.click();
  // Also inject the loading of export data
  showToast('✓ Đã xuất file HTML!', 'success');
}

// ===== TOAST =====
function showToast(msg, type='info') {
  const t = document.createElement('div');
  t.className = `toast ${type}`;
  t.innerHTML = `<span>${type==='success'?'✓':type==='error'?'✗':'ℹ'}</span> ${msg}`;
  document.body.appendChild(t);
  setTimeout(() => t.remove(), 3000);
}

// ===== INIT =====
// Load export data if available
if (window.__EXPORT_DB__) { DB = window.__EXPORT_DB__; save(); }
updateStats();
renderReactions();
</script>
</body>
</html>
