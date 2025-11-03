from zipfile import ZipFile
from PIL import Image, ImageDraw, ImageFont
import os

# --- Create favicon (rose gold "T") ---
size = (64, 64)
favicon = Image.new("RGBA", size, (0, 0, 0, 0))
draw = ImageDraw.Draw(favicon)
font = ImageFont.load_default()
text = "T"
tw, th = draw.textsize(text, font=font)
draw.text(((size[0]-tw)/2, (size[1]-th)/2), text, fill=(183, 110, 121, 255), font=font)
os.makedirs("thabisile-portfolio/assets", exist_ok=True)
favicon.save("thabisile-portfolio/assets/favicon.ico", format="ICO")

# --- index.html with rose gold theme + fade-in scroll animations ---
index_html = """<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Thabisile Mbonambi | Business Analyst & SaaS Solutions Specialist - Open to Remote Roles">
  <title>Thabisile Mbonambi | Business Analyst</title>
  <link rel="icon" href="assets/favicon.ico" type="image/x-icon">
  <style>
    body {font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; margin: 0; padding: 0; background-color: #fff5f5; color: #333;}
    
    header {
      background: linear-gradient(135deg, #b76e79, #f7cac9);
      color: white;
      text-align: center;
      padding: 60px 20px 40px 20px;
    }
    header h1 {margin: 0; font-size: 2.5rem;}
    header h2 {font-weight: normal; margin-top: 10px; font-size: 1.2rem;}

    .remote-banner {
      background-color: #ffe6e6; 
      color: #b76e79; 
      font-weight: 600; 
      text-align: center; 
      padding: 10px;
    }

    main {max-width: 900px; margin: 40px auto; background: white; padding: 30px; border-radius: 10px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);}

    section {margin-bottom: 30px; opacity: 0; transform: translateY(30px); transition: opacity 0.8s ease-out, transform 0.8s ease-out;}

    section.visible {opacity: 1; transform: translateY(0);}

    h3 {
      background: linear-gradient(90deg, #b76e79, #f7cac9);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      border-bottom: 2px solid #b76e79;
      padding-bottom: 6px;
      margin-bottom: 12px;
      transition: 0.3s;
    }
    h3:hover {opacity: 0.8;}

    ul {list-style-type: none; padding: 0;}
    li {margin-bottom: 6px;}

    .buttons {text-align: center; margin-top: 40px;}
    .btn {
      text-decoration: none;
      background-color: #b76e79;
      color: white;
      padding: 12px 24px;
      border-radius: 6px;
      margin: 6px;
      display: inline-block;
      transition: all 0.3s ease;
    }
    .btn:hover {background: linear-gradient(135deg, #b76e79, #f7cac9); color: white; transform: scale(1.05);}

    footer {text-align: center; padding: 20px; font-size: 0.9rem; color: #777;}

    @media (max-width: 600px) {
      header h1 {font-size: 1.8rem;}
      main {margin: 20px; padding: 20px;}
    }
  </style>
</head>
<body>
  <header>
    <h1>Thabisile Mbonambi</h1>
    <h2>Business Analyst | SaaS Solutions Specialist | Key Account Manager</h2>
  </header>
  <div class="remote-banner">💼 Open to Remote Roles</div>
  <main>
    <section>
      <p>I help organizations bridge technology and business needs, armed with a BCom in Business Informatics and over 10 years of SaaS solution experience. My background combining core IT systems with business strategy gives me the perfect lens to analyze operational challenges and design tech-driven solutions.</p>
    </section>
    <section>
      <h3>Core Skills</h3>
      <ul>
        <li>Business & Systems Analysis</li>
        <li>Requirements Gathering & Stakeholder Management</li>
        <li>Data Querying (Oracle SQL)</li>
        <li>Process Optimization & Workflow Design</li>
        <li>Agile & Scrum Methodologies</li>
        <li>Project Planning & Execution</li>
        <li>Change Management & Risk Mitigation</li>
        <li>SaaS Solutions Implementation</li>
        <li>Client Relationship Management</li>
      </ul>
    </section>
    <section>
      <h3>Professional Experience</h3>
      <p><strong>Key Account Manager — VSc Solutions (2024–Present)</strong><br>Closed R1.6M in EDI contracts, led system mock-ups, streamlined onboarding by 40%, and mentored junior analysts.</p>
      <p><strong>Senior Customer Success Manager — VSc Solutions (2021–2023)</strong><br>Generated R19M+ in revenue, improved Jira workflows, enhanced platform adoption by 60%, and delivered 50+ customer implementations.</p>
      <p><strong>Business Development Manager — M2North (2013–2021)</strong><br>Secured multi-year SaaS contracts, managed large-scale implementations, and achieved 92% client retention rate.</p>
    </section>
    <section>
      <h3>Education & Certifications</h3>
      <ul>
        <li><strong>Bachelor of Commerce in Business Informatics</strong> — University of South Africa</li>
        <li><strong>Higher Certificate in Economics, Management & Science</strong> — University of South Africa</li>
      </ul>
      <p><strong>Professional Certifications:</strong><br>Project Management Principles (UP), Agile Scrum Master (Simplilearn), Business Analysis & Jira (Udemy), Transitioning from Waterfall to Agile (LinkedIn), Blockchain for Business (Udemy), Intro to CyberSecurity (Cisco)</p>
    </section>
    <section>
      <h3>Achievements</h3>
      <ul>
        <li>Generated R19M+ in revenue over 4 years</li>
        <li>Reduced onboarding time by 30% through process optimization</li>
        <li>Led Agile transformation and stakeholder workshops</li>
        <li>Employee of the Year — M2North (2019)</li>
      </ul>
    </section>
    <section>
      <h3>Availability</h3>
      <p>Available with a two-month notice period (negotiable). Expected CTC: R850,000 p.a.</p>
    </section>
    <div class="buttons">
      <a class="btn" href="mailto:tabymbonambi@gmail.com">Contact Me</a>
      <a class="btn" href="https://www.linkedin.com/in/thabisile-mbonambi-37856273" target="_blank">View LinkedIn Profile</a>
    </div>
  </main>
  <footer>
    © 2025 Thabisile Mbonambi | All rights reserved
  </footer>

  <script>
    // Scroll-triggered fade-in animation
    document.addEventListener('DOMContentLoaded', () => {
      const sections = document.querySelectorAll('section');
      const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => {
          if(entry.isIntersecting) entry.target.classList.add('visible');
        });
      }, { threshold: 0.2 });
      sections.forEach(section => observer.observe(section));
    });
  </script>
</body>
</html>
"""

# --- README.md ---
readme_md = """# Thabisile Mbonambi | Business Analyst & SaaS Solutions Specialist

Static landing page with rose gold gradient header, premium gradient buttons, modern gradient headers, and smooth scroll fade-in animations.  

🌐 **Live Site:** [https://Bisile27.github.io/thabisile-portfolio/](https://Bisile27.github.io/thabisile-portfolio/)

## 🚀 How to View Locally
```bash
git clone https://github.com/Bisile27/thabisile-portfolio.git
cd thabisile-portfolio
open index.html

