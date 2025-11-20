# Web Practicals — HTML5 / CSS / JavaScript

This repository contains 8 practical exercises (ready-to-upload) for HTML5, CSS and JavaScript. Each exercise has files you can place in a folder and open the main HTML file in a browser. Below are the code snippets and short usage notes. Copy each file to its filename and push to GitHub.

---

## 1. Create a Web page using HTML5 Formatting Tags (CO1)

**Files:** `formatting.html`

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>HTML5 Formatting Tags</title>
</head>
<body>
  <header>
    <h1>HTML5 Formatting Tags Demo</h1>
    <p><em>Simple showcase of semantic and formatting tags</em></p>
  </header>

  <main>
    <section>
      <h2>Text Semantics</h2>
      <p>This paragraph shows <strong>strong</strong>, <em>emphasis</em>, <mark>highlight</mark>, and <small>small print</small>.</p>
      <p>Sample: <ins>inserted text</ins> and <del>deleted text</del>.</p>
    </section>

    <section>
      <h2>Inline Elements</h2>
      <p>Keyboard: <kbd>Ctrl</kbd> + <kbd>C</kbd>. Variable: <var>x</var>. Sample code: <code>console.log('hi')</code>.</p>
    </section>

    <section>
      <h2>Block Elements</h2>
      <article>
        <h3>Article Title</h3>
        <p>This is an <code>&lt;article&gt;</code> block containing a <q>short quote</q> and a <blockquote cite="#">longer quotation block</blockquote>.</p>
      </article>

      <aside>
        <h4>Aside</h4>
        <p>Related note or tip goes here.</p>
      </aside>
    </section>
  </main>

  <footer>
    <p>Author: Pandi Harshan | Practical 1</p>
  </footer>
</body>
</html>
```

---

## 2. Create a Web page using HTML5 List & Tables (CO1)

**Files:** `lists_tables.html`

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Lists and Tables</title>
  <style>
    table { border-collapse: collapse; width: 100%; }
    th, td { border: 1px solid #444; padding: 8px; text-align: left; }
    th { background: #eee; }
  </style>
</head>
<body>
  <h1>HTML Lists & Tables</h1>

  <section>
    <h2>Ordered List</h2>
    <ol>
      <li>First item</li>
      <li>Second item
        <ol type="a">
          <li>Sub item a</li>
          <li>Sub item b</li>
        </ol>
      </li>
      <li>Third item</li>
    </ol>
  </section>

  <section>
    <h2>Unordered List</h2>
    <ul>
      <li>Bullet one</li>
      <li>Bullet two
        <ul>
          <li>Nested bullet</li>
        </ul>
      </li>
    </ul>
  </section>

  <section>
    <h2>Definition List</h2>
    <dl>
      <dt>HTML</dt>
      <dd>Hypertext Markup Language</dd>
      <dt>CSS</dt>
      <dd>Cascading Style Sheets</dd>
    </dl>
  </section>

  <section>
    <h2>Table Example</h2>
    <table>
      <caption>Student Marks</caption>
      <thead>
        <tr><th>Roll</th><th>Name</th><th>Maths</th><th>Science</th></tr>
      </thead>
      <tbody>
        <tr><td>1</td><td>Asha</td><td>85</td><td>90</td></tr>
        <tr><td>2</td><td>Rohan</td><td>78</td><td>82</td></tr>
        <tr><td>3</td><td>Kavya</td><td>92</td><td>88</td></tr>
      </tbody>
      <tfoot>
        <tr><td colspan="4">Generated for practical: Lists & Tables</td></tr>
      </tfoot>
    </table>
  </section>
</body>
</html>
```

---

## 3. Design a Web page to capture data using HTML forms (CO2)

