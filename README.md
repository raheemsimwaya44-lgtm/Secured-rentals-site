# Secured-rentals-site
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="description" content="Secured Rentals: charger plates, dinnerware and glassware for weddings and events in Clarence-Rockland, Ontario.">
<title>Secured Rentals</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:ital,opsz,wght@0,6..96,400..700;1,6..96,400..700&family=Instrument+Sans:wght@400..700&display=swap" rel="stylesheet">
<style>
/* Layout: type-led hero beside a top-down round banquet table; a green "tablecloth" band holds the booking tool. */
:root{
  --bg:#EDEFEA;
  --surface:#F6F7F3;
  --ink:#17231F;
  --muted:#51615A;
  --line:#C8D0C7;
  --accent:#8A6420;
  --brass:#C29A45;
  --brass-deep:#9C772B;
  --brass-ink:#17231F;
  --cloth:#1F3B31;
  --cloth-edge:rgba(255,255,255,.14);
  --on-cloth:#F1F3EE;
  --on-cloth-muted:#BCC9C1;
  --field-bg:rgba(255,255,255,.07);
  --field-edge:rgba(255,255,255,.3);
  --plate:#F4F2EA;
  --plate-shade:#D6D2C4;
  --glass:rgba(255,255,255,.16);
  --glass-edge:rgba(255,255,255,.62);
  --shadow:rgba(23,35,31,.16);
  --btn-bg:#1F3B31;
  --btn-fg:#F4F2EA;
  --focus:#8A6420;
  --font-display:'Bodoni Moda','Bodoni 72',Didot,Georgia,serif;
  --font-body:'Instrument Sans',system-ui,-apple-system,'Segoe UI',Roboto,sans-serif;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --bg:#0E1512;
    --surface:#141D19;
    --ink:#E8EDE8;
    --muted:#9DAEA4;
    --line:#27342D;
    --accent:#D6AF5E;
    --cloth:#1C382E;
    --shadow:rgba(0,0,0,.45);
    --btn-bg:#D0A94F;
    --btn-fg:#14201B;
    --focus:#D6AF5E;
    color-scheme:dark;
  }
}
:root[data-theme="dark"]{
  --bg:#0E1512;
  --surface:#141D19;
  --ink:#E8EDE8;
  --muted:#9DAEA4;
  --line:#27342D;
  --accent:#D6AF5E;
  --cloth:#1C382E;
  --shadow:rgba(0,0,0,.45);
  --btn-bg:#D0A94F;
  --btn-fg:#14201B;
  --focus:#D6AF5E;
  color-scheme:dark;
}

html{color-scheme:light}
body{margin:0}
[hidden]{display:none!important}
*,*::before,*::after{box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  background:var(--bg);
  color:var(--ink);
  font:400 17px/1.6 var(--font-body);
  -webkit-font-smoothing:antialiased;
}
h1,h2,h3,p,ul,ol,dl,dd,figure,blockquote{margin:0}
ul,ol{padding:0;list-style:none}
a{color:inherit;text-underline-offset:3px}
:focus-visible{outline:2px solid var(--focus);outline-offset:3px}

.wrap{
  width:100%;
  max-width:1160px;
  margin-inline:auto;
  padding-left:max(clamp(16px,4vw,40px),env(safe-area-inset-left,0px));
  padding-right:max(clamp(16px,4vw,40px),env(safe-area-inset-right,0px));
}

/* type */
.eyebrow{
  font-size:.78rem;font-weight:600;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);
}
h1,h2,h3{font-family:var(--font-display);font-weight:500;text-wrap:balance;letter-spacing:-.015em}
h1{font-size:clamp(2.6rem,6.2vw,4.9rem);line-height:1.02;letter-spacing:-.025em}
h1 em{font-style:italic;color:var(--accent)}
h2{font-size:clamp(1.9rem,3.8vw,2.9rem);line-height:1.1}
h3{font-size:1.5rem;line-height:1.2}
.lede{font-size:1.15rem;color:var(--muted);max-width:34em}

/* buttons */
.btn{
  display:inline-flex;align-items:center;justify-content:center;
  min-height:48px;padding:0 24px;border-radius:2px;
  font:600 .98rem/1 var(--font-body);text-decoration:none;cursor:pointer;
  border:1.5px solid transparent;
  transition:background-color .15s,color .15s,filter .15s;
}
.btn-primary{background:var(--btn-bg);color:var(--btn-fg)}
.btn-primary:hover{filter:brightness(1.12)}
.btn-ghost{border-color:var(--ink);color:var(--ink);background:transparent}
.btn-ghost:hover{background:var(--ink);color:var(--bg)}
.btn-brass{background:var(--brass);color:var(--brass-ink)}
.btn-brass:hover{filter:brightness(1.08)}

