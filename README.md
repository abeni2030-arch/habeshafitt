[habesha-fit-complete.html](https://github.com/user-attachments/files/27492623/habesha-fit-complete.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Habesha Fit">
<meta name="theme-color" content="#2D6A4F">
<meta name="description" content="Ethiopian fitness app — meal plans, workouts & progress tracking">
<link rel="manifest" href="manifest.json">
<title>Habesha Fit 🇪🇹</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --green:#2D6A4F;--green-light:#40916C;--green-pale:#D8F3DC;
  --gold:#E9C46A;--gold-dark:#C9973A;--red:#E76F51;
  --cream:#FEFAE0;--dark:#1B1B1B;--mid:#4A4A4A;--light:#F5F5F0;
  --radius:16px;--shadow:0 4px 24px rgba(0,0,0,.10);
  --safe-top:env(safe-area-inset-top);--safe-bottom:env(safe-area-inset-bottom);
}
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{font-family:'DM Sans',sans-serif;background:var(--light);color:var(--dark);min-height:100vh;display:flex;flex-direction:column;align-items:center;overscroll-behavior:none}
.screen{display:none;width:100%;max-width:430px;min-height:100vh;flex-direction:column;animation:fadeUp .35s ease}
.screen.active{display:flex}
@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}

/* ════ SPLASH ════ */
#screen-splash{background:linear-gradient(160deg,var(--green) 0%,#1B4332 100%);justify-content:center;align-items:center;padding:calc(40px + var(--safe-top)) 28px 40px;text-align:center}
.flag{font-size:52px;margin-bottom:12px}
.brand{font-family:'Playfair Display',serif;font-size:44px;color:var(--gold);line-height:1}
.brand-sub{font-size:13px;color:rgba(255,255,255,.65);letter-spacing:3px;text-transform:uppercase;margin-top:6px;margin-bottom:32px}
.tagline{color:rgba(255,255,255,.85);font-size:16px;line-height:1.7;margin-bottom:28px}
.feature-pills{display:flex;flex-wrap:wrap;justify-content:center;gap:8px;margin-bottom:36px}
.pill{background:rgba(255,255,255,.12);color:rgba(255,255,255,.85);padding:7px 14px;border-radius:50px;font-size:12px;font-weight:500}
.btn-gold{background:var(--gold);color:var(--dark);font-family:'DM Sans',sans-serif;font-weight:700;font-size:16px;border:none;border-radius:50px;padding:16px 40px;cursor:pointer;width:100%;transition:all .2s}
.btn-gold:active{transform:scale(.97)}
.splash-login{margin-top:16px;font-size:13px;color:rgba(255,255,255,.55);cursor:pointer}
.splash-login span{color:var(--gold);text-decoration:underline}