**Files:** `form_capture.html`

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Form Capture</title>
</head>
<body>
  <h1>Student Registration Form</h1>
  <form id="regForm" action="#" method="post">
    <label>Full Name:<br>
      <input type="text" name="fullname" required>
    </label><br><br>

    <label>Email:<br>
      <input type="email" name="email" required>
    </label><br><br>

    <label>Gender:<br>
      <input type="radio" name="gender" value="male"> Male
      <input type="radio" name="gender" value="female"> Female
      <input type="radio" name="gender" value="other"> Other
    </label><br><br>

    <label>Courses:<br>
      <select name="course">
        <option value="bsc">B.Sc</option>
        <option value="btech">B.Tech</option>
        <option value="msc">M.Sc</option>
      </select>
    </label><br><br>

    <label>Skills:<br>
      <input type="checkbox" name="skill" value="html"> HTML
      <input type="checkbox" name="skill" value="css"> CSS
      <input type="checkbox" name="skill" value="js"> JavaScript
    </label><br><br>

    <label>About You:<br>
      <textarea name="about" rows="4" cols="40"></textarea>
    </label><br><br>

    <button type="submit">Submit</button>
    <button type="reset">Reset</button>
  </form>

  <script>
    // Simple handler to show submitted values (no server)
    document.getElementById('regForm').addEventListener('submit', function(e){
      e.preventDefault();
      const data = new FormData(this);
      const obj = {};
      for (const [k,v] of data.entries()) obj[k]=v;
      alert('Form submitted (preview):\n' + JSON.stringify(obj, null, 2));
    });
  </script>
