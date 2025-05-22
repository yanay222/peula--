import zipfile
import os

# תוכן הקובץ index.html (קוד דף הבית שהכנתי)
html_content = """
<!DOCTYPE html>
<html lang="he">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>פעולה.נט - בית לחם הגלילית</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f8ff;
      color: #003366;
      margin: 0;
      padding: 0;
      direction: rtl;
    }
    header {
      background-color: #004080;
      padding: 20px;
      text-align: center;
      color: white;
      font-size: 1.8em;
      font-weight: bold;
    }
    nav {
      background-color: #0066cc;
      padding: 10px 0;
      text-align: center;
    }
    nav a {
      color: white;
      text-decoration: none;
      margin: 0 15px;
      font-weight: bold;
      font-size: 1.1em;
    }
    nav a:hover {
      text-decoration: underline;
    }
    main {
      padding: 40px 20px;
      max-width: 800px;
      margin: auto;
      text-align: center;
    }
    main h1 {
      font-size: 2.2em;
      margin-bottom: 20px;
    }
    main p {
      font-size: 1.2em;
      line-height: 1.6em;
      margin-bottom: 40px;
    }
    .btn-login {
      background-color: #003366;
      color: white;
      padding: 15px 30px;
      font-size: 1.2em;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      text-decoration: none;
    }
    .btn-login:hover {
      background-color: #002244;
    }
    footer {
      background-color: #004080;
      color: white;
      text-align: center;
      padding: 15px 0;
      margin-top: 40px;
      font-size: 0.9em;
    }
  </style>
</head>
<body>
  <header>
    🛡️ מושב בית לחם הגלילית - פעולה.נט
  </header>
  <nav>
    <a href="#">בית</a>
    <a href="#">אודות</a>
    <a href="#">צור קשר</a>
    <a href="#">כניסה</a>
  </nav>
  <main>
    <h1>ברוכים הבאים לפעולה.נט</h1>
    <p>המערכת למדריכי מושב בית לחם הגלילית לניהול פעילויות, יצירת פעולות ותקשורת קלה בין המדריכים.</p>
    <a href="#" class="btn-login">כניסה למדריכים</a>
  </main>
  <footer>
    &copy; 2025 מושב בית לחם הגלילית
  </footer>
</body>
</html>
"""

# שמירת הקובץ index.html
with open("/mnt/data/index.html", "w", encoding="utf-8") as f:
    f.write(html_content)

# יצירת קובץ ZIP המכיל את index.html
zip_path = "/mnt/data/peula_net.zip"
with zipfile.ZipFile(zip_path, 'w') as zipf:
    zipf.write("/mnt/data/index.html", arcname="index.html")

zip_path