/* header */
.head-row{display:flex;align-items:center;justify-content:space-between;gap:24px;padding-block:18px}
.brand{display:flex;align-items:center;gap:10px;text-decoration:none;font:600 1.3rem/1 var(--font-display);letter-spacing:-.01em}
.brand svg{width:30px;height:30px;flex:none}
.nav{display:flex;gap:28px;font-size:.95rem;font-weight:500}
.nav a{text-decoration:none;color:var(--muted)}
.nav a:hover{color:var(--ink)}
.call{min-height:42px;padding:0 18px;font-size:.92rem}

/* hero */
.hero{padding-block:clamp(28px,5vw,64px) clamp(56px,9vw,104px)}
.hero-grid{display:grid;grid-template-columns:minmax(0,1.05fr) minmax(0,.95fr);gap:clamp(32px,5vw,72px);align-items:center}
.hero-copy{display:flex;flex-direction:column;align-items:flex-start;gap:24px;min-width:0}
.cta-row{display:flex;flex-wrap:wrap;gap:12px}
.proof{display:flex;flex-wrap:wrap;align-items:center;gap:10px;color:var(--muted);font-size:.95rem}
.proof strong{color:var(--ink)}
.stars{display:inline-flex;gap:2px}
.star{width:18px;height:18px;fill:var(--accent)}
.table-fig{min-width:0}
.table-fig svg{display:block;width:100%;height:auto}
.table-fig figcaption{margin-top:12px;font-size:.88rem;color:var(--muted);text-align:center}

/* svg parts */
.c-shadow{fill:var(--shadow)}
.c-cloth{fill:var(--cloth)}
.s-cloth-edge{fill:none;stroke:var(--cloth-edge)}
.c-brass{fill:var(--brass)}
.c-brass-deep{fill:var(--brass-deep)}
.s-brass-deep{fill:none;stroke:var(--brass-deep)}
.c-plate{fill:var(--plate)}
.s-plate-shade{fill:none;stroke:var(--plate-shade)}
.c-glass{fill:var(--glass);stroke:var(--glass-edge)}
.s-glass{fill:none;stroke:var(--glass-edge)}
.c-glass-hi{fill:var(--glass-edge)}

/* bands */
.band{padding-block:clamp(56px,9vw,104px)}
.band-alt{background:var(--surface)}
.sec-head{display:flex;flex-direction:column;gap:14px;margin-bottom:clamp(32px,5vw,56px)}
.sec-lede{color:var(--muted);max-width:52ch}

/* rentals */
.layers{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:clamp(28px,4vw,56px)}
.layers li{display:flex;flex-direction:column;gap:14px;min-width:0}
.motif{width:96px;height:96px;flex:none}
.layers p{color:var(--muted);max-width:30ch}

/* reviews */
.reviews-grid{display:grid;grid-template-columns:minmax(0,.7fr) minmax(0,2fr);gap:clamp(32px,6vw,88px);align-items:start}
.rating{display:flex;flex-direction:column;gap:10px}
.score{font:500 clamp(4.5rem,10vw,7.5rem)/1 var(--font-display);letter-spacing:-.03em;font-variant-numeric:lining-nums}
.rating .stars .star{width:22px;height:22px}
.rating .count{color:var(--muted)}
.quotes{display:flex;flex-direction:column;gap:clamp(28px,4vw,48px);min-width:0}
.quote blockquote p{line-height:1.5}
.quote figcaption{margin-top:14px;font-size:.82rem;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--muted)}
.quote-lead blockquote p{font:400 clamp(1.35rem,2.5vw,1.95rem)/1.4 var(--font-display)}
.quote-pair{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:clamp(24px,4vw,48px);padding-top:clamp(28px,4vw,48px);border-top:1px solid var(--line)}