</body>
</html>
```

---

## 4. Create a Web page with CSS Styles – Internal & External Style Sheet (CO2)

**Files:** `styles_internal.html`, `styles_external.css`

**styles_external.css**

```css
body{font-family: Arial, sans-serif; margin:20px}
.header{background:#0b6; padding:12px; border-radius:6px}
.card{border:1px solid #ccc; padding:12px; margin:12px 0; border-radius:6px}
.btn{display:inline-block; padding:8px 12px; border-radius:4px; text-decoration:none}
```

**styles_internal.html**

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>CSS Internal & External</title>
  <link rel="stylesheet" href="styles_external.css">
  <style>
    .internal-note{color:#444; font-style:italic}
    .btn.primary{background:#0066cc; color:#fff}
  </style>
</head>
<body>
  <div class="header">
    <h1>External + Internal CSS Example</h1>
    <p class="internal-note">This paragraph is styled using an internal stylesheet.</p>
  </div>

  <div class="card">
    <h2>Content Card</h2>
    <p>This card gets border and padding from the external stylesheet.</p>
    <a class="btn primary" href="#">Primary Action</a>
  </div>
</body>
</html>
```

---

## 5. Create a Web page with Navigation Menu and hover effect using HTML and CSS (CO3)

**Files:** `nav_menu.html`, `nav_style.css`

**nav_style.css**

```css
*{box-sizing:border-box}
nav{background:#333}
nav ul{list-style:none; margin:0; padding:0; display:flex}
nav li{margin:0}
nav a{display:block; padding:14px 20px; color:#fff; text-decoration:none}
nav a:hover{background:#555}
.active{background:#0077cc}
.container{padding:16px}
```

**nav_menu.html**

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Navigation Menu</title>
  <link rel="stylesheet" href="nav_style.css">
</head>
<body>
  <nav>
    <ul>
      <li><a href="#home" class="active">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
  <div class="container">
    <h1>Navigation with Hover</h1>
    <p>Hover over menu items to see the effect.</p>
  </div>
</body>
</html>
```

---

## 6. Perform a client side validation using JavaScript user defined function and DOM objects (CO3)

**Files:** `client_validation.html`

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Client-side Validation</title>
  <style>.error{color:red}</style>
</head>
<body>
  <h1>Login Form with Client-side Validation</h1>
  <form id="loginForm" novalidate>
    <label>Username:<br><input type="text" id="username" required></label><br><br>
    <label>Password:<br><input type="password" id="password" required></label><br><br>
    <button type="submit">Login</button>
  </form>
  <p id="msg" class="error"></p>

  <script>
    function validateUser(){
      const u = document.getElementById('username').value.trim();
      const p = document.getElementById('password').value;
      if(u.length < 3) return 'Username must be at least 3 characters';
      if(p.length < 6) return 'Password must be at least 6 characters';
      return '';
    }

    document.getElementById('loginForm').addEventListener('submit', function(e){
      e.preventDefault();
      const err = validateUser();
      const msg = document.getElementById('msg');
      if(err){ msg.textContent = err; }
      else { msg.textContent='Login successful (client-side)'; }
    });
  </script>
</body>
</html>
```

---

## 7. Design a Web page to illustrate the concept of event handling through JavaScript (CO4)

**Files:** `event_handling.html`

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Event Handling Demo</title>
  <style>
    #box{width:150px;height:150px;border:2px solid #333;display:flex;align-items:center;justify-content:center;margin:20px}
    .controls button{margin:4px}
  </style>
</head>
<body>
  <h1>Event Handling Examples</h1>
  <div id="box">Hover or Click me</div>
  <div class="controls">
    <button id="btnClick">Click</button>
    <button id="btnDbl">Double Click</button>
    <button id="btnKey">Listen Keydown</button>
  </div>
  <p id="log">Event log will appear here</p>

  <script>
    const box = document.getElementById('box');
    const log = document.getElementById('log');

    box.addEventListener('mouseenter', ()=> log.textContent = 'Mouse entered box');
    box.addEventListener('mouseleave', ()=> log.textContent = 'Mouse left box');
    box.addEventListener('click', ()=> log.textContent = 'Box clicked');

    document.getElementById('btnClick').addEventListener('click', ()=> alert('Button clicked'));
    document.getElementById('btnDbl').addEventListener('dblclick', ()=> alert('Button double clicked'));

    let keyListening = false;
    document.getElementById('btnKey').addEventListener('click', ()=>{
      if(keyListening) return;
      keyListening = true;
      log.textContent = 'Press any key...';
      window.addEventListener('keydown', function onKey(e){
        log.textContent = 'Key pressed: ' + e.key;
        window.removeEventListener('keydown', onKey);
        keyListening = false;
      });
    });
  </script>
</body>
</html>
```

---

## 8. Develop a Web page and perform login validation and Navigation using JavaScript (CO4)

**Files:** `login_nav.html`

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Login + Navigation</title>
  <style>
    body{font-family:Arial;margin:20px}
    #app{max-width:600px}
    nav a{margin-right:8px}
  </style>
</head>
<body>
  <div id="app">
    <h1>Login and Simple Navigation</h1>

    <div id="loginView">
      <h2>Login</h2>
      <form id="loginForm">
        <label>Username:<br><input id="user" required></label><br><br>
        <label>Password:<br><input id="pass" type="password" required></label><br><br>
        <button type="submit">Login</button>
      </form>
      <p id="loginMsg" style="color:red"></p>
    </div>

    <div id="mainView" style="display:none">
      <nav>
        <a href="#home" data-target="home">Home</a>
        <a href="#profile" data-target="profile">Profile</a>
        <a href="#logout" id="logoutLink">Logout</a>
      </nav>

      <section id="home" class="page"> 
        <h2>Home</h2>
        <p>Welcome to the home page.</p>
      </section>

      <section id="profile" class="page" style="display:none">
        <h2>Profile</h2>
        <p id="profileInfo"></p>
      </section>
    </div>
  </div>

  <script>
    const loginForm = document.getElementById('loginForm');
    const loginView = document.getElementById('loginView');
    const mainView = document.getElementById('mainView');
    const loginMsg = document.getElementById('loginMsg');

    // Simple hard-coded credentials (for practical only)
    const CREDENTIALS = { user: 'student', pass: 'password123' };

    loginForm.addEventListener('submit', function(e){
      e.preventDefault();
      const u = document.getElementById('user').value.trim();
      const p = document.getElementById('pass').value;
      if(u === CREDENTIALS.user && p === CREDENTIALS.pass){
        loginMsg.textContent = '';
        loginView.style.display = 'none';
        mainView.style.display = 'block';
        document.getElementById('profileInfo').textContent = 'Username: ' + u + '\nRole: Student';
      } else {
        loginMsg.textContent = 'Invalid credentials';
      }
    });

    // Navigation handling
    document.querySelectorAll('nav a[data-target]').forEach(a => {
      a.addEventListener('click', function(e){
        e.preventDefault();
```
