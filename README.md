

html_code = '''<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hiddenfindslab - Ultimate Earbud Guide</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
    background: #fafafa;
    color: #111;
    padding: 16px;
    max-width: 480px;
    margin: 0 auto;
  }
  .hero {
    text-align: center;
    margin-bottom: 20px;
    padding: 20px 0;
  }
  .hero h1 {
    font-size: 24px;
    font-weight: 800;
    margin-bottom: 6px;
    letter-spacing: -0.5px;
  }
  .hero p {
    font-size: 14px;
    color: #666;
  }
  .filters {
    display: flex;
    gap: 8px;
    overflow-x: auto;
    padding-bottom: 10px;
    margin-bottom: 16px;
    scrollbar-width: none;
  }
  .filters::-webkit-scrollbar { display: none; }
  .filter-btn {
    flex-shrink: 0;
    padding: 8px 16px;
    border-radius: 24px;
    border: 1.5px solid #e0e0e0;
    background: #fff;
    color: #666;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
  }
  .filter-btn.active {
    background: #111;
    color: #fff;
    border-color: #111;
  }
  .cat-label {
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: #999;
    margin: 16px 0 8px 4px;
  }
  .product-card {
    background: #fff;
    border-radius: 16px;
    padding: 16px;
    margin-bottom: 12px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
    box-shadow: 0 1px 3px rgba(0,0,0,0.04);
    transition: transform 0.15s, box-shadow 0.15s;
  }
  .product-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 16px rgba(0,0,0,0.08);
  }
  .product-img {
    width: 90px;
    height: 90px;
    border-radius: 12px;
    background: #f5f5f5;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    overflow: hidden;
  }
  .product-img img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .product-info { flex: 1; min-width: 0; }
  .badge-row { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 6px; }
  .badge {
    display: inline-block;
    padding: 3px 8px;
    border-radius: 6px;
    font-size: 11px;
    font-weight: 700;
  }
  .badge.deal { background: #ffebee; color: #c62828; }
  .badge.hot { background: #fff3e0; color: #e65100; }
  .badge.budget { background: #e8f5e9; color: #2e7d32; }
  .badge.premium { background: #f3e5f5; color: #6a1b9a; }
  .badge.limited { background: #e3f2fd; color: #1565c0; }
  .product-title {
    font-size: 16px;
    font-weight: 700;
    margin-bottom: 4px;
    line-height: 1.3;
  }
  .price-row {
    display: flex;
    align-items: baseline;
    gap: 8px;
    margin-bottom: 4px;
  }
  .price {
    font-size: 22px;
    font-weight: 800;
    color: #111;
  }
  .was-price {
    font-size: 14px;
    color: #999;
    text-decoration: line-through;
  }
  .meta {
    font-size: 13px;
    color: #666;
    margin-bottom: 6px;
    line-height: 1.4;
  }
  .hook {
    font-size: 13px;
    color: #333;
    font-weight: 500;
    margin-bottom: 12px;
    line-height: 1.4;
  }
  .shop-btn {
    width: 100%;
    padding: 12px 0;
    border-radius: 12px;
    border: none;
    background: #111;
    color: #fff;
    font-size: 15px;
    font-weight: 700;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    text-align: center;
    transition: opacity 0.15s;
  }
  .shop-btn:hover { opacity: 0.85; }
  .table-toggle {
    text-align: center;
    margin: 24px 0 12px;
  }
  .table-toggle button {
    background: #fff;
    border: 1.5px solid #e0e0e0;
    padding: 10px 20px;
    border-radius: 12px;
    font-size: 14px;
    color: #666;
    cursor: pointer;
    font-weight: 600;
  }
  .comparison-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
    background: #fff;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 1px 3px rgba(0,0,0,0.04);
  }
  .comparison-table th {
    text-align: left;
    padding: 12px 10px;
    border-bottom: 1px solid #eee;
    color: #999;
    font-weight: 700;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .comparison-table td {
    padding: 12px 10px;
    border-bottom: 1px solid #f5f5f5;
    vertical-align: top;
  }
  .comparison-table tr:last-child td { border-bottom: none; }
  .hidden { display: none !important; }
  .footer {
    text-align: center;
    padding: 24px 0;
    font-size: 12px;
    color: #999;
  }
  .footer a { color: #666; text-decoration: none; }
</style>
</head>
<body>

<div class="hero">
  <h1>🎧 Ultimate Earbud Guide</h1>
  <p>7 products • $10.79 – $188 • Amazon Prime</p>
</div>

<div class="filters">
  <button class="filter-btn active" onclick="filter('all')">All 7</button>
  <button class="filter-btn" onclick="filter('budget')">Under $30</button>
  <button class="filter-btn" onclick="filter('premium')">Premium</button>
  <button class="filter-btn" onclick="filter('open')">Open-Ear</button>
  <button class="filter-btn" onclick="filter('wired')">Wired</button>
</div>

<div class="cat-label">🔥 Premium Pick</div>
<div class="product-card" data-category="premium">
  <div class="product-img">
    <!-- SWAP THIS: Sony WH-1000XM5 image -->
    <img src="YOUR_SONY_IMAGE_URL_HERE" alt="Sony WH-1000XM5">
  </div>
  <div class="product-info">
    <div class="badge-row">
      <span class="badge premium">Premium</span>
      <span class="badge deal">53% OFF</span>
    </div>
    <div class="product-title">Sony WH-1000XM5</div>
    <div class="price-row">
      <span class="price">$188</span>
      <span class="was-price">$399.99</span>
    </div>
    <div class="meta">⭐ 4.2 (19,761) • 10K+ bought last month • 30hrs</div>
    <div class="hook">Auto NC Optimizer + Alexa. Best noise cancelling on the market.</div>
    <a href="YOUR_SONY_AFFILIATE_LINK" class="shop-btn">Shop on Amazon →</a>
  </div>
</div>

<div class="cat-label">💎 Mid-Range</div>
<div class="product-card" data-category="mid">
  <div class="product-img">
    <!-- SWAP THIS: JBL Tune Flex image -->
    <img src="YOUR_JBL_IMAGE_URL_HERE" alt="JBL Tune Flex">
  </div>
  <div class="product-info">
    <div class="badge-row">
      <span class="badge hot">40% OFF</span>
    </div>
    <div class="product-title">JBL Tune Flex</div>
    <div class="price-row">
      <span class="price">$59.95</span>
      <span class="was-price">$99.95</span>
    </div>
    <div class="meta">⭐ 4.2 (14,106) • 500+ bought • 32hrs • IPX4</div>
    <div class="hook">Real ANC + Ambient Aware. 4 mics for perfect calls. Black: $52.98</div>
    <a href="YOUR_JBL_AFFILIATE_LINK" class="shop-btn">Shop on Amazon →</a>
  </div>
</div>

<div class="cat-label">🏃 Open-Ear Safety</div>
<div class="product-card" data-category="open">
  <div class="product-img">
    <!-- SWAP THIS: Ohayo Open-Ear image -->
    <img src="YOUR_OHAYO_IMAGE_URL_HERE" alt="Ohayo Open-Ear">
  </div>
  <div class="product-info">
    <div class="badge-row">
      <span class="badge hot">40% OFF</span>
    </div>
    <div class="product-title">Ohayo Open-Ear</div>
    <div class="price-row">
      <span class="price">$29.99</span>
      <span class="was-price">$49.99</span>
    </div>
    <div class="meta">4K+ bought last month • 40hrs • BT 5.4 • IPX6</div>
    <div class="hook">Hear music + traffic. Digital display case. Touch control. Beige & Black.</div>
    <a href="YOUR_OHAYO_AFFILIATE_LINK" class="shop-btn">Shop on Amazon →</a>
  </div>
</div>

<div class="cat-label">💰 Budget Champions</div>
<div class="product-card" data-category="budget">
  <div class="product-img">
    <!-- SWAP THIS: Picun B8 image -->
    <img src="YOUR_PICUN_IMAGE_URL_HERE" alt="Picun B8">
  </div>
  <div class="product-info">
    <div class="badge-row">
      <span class="badge deal">36% OFF</span>
    </div>
    <div class="product-title">Picun B8</div>
    <div class="price-row">
      <span class="price">$19</span>
      <span class="was-price">$30</span>
    </div>
    <div class="meta">⭐ 4.6 • 6K+ bought last month • 120hrs • 7 colors</div>
    <div class="hook">120 hours battery. 3 EQ modes. Low latency for gaming.</div>
    <a href="YOUR_PICUN_AFFILIATE_LINK" class="shop-btn">Shop on Amazon →</a>
  </div>
</div>

<div class="product-card" data-category="wired">
  <div class="product-img">
    <!-- SWAP THIS: Zeniper image -->
    <img src="YOUR_ZENIPER_IMAGE_URL_HERE" alt="Zeniper USB-C">
  </div>
  <div class="product-info">
    <div class="badge-row">
      <span class="badge budget">2 PACKS</span>
    </div>
    <div class="product-title">Zeniper USB-C Wired</div>
    <div class="price-row">
      <span class="price">$19.99</span>
      <span class="was-price">$10/set</span>
    </div>
    <div class="meta">⭐ 4.8 (10) • 50+ bought • Inline mic + remote</div>
    <div class="hook">No battery, no pairing. USB-C for iPhone 15/16/17 + iPad Pro.</div>
    <a href="YOUR_ZENIPER_AFFILIATE_LINK" class="shop-btn">Shop on Amazon →</a>
  </div>
</div>

<div class="product-card" data-category="budget">
  <div class="product-img">
    <!-- SWAP THIS: TOZO A1 image -->
    <img src="YOUR_TOZO_IMAGE_URL_HERE" alt="TOZO A1">
  </div>
  <div class="product-info">
    <div class="badge-row">
      <span class="badge deal">44% OFF</span>
    </div>
    <div class="product-title">TOZO A1 (T6)</div>
    <div class="price-row">
      <span class="price">$12.31</span>
      <span class="was-price">$22</span>
    </div>
    <div class="meta">3.7g per earbud • IPX8 • 32hrs • BT 5.3</div>
    <div class="hook">Lighter than a paperclip. Full immersion waterproof. OrigX bass.</div>
    <a href="YOUR_TOZO_AFFILIATE_LINK" class="shop-btn">Shop on Amazon →</a>
  </div>
</div>

<div class="product-card" data-category="budget">
  <div class="product-img">
    <!-- SWAP THIS: AOSRAU image -->
    <img src="YOUR_AOSRAU_IMAGE_URL_HERE" alt="AOSRAU">
  </div>
  <div class="product-info">
    <div class="badge-row">
      <span class="badge limited">Limited Time</span>
      <span class="badge hot">10% OFF</span>
    </div>
    <div class="product-title">AOSRAU Wireless</div>
    <div class="price-row">
      <span class="price">$10.79</span>
      <span class="was-price">$11.99</span>
    </div>
    <div class="meta">⭐ 4.4 (340) • 48hrs • 4 ENC mics • IP7 • 11 colors</div>
    <div class="hook">4 ENC mics + dual LED display. This price shouldn't exist.</div>
    <a href="YOUR_AOSRAU_AFFILIATE_LINK" class="shop-btn">Shop on Amazon →</a>
  </div>
</div>

<div class="table-toggle">
  <button onclick="toggleTable()">📊 View Full Comparison Table</button>
</div>

<div id="table-section" class="hidden">
  <table class="comparison-table">
    <tr>
      <th>Product</th>
      <th>Price</th>
      <th>Battery</th>
      <th>Best For</th>
    </tr>
    <tr><td><strong>Sony XM5</strong></td><td>$188</td><td>30hrs</td><td>Travel/ANC</td></tr>
    <tr><td><strong>JBL Flex</strong></td><td>$59.95</td><td>32hrs</td><td>Everyday</td></tr>
    <tr><td><strong>Ohayo</strong></td><td>$29.99</td><td>40hrs</td><td>Running</td></tr>
    <tr><td><strong>Picun B8</strong></td><td>$19</td><td>120hrs</td><td>Gaming</td></tr>
    <tr><td><strong>Zeniper</strong></td><td>$19.99</td><td>Unlimited</td><td>Backup</td></tr>
    <tr><td><strong>TOZO A1</strong></td><td>$12.31</td><td>32hrs</td><td>Gym</td></tr>
    <tr><td><strong>AOSRAU</strong></td><td>$10.79</td><td>48hrs</td><td>Budget</td></tr>
  </table>
</div>

<div class="footer">
  <p>Links are affiliate. I earn a small commission at no extra cost to you.</p>
  <p style="margin-top:4px;"><a href="https://tiktok.com/@hiddenfindslab">@hiddenfindslab</a></p>
</div>

<script>
function filter(category) {
  document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
  event.target.classList.add('active');
  document.querySelectorAll('.product-card').forEach(card => {
    if (category === 'all') {
      card.classList.remove('hidden');
    } else if (category === 'budget') {
      card.classList.toggle('hidden', !['budget','wired'].includes(card.dataset.category));
    } else {
      card.classList.toggle('hidden', card.dataset.category !== category);
    }
  });
  document.querySelectorAll('.cat-label').forEach(l => l.classList.toggle('hidden', category !== 'all'));
}
function toggleTable() {
  document.getElementById('table-section').classList.toggle('hidden');
}
</script>

</body>
</html>'''

with open('/mnt/agents/output/hiddenfinds_beacons_page.html', 'w') as f:
    f.write(html_code)

print("File saved successfully!")
print(f"File size: {len(html_code)} characters")