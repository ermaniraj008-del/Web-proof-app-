# Web-proof-app-
Web proof app full details in this repo and see this repo

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Hack-Proof Web App | Full Presentation | Maniraj Kumar</title>
<meta name="description" content="Step-by-step presentation of the Hack-Proof Web App: a vulnerable website, the attacks on it, and the secured version. Built by Team Bug Busters for Tech Forge 2026.">
<meta name="theme-color" content="#08090C">
<link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64'%3E%3Crect width='64' height='64' rx='14' fill='%238B93FF'/%3E%3Ctext x='32' y='46' font-size='40' font-family='sans-serif' font-weight='800' text-anchor='middle' fill='%2308090C'%3EM%3C/text%3E%3C/svg%3E">
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@500;700;800&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<script>document.documentElement.classList.add('js')</script>
<style>
:root{--ink:#08090C;--panel:#101116;--panel2:#171921;--line:#252833;--acc:#8B93FF;--sky:#6CC4FF;--mint:#6EE7B7;--rose:#FF8FA3;--amber:#FFC86B;--text:#F4F4F6;--muted:#8A8F9C;--ease:cubic-bezier(.16,1,.3,1);
--display:'Bricolage Grotesque','Trebuchet MS',system-ui,sans-serif;--body:'DM Sans',system-ui,-apple-system,'Segoe UI',sans-serif;--mono:'JetBrains Mono',ui-monospace,Menlo,Consolas,monospace}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;scroll-padding-top:80px}
body{background:var(--ink);color:var(--text);font-family:var(--body);line-height:1.7;overflow-x:hidden;-webkit-font-smoothing:antialiased}
body::before{content:'';position:fixed;inset:0;z-index:-1;pointer-events:none;background:radial-gradient(60% 45% at 85% 0%,rgba(139,147,255,.16),transparent 70%),radial-gradient(50% 40% at 8% 8%,rgba(108,196,255,.07),transparent 70%)}
a{color:inherit;text-decoration:none}ul{list-style:none}
::selection{background:var(--acc);color:var(--ink)}
:focus-visible{outline:2px solid var(--acc);outline-offset:3px;border-radius:6px}
.wrap{width:min(960px,100% - 40px);margin-inline:auto}
.progress{position:fixed;top:0;left:0;height:3px;width:100%;transform-origin:0 50%;transform:scaleX(0);background:linear-gradient(90deg,var(--acc),var(--sky));z-index:120}
nav{position:fixed;top:0;left:0;right:0;z-index:100;padding:12px 0;background:rgba(8,9,12,.85);-webkit-backdrop-filter:blur(12px);backdrop-filter:blur(12px);border-bottom:1px solid var(--line)}
nav .wrap{display:flex;align-items:center;justify-content:space-between;gap:12px}
.back{font-weight:600;font-size:.92rem;padding:8px 16px;border-radius:999px;border:1px solid var(--line);transition:border-color .25s,background .25s}
.back:hover{border-color:#4a4f60;background:rgba(255,255,255,.04)}
.tl{font:500 .8rem var(--mono);color:var(--muted)}
.btn{display:inline-flex;align-items:center;gap:10px;padding:13px 24px;border-radius:12px;font-family:var(--display);font-weight:700;border:1px solid transparent;cursor:pointer;transition:transform .25s var(--ease),background .25s,border-color .25s}
.btn:hover{transform:translateY(-3px)}
.btn-p{background:#F4F4F6;color:#0B0B0F}.btn-p:hover{background:#fff}
.btn-g{border-color:var(--line);background:transparent;color:var(--text)}.btn-g:hover{border-color:#4a4f60;background:rgba(255,255,255,.04)}
header.hero{padding:140px 0 70px}
.kick{display:inline-flex;align-items:center;gap:10px;padding:7px 15px;border:1px solid var(--line);border-radius:999px;background:rgba(16,17,22,.7);font:500 .8rem var(--mono);color:var(--muted)}
.kick i{width:8px;height:8px;border-radius:50%;background:var(--mint);animation:pulse 2s infinite}
@keyframes pulse{0%{box-shadow:0 0 0 0 rgba(110,231,183,.6)}70%,100%{box-shadow:0 0 0 10px rgba(110,231,183,0)}}
h1{font:800 clamp(2.6rem,9vw,5.6rem)/1 var(--display);letter-spacing:-.04em;margin:22px 0 16px}
h1 span{color:var(--acc)}
.sub{color:var(--muted);font-size:1.12rem;max-width:56ch}
.hero .row{display:flex;gap:14px;flex-wrap:wrap;margin-top:30px}
.facts{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:14px;margin-top:44px}
.fact{border-top:2px solid var(--acc);padding-top:10px}.fact b{display:block;font:700 1.05rem var(--display)}.fact small{color:var(--muted);font-size:.84rem}
section{padding:70px 0}
.h2{font:800 clamp(1.8rem,5vw,2.8rem)/1.1 var(--display);letter-spacing:-.03em;margin-bottom:10px}
.lede{color:var(--muted);max-width:60ch;margin-bottom:34px}
.card{background:linear-gradient(160deg,var(--panel),var(--panel2));border:1px solid var(--line);border-radius:20px;padding:26px}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:20px}
.card h3{font:700 1.2rem var(--display);margin-bottom:8px}
.card p,.card li{color:var(--muted);font-size:.97rem}
.card ul{display:grid;gap:8px;margin-top:6px}
.card li{padding-left:20px;position:relative}.card li::before{content:'';position:absolute;left:2px;top:.62em;width:7px;height:7px;background:var(--acc);transform:rotate(45deg)}
/* steps */
.steps{display:grid;gap:18px;counter-reset:s}
.step{display:grid;grid-template-columns:54px 1fr;gap:18px;position:relative}
.num{width:54px;height:54px;border-radius:16px;background:#F4F4F6;color:#0B0B0F;display:grid;place-items:center;font:800 1.3rem var(--display)}
.step .card{padding:22px 24px}
.step h3{font-size:1.15rem}
.step p+p,.step p+ul{margin-top:8px}
code{font:.86em var(--mono);background:rgba(139,147,255,.12);color:#C7CBFF;padding:2px 7px;border-radius:6px}
pre{font:.82rem/1.65 var(--mono);background:#05060a;border:1px solid var(--line);border-radius:14px;padding:16px 18px;overflow-x:auto;color:#c9cdd8;margin-top:12px}
.bad-t{color:var(--rose)}.ok-t{color:var(--mint)}.cm{color:#5d6a85}
/* attacks */
.atk{display:grid;gap:16px}
.atk .card{display:grid;grid-template-columns:150px 1fr 1fr;gap:20px;align-items:start}
.atk h3{margin:0}.atk b{display:block;font:600 .74rem var(--mono);letter-spacing:.06em;text-transform:uppercase;margin-bottom:4px}
.atk .b b{color:var(--rose)}.atk .f b{color:var(--mint)}
/* demo */
.seg{display:inline-flex;padding:3px;border-radius:999px;background:var(--panel2);border:1px solid var(--line)}
.seg button{font:600 .85rem var(--body);padding:8px 18px;border-radius:999px;border:0;background:transparent;color:var(--muted);cursor:pointer;transition:background .25s,color .25s}
.seg button.on{background:#F4F4F6;color:#0B0B0F}
.demo{margin-top:20px;display:grid;gap:20px;grid-template-columns:1fr 1fr}
.demo .card{display:grid;gap:12px;align-content:start}
.mode{font:600 .76rem var(--mono);padding:4px 12px;border-radius:999px;justify-self:start}
.mode.v{background:rgba(255,143,163,.12);color:var(--rose);border:1px solid rgba(255,143,163,.4)}
.mode.s{background:rgba(110,231,183,.12);color:var(--mint);border:1px solid rgba(110,231,183,.4)}
label{font:500 .8rem var(--mono);color:var(--muted)}
input,textarea{width:100%;font:.92rem var(--mono);background:#05060a;border:1px solid var(--line);color:var(--text);padding:11px 13px;border-radius:10px;margin-top:4px}
input:focus,textarea:focus{outline:none;border-color:var(--acc)}
textarea{resize:vertical;min-height:70px}
.chips{display:flex;gap:8px;flex-wrap:wrap}
.chip{font:600 .78rem var(--body);padding:6px 12px;border-radius:999px;border:1px solid var(--line);background:transparent;color:var(--muted);cursor:pointer;transition:border-color .2s,color .2s}
.chip:hover{border-color:var(--acc);color:var(--acc)}
.qbox{font:.8rem/1.6 var(--mono);background:#05060a;border:1px solid var(--line);border-radius:10px;padding:10px 12px;color:var(--muted);word-break:break-all;min-height:44px}
.out{font:500 .88rem var(--mono);padding:12px 14px;border-radius:10px;border:1px dashed var(--line);color:var(--muted);min-height:48px}
.out.bad{color:#ffb3bf;border-color:rgba(255,143,163,.5);background:rgba(255,143,163,.08);animation:shake .4s}
.out.good{color:#9bf0cd;border-color:rgba(110,231,183,.5);background:rgba(110,231,183,.08)}
.out.warn{color:#ffe0a3;border-color:rgba(255,200,107,.5);background:rgba(255,200,107,.08)}
@keyframes shake{25%{transform:translateX(-6px)}75%{transform:translateX(6px)}}
.wall{background:#05060a;border:1px solid var(--line);border-radius:10px;padding:12px;min-height:60px;font-size:.92rem}
.wall iframe{width:100%;height:70px;border:0;background:#fff;border-radius:6px;display:block}
.note{color:var(--muted);font-size:.85rem;margin-top:14px}
.cl{display:grid;grid-template-columns:1fr 1fr;gap:10px 24px;margin-top:6px}
.cl li{color:var(--text)}
/* reveal */
.js .rv{opacity:0;transform:translateY(30px);transition:opacity .8s var(--ease),transform .9s var(--ease)}
.js .rv.in{opacity:1;transform:none}
footer{border-top:1px solid var(--line);padding:30px 0;text-align:center;color:var(--muted);font-size:.9rem}
@media(max-width:780px){.grid2,.demo,.cl,.atk .card{grid-template-columns:1fr}.step{grid-template-columns:44px 1fr;gap:12px}.num{width:44px;height:44px;border-radius:12px;font-size:1.1rem}}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}.js .rv{opacity:1;transform:none}}
</style>
</head>
<body>
<div class="progress" id="progress"></div>
<nav><div class="wrap"><a class="back" href="index.html">← Back to portfolio</a><span class="tl">Tech Forge 2026</span></div></nav>

<header class="hero"><div class="wrap">
<span class="kick"><i></i> Full presentation · Team Bug Busters</span>
<h1>Hack-Proof <span>Web App</span></h1>
<p class="sub">One website, two versions. First a deliberately vulnerable one that can be attacked, then the same site secured so the attacks fail. Built by Maniraj Kumar for Tech Forge 2026 at Government Polytechnic Khagaria.</p>
<div class="row"><a class="btn btn-p" href="#demo">▶ Try the live demo</a><a class="btn btn-g" href="#steps">Read step by step</a></div>
<div class="facts">
<div class="fact"><b>Flask (Python)</b><small>Backend</small></div>
<div class="fact"><b>HTML · CSS · JS</b><small>Frontend</small></div>
<div class="fact"><b>Termux on Android</b><small>Where it runs</small></div>
<div class="fact"><b>2 members</b><small>Team Bug Busters</small></div>
</div></div></header>

<section id="overview"><div class="wrap">
<h2 class="h2 rv">The idea</h2>
<p class="lede rv">Many websites get hacked because of small mistakes. This project shows those mistakes live, then shows how to fix each one.</p>
<div class="grid2">
<div class="card rv"><h3>Problem</h3><p>Beginners build login pages and comment boxes that trust whatever the user types. Attackers use that trust to log in without a password, run scripts in other people's browsers, or guess passwords endlessly.</p></div>
<div class="card rv"><h3>Goal</h3><ul><li>Show real attacks on a vulnerable version</li><li>Show the secured version blocking the same attacks</li><li>Explain every fix in simple words</li><li>Make it easy to run on a phone</li></ul></div>
</div></div></section>

<section id="steps"><div class="wrap">
<h2 class="h2 rv">How it was built, step by step</h2>
<p class="lede rv">Follow these 8 steps to understand or rebuild the whole project.</p>
<div class="steps">
<div class="step rv"><div class="num">1</div><div class="card"><h3>Pick the idea and the stack</h3><p>The idea was a demo that stands out in the competition: a website that is hacked live, then fixed. The stack is <code>Flask</code> for the server and plain HTML, CSS and JavaScript for the pages, so it stays light enough for a phone.</p></div></div>
<div class="step rv"><div class="num">2</div><div class="card"><h3>Set up Flask on Termux</h3><p>Install Python in Termux, create a project folder and install Flask.</p>
<pre>pkg update &amp;&amp; pkg upgrade
pkg install python git
pip install flask flask-wtf flask-limiter
mkdir hack-proof-app &amp;&amp; cd hack-proof-app</pre></div></div>
<div class="step rv"><div class="num">3</div><div class="card"><h3>Plan the two versions</h3><p>Keep one shared look but two behaviours: a <b>vulnerable</b> version and a <b>secured</b> version of the same pages. Both have a login page and a comment page, because these two features are the most attacked.</p>
<ul><li>Login page: tests SQL injection and brute force</li><li>Comment page: tests XSS (script injection)</li></ul></div></div>
<div class="step rv"><div class="num">4</div><div class="card"><h3>Build the vulnerable version on purpose</h3><p>Write the code the way beginners often do: join user input straight into the database query, store passwords as plain text, and print comments without cleaning them.</p>
<pre><span class="cm"># VULNERABLE login</span>
u = request.form['username']
p = request.form['password']
<span class="bad-t">q = f"SELECT * FROM users WHERE username='{u}' AND password='{p}'"</span>
user = db.execute(q).fetchone()</pre></div></div>
<div class="step rv"><div class="num">5</div><div class="card"><h3>Attack it (the demo part)</h3><p>Show the audience three attacks on the vulnerable version: typing <code>admin' --</code> as the username to skip the password check, posting a script in the comment box, and guessing passwords many times with no limit. See the live demo below.</p></div></div>
<div class="step rv"><div class="num">6</div><div class="card"><h3>Fix each problem in the secured version</h3><p>Apply one fix per attack, in the same project.</p>
<pre><span class="cm"># SECURED login</span>
u = request.form['username'].strip()
if not re.fullmatch(r'[A-Za-z0-9_]{3,20}', u): abort(400)   <span class="cm"># validate input</span>
<span class="ok-t">user = db.execute("SELECT * FROM users WHERE username = ?", (u,)).fetchone()</span>
if user and check_password_hash(user['password_hash'], p):    <span class="cm"># hashed password</span>
    ...</pre>
<ul><li>Parameterized queries stop SQL injection</li><li>Password hashing means a stolen database does not reveal passwords</li><li>Output escaping (Jinja2 autoescape) turns scripts into harmless text</li><li><code>Flask-Limiter</code> locks guessing attacks, <code>Flask-WTF</code> adds CSRF tokens</li></ul></div></div>
<div class="step rv"><div class="num">7</div><div class="card"><h3>Add security headers</h3><p>Tell the browser to be strict.</p>
<pre>@app.after_request
def secure(r):
    r.headers['Content-Security-Policy'] = "default-src 'self'"
    r.headers['X-Content-Type-Options'] = 'nosniff'
    r.headers['X-Frame-Options'] = 'DENY'
    return r</pre></div></div>
<div class="step rv"><div class="num">8</div><div class="card"><h3>Run it and present it</h3><p>Start the server in Termux and open it in the phone browser.</p>
<pre>python app.py
<span class="cm"># open http://127.0.0.1:5000 in the browser</span></pre>
<p>On stage, run the attack on the vulnerable version first, then the same attack on the secured version, and compare.</p></div></div>
</div></div></section>

<section id="attacks"><div class="wrap">
<h2 class="h2 rv">Attack vs fix</h2>
<p class="lede rv">Every attack in this project has one clear fix.</p>
<div class="atk">
<div class="card rv"><h3>SQL injection</h3><div class="b"><b>Vulnerable</b><p>User input is glued into the query, so <code>admin' --</code> removes the password check.</p></div><div class="f"><b>Fix</b><p>Parameterized queries plus input validation. Input is treated as data, never as code.</p></div></div>
<div class="card rv"><h3>XSS</h3><div class="b"><b>Vulnerable</b><p>A comment with a script tag is shown as real HTML and runs for every visitor.</p></div><div class="f"><b>Fix</b><p>Escape all output and set a Content-Security-Policy header.</p></div></div>
<div class="card rv"><h3>Brute force</h3><div class="b"><b>Vulnerable</b><p>Unlimited password guesses, so a weak password falls quickly.</p></div><div class="f"><b>Fix</b><p>Rate limiting and temporary lock after repeated failures, plus hashed passwords.</p></div></div>
<div class="card rv"><h3>CSRF</h3><div class="b"><b>Vulnerable</b><p>Another site can send a request that the logged-in user never meant to make.</p></div><div class="f"><b>Fix</b><p>Secret CSRF token in every form, checked by the server.</p></div></div>
</div></div></section>

<section id="demo"><div class="wrap">
<h2 class="h2 rv">Live demo</h2>
<p class="lede rv">Pick a version, then try the attacks yourself. Test accounts: <code>admin / Admin@123</code> and <code>maniraj / Dev@2026</code>.</p>
<div class="seg rv" role="group" aria-label="Version"><button class="on" data-m="v">Vulnerable</button><button data-m="s">Secured</button></div>
<div class="demo">
<div class="card">
<span class="mode v" id="modeTag">VULNERABLE VERSION</span>
<h3>Login</h3>
<div><label for="u">username</label><input id="u" autocomplete="off" spellcheck="false" placeholder="admin"></div>
<div><label for="p">password</label><input id="p" type="text" autocomplete="off" spellcheck="false" placeholder="password"></div>
<div class="chips"><button class="chip" data-p="sql">SQL injection</button><button class="chip" data-p="bf">Brute force</button><button class="chip" data-p="ok">Normal login</button></div>
<button class="btn btn-p" id="go" style="justify-self:start">Log in</button>
<div class="qbox" id="q">Query will appear here.</div>
<div class="out" id="res" aria-live="polite">Waiting for a login attempt.</div>
</div>
<div class="card">
<span class="mode v" id="modeTag2">VULNERABLE VERSION</span>
<h3>Comment wall</h3>
<div><label for="c">your comment</label><textarea id="c" spellcheck="false" placeholder="Nice project!"></textarea></div>
<div class="chips"><button class="chip" data-p="xss">XSS payload</button><button class="chip" data-p="plain">Normal comment</button></div>
<button class="btn btn-p" id="post" style="justify-self:start">Post comment</button>
<div class="wall" id="wall">No comments yet.</div>
<div class="out" id="xres" aria-live="polite">Waiting for a comment.</div>
</div>
</div>
<p class="note">This demo runs inside your browser as a simulation of the same logic, because GitHub Pages cannot run a Flask server. Nothing is sent anywhere. The comment preview is sandboxed, so no real script can run.</p>
</div></section>

<section id="learned"><div class="wrap">
<h2 class="h2 rv">Security checklist</h2>
<p class="lede rv">What this project teaches in one list.</p>
<div class="card rv"><ul class="cl">
<li>Never build queries from raw input</li><li>Validate every input on the server</li>
<li>Hash passwords, never store plain text</li><li>Escape everything you print</li>
<li>Limit login attempts</li><li>Use CSRF tokens in forms</li>
<li>Send security headers</li><li>Keep secrets out of the code</li>
</ul></div>
<h2 class="h2 rv" style="margin-top:56px">What I learned</h2>
<div class="grid2" style="margin-top:20px">
<div class="card rv"><h3>Skills</h3><p>Flask routing, safe database queries, password hashing, output escaping, and presenting a technical idea clearly to an audience.</p></div>
<div class="card rv"><h3>Next steps</h3><ul><li>Add a scoreboard of blocked attacks</li><li>Host the real Flask app online</li><li>Reuse it in a hackathon</li></ul></div>
</div></div></section>

<footer>Built by <b>Maniraj Kumar</b> · Team Bug Busters · <a href="index.html" style="color:var(--acc)">Back to portfolio</a></footer>

<script>
const $=(s,r=document)=>r.querySelector(s),$$=(s,r=document)=>[...r.querySelectorAll(s)];
/* reveal + progress */
const io=new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('in');io.unobserve(e.target)}}),{threshold:.15});
$$('.rv').forEach(el=>io.observe(el));
addEventListener('scroll',()=>{const h=document.documentElement.scrollHeight-innerHeight;$('#progress').style.transform=`scaleX(${h?scrollY/h:0})`},{passive:true});

/* ---------- demo ---------- */
const USERS=[{u:'admin',p:'Admin@123',role:'Administrator'},{u:'maniraj',p:'Dev@2026',role:'Student'}];
let mode='v',fails=0,locked=false,timer=null;
async function sha(t){try{const b=await crypto.subtle.digest('SHA-256',new TextEncoder().encode(t));return[...new Uint8Array(b)].map(x=>x.toString(16).padStart(2,'0')).join('')}catch(e){let h=2166136261;for(const c of t){h^=c.charCodeAt(0);h=Math.imul(h,16777619)}return(h>>>0).toString(16).padStart(8,'0')}}
const esc=t=>t.replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
const out=(el,cls,txt)=>{el.className='out '+cls;el.textContent=txt};
const inj=t=>/'\s*or\s*'?\d+'?\s*=\s*'?\d+/i.test(t)||/'\s*(--|#)/.test(t);
const R={q:$('#q'),res:$('#res'),u:$('#u'),p:$('#p'),x:$('#xres'),wall:$('#wall'),c:$('#c')};
function setMode(m){mode=m;fails=0;locked=false;clearInterval(timer);
 $$('.seg button').forEach(b=>b.classList.toggle('on',b.dataset.m===m));
 [$('#modeTag'),$('#modeTag2')].forEach(t=>{t.className='mode '+m;t.textContent=m==='v'?'VULNERABLE VERSION':'SECURED VERSION'});
 R.q.textContent='Query will appear here.';out(R.res,'','Waiting for a login attempt.');out(R.x,'','Waiting for a comment.');R.wall.textContent='No comments yet.'}
$$('.seg button').forEach(b=>b.onclick=()=>setMode(b.dataset.m));
async function login(u,p){
 if(mode==='v'){
  R.q.textContent=`SELECT * FROM users WHERE username='${u}' AND password='${p}'`;
  if(inj(u)||inj(p)){fails=0;return out(R.res,'bad','⚠ Logged in as admin (Administrator) with NO password. SQL injection worked.')}
  const f=USERS.find(x=>x.u===u&&x.p===p);fails++;
  return f?out(R.res,'good',`Logged in as ${f.u} (${f.role}).`):out(R.res,'warn',`Wrong login. Attempt #${fails}. No limit, you can keep guessing forever.`);
 }
 if(locked)return out(R.res,'warn','🔒 Locked. Too many failed attempts. Please wait.');
 R.q.textContent=`SELECT * FROM users WHERE username = ?   params: ["${u}"]`;
 if(!/^[A-Za-z0-9_]{3,20}$/.test(u))return out(R.res,'good','✔ Blocked. Input validation rejected the username before it reached the database.');
 const f=USERS.find(x=>x.u===u);
 if(f&&await sha(p)===await sha(f.p)){fails=0;return out(R.res,'good',`Logged in as ${f.u} (${f.role}). Password was checked as a hash.`)}
 fails++;
 if(fails>=3){locked=true;let s=10;out(R.res,'warn',`🔒 Locked for ${s}s after 3 failed attempts (rate limiting).`);
  timer=setInterval(()=>{s--;if(s<=0){clearInterval(timer);locked=false;fails=0;out(R.res,'','Unlocked. You can try again.')}else out(R.res,'warn',`🔒 Locked for ${s}s after 3 failed attempts (rate limiting).`)},1000);return}
 out(R.res,'warn',`Wrong login. Attempt ${fails} of 3.`)}
$('#go').onclick=()=>login(R.u.value.trim(),R.p.value);
async function brute(){const g=['123456','password','admin','qwerty','admin123','letmein','Admin@123'];R.u.value='admin';let n=0;
 for(const p of g){n++;R.p.value=p;await login('admin',p);
  if(mode==='v'&&/^Logged in/.test(R.res.textContent)){return out(R.res,'bad',`⚠ Password cracked in ${n} tries (${p}). Nothing stopped the guessing.`)}
  if(mode==='s'&&locked){return out(R.res,'good',`✔ Brute force stopped after ${n} tries. The account got locked.`)}
  await new Promise(r=>setTimeout(r,350))}}
$$('.chip').forEach(c=>c.onclick=()=>{const k=c.dataset.p;
 if(k==='sql'){R.u.value="admin' --";R.p.value='anything'}
 else if(k==='ok'){R.u.value='maniraj';R.p.value='Dev@2026'}
 else if(k==='bf'){brute()}
 else if(k==='xss'){R.c.value='<img src=x onerror="alert(document.cookie)">'}
 else if(k==='plain'){R.c.value='Great project, Bug Busters!'}});
$('#post').onclick=()=>{const t=R.c.value.trim();if(!t)return;
 if(mode==='v'){
  R.wall.innerHTML='<iframe sandbox title="Unsafe preview"></iframe>';$('iframe',R.wall).srcdoc=t;
  /<\s*script|on\w+\s*=|javascript:/i.test(t)?out(R.x,'bad','⚠ XSS: the page printed your input as real HTML. In a real site this script would run for every visitor and could steal their session.'):out(R.x,'good','Comment posted.');
 }else{
  R.wall.textContent=t;
  /<|>/.test(t)?out(R.x,'good','✔ Blocked. The input was escaped, so the script is shown as harmless text.'):out(R.x,'good','Comment posted (escaped).')}};
</script>
</body>
</html>