/* plan */
.plan{
  background:var(--cloth);color:var(--on-cloth);color-scheme:dark;
  padding-block:clamp(56px,9vw,104px);
  --focus:var(--brass);
}
.plan .eyebrow{color:var(--on-cloth-muted)}
.plan-grid{display:grid;grid-template-columns:minmax(0,.85fr) minmax(0,1.15fr);gap:clamp(32px,6vw,88px);align-items:start}
.plan-copy{display:flex;flex-direction:column;gap:18px;min-width:0}
.steps{counter-reset:s;display:flex;flex-direction:column;gap:22px;margin-top:10px}
.steps li{counter-increment:s;display:grid;grid-template-columns:2.4rem minmax(0,1fr);gap:4px 12px}
.steps li::before{
  content:counter(s);grid-row:span 2;
  font:500 2.2rem/1 var(--font-display);color:var(--brass);
}
.steps strong{font-weight:600}
.steps span{color:var(--on-cloth-muted)}

.tool{
  display:flex;flex-direction:column;gap:18px;min-width:0;
  padding:clamp(20px,3vw,32px);
  border:1px solid var(--cloth-edge);background:rgba(255,255,255,.045);
}
.field{display:flex;flex-direction:column;gap:7px;min-width:0;border:0;padding:0;margin:0}
.field label,.field legend{font-size:.88rem;font-weight:600;padding:0}
.field-row{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:18px}
.tool input[type="text"],.tool input[type="date"],.tool input[type="number"],.tool textarea{
  width:100%;min-height:46px;padding:10px 12px;
  font:400 16px/1.5 var(--font-body);color:var(--on-cloth);
  background:var(--field-bg);border:1px solid var(--field-edge);border-radius:2px;
}
.tool textarea{resize:vertical}
.tool ::placeholder{color:var(--on-cloth-muted);opacity:.8}
.checks{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:2px 16px}
.checks label{display:flex;align-items:center;gap:10px;min-height:44px;font-weight:400;font-size:1rem;cursor:pointer}
.checks input{width:18px;height:18px;accent-color:var(--brass);flex:none}
#f-out{background:rgba(0,0,0,.22);line-height:1.55}
.out-actions{display:flex;flex-wrap:wrap;align-items:center;gap:14px}
.status{font-size:.9rem;color:var(--on-cloth-muted);min-width:0}
.hint{font-size:.9rem;color:var(--on-cloth-muted)}

/* find us */
.find-grid{display:grid;grid-template-columns:minmax(0,1fr) minmax(0,1.3fr);gap:clamp(32px,6vw,88px);align-items:start}
.find-head{display:flex;flex-direction:column;gap:14px}
.find-body{display:flex;flex-direction:column;gap:28px;min-width:0}
.details>div{display:grid;grid-template-columns:6.5rem minmax(0,1fr);gap:16px;padding:16px 0;border-top:1px solid var(--line)}
.details>div:last-child{border-bottom:1px solid var(--line)}
.details dt{font-size:.78rem;font-weight:600;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);padding-top:.3em}
.details dd{min-width:0;overflow-wrap:anywhere}
.link-btn{
  margin-left:10px;padding:2px 0;border:0;background:none;cursor:pointer;
  font:600 .88rem var(--font-body);color:var(--accent);text-decoration:underline;text-underline-offset:3px;
}
.find-body .btn{align-self:flex-start}

footer{padding-block:28px;border-top:1px solid var(--line);font-size:.9rem;color:var(--muted)}

@media (max-width:900px){
  .hero-grid,.reviews-grid,.plan-grid,.find-grid{grid-template-columns:minmax(0,1fr)}
  .table-fig{max-width:460px;margin-inline:auto;width:100%}
  .rating{flex-direction:row;flex-wrap:wrap;align-items:center;gap:6px 18px}
  .rating .eyebrow{flex-basis:100%}
}
@media (max-width:820px){.nav{display:none}}
@media (max-width:760px){
  .layers{grid-template-columns:minmax(0,1fr)}
  .quote-pair{grid-template-columns:minmax(0,1fr)}
}
@media (max-width:520px){
  .call-num{display:none}
  .field-row{grid-template-columns:minmax(0,1fr)}
  .checks{grid-template-columns:minmax(0,1fr)}
  .details>div{grid-template-columns:minmax(0,1fr);gap:4px}
}
@media (prefers-reduced-motion:reduce){
  html{scroll-behavior:auto}
  *{transition:none!important}
}
</style>
</head>
<body>
<svg width="0" height="0" style="position:absolute" aria-hidden="true" focusable="false">
  <symbol id="star" viewBox="0 0 20 20"><polygon points="10,1.5 12.6,7.2 18.8,7.8 14.1,12 15.5,18.1 10,15 4.5,18.1 5.9,12 1.2,7.8 7.4,7.2"/></symbol>
</svg>