/* ════ PRICING ════ */
#screen-pricing{background:var(--light);overflow-y:auto;padding-bottom:40px}
.pricing-hero{background:linear-gradient(160deg,var(--green) 0%,#1B4332 100%);padding:calc(48px + var(--safe-top)) 24px 28px;text-align:center;color:white;position:relative;overflow:hidden}
.pricing-hero::before{content:'';position:absolute;top:-60px;right:-60px;width:200px;height:200px;border-radius:50%;background:rgba(233,196,106,.10);pointer-events:none}
.hero-title{font-family:'Playfair Display',serif;font-size:26px;color:var(--gold);line-height:1.2;margin-bottom:8px}
.hero-sub{font-size:13px;color:rgba(255,255,255,.7);line-height:1.6;margin-bottom:18px}
.hero-trust{display:flex;justify-content:center;gap:16px;flex-wrap:wrap}
.trust-item{font-size:12px;color:rgba(255,255,255,.75);font-weight:600}
.billing-toggle{display:flex;background:white;border-radius:50px;padding:4px;margin:20px auto 0;width:fit-content;box-shadow:0 2px 12px rgba(0,0,0,.10)}
.toggle-btn{padding:9px 20px;border-radius:50px;font-size:13px;font-weight:700;cursor:pointer;border:none;background:transparent;font-family:'DM Sans',sans-serif;color:#888;transition:all .25s}
.toggle-btn.active{background:var(--green);color:white}
.save-badge{background:var(--gold);color:var(--dark);font-size:10px;font-weight:800;padding:2px 7px;border-radius:50px;margin-left:4px}
.plans-wrap{padding:20px 16px 0}
.plan-card{background:white;border-radius:20px;padding:20px;margin-bottom:14px;box-shadow:var(--shadow);border:2px solid transparent;position:relative;transition:all .2s;cursor:pointer}
.plan-card.popular{border-color:var(--green)}
.plan-card:active{transform:scale(.99)}
.popular-badge{position:absolute;top:-12px;left:50%;transform:translateX(-50%);background:var(--green);color:white;font-size:11px;font-weight:800;padding:4px 16px;border-radius:50px;white-space:nowrap}
.plan-top{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:14px}
.plan-name{font-family:'Playfair Display',serif;font-size:20px}
.plan-tagline{font-size:12px;color:#888;margin-top:2px}
.plan-price{font-family:'Playfair Display',serif;font-size:30px;color:var(--green);line-height:1;text-align:right}
.plan-price span{font-size:13px;color:#888;font-family:'DM Sans',sans-serif;font-weight:400}
.plan-price-orig{font-size:12px;color:#bbb;text-decoration:line-through;text-align:right;margin-top:2px}
.plan-features{display:flex;flex-direction:column;gap:8px;margin-bottom:16px}
.feat-row{display:flex;align-items:flex-start;gap:10px;font-size:13px;color:var(--mid)}
.feat-check{width:20px;height:20px;border-radius:50%;background:var(--green-pale);color:var(--green);display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;flex-shrink:0;margin-top:1px}
.feat-check.no{background:#FEE2E2;color:#DC2626}
.btn-choose{width:100%;padding:13px;border-radius:12px;font-size:14px;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;border:2px solid var(--green);background:white;color:var(--green);transition:all .2s}
.plan-card.popular .btn-choose{background:var(--green);color:white}
.guarantee-bar{margin:4px 16px 16px;background:white;border-radius:14px;padding:14px;display:flex;align-items:center;gap:12px;box-shadow:var(--shadow)}
.guarantee-icon{font-size:26px;flex-shrink:0}
.guarantee-text h4{font-size:13px;font-weight:700}
.guarantee-text p{font-size:12px;color:#888;margin-top:2px}
.section-lbl{font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:1.5px;color:#888;text-align:center;margin:4px 0 14px}
.testimonials{padding:0 16px;display:flex;flex-direction:column;gap:12px;margin-bottom:20px}
.t-card{background:white;border-radius:14px;padding:16px;box-shadow:var(--shadow)}
.t-top{display:flex;align-items:center;gap:10px;margin-bottom:8px}
.t-avatar{width:38px;height:38px;border-radius:50%;background:var(--green-pale);display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0}
.t-name{font-weight:700;font-size:14px}
.t-meta{font-size:11px;color:#888}
.t-stars{color:var(--gold);font-size:13px;margin-bottom:6px}
.t-text{font-size:13px;color:var(--mid);line-height:1.6}
.faq-wrap{padding:0 16px;margin-bottom:20px}
.faq-item{background:white;border-radius:14px;margin-bottom:10px;overflow:hidden;box-shadow:var(--shadow)}
.faq-q{padding:16px;font-weight:600;font-size:14px;cursor:pointer;display:flex;justify-content:space-between;align-items:center}
.faq-arrow{transition:transform .25s;font-size:12px;color:#888}
.faq-item.open .faq-arrow{transform:rotate(180deg)}
.faq-a{display:none;padding:0 16px 16px;font-size:13px;color:#888;line-height:1.7}
.faq-item.open .faq-a{display:block}

/* ════ CHECKOUT ════ */
#screen-checkout{background:var(--light);overflow-y:auto;padding-bottom:40px}
.checkout-hdr{background:var(--green);padding:calc(48px + var(--safe-top)) 20px 24px;color:white;display:flex;align-items:center;gap:14px}
.btn-back{width:38px;height:38px;background:rgba(255,255,255,.15);border:none;border-radius:10px;color:white;font-size:18px;cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-family:'DM Sans',sans-serif}
.checkout-hdr h2{font-family:'Playfair Display',serif;font-size:22px;color:var(--gold)}
.order-box{background:white;margin:20px 16px 14px;border-radius:20px;padding:20px;box-shadow:var(--shadow)}
.box-title{font-weight:700;font-size:15px;margin-bottom:14px}
.order-row{display:flex;justify-content:space-between;align-items:center;padding:10px 0;border-bottom:1px solid #F5F5F0;font-size:14px}
.order-row:last-child{border-bottom:none;font-weight:700}
.order-row .lbl{color:var(--mid)}
.order-row.total .val{color:var(--green);font-family:'Playfair Display',serif;font-size:22px}
.form-box{margin:0 16px 14px;background:white;border-radius:20px;padding:20px;box-shadow:var(--shadow)}
.field{margin-bottom:16px}
.field label{display:block;font-size:12px;font-weight:700;color:var(--mid);text-transform:uppercase;letter-spacing:.8px;margin-bottom:6px}
.field input,.field select{width:100%;padding:14px 16px;border:2px solid #E0E0D8;border-radius:12px;font-family:'DM Sans',sans-serif;font-size:15px;background:white;color:var(--dark);outline:none;transition:border .2s;-webkit-appearance:none}
.field input:focus,.field select:focus{border-color:var(--green)}
.field-row{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.pm-box{margin:0 16px 14px;background:white;border-radius:20px;padding:20px;box-shadow:var(--shadow)}
.pm-options{display:flex;flex-direction:column;gap:10px}
.pm-opt{display:flex;align-items:center;gap:14px;padding:14px;border:2px solid #E0E0D8;border-radius:14px;cursor:pointer;transition:all .2s}
.pm-opt.selected{border-color:var(--green);background:#FAFFFC}
.pm-radio{width:20px;height:20px;border-radius:50%;border:2px solid #E0E0D8;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all .2s}
.pm-opt.selected .pm-radio{border-color:var(--green);background:var(--green)}
.pm-radio::after{content:'';width:8px;height:8px;border-radius:50%;background:white}
.pm-icon{font-size:24px;width:44px;height:44px;background:var(--light);border-radius:10px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.pm-info h4{font-size:14px;font-weight:700}
.pm-info p{font-size:12px;color:#888;margin-top:2px}
.pm-extra{margin-top:12px;padding-top:12px;border-top:1px solid #F5F5F0;display:none}
.pm-extra.show{display:block}
.bank-info{background:var(--light);border-radius:10px;padding:14px;font-size:13px;color:var(--mid);line-height:1.9}
.btn-pay{width:calc(100% - 32px);margin:0 16px;padding:18px;background:var(--green);color:white;border:none;border-radius:16px;font-size:17px;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;display:flex;align-items:center;justify-content:center;gap:10px;box-shadow:0 6px 24px rgba(45,106,79,.3)}
.btn-pay:active{transform:scale(.97)}
.secure-note{text-align:center;font-size:12px;color:#999;margin-top:12px;padding-bottom:8px}

/* ════ SUCCESS ════ */
#screen-success{background:linear-gradient(160deg,var(--green) 0%,#1B4332 100%);justify-content:center;align-items:center;padding:calc(40px + var(--safe-top)) 28px 40px;text-align:center}
.success-circle{width:100px;height:100px;background:rgba(255,255,255,.15);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:48px;margin:0 auto 24px;animation:popIn .5s ease}
@keyframes popIn{from{transform:scale(0)}to{transform:scale(1)}}
.success-title{font-family:'Playfair Display',serif;font-size:34px;color:var(--gold);margin-bottom:12px}
.success-sub{font-size:15px;color:rgba(255,255,255,.8);line-height:1.7;margin-bottom:28px}
.success-card{background:rgba(255,255,255,.12);border-radius:16px;padding:20px;margin-bottom:28px;text-align:left;width:100%}
.success-row{display:flex;justify-content:space-between;padding:9px 0;border-bottom:1px solid rgba(255,255,255,.1);font-size:14px;color:rgba(255,255,255,.85)}
.success-row:last-child{border-bottom:none;font-weight:700;color:var(--gold)}
.btn-start-app{width:100%;padding:16px;background:var(--gold);color:var(--dark);border:none;border-radius:50px;font-size:16px;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;margin-bottom:12px}
.btn-share-app{width:100%;padding:15px;background:rgba(255,255,255,.12);color:white;border:none;border-radius:50px;font-size:15px;font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif}

/* ════ SETUP ════ */
#screen-setup{background:var(--cream);overflow-y:auto}
.setup-hdr{background:var(--green);padding:calc(48px + var(--safe-top)) 28px 28px;color:white}
.setup-hdr h2{font-family:'Playfair Display',serif;font-size:26px;color:var(--gold)}
.setup-hdr p{font-size:13px;color:rgba(255,255,255,.7);margin-top:4px}
.setup-body{padding:28px;flex:1}
.form-group{margin-bottom:20px}
.form-group label{display:block;font-size:12px;font-weight:700;color:var(--mid);margin-bottom:6px;text-transform:uppercase;letter-spacing:.8px}
.form-group input,.form-group select{width:100%;padding:14px 16px;border:2px solid #E0E0D8;border-radius:12px;font-family:'DM Sans',sans-serif;font-size:15px;background:white;color:var(--dark);outline:none;transition:border .2s;-webkit-appearance:none}
.form-group input:focus,.form-group select:focus{border-color:var(--green)}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.chip-group{display:flex;flex-wrap:wrap;gap:8px}
.chip{padding:9px 16px;border-radius:50px;border:2px solid #E0E0D8;background:white;font-size:13px;font-weight:500;cursor:pointer;transition:all .2s}
.chip.selected{background:var(--green);border-color:var(--green);color:white}
.setup-btn{background:var(--green);color:white;font-family:'DM Sans',sans-serif;font-weight:700;font-size:16px;border:none;border-radius:50px;padding:16px;cursor:pointer;width:100%;margin-top:8px}

/* ════ MAIN APP ════ */
#screen-app{background:var(--light);padding-bottom:calc(72px + var(--safe-bottom));overflow-y:auto;-webkit-overflow-scrolling:touch}
.app-header{background:var(--green);padding:calc(48px + var(--safe-top)) 22px 20px;color:white}
.app-header-top{display:flex;justify-content:space-between;align-items:center}
.greeting{font-size:13px;color:rgba(255,255,255,.65)}
.user-name{font-family:'Playfair Display',serif;font-size:22px;color:var(--gold)}
.avatar{width:42px;height:42px;border-radius:50%;background:var(--gold);display:flex;align-items:center;justify-content:center;font-size:20px;flex-shrink:0;cursor:pointer}
.calorie-card{margin-top:18px;background:rgba(255,255,255,.12);border-radius:14px;padding:16px;display:flex;align-items:center;gap:16px}
.cal-main{flex:1}
.cal-num{font-size:32px;font-weight:700;color:white}
.cal-label{font-size:11px;color:rgba(255,255,255,.6);text-transform:uppercase;letter-spacing:1px}
.cal-macros{display:flex;gap:12px}
.macro{text-align:center}
.macro-val{font-size:15px;font-weight:600;color:var(--gold)}
.macro-lbl{font-size:10px;color:rgba(255,255,255,.55);text-transform:uppercase}
.tab-bar{display:flex;background:white;border-bottom:1px solid #ECEAE2;position:sticky;top:0;z-index:10}
.tab{flex:1;padding:13px 0;text-align:center;font-size:11px;font-weight:700;color:#999;cursor:pointer;border-bottom:3px solid transparent;text-transform:uppercase;letter-spacing:.5px;transition:all .2s}
.tab.active{color:var(--green);border-bottom-color:var(--green)}
.tab-icon{font-size:18px;display:block;margin-bottom:2px}
.tab-content{display:none;padding:20px}
.tab-content.active{display:block}
.section-title{font-family:'Playfair Display',serif;font-size:20px;margin-bottom:4px}
.section-sub{font-size:13px;color:#888;margin-bottom:16px}

/* MEALS */
.meal-slot{margin-bottom:14px}
.slot-label{font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:#888;margin-bottom:6px}
.meal-card{background:white;border-radius:var(--radius);padding:14px;box-shadow:var(--shadow);display:flex;align-items:center;gap:12px}
.meal-emoji{font-size:32px;width:50px;height:50px;display:flex;align-items:center;justify-content:center;background:var(--light);border-radius:12px;flex-shrink:0}
.meal-info{flex:1;min-width:0}
.meal-name{font-weight:600;font-size:14px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.meal-name-am{font-size:11px;color:#999;margin-bottom:3px}
.meal-meta{display:flex;gap:6px;align-items:center;flex-wrap:wrap;margin-top:4px}
.badge{font-size:10px;font-weight:700;padding:3px 7px;border-radius:50px;text-transform:uppercase;white-space:nowrap}
.badge-cal{background:var(--green-pale);color:var(--green)}
.badge-protein{background:#FFF0E6;color:var(--red)}
.badge-vegan{background:#E8F4FD;color:#2196F3}
.badge-oil-low{background:#E8F5E9;color:#388E3C}
.badge-oil-high{background:#FFF3E0;color:#F57C00}
.meal-actions{display:flex;flex-direction:column;gap:6px;flex-shrink:0}
.btn-swap-m{background:var(--green-pale);color:var(--green);border:none;border-radius:8px;padding:7px 10px;font-size:12px;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif}
.btn-ate{background:white;color:#888;border:2px solid #E0E0D8;border-radius:8px;padding:7px 10px;font-size:12px;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif}
.btn-ate.done{background:var(--gold);border-color:var(--gold);color:var(--dark)}
.fasting-banner{background:linear-gradient(135deg,#1A4A7A,#2D6A4F);border-radius:var(--radius);padding:14px 16px;margin-bottom:16px;display:flex;align-items:center;gap:12px;color:white}
.fasting-icon{font-size:24px}
.fasting-text h4{font-size:14px;font-weight:600}
.fasting-text p{font-size:12px;color:rgba(255,255,255,.7)}

/* WORKOUT */
.workout-mode-toggle{display:flex;background:white;border-radius:14px;padding:4px;box-shadow:var(--shadow);margin-bottom:18px;gap:4px}
.mode-btn{flex:1;padding:10px;text-align:center;border-radius:10px;font-size:13px;font-weight:700;cursor:pointer;border:none;background:transparent;font-family:'DM Sans',sans-serif;color:#999}
.mode-btn.active{background:var(--green);color:white}
.day-selector{display:flex;gap:8px;margin-bottom:20px;overflow-x:auto;padding-bottom:4px;scrollbar-width:none}
.day-selector::-webkit-scrollbar{display:none}
.day-btn{min-width:52px;height:66px;border-radius:14px;border:2px solid #E0E0D8;background:white;display:flex;flex-direction:column;align-items:center;justify-content:center;cursor:pointer;transition:all .2s;font-family:'DM Sans',sans-serif;flex-shrink:0}
.day-btn.active{background:var(--green);border-color:var(--green);color:white}
.day-btn.rest-day{background:#F5F5F0}
.day-name{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.5px}
.day-num{font-size:20px;font-weight:700}
.day-tag{font-size:9px;opacity:.7}
.workout-summary{background:white;border-radius:14px;padding:14px;box-shadow:var(--shadow);margin-bottom:16px;display:flex}
.summary-item{flex:1;text-align:center;border-right:1px solid #F0EEE6}
.summary-item:last-child{border-right:none}
.summary-val{font-family:'Playfair Display',serif;font-size:22px;color:var(--green)}
.summary-lbl{font-size:10px;color:#999;text-transform:uppercase;letter-spacing:.5px;margin-top:2px}
.muscle-section{margin-bottom:16px}
.muscle-header{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.muscle-icon{font-size:22px;width:40px;height:40px;background:var(--green-pale);border-radius:10px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.muscle-name{font-weight:700;font-size:15px}
.muscle-count{font-size:12px;color:#888}
.exercise-card{background:white;border-radius:14px;padding:14px;box-shadow:var(--shadow);margin-bottom:10px}
.exercise-card.done{opacity:.55}
.exercise-card-top{display:flex;align-items:flex-start;gap:12px}
.ex-num{width:28px;height:28px;background:var(--green);color:white;border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:700;flex-shrink:0;margin-top:2px}
.ex-body{flex:1}
.ex-name-big{font-weight:700;font-size:15px}
.ex-muscle-tag{font-size:11px;color:#888;margin-top:2px}
.ex-details{display:flex;gap:8px;margin-top:8px;flex-wrap:wrap}
.ex-badge{background:var(--light);border-radius:8px;padding:5px 10px;font-size:12px;font-weight:600;color:var(--mid)}
.ex-badge.sets{background:var(--green-pale);color:var(--green)}
.ex-badge.reps{background:#FFF0E6;color:var(--red)}
.ex-badge.rest-b{background:#F3F0FF;color:#7C3AED}
.ex-btn-row{display:flex;gap:8px;margin-top:10px}
.btn-swap-ex{flex:1;background:var(--light);border:2px solid #E0E0D8;border-radius:10px;padding:9px;font-size:12px;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;color:var(--mid)}
.btn-done-ex{flex:1;background:white;border:2px solid #E0E0D8;border-radius:10px;padding:9px;font-size:12px;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;color:#888}
.btn-done-ex.checked{background:var(--gold);border-color:var(--gold);color:var(--dark)}
.ex-tag{font-size:10px;font-weight:700;padding:3px 8px;border-radius:50px;background:var(--light);color:var(--mid)}
.ex-tag.compound{background:#EDE9FE;color:#7C3AED}
.ex-tag.isolation{background:#FFF0E6;color:var(--red)}
.ex-tag.cable{background:#E8F4FD;color:#0284C7}
.ex-tag.dumbbell{background:var(--green-pale);color:var(--green)}
.ex-tag.barbell{background:#FEF9C3;color:#854D0E}
.rest-day-card{background:white;border-radius:var(--radius);padding:32px 24px;text-align:center;box-shadow:var(--shadow)}
.rest-emoji{font-size:52px;margin-bottom:14px}
.rest-day-card h3{font-family:'Playfair Display',serif;font-size:22px;margin-bottom:10px}
.rest-day-card p{font-size:14px;color:#888;line-height:1.6}

/* PROGRESS */
.stat-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:20px}
.stat-card{background:white;border-radius:var(--radius);padding:16px;box-shadow:var(--shadow)}
.stat-value{font-family:'Playfair Display',serif;font-size:28px;color:var(--green)}
.stat-unit{font-size:14px;color:#888}
.stat-label{font-size:12px;color:#999;margin-top:2px}
.stat-change{font-size:12px;font-weight:700;margin-top:4px}
.stat-change.positive{color:var(--green)}
.stat-change.negative{color:var(--red)}
.weight-log{background:white;border-radius:var(--radius);padding:20px;box-shadow:var(--shadow);margin-bottom:14px}
.weight-log h4{font-weight:700;font-size:15px;margin-bottom:14px}
.chart-bars{display:flex;align-items:flex-end;gap:6px;height:80px}
.chart-bar-wrap{flex:1;display:flex;flex-direction:column;align-items:center;gap:4px}
.chart-bar{width:100%;background:var(--green-pale);border-radius:6px 6px 0 0}
.chart-bar.highlight{background:var(--green)}
.chart-week{font-size:10px;color:#999}
.chart-val{font-size:10px;font-weight:700;color:var(--mid)}
.adherence-wrap{background:white;border-radius:var(--radius);padding:18px;box-shadow:var(--shadow);margin-bottom:14px}
.adherence-title{font-weight:700;font-size:15px;margin-bottom:14px}
.adh-row{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.adh-name{font-size:13px;font-weight:500;width:72px;flex-shrink:0}
.adh-bg{flex:1;height:10px;background:#F0EEE6;border-radius:50px}
.adh-fill{height:100%;background:var(--green);border-radius:50px}
.adh-pct{font-size:12px;font-weight:700;color:var(--green);width:36px;text-align:right}
.checkin-card{background:white;border-radius:var(--radius);padding:20px;box-shadow:var(--shadow)}
.checkin-card h4{font-weight:700;font-size:15px;margin-bottom:14px}
.checkin-row{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.checkin-label{font-size:13px;flex:1;color:var(--mid)}
.checkin-row input{width:80px;padding:9px 12px;border:2px solid #E0E0D8;border-radius:10px;font-size:15px;font-family:'DM Sans',sans-serif;text-align:center;outline:none}
.checkin-row input:focus{border-color:var(--green)}
.energy-stars{display:flex;gap:6px;margin-top:6px}
.star{font-size:26px;cursor:pointer;filter:grayscale(1);transition:filter .15s}
.star.lit{filter:grayscale(0)}
.btn-log{width:100%;padding:14px;background:var(--green);color:white;border:none;border-radius:12px;font-size:15px;font-weight:700;cursor:pointer;margin-top:16px;font-family:'DM Sans',sans-serif}

/* plan chip in header */
.plan-chip{background:rgba(255,255,255,.15);color:var(--gold);font-size:11px;font-weight:700;padding:4px 10px;border-radius:50px;margin-top:4px;display:inline-block}

/* BOTTOM NAV */
.bottom-nav{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:430px;background:white;border-top:1px solid #ECEAE2;display:flex;z-index:50;padding-bottom:var(--safe-bottom)}
.nav-item{flex:1;padding:10px 0;display:flex;flex-direction:column;align-items:center;gap:3px;cursor:pointer;color:#BBB;transition:all .2s}
.nav-item.active{color:var(--green)}
.nav-icon{font-size:22px}
.nav-label{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.5px}

/* MODALS */
.modal-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.5);z-index:100;align-items:flex-end;justify-content:center}
.modal-overlay.open{display:flex}
.modal{background:white;border-radius:24px 24px 0 0;padding:24px;padding-bottom:calc(24px + var(--safe-bottom));width:100%;max-width:430px;max-height:85vh;overflow-y:auto;animation:slideUp .3s ease}
@keyframes slideUp{from{transform:translateY(100%)}to{transform:translateY(0)}}
.modal-handle{width:40px;height:4px;background:#E0E0D8;border-radius:2px;margin:0 auto 20px}
.modal-title{font-family:'Playfair Display',serif;font-size:20px;margin-bottom:4px}
.modal-sub{font-size:13px;color:#888;margin-bottom:16px}
.swap-filters{display:flex;gap:8px;margin-bottom:16px;overflow-x:auto;padding-bottom:4px;scrollbar-width:none}
.swap-filters::-webkit-scrollbar{display:none}
.filter-chip{padding:7px 14px;border-radius:50px;border:2px solid #E0E0D8;background:white;font-size:12px;font-weight:700;cursor:pointer;white-space:nowrap;font-family:'DM Sans',sans-serif}
.filter-chip.active{background:var(--green);border-color:var(--green);color:white}
.swap-opt-wrap{position:relative;margin-bottom:10px}
.swap-opt{display:flex;align-items:center;gap:12px;padding:14px;border:2px solid #F0EEE6;border-radius:14px;cursor:pointer;transition:all .2s}
.swap-opt.best{border-color:var(--gold);background:#FFFDF0}
.swap-best-badge{position:absolute;top:-9px;right:12px;background:var(--gold);color:var(--dark);font-size:10px;font-weight:700;padding:2px 8px;border-radius:50px}
.swap-diff{font-size:11px;font-weight:700}
.diff-green{color:var(--green)}
.diff-red{color:var(--red)}
.ex-swap-opt{display:flex;align-items:center;gap:12px;padding:14px;border:2px solid #F0EEE6;border-radius:14px;margin-bottom:10px;cursor:pointer;transition:all .2s}
.ex-swap-opt.current-ex{border-color:var(--gold);background:#FFFDF0}
.ex-swap-icon{font-size:26px;width:46px;height:46px;display:flex;align-items:center;justify-content:center;background:var(--light);border-radius:12px;flex-shrink:0}
.ex-swap-name{font-weight:700;font-size:14px}
.ex-swap-detail{font-size:12px;color:#888;margin-top:3px}
.ex-swap-tip{font-size:11px;color:#999;margin-top:4px;font-style:italic}
.current-badge{background:var(--gold);color:var(--dark);font-size:10px;font-weight:700;padding:2px 8px;border-radius:50px;margin-left:6px}
.btn-close-modal{width:100%;padding:16px;background:var(--green);color:white;border:none;border-radius:14px;font-size:16px;font-weight:700;cursor:pointer;margin-top:8px;font-family:'DM Sans',sans-serif}

/* TOAST */
.toast{position:fixed;top:calc(20px + var(--safe-top));left:50%;transform:translateX(-50%) translateY(-100px);background:var(--dark);color:white;padding:12px 24px;border-radius:50px;font-size:14px;font-weight:500;z-index:200;transition:transform .3s ease;white-space:nowrap;box-shadow:0 4px 20px rgba(0,0,0,.25)}
.toast.show{transform:translateX(-50%) translateY(0)}
</style>
</head>
<body>

<!-- ════════════ SPLASH ════════════ -->
<div class="screen active" id="screen-splash">
  <div class="flag">🇪🇹</div>
  <div class="brand">Habesha Fit</div>
  <div class="brand-sub">Ethiopian Fitness · ሃበሻ ፊት</div>
  <p class="tagline">Your fitness journey, built around<br>the foods and culture you love.</p>
  <div class="feature-pills">
    <div class="pill">🍽️ Ethiopian Meals</div>
    <div class="pill">🔄 Meal Swap</div>
    <div class="pill">🏋️ Gym & Home</div>
    <div class="pill">🔀 Exercise Swap</div>
    <div class="pill">🕊️ Fasting Mode</div>
    <div class="pill">📊 Progress</div>
  </div>
  <button class="btn-gold" onclick="goTo('screen-pricing')">View Plans & Pricing →</button>
  <div class="splash-login" onclick="tryLogin()">Already subscribed? <span>Sign in</span></div>
</div>

<!-- ════════════ PRICING ════════════ -->
<div class="screen" id="screen-pricing">
  <div class="pricing-hero">
    <div class="hero-title">Get Your Personal<br>Ethiopian Meal Plan</div>
    <p class="hero-sub">Customized to your body, your goals,<br>and the food you already love.</p>
    <div class="hero-trust">
      <div class="trust-item">✓ Ethiopian foods</div>
      <div class="trust-item">✓ Fasting support</div>
      <div class="trust-item">✓ Cancel anytime</div>
    </div>
    <div class="billing-toggle">
      <button class="toggle-btn active" id="btn-monthly" onclick="setBilling('monthly')">Monthly</button>
      <button class="toggle-btn" id="btn-yearly" onclick="setBilling('yearly')">Yearly <span class="save-badge">Save 30%</span></button>
    </div>
  </div>

  <div class="plans-wrap">
    <!-- BASIC -->
    <div class="plan-card" id="card-basic">
      <div class="plan-top">
        <div><div class="plan-name">🌱 Basic</div><div class="plan-tagline">Start your journey</div></div>
        <div><div class="plan-price" id="price-basic">199 <span>ETB/mo</span></div><div class="plan-price-orig" id="orig-basic" style="display:none"></div></div>
      </div>
      <div class="plan-features">
        <div class="feat-row"><div class="feat-check">✓</div>7-day Ethiopian meal plan</div>
        <div class="feat-row"><div class="feat-check">✓</div>Calorie & macro calculator</div>
        <div class="feat-row"><div class="feat-check">✓</div>Meal swap feature</div>
        <div class="feat-row"><div class="feat-check">✓</div>Fasting day meals included</div>
        <div class="feat-row"><div class="feat-check no">✗</div><span style="color:#bbb">Weekly plan updates</span></div>
        <div class="feat-row"><div class="feat-check no">✗</div><span style="color:#bbb">Trainer support</span></div>
      </div>
      <button class="btn-choose" onclick="selectPlan('basic')">Choose Basic</button>
    </div>
    <!-- STANDARD -->
    <div class="plan-card popular" id="card-standard">
      <div class="popular-badge">⭐ MOST POPULAR</div>
      <div class="plan-top">
        <div><div class="plan-name">🔥 Standard</div><div class="plan-tagline">Best for real results</div></div>
        <div><div class="plan-price" id="price-standard">349 <span>ETB/mo</span></div><div class="plan-price-orig" id="orig-standard" style="display:none"></div></div>
      </div>
      <div class="plan-features">
        <div class="feat-row"><div class="feat-check">✓</div>30-day Ethiopian meal plan</div>
        <div class="feat-row"><div class="feat-check">✓</div>Calorie & macro calculator</div>
        <div class="feat-row"><div class="feat-check">✓</div>Meal swap feature</div>
        <div class="feat-row"><div class="feat-check">✓</div>Fasting day meals included</div>
        <div class="feat-row"><div class="feat-check">✓</div>Weekly plan updates</div>
        <div class="feat-row"><div class="feat-check">✓</div>Progress tracking dashboard</div>
        <div class="feat-row"><div class="feat-check no">✗</div><span style="color:#bbb">Direct trainer support</span></div>
      </div>
      <button class="btn-choose" onclick="selectPlan('standard')">Choose Standard</button>
    </div>
    <!-- PREMIUM -->
    <div class="plan-card" id="card-premium">
      <div class="plan-top">
        <div><div class="plan-name">👑 Premium</div><div class="plan-tagline">Full trainer experience</div></div>
        <div><div class="plan-price" id="price-premium">499 <span>ETB/mo</span></div><div class="plan-price-orig" id="orig-premium" style="display:none"></div></div>
      </div>
      <div class="plan-features">
        <div class="feat-row"><div class="feat-check">✓</div>30-day Ethiopian meal plan</div>
        <div class="feat-row"><div class="feat-check">✓</div>Calorie & macro calculator</div>
        <div class="feat-row"><div class="feat-check">✓</div>Meal swap feature</div>
        <div class="feat-row"><div class="feat-check">✓</div>Fasting day meals included</div>
        <div class="feat-row"><div class="feat-check">✓</div>Weekly plan updates</div>
        <div class="feat-row"><div class="feat-check">✓</div>Progress tracking dashboard</div>
        <div class="feat-row"><div class="feat-check">✓</div>Direct WhatsApp support</div>
        <div class="feat-row"><div class="feat-check">✓</div>Monthly 1-on-1 check-in call</div>
      </div>
      <button class="btn-choose" onclick="selectPlan('premium')">Choose Premium</button>
    </div>
  </div>

  <div class="guarantee-bar">
    <div class="guarantee-icon">🛡️</div>
    <div class="guarantee-text"><h4>7-Day Money Back Guarantee</h4><p>Not happy in the first week? Full refund, no questions asked.</p></div>
  </div>

  <div class="section-lbl">What clients say</div>
  <div class="testimonials">
    <div class="t-card">
      <div class="t-top"><div class="t-avatar">👩🏾</div><div><div class="t-name">Hiwot T.</div><div class="t-meta">Lost 6kg · Addis Ababa</div></div></div>
      <div class="t-stars">⭐⭐⭐⭐⭐</div>
      <div class="t-text">"Finally a plan with real Ethiopian food! I lost weight eating Misir Wot and Shiro — no boring salads."</div>
    </div>
    <div class="t-card">
      <div class="t-top"><div class="t-avatar">👨🏾</div><div><div class="t-name">Biruk A.</div><div class="t-meta">Gained 4kg muscle · Hawassa</div></div></div>
      <div class="t-stars">⭐⭐⭐⭐⭐</div>
      <div class="t-text">"The meal swap is amazing. When I can't find one ingredient I swap it instantly. The Amharic names make it so easy."</div>
    </div>
  </div>

  <div class="section-lbl">Common questions</div>
  <div class="faq-wrap">
    <div class="faq-item" onclick="toggleFaq(this)"><div class="faq-q">Can I cancel anytime? <span class="faq-arrow">▼</span></div><div class="faq-a">Yes! Cancel anytime — no penalty. You keep access until your billing period ends.</div></div>
    <div class="faq-item" onclick="toggleFaq(this)"><div class="faq-q">How do I pay? <span class="faq-arrow">▼</span></div><div class="faq-a">We accept TeleBirr, bank transfer (CBE, Awash, Dashen), and WhatsApp payment arrangement.</div></div>
    <div class="faq-item" onclick="toggleFaq(this)"><div class="faq-q">Does it support Orthodox fasting? <span class="faq-arrow">▼</span></div><div class="faq-a">Yes! On Wednesday and Friday the app automatically shows vegan Ethiopian meals for fasting days.</div></div>
    <div class="faq-item" onclick="toggleFaq(this)"><div class="faq-q">What if I don't like a meal? <span class="faq-arrow">▼</span></div><div class="faq-a">Every meal has a Swap button. Just tap it to see alternatives — filtered by Vegan, High Protein, or Low Carb.</div></div>
  </div>
</div>

<!-- ════════════ CHECKOUT ════════════ -->
<div class="screen" id="screen-checkout">
  <div class="checkout-hdr">
    <button class="btn-back" onclick="goTo('screen-pricing')">←</button>
    <div><div style="font-size:12px;color:rgba(255,255,255,.65)">Almost there!</div><h2>Complete Your Order</h2></div>
  </div>
  <div class="order-box">
    <div class="box-title">Order Summary</div>
    <div class="order-row"><span class="lbl">Plan</span><span class="val" id="sum-plan">Standard</span></div>
    <div class="order-row"><span class="lbl">Billing</span><span class="val" id="sum-billing">Monthly</span></div>
    <div class="order-row"><span class="lbl">Duration</span><span class="val" id="sum-duration">1 month</span></div>
    <div class="order-row total"><span class="lbl">Total</span><span class="val" id="sum-total">349 ETB</span></div>
  </div>
  <div class="form-box">
    <div class="box-title">Your Information</div>
    <div class="field"><label>Full Name</label><input type="text" id="co-name" placeholder="e.g. Selam Tesfaye"></div>
    <div class="field"><label>Phone Number</label><input type="tel" id="co-phone" placeholder="09xxxxxxxx"></div>
    <div class="field"><label>Email (optional)</label><input type="email" id="co-email" placeholder="selam@email.com"></div>
    <div class="field-row">
      <div class="field"><label>Goal</label><select id="co-goal"><option>Fat Loss</option><option>Muscle Gain</option><option>Maintain</option></select></div>
      <div class="field"><label>Sex</label><select id="co-sex"><option>Female</option><option>Male</option></select></div>
    </div>
  </div>
  <div class="pm-box">
    <div class="box-title">Payment Method</div>
    <div class="pm-options">
      <div class="pm-opt selected" id="pm-telebirr" onclick="selectPM('telebirr')">
        <div class="pm-radio"></div><div class="pm-icon">📱</div>
        <div class="pm-info"><h4>TeleBirr</h4><p>Pay instantly with your TeleBirr wallet</p></div>
      </div>
      <div class="pm-extra show" id="ext-telebirr">
        <div class="field" style="margin-bottom:0"><label>TeleBirr Phone</label><input type="tel" id="co-telebirr" placeholder="09xxxxxxxx"></div>
      </div>
      <div class="pm-opt" id="pm-bank" onclick="selectPM('bank')">
        <div class="pm-radio"></div><div class="pm-icon">🏦</div>
        <div class="pm-info"><h4>Bank Transfer</h4><p>CBE, Awash, Dashen or any Ethiopian bank</p></div>
      </div>
      <div class="pm-extra" id="ext-bank">
        <div class="bank-info"><strong>Bank:</strong> Commercial Bank of Ethiopia (CBE)<br><strong>Account:</strong> 1000300284087<br><strong>Name:</strong> Habesha Fit<br><span style="font-size:12px;color:#888">Send transfer screenshot to WhatsApp. Plan activates within 2 hours.</span></div>
      </div>
      <div class="pm-opt" id="pm-whatsapp" onclick="selectPM('whatsapp')">
        <div class="pm-radio"></div><div class="pm-icon">💬</div>
        <div class="pm-info"><h4>Pay via WhatsApp</h4><p>Contact trainer directly to arrange</p></div>
      </div>
    </div>
  </div>
  <button class="btn-pay" onclick="processPayment()">🔒 <span id="pay-btn-text">Pay 349 ETB — Start Now</span></button>
  <div class="secure-note">🔒 Secure & confidential · Cancel anytime</div>
</div>

<!-- ════════════ SUCCESS ════════════ -->
<div class="screen" id="screen-success">
  <div class="success-circle">🎉</div>
  <div class="success-title">You're In!</div>
  <p class="success-sub">Your Habesha Fit plan is now active.<br>Let's get to work — ወደ ሥራ እንሂድ!</p>
  <div class="success-card">
    <div class="success-row"><span>Plan</span><span id="suc-plan">Standard</span></div>
    <div class="success-row"><span>Phone</span><span id="suc-phone">09xxxxxxxx</span></div>
    <div class="success-row"><span>Status</span><span>✅ Active</span></div>
    <div class="success-row"><span>Amount Paid</span><span id="suc-amount">349 ETB</span></div>
  </div>
  <button class="btn-start-app" onclick="goTo('screen-setup')">Set Up My Profile →</button>
  <button class="btn-share-app" onclick="shareApp()">📤 Share Habesha Fit with friends</button>
</div>

<!-- ════════════ SETUP ════════════ -->
<div class="screen" id="screen-setup">
  <div class="setup-hdr"><h2>Build Your Plan</h2><p>Tell us about yourself — we'll do the rest</p></div>
  <div class="setup-body">
    <div class="form-row">
      <div class="form-group"><label>Your Name</label><input type="text" id="inp-name" placeholder="e.g. Selam" value="Selam"></div>
      <div class="form-group"><label>Goal</label><select id="inp-goal"><option value="fat_loss">Fat Loss</option><option value="muscle">Muscle Gain</option><option value="maintain">Maintain</option></select></div>
    </div>
    <div class="form-row">
      <div class="form-group"><label>Weight (kg)</label><input type="number" id="inp-weight" placeholder="70" value="72"></div>
      <div class="form-group"><label>Height (cm)</label><input type="number" id="inp-height" placeholder="165" value="165"></div>
    </div>
    <div class="form-row">
      <div class="form-group"><label>Age</label><input type="number" id="inp-age" placeholder="28" value="28"></div>
      <div class="form-group"><label>Sex</label><select id="inp-sex"><option value="female">Female</option><option value="male">Male</option></select></div>
    </div>
    <div class="form-group"><label>Activity Level</label>
      <select id="inp-activity">
        <option value="1.2">Sedentary (desk job)</option>
        <option value="1.375" selected>Lightly active (1–3x/week)</option>
        <option value="1.55">Moderately active (3–5x/week)</option>
        <option value="1.725">Very active (6–7x/week)</option>
      </select>
    </div>
    <div class="form-group"><label>Fasting Type</label>
      <div class="chip-group"><div class="chip selected" onclick="selectChip(this)">Orthodox Fast</div><div class="chip" onclick="selectChip(this)">Partial Fast</div><div class="chip" onclick="selectChip(this)">None</div></div>
    </div>
    <div class="form-group"><label>Workout Location</label>
      <div class="chip-group"><div class="chip" onclick="selectChip(this)">Home Only</div><div class="chip selected" onclick="selectChip(this)">Gym</div><div class="chip" onclick="selectChip(this)">Both</div></div>
    </div>
    <button class="setup-btn" onclick="buildPlan()">Create My Plan — ዕቅዴን ፍጠር →</button>
  </div>
</div>

<!-- ════════════ MAIN APP ════════════ -->
<div class="screen" id="screen-app">
  <div class="app-header">
    <div class="app-header-top">
      <div>
        <div class="greeting" id="greeting">Good morning,</div>
        <div class="user-name" id="display-name">Selam</div>
        <div class="plan-chip" id="display-plan">🔥 Standard Plan</div>
      </div>
      <div class="avatar" onclick="goTo('screen-pricing')" title="Upgrade plan">💪</div>
    </div>
    <div class="calorie-card">
      <div class="cal-main"><div class="cal-num" id="display-cal">1,680</div><div class="cal-label">Daily Calories</div></div>
      <div class="cal-macros">
        <div class="macro"><div class="macro-val" id="display-protein">126g</div><div class="macro-lbl">Protein</div></div>
        <div class="macro"><div class="macro-val" id="display-carbs">189g</div><div class="macro-lbl">Carbs</div></div>
        <div class="macro"><div class="macro-val" id="display-fat">47g</div><div class="macro-lbl">Fat</div></div>
      </div>
    </div>
  </div>

  <div class="tab-bar">
    <div class="tab active" onclick="switchTab('meals',this)"><span class="tab-icon">🍽️</span>Meals</div>
    <div class="tab" onclick="switchTab('workout',this)"><span class="tab-icon">🏋️</span>Workout</div>
    <div class="tab" onclick="switchTab('progress',this)"><span class="tab-icon">📊</span>Progress</div>
  </div>

  <!-- MEALS TAB -->
  <div class="tab-content active" id="tab-meals">
    <div class="fasting-banner" id="fasting-banner" style="display:none">
      <div class="fasting-icon">🕊️</div>
      <div class="fasting-text"><h4>Orthodox Fasting Day</h4><p>Vegan plan active — ጾም ይበረክትልዎ</p></div>
    </div>
    <div class="section-title">Today's Meal Plan</div>
    <div class="section-sub" id="today-date"></div>
    <div id="meal-slots"></div>
  </div>

  <!-- WORKOUT TAB -->
  <div class="tab-content" id="tab-workout">
    <div class="section-title">Workout Plan</div>
    <div class="section-sub" id="workout-subtitle">Gym Split · 5 Days</div>
    <div class="workout-mode-toggle">
      <button class="mode-btn" id="btn-home" onclick="setWorkoutMode('home')">🏠 Home</button>
      <button class="mode-btn active" id="btn-gym" onclick="setWorkoutMode('gym')">🏋️ Gym</button>
    </div>
    <div class="day-selector" id="day-selector"></div>
    <div id="workout-content"></div>
  </div>

  <!-- PROGRESS TAB -->
  <div class="tab-content" id="tab-progress">
    <div class="section-title">Your Progress</div>
    <div class="section-sub">Keep going — you're doing great! 🔥</div>
    <div class="stat-grid">
      <div class="stat-card"><div class="stat-value" id="prog-weight">72<span class="stat-unit">kg</span></div><div class="stat-label">Current Weight</div><div class="stat-change negative">↓ 1.2kg this month</div></div>
      <div class="stat-card"><div class="stat-value">18<span class="stat-unit">d</span></div><div class="stat-label">Streak 🔥</div><div class="stat-change positive">Personal best!</div></div>
      <div class="stat-card"><div class="stat-value">76<span class="stat-unit">%</span></div><div class="stat-label">Adherence</div><div class="stat-change positive">↑ vs last week</div></div>
      <div class="stat-card"><div class="stat-value">12<span class="stat-unit">wk</span></div><div class="stat-label">Journey</div><div class="stat-change positive">Since Jan 2026</div></div>
    </div>
    <div class="weight-log"><h4>Weight Trend (kg)</h4><div class="chart-bars" id="weight-chart"></div></div>
    <div class="adherence-wrap">
      <div class="adherence-title">Weekly Adherence</div>
      <div class="adh-row"><div class="adh-name">Meals</div><div class="adh-bg"><div class="adh-fill" style="width:82%"></div></div><div class="adh-pct">82%</div></div>
      <div class="adh-row"><div class="adh-name">Workouts</div><div class="adh-bg"><div class="adh-fill" style="width:67%"></div></div><div class="adh-pct">67%</div></div>
      <div class="adh-row"><div class="adh-name">Water</div><div class="adh-bg"><div class="adh-fill" style="width:90%"></div></div><div class="adh-pct">90%</div></div>
    </div>
    <div class="checkin-card">
      <h4>Weekly Check-In</h4>
      <div class="checkin-row"><div class="checkin-label">Current weight (kg)</div><input type="number" id="checkin-weight" placeholder="72" value="72"></div>
      <div><div class="checkin-label">Energy level this week</div>
        <div class="energy-stars">
          <span class="star lit" onclick="setStars(1)">⭐</span><span class="star lit" onclick="setStars(2)">⭐</span><span class="star lit" onclick="setStars(3)">⭐</span><span class="star" onclick="setStars(4)">⭐</span><span class="star" onclick="setStars(5)">⭐</span>
        </div>
      </div>
      <button class="btn-log" onclick="logCheckin()">Log This Week ✓</button>
    </div>
  </div>

  <div class="bottom-nav">
    <div class="nav-item active" onclick="switchTab('meals',document.querySelector('.tab'))"><div class="nav-icon">🍽️</div><div class="nav-label">Meals</div></div>
    <div class="nav-item" onclick="switchTab('workout',document.querySelectorAll('.tab')[1])"><div class="nav-icon">🏋️</div><div class="nav-label">Workout</div></div>
    <div class="nav-item" onclick="switchTab('progress',document.querySelectorAll('.tab')[2])"><div class="nav-icon">📊</div><div class="nav-label">Progress</div></div>
  </div>
</div>

<!-- MEAL SWAP MODAL -->
<div class="modal-overlay" id="meal-modal">
  <div class="modal">
    <div class="modal-handle"></div>
    <div class="modal-title">Swap Meal 🔄</div>
    <div class="modal-sub" id="meal-modal-sub">Choose a replacement</div>
    <div class="swap-filters">
      <div class="filter-chip active" onclick="setMealFilter('all',this)">All</div>
      <div class="filter-chip" onclick="setMealFilter('vegan',this)">Vegan 🌿</div>
      <div class="filter-chip" onclick="setMealFilter('high_protein',this)">High Protein 💪</div>
      <div class="filter-chip" onclick="setMealFilter('low_carb',this)">Low Carb</div>
    </div>
    <div id="meal-swap-options"></div>
    <button class="btn-close-modal" onclick="closeMealModal()">Close</button>
  </div>
</div>

<!-- EXERCISE SWAP MODAL -->
<div class="modal-overlay" id="ex-modal">
  <div class="modal">
    <div class="modal-handle"></div>
    <div class="modal-title">Swap Exercise 🔀</div>
    <div class="modal-sub" id="ex-modal-sub">Choose an alternative</div>
    <div id="ex-swap-options"></div>
    <button class="btn-close-modal" onclick="closeExModal()">Close</button>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
// ═══════ EXERCISE DATABASE ═══════
const EX={
  back:[
    {id:'b1',name:'Barbell Deadlift',emoji:'🏋️',sets:4,reps:'5',rest:180,muscle:'Full Back',tags:['barbell','compound'],tip:'Keep back straight, drive through heels'},
    {id:'b2',name:'Bent Over Barbell Row',emoji:'🏋️',sets:4,reps:'8',rest:120,muscle:'Mid Back / Lats',tags:['barbell','compound'],tip:'Pull to lower chest, squeeze blades'},
    {id:'b3',name:'Lat Pulldown',emoji:'🔧',sets:4,reps:'10',rest:90,muscle:'Lats',tags:['cable','compound'],tip:'Pull to upper chest, lean back slightly'},
    {id:'b4',name:'Seated Cable Row',emoji:'🔧',sets:3,reps:'12',rest:90,muscle:'Mid Back',tags:['cable','compound'],tip:'Keep chest up, pull to belly button'},
    {id:'b5',name:'Single Arm DB Row',emoji:'💪',sets:3,reps:'12',rest:75,muscle:'Lats/Rhomboids',tags:['dumbbell','compound'],tip:'Brace core, row elbow past torso'},
    {id:'b6',name:'T-Bar Row',emoji:'🏋️',sets:3,reps:'10',rest:120,muscle:'Mid Back',tags:['barbell','compound'],tip:'Keep torso at 45°'},
    {id:'b7',name:'Face Pull',emoji:'🔧',sets:3,reps:'15',rest:60,muscle:'Rear Delt/Upper Back',tags:['cable','isolation'],tip:'Pull to face, elbows high'},
    {id:'b8',name:'Pull-ups',emoji:'⬆️',sets:4,reps:'8',rest:120,muscle:'Lats/Biceps',tags:['compound'],tip:'Full range, dead hang to chin over bar'},
  ],
  chest:[
    {id:'c1',name:'Flat Barbell Bench Press',emoji:'🏋️',sets:4,reps:'8',rest:150,muscle:'Middle Chest',tags:['barbell','compound'],tip:'Lower to nipple line, drive up and in'},
    {id:'c2',name:'Incline Dumbbell Press',emoji:'💪',sets:4,reps:'10',rest:120,muscle:'Upper Chest',tags:['dumbbell','compound'],tip:'30–45° incline, feel the stretch'},
    {id:'c3',name:'Cable Fly (Mid)',emoji:'🔧',sets:3,reps:'12',rest:75,muscle:'Middle Chest',tags:['cable','isolation'],tip:'Slight elbow bend, squeeze at center'},
    {id:'c4',name:'High to Low Cable Fly',emoji:'🔧',sets:3,reps:'12',rest:75,muscle:'Lower Chest',tags:['cable','isolation'],tip:'Pull down and across body'},
    {id:'c5',name:'Low to High Cable Fly',emoji:'🔧',sets:3,reps:'12',rest:75,muscle:'Upper Chest',tags:['cable','isolation'],tip:'Pull up and across, arms arc upward'},
    {id:'c6',name:'Dumbbell Bench Press',emoji:'💪',sets:4,reps:'10',rest:120,muscle:'Middle Chest',tags:['dumbbell','compound'],tip:'Greater range than barbell'},
    {id:'c7',name:'Chest Dips',emoji:'⬇️',sets:3,reps:'12',rest:90,muscle:'Lower Chest',tags:['compound'],tip:'Lean forward to hit chest'},
    {id:'c8',name:'Pec Dec Machine',emoji:'🔧',sets:3,reps:'15',rest:60,muscle:'Inner Chest',tags:['isolation'],tip:'Keep slight elbow bend throughout'},
  ],
  shoulder:[
    {id:'sh1',name:'Overhead Barbell Press',emoji:'🏋️',sets:4,reps:'8',rest:150,muscle:'Front/Overall Delt',tags:['barbell','compound'],tip:'Press straight up, bar in front of face'},
    {id:'sh2',name:'Dumbbell Lateral Raise',emoji:'💪',sets:4,reps:'15',rest:60,muscle:'Side Delt',tags:['dumbbell','isolation'],tip:'Lead with elbows, slight forward tilt'},
    {id:'sh3',name:'Cable Lateral Raise',emoji:'🔧',sets:3,reps:'15',rest:60,muscle:'Side Delt',tags:['cable','isolation'],tip:'More constant tension than dumbbells'},
    {id:'sh4',name:'Seated DB Press',emoji:'💪',sets:4,reps:'10',rest:120,muscle:'Overall Delt',tags:['dumbbell','compound'],tip:'Full range, touch dumbbells at top'},
    {id:'sh5',name:'Front Raise',emoji:'💪',sets:3,reps:'12',rest:60,muscle:'Front Delt',tags:['dumbbell','isolation'],tip:'Raise to eye level, control descent'},
    {id:'sh6',name:'Reverse Pec Dec',emoji:'🔧',sets:3,reps:'15',rest:60,muscle:'Rear Delt',tags:['isolation'],tip:'Arms parallel, squeeze rear delts'},
    {id:'sh7',name:'Arnold Press',emoji:'💪',sets:3,reps:'12',rest:90,muscle:'All Three Delt Heads',tags:['dumbbell','compound'],tip:'Rotate palms as you press up'},
  ],
  triceps:[
    {id:'t1',name:'Tricep Rope Pushdown',emoji:'🔧',sets:4,reps:'12',rest:75,muscle:'All Tricep Heads',tags:['cable','isolation'],tip:'Elbows fixed, spread rope at bottom'},
    {id:'t2',name:'Skull Crushers',emoji:'🏋️',sets:3,reps:'12',rest:90,muscle:'Long Head',tags:['barbell','isolation'],tip:'Lower to forehead, keep elbows fixed'},
    {id:'t3',name:'Overhead Cable Extension',emoji:'🔧',sets:3,reps:'12',rest:75,muscle:'Long Head',tags:['cable','isolation'],tip:'Great long head stretch overhead'},
    {id:'t4',name:'Dumbbell Kickback',emoji:'💪',sets:3,reps:'15',rest:60,muscle:'Lateral Head',tags:['dumbbell','isolation'],tip:'Elbow stays fixed, extend fully'},
    {id:'t5',name:'Close Grip Bench Press',emoji:'🏋️',sets:3,reps:'10',rest:120,muscle:'All Tricep Heads',tags:['barbell','compound'],tip:'Hands shoulder width, tuck elbows'},
    {id:'t6',name:'Tricep Dips',emoji:'⬇️',sets:3,reps:'12',rest:90,muscle:'Lateral Head',tags:['compound'],tip:'Stay upright to target triceps'},
    {id:'t7',name:'Straight Bar Pushdown',emoji:'🔧',sets:3,reps:'15',rest:60,muscle:'Lateral Head',tags:['cable','isolation'],tip:'Wrists locked, squeeze at bottom'},
  ],
  biceps:[
    {id:'bi1',name:'Barbell Curl',emoji:'🏋️',sets:4,reps:'10',rest:90,muscle:'Both Bicep Heads',tags:['barbell','isolation'],tip:'Full range, squeeze hard at top'},
    {id:'bi2',name:'Hammer Curl',emoji:'💪',sets:3,reps:'12',rest:75,muscle:'Brachialis/Long Head',tags:['dumbbell','isolation'],tip:'Neutral grip, great for thickness'},
    {id:'bi3',name:'Preacher Curl',emoji:'💪',sets:3,reps:'12',rest:90,muscle:'Short Head/Peak',tags:['dumbbell','isolation'],tip:'Eliminates cheating, great peak builder'},
    {id:'bi4',name:'Incline Dumbbell Curl',emoji:'💪',sets:3,reps:'12',rest:75,muscle:'Long Head Stretch',tags:['dumbbell','isolation'],tip:'Great stretch, sit back on bench'},
    {id:'bi5',name:'Cable Curl',emoji:'🔧',sets:3,reps:'15',rest:60,muscle:'Both Heads',tags:['cable','isolation'],tip:'Constant tension throughout'},
    {id:'bi6',name:'Concentration Curl',emoji:'💪',sets:3,reps:'15',rest:60,muscle:'Bicep Peak',tags:['dumbbell','isolation'],tip:'Elbow on knee, squeeze at top'},
    {id:'bi7',name:'EZ Bar Curl',emoji:'🏋️',sets:4,reps:'10',rest:90,muscle:'Both Heads',tags:['barbell','isolation'],tip:'Easier on wrists than straight bar'},
  ],
  forearm:[
    {id:'fo1',name:'Wrist Curl',emoji:'💪',sets:3,reps:'20',rest:45,muscle:'Forearm Flexors',tags:['dumbbell','isolation'],tip:'Rest forearms on bench, full range'},
    {id:'fo2',name:'Reverse Wrist Curl',emoji:'💪',sets:3,reps:'20',rest:45,muscle:'Forearm Extensors',tags:['dumbbell','isolation'],tip:'Balances forearm development'},
    {id:'fo3',name:'Farmer Walk',emoji:'🚶',sets:3,reps:'30m',rest:90,muscle:'Full Forearm/Grip',tags:['compound'],tip:'Heavy dumbbells, walk with control'},
    {id:'fo4',name:'Dead Hang',emoji:'⬆️',sets:3,reps:'30s',rest:60,muscle:'Grip Strength',tags:['compound'],tip:'Hang from bar, full relaxation'},
    {id:'fo5',name:'Plate Pinch',emoji:'🔧',sets:3,reps:'30s',rest:60,muscle:'Pinch Grip',tags:['isolation'],tip:'Pinch weight plate with fingers'},
  ],
  quad:[
    {id:'q1',name:'Barbell Back Squat',emoji:'🏋️',sets:4,reps:'8',rest:180,muscle:'Quads/Glutes',tags:['barbell','compound'],tip:'Break parallel, drive knees out'},
    {id:'q2',name:'Leg Press',emoji:'🔧',sets:4,reps:'12',rest:120,muscle:'Quads/Glutes',tags:['compound'],tip:'Feet shoulder width, full range'},
    {id:'q3',name:'Hack Squat',emoji:'🔧',sets:3,reps:'12',rest:120,muscle:'Quads',tags:['compound'],tip:'Feet low on platform for more quad'},
    {id:'q4',name:'Leg Extension',emoji:'🔧',sets:3,reps:'15',rest:75,muscle:'Quad Isolation',tags:['isolation'],tip:'Squeeze hard at top, slow descent'},
    {id:'q5',name:'Bulgarian Split Squat',emoji:'💪',sets:3,reps:'10',rest:90,muscle:'Quad/Glute',tags:['dumbbell','compound'],tip:'Back foot elevated, knee tracks toe'},
    {id:'q6',name:'Front Squat',emoji:'🏋️',sets:4,reps:'8',rest:150,muscle:'Quads',tags:['barbell','compound'],tip:'More quad emphasis than back squat'},
    {id:'q7',name:'Walking Lunges',emoji:'🚶',sets:3,reps:'12 each',rest:90,muscle:'Quad/Glute',tags:['dumbbell','compound'],tip:'Long step, keep torso upright'},
  ],
  hamstring:[
    {id:'h1',name:'Romanian Deadlift (RDL)',emoji:'🏋️',sets:4,reps:'10',rest:120,muscle:'Hamstrings/Glutes',tags:['barbell','compound'],tip:'Hinge at hips, feel the stretch'},
    {id:'h2',name:'Lying Leg Curl',emoji:'🔧',sets:4,reps:'12',rest:90,muscle:'Hamstrings',tags:['isolation'],tip:'Full range, squeeze at top'},
    {id:'h3',name:'Seated Leg Curl',emoji:'🔧',sets:3,reps:'15',rest:75,muscle:'Hamstrings',tags:['isolation'],tip:'Greater stretch than lying version'},
    {id:'h4',name:'Sumo Deadlift',emoji:'🏋️',sets:3,reps:'8',rest:150,muscle:'Hamstrings/Inner Thigh',tags:['barbell','compound'],tip:'Wide stance, toes pointed out'},
    {id:'h5',name:'Nordic Hamstring Curl',emoji:'💪',sets:3,reps:'8',rest:120,muscle:'Hamstrings',tags:['compound'],tip:'Hardest bodyweight hamstring move'},
    {id:'h6',name:'Good Morning',emoji:'🏋️',sets:3,reps:'12',rest:90,muscle:'Hamstrings/Lower Back',tags:['barbell','compound'],tip:'Hinge forward, slight knee bend'},
  ],
  calf:[
    {id:'ca1',name:'Standing Calf Raise',emoji:'🔧',sets:5,reps:'20',rest:60,muscle:'Gastrocnemius',tags:['compound'],tip:'Full stretch at bottom, squeeze top'},
    {id:'ca2',name:'Seated Calf Raise',emoji:'🔧',sets:4,reps:'20',rest:60,muscle:'Soleus',tags:['isolation'],tip:'Bent knee targets deeper soleus'},
    {id:'ca3',name:'Leg Press Calf Raise',emoji:'🔧',sets:4,reps:'20',rest:60,muscle:'Gastrocnemius',tags:['compound'],tip:'Place toes on platform edge'},
    {id:'ca4',name:'Single Leg Calf Raise',emoji:'💪',sets:3,reps:'15 each',rest:60,muscle:'Gastrocnemius',tags:['isolation'],tip:'Hold dumbbell, use wall for balance'},
  ],
};

const EX_POOLS={back:EX.back,chest:EX.chest,shoulder:EX.shoulder,triceps:EX.triceps,biceps:EX.biceps,forearm:EX.forearm,quad:EX.quad,hamstring:EX.hamstring,calf:EX.calf};

// ═══════ GYM PLAN ═══════
const GYM_PLAN=[
  {day:'Mon',label:'Back & Triceps',emoji:'🏋️',rest:false,groups:[
    {muscle:'Back',icon:'🔙',slots:['b2','b3','b4']},
    {muscle:'Triceps',icon:'💥',slots:['t1','t2']},
  ]},
  {day:'Tue',label:'Chest & Biceps',emoji:'💪',rest:false,groups:[
    {muscle:'Upper Chest',icon:'⬆️',slots:['c2','c5']},
    {muscle:'Middle Chest',icon:'➡️',slots:['c1']},
    {muscle:'Biceps',icon:'💪',slots:['bi2','bi3']},
  ]},
  {day:'Wed',label:'Legs Day',emoji:'🦵',rest:false,groups:[
    {muscle:'Quads',icon:'🦵',slots:['q1','q2','q4']},
    {muscle:'Hamstrings',icon:'🦶',slots:['h1','h2']},
    {muscle:'Calves',icon:'🦿',slots:['ca1','ca2']},
  ]},
  {day:'Thu',label:'Rest Day',emoji:'😴',rest:true,groups:[]},
  {day:'Fri',label:'Shoulders & Arms',emoji:'💥',rest:false,groups:[
    {muscle:'Shoulders',icon:'🔝',slots:['sh1','sh2','sh6']},
    {muscle:'Biceps',icon:'💪',slots:['bi1','bi5']},
    {muscle:'Triceps',icon:'💥',slots:['t3','t6']},
    {muscle:'Forearms',icon:'✊',slots:['fo1','fo3']},
  ]},
  {day:'Sat',label:'Back & Chest',emoji:'🏆',rest:false,groups:[
    {muscle:'Back',icon:'🔙',slots:['b1','b5','b7']},
    {muscle:'Chest',icon:'💎',slots:['c3','c7']},
  ]},
  {day:'Sun',label:'Rest Day',emoji:'🧘',rest:true,groups:[]},
];

// ═══════ HOME PLAN ═══════
const HOME_PLAN=[
  {day:'Mon',label:'Chest & Arms',emoji:'💪',rest:false,groups:[
    {muscle:'Chest',icon:'💎',slots:[
      {id:'hp1',name:'Push-ups',emoji:'💪',sets:3,reps:'12',rest:60,muscle:'Chest',tags:['compound'],tip:'Keep core tight, full range'},
      {id:'hp2',name:'Diamond Push-ups',emoji:'💎',sets:3,reps:'10',rest:60,muscle:'Triceps/Inner Chest',tags:['compound'],tip:'Hands form diamond shape'},
      {id:'hp3',name:'Wide Push-ups',emoji:'💪',sets:3,reps:'12',rest:60,muscle:'Outer Chest',tags:['compound'],tip:'Wider than shoulder width'},
    ]},
    {muscle:'Biceps',icon:'💪',slots:[
      {id:'hp4',name:'Towel Curl',emoji:'🧴',sets:3,reps:'12',rest:60,muscle:'Biceps',tags:['isolation'],tip:'Loop towel under foot, curl up'},
      {id:'hp5',name:'Chin-ups',emoji:'⬆️',sets:3,reps:'8',rest:90,muscle:'Biceps/Back',tags:['compound'],tip:'Underhand grip, squeeze at top'},
    ]},
  ]},
  {day:'Tue',label:'Lower Body',emoji:'🦵',rest:false,groups:[
    {muscle:'Quads/Glutes',icon:'🦵',slots:[
      {id:'hp6',name:'Squats',emoji:'🏃',sets:4,reps:'15',rest:60,muscle:'Quads/Glutes',tags:['compound'],tip:'Break parallel, drive knees out'},
      {id:'hp7',name:'Jump Squats',emoji:'⬆️',sets:3,reps:'12',rest:60,muscle:'Power/Quads',tags:['compound'],tip:'Explode up, land softly'},
      {id:'hp8',name:'Bulgarian Split Squat',emoji:'🦵',sets:3,reps:'10 each',rest:75,muscle:'Quad/Glute',tags:['compound'],tip:'Back foot on chair'},
    ]},
    {muscle:'Hamstrings',icon:'🦶',slots:[
      {id:'hp9',name:'Glute Bridge',emoji:'🌉',sets:3,reps:'20',rest:45,muscle:'Glutes/Hamstrings',tags:['isolation'],tip:'Drive hips up, squeeze glutes'},
      {id:'hp10',name:'Reverse Lunges',emoji:'🚶',sets:3,reps:'12 each',rest:60,muscle:'Hamstrings/Glutes',tags:['compound'],tip:'Step back, knee over ankle'},
    ]},
    {muscle:'Calves',icon:'🦿',slots:[
      {id:'hp11',name:'Calf Raises',emoji:'⬆️',sets:4,reps:'20',rest:30,muscle:'Calves',tags:['isolation'],tip:'Full stretch at bottom'},
    ]},
  ]},
  {day:'Wed',label:'Rest Day',emoji:'😴',rest:true,groups:[]},
  {day:'Thu',label:'Back & Core',emoji:'🏋️',rest:false,groups:[
    {muscle:'Back',icon:'🔙',slots:[
      {id:'hp12',name:'Superman Hold',emoji:'🦸',sets:3,reps:'12',rest:45,muscle:'Lower Back',tags:['isolation'],tip:'Lift arms and legs together'},
      {id:'hp13',name:'Pull-ups',emoji:'⬆️',sets:4,reps:'8',rest:120,muscle:'Lats',tags:['compound'],tip:'Full dead hang to chin over bar'},
      {id:'hp14',name:'Renegade Row',emoji:'💪',sets:3,reps:'10 each',rest:75,muscle:'Back/Core',tags:['compound'],tip:'In push-up position, row each arm'},
    ]},
    {muscle:'Core',icon:'🔥',slots:[
      {id:'hp15',name:'Plank',emoji:'🏄',sets:3,reps:'45 sec',rest:45,muscle:'Core',tags:['compound'],tip:'Keep hips level, breathe steadily'},
      {id:'hp16',name:'Mountain Climbers',emoji:'🏔️',sets:3,reps:'30 sec',rest:45,muscle:'Core/Cardio',tags:['compound'],tip:'Drive knees fast to chest'},
    ]},
  ]},
  {day:'Fri',label:'Full Body',emoji:'⚡',rest:false,groups:[
    {muscle:'Full Body',icon:'⚡',slots:[
      {id:'hp17',name:'Burpees',emoji:'🔥',sets:3,reps:'10',rest:60,muscle:'Full Body',tags:['compound'],tip:'Chest to floor, explosive jump'},
      {id:'hp18',name:'Push-up to T',emoji:'💪',sets:3,reps:'10',rest:60,muscle:'Chest/Core',tags:['compound'],tip:'Push up, rotate to side plank'},
      {id:'hp19',name:'High Knees',emoji:'🏃',sets:3,reps:'30 sec',rest:30,muscle:'Cardio/Core',tags:['compound'],tip:'Drive knees to hip height'},
      {id:'hp20',name:'Pike Push-ups',emoji:'⬆️',sets:3,reps:'10',rest:60,muscle:'Shoulders',tags:['compound'],tip:'Hips high, lower head to floor'},
    ]},
  ]},
  {day:'Sat',label:'Active Rest',emoji:'🧘',rest:true,groups:[]},
  {day:'Sun',label:'Rest Day',emoji:'😴',rest:true,groups:[]},
];

// ═══════ FOOD DATA ═══════
const FOODS={
  breakfast:[
    {id:'f1',name:'Firfir with Egg',amharic:'ፍርፍር ከእንቁላል',emoji:'🍳',kcal:380,protein:22,carbs:42,fat:12,vegan:false,oil:'medium',tag:'high_protein'},
    {id:'f2',name:'Genfo (Barley Porridge)',amharic:'ገንፎ',emoji:'🥣',kcal:310,protein:10,carbs:58,fat:7,vegan:true,oil:'low',tag:'vegan'},
    {id:'f3',name:'Injera with Honey',amharic:'ኢንጀራ ከማር',emoji:'🫓',kcal:290,protein:8,carbs:62,fat:3,vegan:true,oil:'low',tag:'vegan'},
    {id:'f4',name:'Egg Scramble & Tomato',amharic:'እንቁላል ፉርፉር',emoji:'🍅',kcal:340,protein:24,carbs:14,fat:18,vegan:false,oil:'medium',tag:'high_protein'},
    {id:'f5',name:'Kita with Butter',amharic:'ቂጣ ከቅቤ',emoji:'🫓',kcal:420,protein:11,carbs:68,fat:13,vegan:false,oil:'low',tag:''},
  ],
  lunch:[
    {id:'l1',name:'Misir Wot with Injera',amharic:'ምስር ወጥ',emoji:'🫘',kcal:480,protein:22,carbs:78,fat:9,vegan:true,oil:'medium',tag:'vegan'},
    {id:'l2',name:'Tibs (Sautéed Beef)',amharic:'ጥብስ',emoji:'🥩',kcal:520,protein:42,carbs:12,fat:28,vegan:false,oil:'high',tag:'high_protein'},
    {id:'l3',name:'Shiro Wot with Injera',amharic:'ሽሮ ወጥ',emoji:'🍲',kcal:440,protein:20,carbs:72,fat:8,vegan:true,oil:'medium',tag:'vegan'},
    {id:'l4',name:'Gomen (Collard Greens)',amharic:'ጎመን',emoji:'🥬',kcal:280,protein:12,carbs:32,fat:11,vegan:true,oil:'low',tag:'low_carb'},
    {id:'l5',name:'Doro Wot with Rice',amharic:'ዶሮ ወጥ',emoji:'🍗',kcal:560,protein:48,carbs:52,fat:18,vegan:false,oil:'medium',tag:'high_protein'},
    {id:'l6',name:'Ayib Fresh Cheese Salad',amharic:'አይብ ሰላጣ',emoji:'🧀',kcal:320,protein:18,carbs:14,fat:20,vegan:false,oil:'low',tag:'low_carb'},
  ],
  dinner:[
    {id:'d1',name:'Lentil Soup (Messer)',amharic:'ምስር ሾርባ',emoji:'🍵',kcal:360,protein:18,carbs:55,fat:6,vegan:true,oil:'low',tag:'vegan'},
    {id:'d2',name:'Lamb Tibs with Injera',amharic:'የበግ ጥብስ',emoji:'🍖',kcal:500,protein:38,carbs:42,fat:22,vegan:false,oil:'high',tag:'high_protein'},
    {id:'d3',name:'Atkilt Wot (Veggie Stew)',amharic:'አትክልት ወጥ',emoji:'🥕',kcal:310,protein:10,carbs:48,fat:8,vegan:true,oil:'medium',tag:'vegan'},
    {id:'d4',name:'Firfir with Berbere',amharic:'ፍርፍር ከበርበሬ',emoji:'🌶️',kcal:390,protein:14,carbs:62,fat:9,vegan:true,oil:'medium',tag:'vegan'},
    {id:'d5',name:'Grilled Chicken & Salad',amharic:'የተጠበሰ ዶሮ',emoji:'🍗',kcal:420,protein:44,carbs:18,fat:16,vegan:false,oil:'low',tag:'high_protein'},
  ],
  snack:[
    {id:'s1',name:'Roasted Chickpeas (Kolo)',amharic:'ቆሎ',emoji:'🫘',kcal:180,protein:9,carbs:28,fat:4,vegan:true,oil:'low',tag:'vegan'},
    {id:'s2',name:'Banana & Groundnuts',amharic:'ሙዝ ከኦቾሎኒ',emoji:'🍌',kcal:210,protein:6,carbs:32,fat:8,vegan:true,oil:'low',tag:'vegan'},
    {id:'s3',name:'Ayib with Honey',amharic:'አይብ ከማር',emoji:'🍯',kcal:190,protein:10,carbs:22,fat:7,vegan:false,oil:'low',tag:''},
    {id:'s4',name:'Boiled Eggs x2',amharic:'የተቀቀለ እንቁላል',emoji:'🥚',kcal:140,protein:12,carbs:1,fat:10,vegan:false,oil:'low',tag:'high_protein'},
  ]
};

// ═══════ STATE ═══════
const PLANS={basic:{name:'🌱 Basic',monthly:199,yearly:139},standard:{name:'🔥 Standard',monthly:349,yearly:244},premium:{name:'👑 Premium',monthly:499,yearly:349}};
let billingCycle='monthly',selectedPlanKey='standard',selectedPMKey='telebirr';
let workoutMode='gym',selectedDay=0;
let currentPlan={breakfast:null,lunch:null,dinner:null,snack:null};
let ateStatus={},liveExercises={},doneExercises={};
let mealSwapSlot=null,mealSwapFilter='all',swapCtx=null;
const WEIGHT_DATA=[74.2,73.8,73.5,73.1,72.8,72.4,72.0];
const WEIGHT_WEEKS=['W1','W2','W3','W4','W5','W6','W7'];

// ═══════ NAVIGATION ═══════
function goTo(id){document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));document.getElementById(id).classList.add('active');window.scrollTo(0,0);}
function switchTab(name,el){document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));document.querySelectorAll('.tab-content').forEach(c=>c.classList.remove('active'));el.classList.add('active');document.getElementById('tab-'+name).classList.add('active');}
function selectChip(el){el.closest('.chip-group').querySelectorAll('.chip').forEach(c=>c.classList.remove('selected'));el.classList.add('selected');}
function tryLogin(){const s=localStorage.getItem('hf_user');if(s){try{const u=JSON.parse(s);restoreUser(u);goTo('screen-app');}catch(e){showToast('No saved account found');}}else{showToast('No account found — please subscribe first');}}

// ═══════ PRICING ═══════
function setBilling(c){billingCycle=c;document.getElementById('btn-monthly').classList.toggle('active',c==='monthly');document.getElementById('btn-yearly').classList.toggle('active',c==='yearly');updatePrices();}
function updatePrices(){Object.keys(PLANS).forEach(k=>{const p=PLANS[k],isY=billingCycle==='yearly',price=isY?p.yearly:p.monthly;document.getElementById('price-'+k).innerHTML=price+' <span>ETB/mo</span>';const o=document.getElementById('orig-'+k);if(isY){o.textContent=p.monthly+' ETB';o.style.display='block';}else{o.style.display='none';}});}
function selectPlan(k){selectedPlanKey=k;const p=PLANS[k],price=billingCycle==='yearly'?p.yearly:p.monthly,total=billingCycle==='yearly'?p.yearly*12:p.monthly;document.getElementById('sum-plan').textContent=p.name;document.getElementById('sum-billing').textContent=billingCycle==='yearly'?'Yearly':'Monthly';document.getElementById('sum-duration').textContent=billingCycle==='yearly'?'12 months':'1 month';document.getElementById('sum-total').textContent=total+' ETB';document.getElementById('pay-btn-text').textContent='Pay '+total+' ETB — Start Now';goTo('screen-checkout');}
function toggleFaq(el){el.classList.toggle('open');}

// ═══════ CHECKOUT ═══════
function selectPM(pm){selectedPMKey=pm;['telebirr','bank','whatsapp'].forEach(k=>{document.getElementById('pm-'+k).classList.remove('selected');document.getElementById('ext-'+k)&&document.getElementById('ext-'+k).classList.remove('show');});document.getElementById('pm-'+pm).classList.add('selected');const ext=document.getElementById('ext-'+pm);if(ext)ext.classList.add('show');}
function processPayment(){
  const name=document.getElementById('co-name').value.trim();
  const phone=document.getElementById('co-phone').value.trim();
  if(!name){showToast('⚠️ Please enter your name');return;}
  if(!phone){showToast('⚠️ Please enter your phone number');return;}
  if(selectedPMKey==='whatsapp'){const p=PLANS[selectedPlanKey],total=billingCycle==='yearly'?p.yearly*12:p.monthly,msg=encodeURIComponent(`Hello! I want to subscribe to Habesha Fit.\n\nPlan: ${p.name}\nBilling: ${billingCycle}\nAmount: ${total} ETB\nName: ${name}\nPhone: ${phone}`);window.open(`https://wa.me/251913069216?text=${msg}`,'_blank');return;}
  const p=PLANS[selectedPlanKey],total=billingCycle==='yearly'?p.yearly*12:p.monthly;
  document.getElementById('suc-plan').textContent=p.name;
  document.getElementById('suc-phone').textContent=phone;
  document.getElementById('suc-amount').textContent=total+' ETB';
  localStorage.setItem('hf_subscription',JSON.stringify({plan:selectedPlanKey,planName:p.name,billing:billingCycle,total,phone,name,date:new Date().toISOString()}));
  goTo('screen-success');
}

// ═══════ BUILD PLAN ═══════
function buildPlan(){
  const name=document.getElementById('inp-name').value||'Friend';
  const weight=parseFloat(document.getElementById('inp-weight').value)||70;
  const height=parseFloat(document.getElementById('inp-height').value)||165;
  const age=parseFloat(document.getElementById('inp-age').value)||28;
  const sex=document.getElementById('inp-sex').value;
  const activity=parseFloat(document.getElementById('inp-activity').value);
  const goal=document.getElementById('inp-goal').value;
  let bmr=sex==='male'?10*weight+6.25*height-5*age+5:10*weight+6.25*height-5*age-161;
  let tdee=Math.round(bmr*activity);
  if(goal==='fat_loss')tdee-=400;if(goal==='muscle')tdee+=250;
  const protein=Math.round(weight*1.8),fat=Math.round(tdee*.25/9),carbs=Math.round((tdee-protein*4-fat*9)/4);
  const sub=JSON.parse(localStorage.getItem('hf_subscription')||'{}');
  const planName=sub.planName||'🔥 Standard Plan';
  localStorage.setItem('hf_user',JSON.stringify({name,weight,height,age,sex,activity,goal,tdee,protein,fat,carbs,planName}));
  restoreUser({name,tdee,protein,fat,carbs,planName});
  currentPlan.breakfast=randFrom(FOODS.breakfast);currentPlan.lunch=randFrom(FOODS.lunch);currentPlan.dinner=randFrom(FOODS.dinner);currentPlan.snack=randFrom(FOODS.snack);ateStatus={};
  document.getElementById('today-date').textContent=new Date().toLocaleDateString('en-US',{weekday:'long',month:'long',day:'numeric'});
  renderMeals();setWorkoutMode('gym');renderWeightChart();goTo('screen-app');
}
function restoreUser(u){
  document.getElementById('display-name').textContent=u.name;
  document.getElementById('display-cal').textContent=(u.tdee||1680).toLocaleString();
  document.getElementById('display-protein').textContent=(u.protein||126)+'g';
  document.getElementById('display-carbs').textContent=(u.carbs||189)+'g';
  document.getElementById('display-fat').textContent=(u.fat||47)+'g';
  document.getElementById('display-plan').textContent=u.planName||'🔥 Standard Plan';
  const h=new Date().getHours();
  document.getElementById('greeting').textContent=h<12?'Good morning,':h<17?'Good afternoon,':'Good evening,';
}
function randFrom(arr){return arr[Math.floor(Math.random()*arr.length)];}

// ═══════ MEALS ═══════
const SLOT_LABELS={breakfast:'Breakfast',lunch:'Lunch',dinner:'Dinner',snack:'Snack'};
function renderMeals(){
  const c=document.getElementById('meal-slots');c.innerHTML='';
  ['breakfast','lunch','dinner','snack'].forEach(slot=>{
    const meal=currentPlan[slot],ate=ateStatus[slot];
    const div=document.createElement('div');div.className='meal-slot';
    div.innerHTML=`<div class="slot-label">${SLOT_LABELS[slot]}</div>
      <div class="meal-card" style="${ate?'opacity:.6':''}">
        <div class="meal-emoji">${meal.emoji}</div>
        <div class="meal-info">
          <div class="meal-name">${meal.name}</div><div class="meal-name-am">${meal.amharic}</div>
          <div class="meal-meta">
            <span class="badge badge-cal">${meal.kcal} kcal</span>
            <span class="badge badge-protein">${meal.protein}g prot</span>
            ${meal.vegan?'<span class="badge badge-vegan">Vegan</span>':''}
            <span class="badge ${meal.oil==='low'?'badge-oil-low':'badge-oil-high'}">${meal.oil==='low'?'🟢 Low':meal.oil==='medium'?'🟡 Med':'🔴 High'} oil</span>
          </div>
        </div>
        <div class="meal-actions">
          <button class="btn-swap-m" onclick="openMealModal('${slot}')">🔄 Swap</button>
          <button class="btn-ate ${ate?'done':''}" onclick="markAte('${slot}')">${ate?'✓ Ate':'+ Log'}</button>
        </div>
      </div>`;
    c.appendChild(div);
  });
}
function markAte(slot){ateStatus[slot]=!ateStatus[slot];renderMeals();if(ateStatus[slot])showToast('✓ Meal logged!');}
function openMealModal(slot){mealSwapSlot=slot;mealSwapFilter='all';document.getElementById('meal-modal-sub').textContent='Swapping: '+currentPlan[slot].name;document.querySelectorAll('.filter-chip').forEach(c=>c.classList.remove('active'));document.querySelectorAll('.filter-chip')[0].classList.add('active');renderMealSwapOpts();document.getElementById('meal-modal').classList.add('open');}
function closeMealModal(){document.getElementById('meal-modal').classList.remove('open');}
function setMealFilter(f,el){mealSwapFilter=f;document.querySelectorAll('.filter-chip').forEach(c=>c.classList.remove('active'));el.classList.add('active');renderMealSwapOpts();}
function renderMealSwapOpts(){
  const cur=currentPlan[mealSwapSlot];let pool=FOODS[mealSwapSlot].filter(f=>f.id!==cur.id);
  if(mealSwapFilter==='vegan')pool=pool.filter(f=>f.vegan);
  else if(mealSwapFilter==='high_protein')pool=pool.filter(f=>f.tag==='high_protein');
  else if(mealSwapFilter==='low_carb')pool=pool.filter(f=>f.tag==='low_carb');
  const c=document.getElementById('meal-swap-options');c.innerHTML='';
  if(!pool.length){c.innerHTML='<p style="text-align:center;color:#999;padding:20px">No options for this filter</p>';return;}
  pool.forEach((food,i)=>{
    const calDiff=food.kcal-cur.kcal,protDiff=food.protein-cur.protein;
    const wrap=document.createElement('div');wrap.className='swap-opt-wrap';
    wrap.innerHTML=`${i===0?'<span class="swap-best-badge">⭐ Best Match</span>':''}
      <div class="swap-opt ${i===0?'best':''}" onclick="confirmMealSwap('${food.id}')">
        <div style="font-size:28px">${food.emoji}</div>
        <div style="flex:1"><div style="font-weight:700;font-size:14px">${food.name}</div><div style="font-size:11px;color:#999">${food.amharic}</div>
          <div class="meal-meta" style="margin-top:4px"><span class="badge badge-cal">${food.kcal} kcal</span><span class="badge badge-protein">${food.protein}g</span>${food.vegan?'<span class="badge badge-vegan">Vegan</span>':''}</div>
        </div>
        <div style="text-align:right;flex-shrink:0"><div class="swap-diff ${calDiff<=0?'diff-green':'diff-red'}">${calDiff>0?'+':''}${calDiff} kcal</div><div class="swap-diff ${protDiff>=0?'diff-green':'diff-red'}" style="margin-top:2px">${protDiff>0?'+':''}${protDiff}g</div></div>
      </div>`;
    c.appendChild(wrap);
  });
}
function confirmMealSwap(id){currentPlan[mealSwapSlot]=FOODS[mealSwapSlot].find(f=>f.id===id);closeMealModal();renderMeals();showToast('✓ Swapped to '+currentPlan[mealSwapSlot].name+'!');}

// ═══════ WORKOUT ═══════
function getPlan(){return workoutMode==='gym'?GYM_PLAN:HOME_PLAN;}
function setWorkoutMode(mode){workoutMode=mode;document.getElementById('btn-home').classList.toggle('active',mode==='home');document.getElementById('btn-gym').classList.toggle('active',mode==='gym');document.getElementById('workout-subtitle').textContent=mode==='gym'?'Gym Split · 5 Days':'Home Workout · No Equipment';liveExercises={};doneExercises={};renderWorkout();}
function getMusclePool(m){const ml=m.toLowerCase();if(ml.includes('back'))return 'back';if(ml.includes('chest'))return 'chest';if(ml.includes('shoulder')||ml.includes('delt'))return 'shoulder';if(ml.includes('tricep'))return 'triceps';if(ml.includes('bicep'))return 'biceps';if(ml.includes('forearm'))return 'forearm';if(ml.includes('quad'))return 'quad';if(ml.includes('hamstring'))return 'hamstring';if(ml.includes('calf')||ml.includes('calves'))return 'calf';return 'back';}
function findExById(id){for(const pool of Object.values(EX)){const f=pool.find(e=>e.id===id);if(f)return f;}return null;}
function renderWorkout(){
  const plan=getPlan();
  const sel=document.getElementById('day-selector');sel.innerHTML='';
  plan.forEach((w,i)=>{const btn=document.createElement('div');btn.className=`day-btn ${w.rest?'rest-day':''} ${i===selectedDay?'active':''}`;btn.innerHTML=`<div class="day-name">${w.day}</div><div class="day-num">${w.emoji}</div><div class="day-tag">${w.rest?'Rest':w.groups.length+' grp'}</div>`;btn.onclick=()=>{selectedDay=i;renderWorkout();};sel.appendChild(btn);});
  const content=document.getElementById('workout-content');const w=plan[selectedDay];
  if(w.rest){content.innerHTML=`<div class="rest-day-card"><div class="rest-emoji">${w.emoji}</div><h3>${w.label}</h3><p>Rest is where muscles grow. Stay hydrated, eat your protein, and come back stronger! 💪</p></div>`;return;}
  const totalEx=w.groups.reduce((s,g)=>s+g.slots.length,0);
  const doneCnt=Object.keys(doneExercises).filter(k=>k.startsWith(selectedDay+'_')&&doneExercises[k]).length;
  content.innerHTML=`<div class="workout-summary"><div class="summary-item"><div class="summary-val">${w.groups.length}</div><div class="summary-lbl">Muscle Groups</div></div><div class="summary-item"><div class="summary-val">${totalEx}</div><div class="summary-lbl">Exercises</div></div><div class="summary-item"><div class="summary-val">${doneCnt}/${totalEx}</div><div class="summary-lbl">Done</div></div></div>`;
  w.groups.forEach((group,gi)=>{
    const sec=document.createElement('div');sec.className='muscle-section';
    sec.innerHTML=`<div class="muscle-header"><div class="muscle-icon">${group.icon||'💪'}</div><div><div class="muscle-name">${group.muscle}</div><div class="muscle-count">${group.slots.length} exercise${group.slots.length>1?'s':''}</div></div></div>`;
    group.slots.forEach((slot,si)=>{
      const key=`${selectedDay}_${gi}_${si}`;
      let ex=liveExercises[key]||(typeof slot==='string'?findExById(slot):slot);
      if(!ex)return;
      const isDone=doneExercises[key];
      const card=document.createElement('div');card.className=`exercise-card ${isDone?'done':''}`;
      const tagHtml=(ex.tags||[]).map(t=>`<span class="ex-tag ${t}">${t}</span>`).join('');
      card.innerHTML=`<div class="exercise-card-top"><div class="ex-num">${si+1}</div><div class="ex-body"><div class="ex-name-big">${ex.emoji||'💪'} ${ex.name}</div><div class="ex-muscle-tag">${ex.muscle}</div><div class="ex-details"><span class="ex-badge sets">🔁 ${ex.sets} sets</span><span class="ex-badge reps">× ${ex.reps}</span><span class="ex-badge rest-b">⏱ ${ex.rest}s</span></div>${ex.tip?`<div style="font-size:11px;color:#999;margin-top:6px;font-style:italic">💡 ${ex.tip}</div>`:''}<div style="display:flex;gap:6px;margin-top:8px;flex-wrap:wrap">${tagHtml}</div></div></div><div class="ex-btn-row"><button class="btn-swap-ex" onclick="openExModal(${selectedDay},${gi},${si},'${getMusclePool(group.muscle)}')">🔀 Swap</button><button class="btn-done-ex ${isDone?'checked':''}" onclick="toggleDone('${key}')">${isDone?'✓ Done':'Mark Done'}</button></div>`;
      sec.appendChild(card);
    });
    content.appendChild(sec);
  });
}
function toggleDone(key){doneExercises[key]=!doneExercises[key];renderWorkout();if(doneExercises[key])showToast('✓ Exercise logged!');}
function openExModal(dayIdx,gi,si,poolKey){
  swapCtx={dayIdx,gi,si,poolKey};
  const plan=getPlan(),group=plan[dayIdx].groups[gi],key=`${dayIdx}_${gi}_${si}`,slot=group.slots[si];
  const cur=liveExercises[key]||(typeof slot==='string'?findExById(slot):slot);
  document.getElementById('ex-modal-sub').textContent='Replacing: '+(cur?cur.name:'exercise');
  const pool=EX_POOLS[poolKey]||[];const c=document.getElementById('ex-swap-options');c.innerHTML='';
  pool.forEach(ex=>{
    const isCur=cur&&ex.id===cur.id;const div=document.createElement('div');div.className=`ex-swap-opt ${isCur?'current-ex':''}`;
    const tagHtml=(ex.tags||[]).map(t=>`<span class="ex-tag ${t}">${t}</span>`).join('');
    div.innerHTML=`<div class="ex-swap-icon">${ex.emoji||'💪'}</div><div style="flex:1"><div class="ex-swap-name">${ex.name}${isCur?'<span class="current-badge">Current</span>':''}</div><div class="ex-swap-detail">${ex.sets} sets × ${ex.reps} · ${ex.rest}s rest</div><div class="ex-swap-detail">${ex.muscle}</div>${ex.tip?`<div class="ex-swap-tip">💡 ${ex.tip}</div>`:''}<div style="display:flex;gap:6px;margin-top:6px;flex-wrap:wrap">${tagHtml}</div></div>`;
    if(!isCur)div.onclick=()=>confirmExSwap(ex);
    c.appendChild(div);
  });
  document.getElementById('ex-modal').classList.add('open');
}
function confirmExSwap(ex){if(!swapCtx)return;liveExercises[`${swapCtx.dayIdx}_${swapCtx.gi}_${swapCtx.si}`]=ex;closeExModal();renderWorkout();showToast('✓ Swapped to '+ex.name+'!');}
function closeExModal(){document.getElementById('ex-modal').classList.remove('open');swapCtx=null;}

// ═══════ PROGRESS ═══════
function renderWeightChart(){
  const max=Math.max(...WEIGHT_DATA),min=Math.min(...WEIGHT_DATA),range=max-min||1;
  const chart=document.getElementById('weight-chart');chart.innerHTML='';
  WEIGHT_DATA.forEach((w,i)=>{const h=((w-min)/range*55+18),isLast=i===WEIGHT_DATA.length-1;const wrap=document.createElement('div');wrap.className='chart-bar-wrap';wrap.innerHTML=`<div class="chart-val">${w}</div><div class="chart-bar ${isLast?'highlight':''}" style="height:${h}px"></div><div class="chart-week">${WEIGHT_WEEKS[i]}</div>`;chart.appendChild(wrap);});
}
function setStars(n){document.querySelectorAll('.star').forEach((s,i)=>s.classList.toggle('lit',i<n));}
function logCheckin(){const w=document.getElementById('checkin-weight').value;document.getElementById('prog-weight').innerHTML=w+'<span class="stat-unit">kg</span>';localStorage.setItem('hf_weight',w);showToast('✓ Check-in saved! Weight: '+w+'kg');}

// ═══════ SHARE ═══════
function shareApp(){if(navigator.share){navigator.share({title:'Habesha Fit 🇪🇹',text:'Ethiopian fitness app with real meal plans!',url:window.location.href});}else{navigator.clipboard&&navigator.clipboard.writeText(window.location.href);showToast('✓ Link copied! Share with friends');}}

// ═══════ TOAST ═══════
function showToast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),2500);}

// ═══════ CLOSE MODALS ═══════
document.getElementById('meal-modal').addEventListener('click',function(e){if(e.target===this)closeMealModal();});
document.getElementById('ex-modal').addEventListener('click',function(e){if(e.target===this)closeExModal();});

// ═══════ INIT ═══════
const dayMap={0:6,1:0,2:1,3:2,4:3,5:4,6:5};
selectedDay=dayMap[new Date().getDay()];
// Return existing user directly to app
const savedUser=localStorage.getItem('hf_user');
if(savedUser){try{const u=JSON.parse(savedUser);restoreUser(u);currentPlan.breakfast=randFrom(FOODS.breakfast);currentPlan.lunch=randFrom(FOODS.lunch);currentPlan.dinner=randFrom(FOODS.dinner);currentPlan.snack=randFrom(FOODS.snack);document.getElementById('today-date').textContent=new Date().toLocaleDateString('en-US',{weekday:'long',month:'long',day:'numeric'});renderMeals();setWorkoutMode('gym');renderWeightChart();goTo('screen-app');}catch(e){}}
</script>
</body>
</html>
