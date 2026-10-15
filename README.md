🛡️ Hack-Proof Web App
One website, two versions. First a deliberately vulnerable site that can be attacked, then the same site secured so the attacks fail.
Built by Maniraj Kumar and Team Bug Busters for Tech Forge 2026 at Government Polytechnic Khagaria.


Backend
Python, Flask
Frontend
HTML, CSS, JavaScript
Runs on
Termux (Android phone)
Team
Bug Busters (2 members)
🔗 Live demo and full presentation: https://ermaniraj008-del.github.io/My-portfolio-/hack-proof-presentation.html
📌 Table of contents
The idea
Step-by-step: how it was built
Attack vs fix
How to run it
Security checklist
What I learned
Team
💡 The idea
Many websites get hacked because of small mistakes. Beginners build login pages and comment boxes that trust whatever the user types. Attackers use that trust to:
log in without a password,
run scripts in other people's browsers,
guess passwords again and again.
This project shows those mistakes live, then shows how to fix each one.
Goals
Show real attacks on a vulnerable version
Show the secured version blocking the same attacks
Explain every fix in simple words
Make it easy to run on a phone
🪜 Step-by-step: how it was built
Step 1: Pick the idea and the stack
The idea was a demo that stands out: a website that is hacked live, then fixed. The stack is Flask for the server and plain HTML, CSS and JavaScript for the pages, so it stays light enough for a phone.
Step 2: Set up Flask on Termux
pkg update && pkg upgrade
pkg install python git
pip install flask flask-wtf flask-limiter
mkdir hack-proof-app && cd hack-proof-app
Step 3: Plan the two versions
Keep one shared look but two behaviours: a vulnerable version and a secured version of the same pages. Both have:
a login page (tests SQL injection and brute force)
a comment page (tests XSS, which means script injection)
Step 4: Build the vulnerable version on purpose
Write the code the way beginners often do: join user input straight into the database query, store passwords as plain text, and print comments without cleaning them.
# VULNERABLE login
u = request.form['username']
p = request.form['password']
q = f"SELECT * FROM users WHERE username='{u}' AND password='{p}'"   # dangerous
user = db.execute(q).fetchone()
Step 5: Attack it (the demo part)
Show three attacks on the vulnerable version:
Type admin' -- as the username to skip the password check (SQL injection)
Post a script in the comment box so it runs for every visitor (XSS)
Guess passwords many times with no limit (brute force)
Step 6: Fix each problem in the secured version
# SECURED login
import re
from werkzeug.security import check_password_hash

u = request.form['username'].strip()
if not re.fullmatch(r'[A-Za-z0-9_]{3,20}', u):      # validate input
    abort(400)

user = db.execute("SELECT * FROM users WHERE username = ?", (u,)).fetchone()   # safe query
if user and check_password_hash(user['password_hash'], request.form['password']):
    ...   # logged in
Parameterized queries stop SQL injection
Password hashing means a stolen database does not reveal passwords
Output escaping (Jinja2 autoescape) turns scripts into harmless text
Flask-Limiter locks guessing attacks, Flask-WTF adds CSRF tokens
Step 7: Add security headers
@app.after_request
def secure(r):
    r.headers['Content-Security-Policy'] = "default-src 'self'"
    r.headers['X-Content-Type-Options'] = 'nosniff'
    r.headers['X-Frame-Options'] = 'DENY'
    return r
Step 8: Run it and present it
python app.py
# open http://127.0.0.1:5000 in the phone browser
On stage, run the attack on the vulnerable version first, then the same attack on the secured version, and compare.
⚔️ Attack vs fix
Attack
Why the vulnerable version fails
Fix in the secured version
SQL injection
User input is glued into the query, so admin' -- removes the password check
Parameterized queries and input validation
XSS
A comment with a script tag is shown as real HTML and runs for every visitor
Escape all output and set a Content-Security-Policy header
Brute force
Unlimited password guesses, so a weak password falls quickly
Rate limiting, temporary lock, hashed passwords
CSRF
Another site can send a request the user never meant to make
Secret CSRF token in every form
▶️ How to run it
On Termux (Android)
pkg install python git
git clone https://github.com/ermaniraj008-del/Web-proof-app-.git
cd Web-proof-app-
pip install flask flask-wtf flask-limiter
python app.py
Then open http://127.0.0.1:5000 in your browser.
On a computer
git clone https://github.com/ermaniraj008-del/Web-proof-app-.git
cd Web-proof-app-
pip install flask flask-wtf flask-limiter
python app.py
The browser demo on the presentation page is a simulation of the same logic. The real Flask app runs locally with the steps above.
✅ Security checklist
[x] Never build queries from raw input
[x] Validate every input on the server
[x] Hash passwords, never store plain text
[x] Escape everything you print
[x] Limit login attempts
[x] Use CSRF tokens in forms
[x] Send security headers
[x] Keep secrets out of the code
🎓 What I learned
Flask routing and forms
Safe database queries
Password hashing
Output escaping and security headers
Explaining a technical idea clearly to an audience
Next steps
Add a scoreboard of blocked attacks
Host the real Flask app online
Reuse it in a hackathon
👥 Team
Bug Busters: Maniraj Kumar and teammate
Government Polytechnic Khagaria, Computer Science & Engineering
🌐 Portfolio: https://ermaniraj008-del.github.io/My-portfolio-/