<header>
  <div class="wrap head-row">
    <a class="brand" href="#top" aria-label="Secured Rentals, back to top">
      <svg viewBox="0 0 30 30" aria-hidden="true"><circle cx="15" cy="15" r="14" class="c-brass"/><circle cx="15" cy="15" r="11.5" class="s-brass-deep" stroke-width="1"/><circle cx="15" cy="15" r="8" class="c-plate"/></svg>
      <span>Secured Rentals</span>
    </a>
    <nav class="nav" aria-label="Sections">
      <a href="#rentals">Rentals</a>
      <a href="#reviews">Reviews</a>
      <a href="#plan">Plan a rental</a>
      <a href="#find">Find us</a>
    </nav>
    <a class="btn btn-ghost call" href="tel:+12269781275">Call<span class="call-num">&nbsp;(226) 978-1275</span></a>
  </div>
</header>

<main id="top">
  <section class="hero">
    <div class="wrap hero-grid">
      <div class="hero-copy">
        <p class="eyebrow">Party &amp; event rentals · Clarence-Rockland, Ontario</p>
        <h1>Beautiful tables, <em>delivered on time.</em></h1>
        <p class="lede">Charger plates, dinnerware and glassware for weddings and events. We deliver them clean and on schedule, then collect them after your event.</p>
        <div class="cta-row">
          <a class="btn btn-primary" href="#plan">Plan your rental</a>
          <a class="btn btn-ghost" href="tel:+12269781275">Call (226) 978-1275</a>
        </div>
        <p class="proof">
          <span class="stars" role="img" aria-label="5 out of 5 stars">
            <svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg>
          </span>
          <span><strong>5.0</strong> on Google from 4 customer reviews</span>
        </p>
      </div>

      <figure class="table-fig">
        <svg viewBox="0 0 520 520" role="img" aria-label="A round banquet table seen from above, set for six with charger plates, dinner plates and glasses">
          <defs>
            <g id="setting">
              <circle cx="260" cy="118" r="52" class="c-brass"/>
              <circle cx="260" cy="118" r="46" class="s-brass-deep" stroke-width="1.5"/>
              <circle cx="260" cy="118" r="37" class="c-plate"/>
              <circle cx="260" cy="118" r="27" class="s-plate-shade" stroke-width="2"/>
              <circle cx="320" cy="80" r="14" class="c-glass" stroke-width="1.5"/>
              <circle cx="320" cy="80" r="8" class="s-glass" stroke-width="1"/>
              <circle cx="315" cy="75" r="3" class="c-glass-hi"/>
            </g>
          </defs>
          <circle cx="260" cy="272" r="244" class="c-shadow"/>
          <circle cx="260" cy="260" r="244" class="c-cloth"/>
          <circle cx="260" cy="260" r="234" class="s-cloth-edge" stroke-width="1.5"/>
          <use href="#setting"/>
          <use href="#setting" transform="rotate(60 260 260)"/>
          <use href="#setting" transform="rotate(120 260 260)"/>
          <use href="#setting" transform="rotate(180 260 260)"/>
          <use href="#setting" transform="rotate(240 260 260)"/>
          <use href="#setting" transform="rotate(300 260 260)"/>
          <circle cx="260" cy="260" r="42" class="s-brass-deep" stroke-width="1.5" style="stroke:var(--brass)"/>
          <circle cx="260" cy="260" r="24" class="c-brass"/>
          <circle cx="260" cy="260" r="13" class="c-plate"/>
          <circle cx="260" cy="260" r="4" class="c-brass-deep"/>
        </svg>
        <figcaption>A round table for six, seen from above.</figcaption>
      </figure>
    </div>
  </section>

  <section class="band band-alt" id="rentals">
    <div class="wrap">
      <div class="sec-head">
        <p class="eyebrow">Rentals</p>
        <h2>What goes on your table</h2>
        <p class="sec-lede">These are the items customers have rented for weddings and events. If you need something else, call and ask.</p>
      </div>
      <ul class="layers">
        <li>
          <svg class="motif" viewBox="0 0 96 96" aria-hidden="true">
            <circle cx="48" cy="48" r="48" class="c-cloth"/>
            <circle cx="48" cy="48" r="34" class="c-brass"/>
            <circle cx="48" cy="48" r="29" class="s-brass-deep" stroke-width="1.5"/>
            <circle cx="48" cy="48" r="21" class="s-brass-deep" stroke-width="1"/>
          </svg>
          <h3>Charger plates</h3>
          <p>The decorative base under each dinner plate. Customers describe them as beautiful.</p>
        </li>
        <li>
          <svg class="motif" viewBox="0 0 96 96" aria-hidden="true">
            <circle cx="48" cy="48" r="48" class="c-cloth"/>
            <circle cx="48" cy="48" r="34" class="c-plate"/>
            <circle cx="48" cy="48" r="24" class="s-plate-shade" stroke-width="2"/>
          </svg>
          <h3>Dinnerware</h3>
          <p>Plates for the meal. Reviewers note that everything arrives clean.</p>
        </li>
        <li>
          <svg class="motif" viewBox="0 0 96 96" aria-hidden="true">
            <circle cx="48" cy="48" r="48" class="c-cloth"/>
            <circle cx="48" cy="48" r="26" class="c-glass" stroke-width="2"/>
            <circle cx="48" cy="48" r="17" class="s-glass" stroke-width="1.2"/>
            <circle cx="40" cy="40" r="4" class="c-glass-hi"/>
          </svg>
          <h3>Glassware</h3>
          <p>Glasses for every seat at the table, delivered with the rest of your order.</p>
        </li>
      </ul>
    </div>
  </section>

  <section class="band" id="reviews">
    <div class="wrap reviews-grid">
      <div class="rating">
        <p class="eyebrow">Google reviews</p>
        <p class="score">5.0</p>
        <span class="stars" role="img" aria-label="5 out of 5 stars">
          <svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg><svg class="star"><use href="#star"/></svg>
        </span>
        <p class="count">4 reviews</p>
      </div>
      <div class="quotes">
        <figure class="quote quote-lead">
          <blockquote><p>We had an excellent experience with this rental company for our wedding. Everything was delivered right on time, and the quality exceeded our expectations. The charger plates, dinnerware, and glassware were absolutely beautiful…</p></blockquote>
          <figcaption>MissDH · Wedding</figcaption>
        </figure>
        <div class="quote-pair">
          <figure class="quote">
            <blockquote><p>We rented items at secured rental for our event and I must say, it turned out amazing. The communication was great, items were clean and beautiful. We will definitely be patronizing for my upcoming events. Highly recommended.</p></blockquote>
            <figcaption>Charminprints Anddecor · Event</figcaption>
          </figure>
          <figure class="quote">
            <blockquote><p>Amazing communication and organization. Pick up and drop off in timely organized fashion. Very friendly couple, would highly recommend!</p></blockquote>
            <figcaption>Nicole</figcaption>
          </figure>
        </div>
      </div>
    </div>
  </section>

  <section class="plan" id="plan">
    <div class="wrap plan-grid">
      <div class="plan-copy">
        <p class="eyebrow">Plan your rental</p>
        <h2>Tell us about your event</h2>
        <ol class="steps">
          <li><strong>Send your date and items</strong><span>Fill in the form, then send the message to (226) 978-1275 or call.</span></li>
          <li><strong>Agree a delivery time</strong><span>We confirm what you need and when it should arrive.</span></li>
          <li><strong>We deliver and collect</strong><span>Your rentals arrive on schedule and we pick them up after the event.</span></li>
        </ol>
      </div>

      <form class="tool" id="req" autocomplete="off" novalidate>
        <div class="field">
          <label for="f-name">Your name</label>
          <input id="f-name" type="text" placeholder="First and last name">
        </div>
        <div class="field-row">
          <div class="field">
            <label for="f-date">Event date</label>
            <input id="f-date" type="date">
          </div>
          <div class="field">
            <label for="f-guests">Guests</label>
            <input id="f-guests" type="number" min="1" inputmode="numeric" placeholder="For example, 80">
          </div>
        </div>
        <fieldset class="field">
          <legend>What do you need?</legend>
          <div class="checks">
            <label for="i-charger"><input id="i-charger" type="checkbox" name="item" value="charger plates" checked> Charger plates</label>
            <label for="i-dinner"><input id="i-dinner" type="checkbox" name="item" value="dinnerware" checked> Dinnerware</label>
            <label for="i-glass"><input id="i-glass" type="checkbox" name="item" value="glassware" checked> Glassware</label>
            <label for="i-other"><input id="i-other" type="checkbox" name="item" value="other items"> Something else</label>
          </div>
        </fieldset>
        <div class="field">
          <label for="f-notes">Anything else</label>
          <textarea id="f-notes" rows="3" placeholder="Venue, delivery time, other items"></textarea>
        </div>
        <div class="field">
          <label for="f-out">Your message</label>
          <textarea id="f-out" rows="9" readonly></textarea>
        </div>
        <div class="out-actions">
          <button type="button" class="btn btn-brass" id="copy-msg">Copy message</button>
          <span class="status" id="msg-status" role="status" aria-live="polite"></span>
        </div>
        <p class="hint">Copy this message and send it to (226) 978-1275, or call to talk it through.</p>
      </form>
    </div>
  </section>

  <section class="band" id="find">
    <div class="wrap find-grid">
      <div class="find-head">
        <p class="eyebrow">Find us</p>
        <h2>Clarence-Rockland, Ontario</h2>
      </div>
      <div class="find-body">
        <dl class="details">
          <div>
            <dt>Phone</dt>
            <dd><a href="tel:+12269781275" id="phone-num">(226) 978-1275</a><button type="button" class="link-btn" id="copy-phone">Copy</button> <span class="status" id="phone-status" role="status" aria-live="polite"></span></dd>
          </div>
          <div>
            <dt>Address</dt>
            <dd>1252 Diamond St<br>Clarence-Rockland, ON K4K 0M5</dd>
          </div>
          <div>
            <dt>Plus code</dt>
            <dd>GPQF+75 Clarence-Rockland, Ontario</dd>
          </div>
          <div>
            <dt>Booking</dt>
            <dd>Call or message to arrange a delivery and pick-up time.</dd>
          </div>
        </dl>
        <a class="btn btn-ghost" href="https://www.google.com/maps/search/?api=1&amp;query=1252+Diamond+St+Clarence-Rockland+ON+K4K+0M5" target="_blank" rel="noopener">Open in Google Maps</a>
      </div>
    </div>
  </section>
