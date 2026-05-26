<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Men's Area — Mobile Wellness Menu</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Josefin+Sans:wght@200;300;400&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  :root {
    --cream: #F5EFE4;
    --warm-white: #FAF7F2;
    --bark: #5C3D2E;
    --gold: #C9A86C;
    --sage: #7A8C6E;
    --dark: #2C1F14;
    --muted: #A89280;
  }
  body {
    background: #E8E0D5;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 100vh;
    padding: 40px 20px;
    font-family: 'Cormorant Garamond', serif;
  }
  .card {
    width: 420px;
    background: var(--warm-white);
    position: relative;
    overflow: hidden;
    box-shadow: 0 20px 60px rgba(44,31,20,0.25);
  }
  .card::before {
    content: '';
    display: block;
    height: 6px;
    background: linear-gradient(90deg, var(--bark), var(--gold), var(--sage), var(--gold), var(--bark));
  }
  .inner {
    position: relative;
    z-index: 1;
    padding: 40px 36px 36px;
  }
  .corner {
    position: absolute;
    width: 40px;
    height: 40px;
    z-index: 2;
  }
  .corner-tl { top: 14px; left: 14px; border-top: 1px solid var(--gold); border-left: 1px solid var(--gold); }
  .corner-tr { top: 14px; right: 14px; border-top: 1px solid var(--gold); border-right: 1px solid var(--gold); }
  .corner-bl { bottom: 14px; left: 14px; border-bottom: 1px solid var(--gold); border-left: 1px solid var(--gold); }
  .corner-br { bottom: 14px; right: 14px; border-bottom: 1px solid var(--gold); border-right: 1px solid var(--gold); }
  .header { text-align: center; margin-bottom: 32px; }
  .brand-line {
    font-family: 'Josefin Sans', sans-serif;
    font-weight: 200;
    font-size: 10px;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 8px;
  }
  .brand-name {
    font-size: 38px;
    font-weight: 300;
    color: var(--bark);
    line-height: 1;
    letter-spacing: 2px;
  }
  .brand-name em {
    font-style: italic;
    font-weight: 400;
    color: var(--gold);
  }
  .tagline {
    font-size: 12px;
    font-style: italic;
    color: var(--muted);
    margin-top: 10px;
    font-weight: 300;
    letter-spacing: 1px;
  }
  .divider {
    display: flex;
    align-items: center;
    gap: 12px;
    margin: 20px 0;
  }
  .divider-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
  }
  .divider-diamond {
    width: 6px;
    height: 6px;
    background: var(--gold);
    transform: rotate(45deg);
    flex-shrink: 0;
  }
  .section-label {
    font-family: 'Josefin Sans', sans-serif;
    font-weight: 300;
    font-size: 9px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--sage);
    text-align: center;
    margin-bottom: 18px;
  }
  .services { display: flex; flex-direction: column; }
  .service-row {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    padding: 10px 0;
    border-bottom: 1px solid rgba(139,99,71,0.1);
    gap: 8px;
  }
  .service-row:last-child { border-bottom: none; }
  .service-left { flex: 1; }
  .service-name { font-size: 17px; font-weight: 400; color: var(--dark); line-height: 1.2; }
  .service-duration {
    font-family: 'Josefin Sans', sans-serif;
    font-size: 9px;
    font-weight: 300;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
    margin-top: 2px;
  }
  .service-price { font-size: 15px; font-weight: 300; color: var(--bark); white-space: nowrap; text-align: right; }
  .service-price span { font-size: 11px; color: var(--muted); }
  .service-row.highlight {
    background: linear-gradient(90deg, transparent, rgba(201,168,108,0.08), transparent);
    margin: 0 -8px;
    padding: 10px 8px;
  }
  .service-row.highlight .service-name { color: var(--bark); font-style: italic; }
  .mobile-note {
    background: linear-gradient(135deg, rgba(92,61,46,0.05), rgba(201,168,108,0.1));
    border-left: 2px solid var(--gold);
    padding: 14px 16px;
    margin: 24px 0 0;
  }
  .mobile-note p {
    font-size: 13px;
    font-style: italic;
    color: var(--bark);
    line-height: 1.7;
    font-weight: 300;
  }
  .footer { margin-top: 28px; text-align: center; }
  .footer-label {
    font-family: 'Josefin Sans', sans-serif;
    font-weight: 300;
    font-size: 9px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 10px;
  }
  .phone-number {
    font-size: 20px;
    color: var(--bark);
    letter-spacing: 1px;
    font-weight: 400;
    margin-bottom: 18px;
  }
  .order-btn {
    display: block;
    width: 100%;
    background: var(--bark);
    color: var(--cream);
    font-family: 'Josefin Sans', sans-serif;
    font-weight: 300;
    font-size: 12px;
    letter-spacing: 4px;
    text-transform: uppercase;
    padding: 16px 32px;
    text-decoration: none;
    text-align: center;
    margin-bottom: 18px;
    cursor: pointer;
  }
  .order-btn:hover { background: var(--dark); }
  .social-row {
    font-family: 'Josefin Sans', sans-serif;
    font-size: 9px;
    letter-spacing: 3px;
    color: var(--muted);
    text-transform: uppercase;
    margin-top: 8px;
  }
  .location-row {
    font-size: 12px;
    font-style: italic;
    color: var(--muted);
    margin-top: 6px;
    letter-spacing: 0.5px;
  }
  .bottom-border {
    height: 4px;
    background: linear-gradient(90deg, var(--sage), var(--gold), var(--bark));
    margin-top: 32px;
  }
  @media print {
    body { background: white; padding: 0; }
    .card { box-shadow: none; margin: 0 auto; }
  }
