<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SME Social Media Marketing Survey — Lagos State Research</title>
<style>
  :root {
    --green: #1a7a4a;
    --green-light: #e8f5ee;
    --green-mid: #2da65e;
    --green-dark: #0f5232;
    --white: #ffffff;
    --bg: #f5f7f5;
    --text: #1a1f1a;
    --text-muted: #556055;
    --text-hint: #8a9e8a;
    --border: #d0dbd0;
    --border-strong: #a8bfa8;
    --error: #c0392b;
    --radius: 10px;
    --radius-sm: 6px;
    --shadow: 0 1px 4px rgba(0,0,0,0.07);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    background: var(--bg);
    color: var(--text);
    font-size: 15px;
    line-height: 1.6;
    min-height: 100vh;
  }

  .page-header {
    background: var(--green-dark);
    color: #fff;
    padding: 2rem 1rem 1.5rem;
    text-align: center;
  }
  .page-header .eyebrow {
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    opacity: 0.7;
    margin-bottom: 0.5rem;
  }
  .page-header h1 {
    font-size: clamp(17px, 3vw, 22px);
    font-weight: 600;
    line-height: 1.35;
    max-width: 560px;
    margin: 0 auto 0.75rem;
  }
  .page-header p {
    font-size: 13px;
    opacity: 0.8;
    max-width: 480px;
    margin: 0 auto;
    line-height: 1.6;
  }

  .progress-bar-wrap {
    background: rgba(255,255,255,0.15);
    height: 6px;
    border-radius: 3px;
    margin: 1.25rem auto 0;
    max-width: 400px;
    overflow: hidden;
  }
  .progress-bar-fill {
    height: 100%;
    background: #5ee89a;
    border-radius: 3px;
    transition: width 0.5s ease;
    width: 0%;
  }
  .progress-label {
    font-size: 12px;
    opacity: 0.75;
    margin-top: 0.4rem;
    text-align: center;
  }

  .container {
    max-width: 680px;
    margin: 0 auto;
    padding: 1.5rem 1rem 3rem;
  }

  .card {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1.5rem;
    margin-bottom: 1.25rem;
    box-shadow: var(--shadow);
  }

  .section-badge {
    display: inline-block;
    background: var(--green-light);
    color: var(--green-dark);
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 3px 10px;
    border-radius: 20px;
    margin-bottom: 0.5rem;
  }
  .section-title {
    font-size: 16px;
    font-weight: 600;
    margin-bottom: 0.25rem;
    color: var(--green-dark);
  }
  .section-sub {
    font-size: 13px;
    color: var(--text-muted);
    margin-bottom: 1.25rem;
    line-height: 1.5;
  }

  .qblock { margin-bottom: 1.5rem; }
  .qblock:last-child { margin-bottom: 0; }

  .qlabel {
    font-size: 14px;
    margin-bottom: 0.6rem;
    line-height: 1.5;
    color: var(--text);
  }
  .qnum { font-weight: 600; color: var(--green); margin-right: 4px; }
  .req { color: var(--error); font-size: 12px; margin-left: 2px; }

  select {
    width: 100%;
    border: 1px solid var(--border-strong);
    border-radius: var(--radius-sm);
    padding: 9px 12px;
    font-size: 14px;
    background: var(--white);
    color: var(--text);
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%23556055' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    cursor: pointer;
  }
  select:focus { outline: 2px solid var(--green-mid); border-color: var(--green-mid); }

  .radio-group, .checkbox-group {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  .radio-opt, .checkbox-opt {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 14px;
    cursor: pointer;
    padding: 9px 12px;
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    transition: background 0.15s, border-color 0.15s;
    line-height: 1.4;
  }
  .radio-opt:hover, .checkbox-opt:hover {
    background: var(--green-light);
    border-color: var(--green-mid);
  }
  .radio-opt input, .checkbox-opt input {
    accent-color: var(--green);
    margin-top: 2px;
    flex-shrink: 0;
    width: 15px;
    height: 15px;
  }

  .likert-wrap { margin-top: 6px; }
  .likert-scale {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 4px;
  }
  .likert-cell {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
    padding: 10px 4px 8px;
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    cursor: pointer;
    transition: background 0.15s, border-color 0.15s;
    text-align: center;
    line-height: 1.2;
  }
  .likert-cell:hover { background: var(--green-light); border-color: var(--green-mid); }
  .likert-cell.selected { background: var(--green-light); border-color: var(--green); }
  .likert-cell input { accent-color: var(--green); width: 15px; height: 15px; cursor: pointer; }
  .likert-cell .val { font-size: 14px; font-weight: 600; color: var(--green-dark); }
  .likert-cell .lbl { font-size: 10px; color: var(--text-muted); }
  .likert-ends {
    display: flex;
    justify-content: space-between;
    font-size: 11px;
    color: var(--text-hint);
    margin-top: 4px;
    padding: 0 2px;
  }

  .submit-wrap { margin-top: 0.5rem; }
  .error-banner {
    background: #fdf0ef;
    border: 1px solid #f1b8b5;
    color: var(--error);
    border-radius: var(--radius-sm);
    padding: 10px 14px;
    font-size: 13px;
    margin-bottom: 0.75rem;
    display: none;
  }
  .submit-btn {
    width: 100%;
    padding: 14px;
    background: var(--green);
    color: #fff;
    border: none;
    border-radius: var(--radius);
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    letter-spacing: 0.02em;
    transition: background 0.2s, transform 0.1s;
  }
  .submit-btn:hover { background: var(--green-dark); }
  .submit-btn:active { transform: scale(0.99); }
  .submit-btn:disabled { opacity: 0.55; cursor: not-allowed; transform: none; }

  .success-wrap {
    text-align: center;
    padding: 3rem 1.5rem;
    display: none;
  }
  .success-icon {
    width: 64px;
    height: 64px;
    border-radius: 50%;
    background: var(--green-light);
    margin: 0 auto 1.25rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .success-icon svg { width: 32px; height: 32px; stroke: var(--green); }
  .success-wrap h2 { font-size: 20px; font-weight: 600; margin-bottom: 0.5rem; color: var(--green-dark); }
  .success-wrap p { font-size: 14px; color: var(--text-muted); max-width: 380px; margin: 0 auto 0.5rem; }

  .count-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(255,255,255,0.12);
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: 30px;
    padding: 6px 14px;
    margin-top: 1rem;
    font-size: 13px;
    color: #fff;
  }
  .count-pill .n { font-size: 18px; font-weight: 700; color: #5ee89a; }

  .divider { height: 1px; background: var(--border); margin: 1.25rem 0; }

  @media (max-width: 480px) {
    .likert-cell .lbl { display: none; }
    .card { padding: 1.25rem 1rem; }
  }
</style>
</head>
<body>

<div class="page-header">
  <div class="eyebrow">Academic Research — University Study</div>
  <h1>Social Media Marketing &amp; SME Performance in Lagos State</h1>
  <p>This survey supports an academic study on how social media marketing affects SME performance in Ikeja, Surulere, and Yaba LGAs. All responses are anonymous and used for research only. Takes 8–10 minutes.</p>
  <div class="count-pill">
    <span>Responses collected:</span>
    <span class="n" id="hdr-count">0</span>
    <span>/ 100</span>
  </div>
  <div class="progress-bar-wrap">
    <div class="progress-bar-fill" id="prog-fill"></div>
  </div>
  <div class="progress-label" id="prog-label">0 of 100 target responses</div>
</div>

<div class="container">
  <div id="form-wrap">

    <!-- Section A -->
    <div class="card">
      <div class="section-badge">Section A</div>
      <div class="section-title">Demographic &amp; Business Profile</div>
      <div class="section-sub">Please provide general information about yourself and your business. All fields are required.</div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">1.</span> Gender <span class="req">*</span></div>
        <div class="radio-group">
          <label class="radio-opt"><input type="radio" name="q1" value="Male"> Male</label>
          <label class="radio-opt"><input type="radio" name="q1" value="Female"> Female</label>
          <label class="radio-opt"><input type="radio" name="q1" value="Prefer not to say"> Prefer not to say</label>
        </div>
      </div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">2.</span> Highest educational qualification <span class="req">*</span></div>
        <select id="q2">
          <option value="">— Select qualification —</option>
          <option>WAEC / NECO / O-Level</option>
          <option>OND / NCE</option>
          <option>HND / B.Sc.</option>
          <option>Postgraduate (M.Sc. / MBA / Ph.D.)</option>
          <option>Other</option>
        </select>
      </div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">3.</span> Which LGA does your business operate in? <span class="req">*</span></div>
        <div class="radio-group">
          <label class="radio-opt"><input type="radio" name="q3" value="Ikeja"> Ikeja</label>
          <label class="radio-opt"><input type="radio" name="q3" value="Surulere"> Surulere</label>
          <label class="radio-opt"><input type="radio" name="q3" value="Yaba"> Yaba</label>
        </div>
      </div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">4.</span> Business sector <span class="req">*</span></div>
        <select id="q4">
          <option value="">— Select sector —</option>
          <option>Retail</option>
          <option>Services</option>
          <option>Food and Beverage</option>
          <option>Fashion and Beauty</option>
          <option>Light Manufacturing</option>
          <option>Technology</option>
          <option>Other</option>
        </select>
      </div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">5.</span> How many years has your business been in operation? <span class="req">*</span></div>
        <div class="radio-group">
          <label class="radio-opt"><input type="radio" name="q5" value="Less than 1 year"> Less than 1 year</label>
          <label class="radio-opt"><input type="radio" name="q5" value="1–3 years"> 1–3 years</label>
          <label class="radio-opt"><input type="radio" name="q5" value="4–6 years"> 4–6 years</label>
          <label class="radio-opt"><input type="radio" name="q5" value="7–10 years"> 7–10 years</label>
          <label class="radio-opt"><input type="radio" name="q5" value="More than 10 years"> More than 10 years</label>
        </div>
      </div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">6.</span> Total number of employees (including owner) <span class="req">*</span></div>
        <div class="radio-group">
          <label class="radio-opt"><input type="radio" name="q6" value="1–9"> 1–9 (Micro enterprise)</label>
          <label class="radio-opt"><input type="radio" name="q6" value="10–49"> 10–49 (Small enterprise)</label>
          <label class="radio-opt"><input type="radio" name="q6" value="50–99"> 50–99 (Medium enterprise)</label>
          <label class="radio-opt"><input type="radio" name="q6" value="100–199"> 100–199 (Medium enterprise)</label>
        </div>
      </div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">7.</span> Which social media platforms does your business actively use for marketing? <em style="color:var(--text-muted);font-size:13px">(Select all that apply)</em> <span class="req">*</span></div>
        <div class="checkbox-group">
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="WhatsApp"> WhatsApp / WhatsApp Business</label>
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="Facebook"> Facebook</label>
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="Instagram"> Instagram</label>
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="TikTok"> TikTok</label>
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="Twitter/X"> Twitter / X</label>
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="LinkedIn"> LinkedIn</label>
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="YouTube"> YouTube</label>
          <label class="checkbox-opt"><input type="checkbox" name="q7" value="None"> None — we do not use social media for marketing</label>
        </div>
      </div>

      <div class="qblock">
        <div class="qlabel"><span class="qnum">8.</span> How long has your business been using social media for marketing? <span class="req">*</span></div>
        <div class="radio-group">
          <label class="radio-opt"><input type="radio" name="q8" value="Less than 1 year"> Less than 1 year</label>
          <label class="radio-opt"><input type="radio" name="q8" value="1–2 years"> 1–2 years</label>
          <label class="radio-opt"><input type="radio" name="q8" value="3–5 years"> 3–5 years</label>
          <label class="radio-opt"><input type="radio" name="q8" value="More than 5 years"> More than 5 years</label>
          <label class="radio-opt"><input type="radio" name="q8" value="We do not use social media"> We do not use social media</label>
        </div>
      </div>
    </div>

    <!-- Section B -->
    <div class="card">
      <div class="section-badge">Section B</div>
      <div class="section-title">Social Media Content Quality</div>
      <div class="section-sub">Rate each statement about your business's social media content.<br>
        <strong>1 = Strongly Disagree &nbsp;·&nbsp; 3 = Neutral &nbsp;·&nbsp; 5 = Strongly Agree</strong>
      </div>
      <div id="section-b"></div>
    </div>

    <!-- Section C -->
    <div class="card">
      <div class="section-badge">Section C</div>
      <div class="section-title">Customer Engagement via Social Media</div>
      <div class="section-sub">Rate how your business engages customers on social media.<br>
        <strong>1 = Strongly Disagree &nbsp;·&nbsp; 3 = Neutral &nbsp;·&nbsp; 5 = Strongly Agree</strong>
      </div>
      <div id="section-c"></div>
    </div>

    <!-- Section D -->
    <div class="card">
      <div class="section-badge">Section D</div>
      <div class="section-title">Social Media Advertising</div>
      <div class="section-sub">Rate your business's social media advertising activities.<br>
        <strong>1 = Strongly Disagree &nbsp;·&nbsp; 3 = Neutral &nbsp;·&nbsp; 5 = Strongly Agree</strong>
      </div>
      <div id="section-d"></div>
    </div>

    <!-- Section E -->
    <div class="card">
      <div class="section-badge">Section E</div>
      <div class="section-title">Business Performance</div>
      <div class="section-sub">Compared to 12 months ago, how has each area of your business performed?<br>
        <strong>1 = Declined Significantly &nbsp;·&nbsp; 3 = No Change &nbsp;·&nbsp; 5 = Improved Significantly</strong>
      </div>
      <div id="section-e"></div>
    </div>

    <div class="error-banner" id="err-banner"></div>
    <div class="submit-wrap">
      <button class="submit-btn" id="submit-btn" onclick="submitForm()">Submit Response →</button>
    </div>
  </div>

  <div class="success-wrap" id="success-wrap">
    <div class="success-icon">
      <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="20 6 9 17 4 12"></polyline>
      </svg>
    </div>
    <h2>Response Submitted!</h2>
    <p>Thank you for taking part in this research. Your contribution helps advance understanding of digital marketing among Nigerian SMEs.</p>
    <p style="font-size:13px;margin-top:0.75rem">You may now close this page.</p>
  </div>
</div>

<script>
const LABELS_B = ['Strongly Disagree','Disagree','Neutral','Agree','Strongly Agree'];
const LABELS_E = ['Declined Significantly','Declined','No Change','Improved','Improved Significantly'];

const QB = [
  {id:'b1', text:'The content we post on social media provides useful and relevant information to our customers.'},
  {id:'b2', text:'Our social media posts are visually appealing and professionally designed.'},
  {id:'b3', text:'We maintain a consistent posting schedule on our social media platforms.'},
  {id:'b4', text:'Our social media content is original and tailored specifically to our target audience.'},
  {id:'b5', text:'The content we share on social media entertains as well as informs our followers.'},
  {id:'b6', text:'We regularly review and improve the quality of our social media content based on audience feedback.'},
];
const QC = [
  {id:'c1', text:'We respond promptly to customer comments and messages on our social media pages.'},
  {id:'c2', text:'We actively ask questions and encourage our followers to interact with our posts.'},
  {id:'c3', text:'We acknowledge and respond to both positive and negative customer reviews on social media.'},
  {id:'c4', text:'Our social media activities have helped us build a loyal online community around our brand.'},
  {id:'c5', text:'We use features such as polls, live sessions, or stories to engage our audience interactively.'},
  {id:'c6', text:'Customer engagement on our social media pages has led to measurable increases in sales enquiries.'},
];
const QD = [
  {id:'d1', text:'We allocate a defined budget for paid social media advertising on a monthly basis.'},
  {id:'d2', text:'Our paid social media ads are targeted at specific customer demographics and locations.'},
  {id:'d3', text:'We regularly assess the performance of our social media advertising campaigns using analytics tools.'},
  {id:'d4', text:'Social media advertising has directly contributed to new customer acquisitions for our business.'},
  {id:'d5', text:'We believe our social media advertising investment generates a good return relative to the cost.'},
];
const QE = [
  {id:'e1', text:'Overall monthly sales revenue'},
  {id:'e2', text:'Number of new customers acquired'},
  {id:'e3', text:'Size of our total active customer base'},
  {id:'e4', text:'Profit margins / business profitability'},
  {id:'e5', text:'Rate at which existing customers make repeat purchases'},
  {id:'e6', text:'Overall brand awareness in our local market'},
  {id:'e7', text:'Customer satisfaction with our products or services'},
  {id:'e8', text:'Overall business performance compared to competitors'},
];

let qCounter = 9;

function buildLikert(items, containerId, labels) {
  const el = document.getElementById(containerId);
  items.forEach(item => {
    const n = qCounter++;
    const lbs = labels || LABELS_B;
    let html = `<div class="qblock" id="qblock-${item.id}">
      <div class="qlabel"><span class="qnum">${n}.</span> ${item.text} <span class="req">*</span></div>
      <div class="likert-wrap">
        <div class="likert-scale" id="likert-${item.id}">`;
    for(let v=1;v<=5;v++){
      html += `<label class="likert-cell" id="lc-${item.id}-${v}">
        <input type="radio" name="${item.id}" value="${v}" onchange="selectLikert('${item.id}',${v})">
        <span class="val">${v}</span>
        <span class="lbl">${lbs[v-1].split(' ').slice(0,2).join(' ')}</span>
      </label>`;
    }
    html += `</div>
        <div class="likert-ends"><span>${lbs[0]}</span><span>${lbs[4]}</span></div>
      </div>
    </div>`;
    el.insertAdjacentHTML('beforeend', html);
  });
}

function selectLikert(name, val) {
  for(let v=1;v<=5;v++){
    const el = document.getElementById(`lc-${name}-${v}`);
    if(el) el.classList.toggle('selected', v===val);
  }
}

buildLikert(QB, 'section-b', LABELS_B);
buildLikert(QC, 'section-c', LABELS_B);
buildLikert(QD, 'section-d', LABELS_B);
buildLikert(QE, 'section-e', LABELS_E);

function loadCount() {
  try {
    const raw = localStorage.getItem('sme_survey_count') || '0';
    const n = parseInt(raw) || 0;
    updateCounter(n);
  } catch(e) {}
}

function updateCounter(n) {
  const el = document.getElementById('hdr-count');
  const fill = document.getElementById('prog-fill');
  const lbl = document.getElementById('prog-label');
  if(el) el.textContent = n;
  if(fill) fill.style.width = Math.min((n/100)*100, 100) + '%';
  if(lbl) lbl.textContent = `${n} of 100 target responses`;
}

function getRadio(name){
  const el = document.querySelector(`input[name="${name}"]:checked`);
  return el ? el.value : null;
}
function getSelect(id){
  const el = document.getElementById(id);
  return el && el.value ? el.value : null;
}
function getCheckboxes(name){
  return [...document.querySelectorAll(`input[name="${name}"]:checked`)].map(e=>e.value);
}

function validate() {
  if(!getRadio('q1')) return 'Please answer Question 1 (Gender).';
  if(!getSelect('q2')) return 'Please answer Question 2 (Education).';
  if(!getRadio('q3')) return 'Please answer Question 3 (LGA).';
  if(!getSelect('q4')) return 'Please answer Question 4 (Business sector).';
  if(!getRadio('q5')) return 'Please answer Question 5 (Years in operation).';
  if(!getRadio('q6')) return 'Please answer Question 6 (Number of employees).';
  if(!getCheckboxes('q7').length) return 'Please answer Question 7 (Social media platforms).';
  if(!getRadio('q8')) return 'Please answer Question 8 (Social media duration).';
  const all = [...QB,...QC,...QD,...QE];
  for(const q of all){
    if(!getRadio(q.id)) return `Please answer all rating questions. Missing: "${q.text.substring(0,50)}..."`;
  }
  return null;
}

function submitForm() {
  const err = validate();
  const errBanner = document.getElementById('err-banner');
  if(err){
    errBanner.textContent = '⚠ ' + err;
    errBanner.style.display = 'block';
    errBanner.scrollIntoView({behavior:'smooth', block:'center'});
    return;
  }
  errBanner.style.display = 'none';
  const btn = document.getElementById('submit-btn');
  btn.disabled = true;
  btn.textContent = 'Submitting…';

  const resp = {
    ts: new Date().toISOString(),
    q1:getRadio('q1'), q2:getSelect('q2'), q3:getRadio('q3'), q4:getSelect('q4'),
    q5:getRadio('q5'), q6:getRadio('q6'), q7:getCheckboxes('q7').join(';'), q8:getRadio('q8'),
  };
  [...QB,...QC,...QD,...QE].forEach(q => { resp[q.id] = parseInt(getRadio(q.id)); });

  try {
    const all = JSON.parse(localStorage.getItem('sme_survey_responses') || '[]');
    all.push(resp);
    localStorage.setItem('sme_survey_responses', JSON.stringify(all));
    const count = all.length;
    localStorage.setItem('sme_survey_count', String(count));
    updateCounter(count);
  } catch(e) {}

  document.getElementById('form-wrap').style.display = 'none';
  document.getElementById('success-wrap').style.display = 'block';
  window.scrollTo({top:0, behavior:'smooth'});
}

loadCount();
</script>
</body>
</html>