</main>

<footer>
  <div class="wrap">© 2026 Secured Rentals · Clarence-Rockland, Ontario</div>
</footer>

<script>
(function () {
  var $ = function (id) { return document.getElementById(id); };
  var out = $('f-out');

  function joinList(a) {
    if (a.length < 2) { return a.join(''); }
    return a.slice(0, -1).join(', ') + ' and ' + a[a.length - 1];
  }

  function fmtDate(v) {
    if (!v) { return ''; }
    var p = v.split('-');
    if (p.length !== 3) { return ''; }
    var d = new Date(+p[0], +p[1] - 1, +p[2]);
    if (isNaN(d.getTime())) { return ''; }
    try {
      return d.toLocaleDateString('en-CA', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
    } catch (e) { return v; }
  }

  function build() {
    var items = [].slice.call(document.querySelectorAll('input[name="item"]:checked')).map(function (c) { return c.value; });
    var name = $('f-name').value.trim();
    var date = fmtDate($('f-date').value);
    var guests = $('f-guests').value.trim();
    var notes = $('f-notes').value.trim();

    var parts = ["Hi Secured Rentals, I'd like to ask about renting " + (items.length ? joinList(items) : 'items') + ' for an event.'];
    var details = [];
    if (date) { details.push('Event date: ' + date); }
    if (guests) { details.push('Guests: ' + guests); }
    if (notes) { details.push('Notes: ' + notes); }
    if (details.length) { parts.push(''); parts = parts.concat(details); }
    parts.push('', name ? 'Thanks, ' + name : 'Thanks');
    out.value = parts.join('\n');
  }

  function selectNode(node) {
    try {
      var r = document.createRange();
      r.selectNodeContents(node);
      var s = window.getSelection();
      s.removeAllRanges();
      s.addRange(r);
    } catch (e) {}
  }

  function copy(text, statusEl, okText, selectFn) {
    function fallback() {
      selectFn();
      statusEl.textContent = 'Selected. Use your device’s copy command.';
    }
    try {
      if (navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(text).then(function () { statusEl.textContent = okText; }, fallback);
      } else { fallback(); }
    } catch (e) { fallback(); }
  }

  $('req').addEventListener('input', build);
  $('req').addEventListener('change', build);
  $('req').addEventListener('submit', function (e) { e.preventDefault(); });

  $('copy-msg').addEventListener('click', function () {
    copy(out.value, $('msg-status'), 'Copied. Send it to (226) 978-1275.', function () { out.focus(); out.select(); });
  });

  $('copy-phone').addEventListener('click', function () {
    copy('(226) 978-1275', $('phone-status'), 'Copied.', function () { selectNode($('phone-num')); });
  });

  build();
})();
</script>
</body>
</html>