</style>
</head>
<body>
<div class="card">
  <div class="corner corner-tl"></div>
  <div class="corner corner-tr"></div>
  <div class="corner corner-bl"></div>
  <div class="corner corner-br"></div>

  <div class="inner">
    <div class="header">
      <div class="brand-line">Mobile Wellness · Bali & Java</div>
      <div class="brand-name">Men's <em>Area</em></div>
      <div class="tagline">We travel. We stop. We heal.</div>
    </div>

    <div class="divider">
      <div class="divider-line"></div>
      <div class="divider-diamond"></div>
      <div class="divider-line"></div>
    </div>

    <div class="section-label">Our Services</div>

    <div class="services">
      <div class="service-row">
        <div class="service-left">
          <div class="service-name">Balinese Massage</div>
          <div class="service-duration">60 min · 90 min</div>
        </div>
        <div class="service-price">150k <span>/</span> 200k</div>
      </div>
      <div class="service-row">
        <div class="service-left">
          <div class="service-name">Body Scrub</div>
          <div class="service-duration">60 min</div>
        </div>
        <div class="service-price">120k</div>
      </div>
      <div class="service-row">
        <div class="service-left">
          <div class="service-name">Head & Scalp Massage</div>
          <div class="service-duration">30 min</div>
        </div>
        <div class="service-price">80k</div>
      </div>
      <div class="service-row">
        <div class="service-left">
          <div class="service-name">Haircut</div>
          <div class="service-duration">30–45 min</div>
        </div>
        <div class="service-price">75k</div>
      </div>
      <div class="service-row">
        <div class="service-left">
          <div class="service-name">Manicure</div>
          <div class="service-duration">45 min</div>
        </div>
        <div class="service-price">80k</div>
      </div>
      <div class="service-row">
        <div class="service-left">
          <div class="service-name">Pedicure</div>
          <div class="service-duration">45 min</div>
        </div>
        <div class="service-price">90k</div>
      </div>
      <div class="service-row highlight">
        <div class="service-left">
          <div class="service-name">Manicure & Pedicure</div>
          <div class="service-duration">75 min · combo</div>
        </div>
        <div class="service-price">150k</div>
      </div>
      <div class="service-row">
        <div class="service-left">
          <div class="service-name">Express Face Treatment</div>
          <div class="service-duration">30 min</div>
        </div>
        <div class="service-price">90k</div>
      </div>
    </div>

    <div class="mobile-note">
      <p>See our car on the road? Stop us.<br>
      We set up wherever you are — your home, your hotel, your garden.</p>
    </div>

    <div class="divider" style="margin-top:24px;">
      <div class="divider-line"></div>
      <div class="divider-diamond"></div>
      <div class="divider-line"></div>
    </div>

    <div class="footer">
      <div class="footer-label">Book via WhatsApp</div>
      <div class="phone-number">+62 818 0555 9651</div>
      <a class="order-btn" href="https://wa.me/6281805559651?text=Hi%20Men's%20Area!%20I%20would%20like%20to%20book%20a%20mobile%20wellness%20service.%20Please%20let%20me%20know%20your%20availability%20%F0%9F%8C%BF" target="_blank">
        ✦ &nbsp; ORDER NOW &nbsp; ✦
      </a>
      <div class="social-row">@mensareagianyar &nbsp;·&nbsp; Instagram &nbsp;&amp;&nbsp; X</div>
      <div class="location-row">Gianyar, Bali &nbsp;·&nbsp; Mobile across Bali & Java</div>
    </div>
  </div>

  <div class="bottom-border"></div>
</div>
</body>
</html>
