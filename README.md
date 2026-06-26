<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Saeed Ullah — Data Analyst</title>
<style>
  :root{
    --bg:#0B1A14;
    --bg-soft:#0F2419;
    --panel:#11281F;
    --panel-border:#1E3D2E;
    --ink:#EAF3EE;
    --ink-dim:#9FB8AC;
    --ink-faint:#5C7A6E;
    --green:#34D399;
    --green-soft:#A7F3D0;
    --green-deep:#0E5B3D;
    --mono: "JetBrains Mono","SFMono-Regular",Consolas,monospace;
    --sans: "Inter","Segoe UI",system-ui,-apple-system,sans-serif;
  }

  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:
      radial-gradient(circle at 12% 8%, rgba(52,211,153,0.07), transparent 40%),
      radial-gradient(circle at 88% 60%, rgba(52,211,153,0.05), transparent 45%),
      var(--bg);
    color:var(--ink);
    font-family:var(--sans);
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }

  a{color:inherit; text-decoration:none;}

  ::selection{ background:var(--green); color:#06140F; }

  .wrap{ max-width:980px; margin:0 auto; padding:0 28px; }

  /* ---------- NAV ---------- */
  nav{
    position:sticky; top:0; z-index:50;
    background:rgba(11,26,20,0.85);
    backdrop-filter: blur(10px);
    border-bottom:1px solid var(--panel-border);
  }
  nav .wrap{
    display:flex; align-items:center; justify-content:space-between;
    height:64px;
  }
  .brand{
    font-family:var(--mono); font-size:14px; letter-spacing:0.04em;
    color:var(--green-soft); display:flex; align-items:center; gap:8px;
  }
  .brand .dot{ width:7px; height:7px; border-radius:50%; background:var(--green); box-shadow:0 0 8px var(--green); }
  .navlinks{ display:flex; gap:28px; font-size:14px; color:var(--ink-dim); }
  .navlinks a{ transition:color .2s; }
  .navlinks a:hover{ color:var(--green-soft); }
  .navlinks .cta{
    border:1px solid var(--green-deep); padding:7px 14px; border-radius:6px;
    color:var(--green-soft); font-family:var(--mono); font-size:12.5px;
  }
  .navlinks .cta:hover{ background:var(--green-deep); }

  @media (max-width:680px){ .navlinks{ display:none; } }

  /* ---------- HERO ---------- */
  header.hero{ padding:88px 0 64px; border-bottom:1px solid var(--panel-border); }
  .eyebrow{
    font-family:var(--mono); font-size:12.5px; letter-spacing:0.12em;
    text-transform:uppercase; color:var(--green); margin-bottom:18px;
    display:flex; align-items:center; gap:10px;
  }
  .eyebrow::before{ content:""; width:18px; height:1px; background:var(--green); }

  h1{
    font-size:clamp(40px,6vw,64px); font-weight:700; letter-spacing:-0.02em;
    line-height:1.05; color:var(--ink);
  }
  h1 .accent{ color:var(--green-soft); }

  .role-line{
    margin-top:18px; font-size:18px; color:var(--ink-dim); max-width:620px;
  }
  .role-line strong{ color:var(--ink); font-weight:600; }

  .hero-meta{
    margin-top:30px; display:flex; flex-wrap:wrap; gap:10px;
  }
  .pill{
    font-family:var(--mono); font-size:12.5px; color:var(--ink-dim);
    border:1px solid var(--panel-border); background:var(--panel);
    padding:6px 12px; border-radius:20px;
  }

  /* ---------- METRIC STRIP (signature element) ---------- */
  .metrics{
    margin-top:48px; display:grid; grid-template-columns:repeat(4,1fr); gap:1px;
    background:var(--panel-border); border:1px solid var(--panel-border); border-radius:10px;
    overflow:hidden;
  }
  .metric{
    background:var(--bg-soft); padding:22px 18px; position:relative; overflow:hidden;
  }
  .metric .bars{
    position:absolute; bottom:0; left:0; right:0; height:34px;
    display:flex; align-items:flex-end; gap:3px; padding:0 18px; opacity:0.5;
  }
  .metric .bars span{
    flex:1; background:var(--green); border-radius:2px 2px 0 0;
    transform:scaleY(0); transform-origin:bottom;
    animation:rise .9s ease forwards;
  }
  @keyframes rise{ to{ transform:scaleY(1); } }
  .metric .num{
    font-family:var(--mono); font-size:28px; font-weight:700; color:var(--green-soft);
    position:relative; z-index:2;
  }
  .metric .label{
    font-size:12.5px; color:var(--ink-dim); margin-top:4px; position:relative; z-index:2;
  }
  @media (max-width:680px){ .metrics{ grid-template-columns:repeat(2,1fr); } }

  /* ---------- SECTION SCAFFOLD ---------- */
  section{ padding:64px 0; border-bottom:1px solid var(--panel-border); }
  .section-head{
    display:flex; align-items:baseline; justify-content:space-between;
    margin-bottom:36px; gap:16px;
  }
  .section-head h2{
    font-size:26px; font-weight:700; color:var(--ink); letter-spacing:-0.01em;
  }
  .section-tag{
    font-family:var(--mono); font-size:12px; color:var(--green); letter-spacing:.06em;
    text-transform:uppercase;
  }

  /* ---------- ABOUT ---------- */
  .about-grid{ display:grid; grid-template-columns:1.3fr 1fr; gap:48px; }
  .about-grid p{ color:var(--ink-dim); font-size:15.5px; margin-bottom:14px; }
  .about-grid p strong{ color:var(--ink); }
  .stack-list{ display:flex; flex-direction:column; gap:14px; }
  .stack-row{ display:flex; justify-content:space-between; border-bottom:1px dashed var(--panel-border); padding-bottom:10px; font-size:14px; }
  .stack-row span:first-child{ color:var(--ink-dim); font-family:var(--mono); font-size:12.5px; }
  .stack-row span:last-child{ color:var(--ink); text-align:right; max-width:62%; }
  @media (max-width:780px){ .about-grid{ grid-template-columns:1fr; } }

  /* ---------- SKILLS ---------- */
  .skills-grid{ display:grid; grid-template-columns:1fr 1fr; gap:32px; margin-top:56px; }
  .skill-group-label{
    font-family:var(--mono); font-size:12px; letter-spacing:.08em; text-transform:uppercase;
    color:var(--green); margin-bottom:14px; display:flex; align-items:center; gap:8px;
  }
  .skill-group-label::after{ content:""; flex:1; height:1px; background:var(--panel-border); }
  .tag-cloud{ display:flex; flex-wrap:wrap; gap:8px; }
  .tag{
    font-size:13px; color:var(--ink-dim); background:var(--panel);
    border:1px solid var(--panel-border); padding:6px 12px; border-radius:6px;
    transition:.2s;
  }
  .tag:hover{ border-color:var(--green-deep); color:var(--green-soft); }
  @media (max-width:780px){ .skills-grid{ grid-template-columns:1fr; } }

  /* ---------- PROJECTS ---------- */
  .project{
    background:var(--panel); border:1px solid var(--panel-border); border-radius:12px;
    padding:30px; margin-bottom:20px; position:relative; overflow:hidden;
    transition:border-color .25s, transform .25s;
  }
  .project:hover{ border-color:var(--green-deep); transform:translateY(-2px); }
  .project::before{
    content:""; position:absolute; top:0; left:0; width:3px; height:100%;
    background:var(--green); opacity:0.7;
  }
  .project-top{ display:flex; justify-content:space-between; align-items:flex-start; gap:16px; flex-wrap:wrap; }
  .project h3{ font-size:19px; color:var(--ink); font-weight:600; }
  .project .tools{
    font-family:var(--mono); font-size:11.5px; color:var(--green-soft);
    background:rgba(52,211,153,0.08); border:1px solid var(--green-deep);
    padding:4px 10px; border-radius:20px; white-space:nowrap;
  }
  .project ul{ margin-top:16px; padding-left:0; list-style:none; display:flex; flex-direction:column; gap:9px; }
  .project li{ color:var(--ink-dim); font-size:14.5px; padding-left:18px; position:relative; }
  .project li::before{ content:"→"; position:absolute; left:0; color:var(--green); font-family:var(--mono); }

  /* ---------- EXPERIENCE ---------- */
  .xp-row{ display:flex; gap:24px; padding:20px 0; border-bottom:1px solid var(--panel-border); }
  .xp-row:last-child{ border-bottom:none; }
  .xp-date{ font-family:var(--mono); font-size:12.5px; color:var(--ink-faint); min-width:130px; padding-top:3px; }
  .xp-body h4{ font-size:16.5px; color:var(--ink); font-weight:600; }
  .xp-body .org{ font-size:13.5px; color:var(--green-soft); margin-top:2px; margin-bottom:10px; }
  .xp-body ul{ list-style:none; display:flex; flex-direction:column; gap:7px; }
  .xp-body li{ color:var(--ink-dim); font-size:14px; padding-left:16px; position:relative; }
  .xp-body li::before{ content:"–"; position:absolute; left:0; color:var(--ink-faint); }
  @media (max-width:680px){ .xp-row{ flex-direction:column; gap:6px; } }

  /* ---------- CERTS ---------- */
  .cert-grid{ display:grid; grid-template-columns:repeat(2,1fr); gap:12px; }
  .cert{
    border:1px solid var(--panel-border); border-radius:8px; padding:14px 16px;
    font-size:13.5px; color:var(--ink-dim); display:flex; align-items:center; gap:10px;
  }
  .cert::before{ content:"✓"; color:var(--green); font-family:var(--mono); font-weight:700; }
  @media (max-width:680px){ .cert-grid{ grid-template-columns:1fr; } }

  /* ---------- CONTACT / FOOTER ---------- */
  footer{ padding:64px 0 48px; text-align:center; }
  footer h2{ font-size:30px; color:var(--ink); margin-bottom:14px; }
  footer p{ color:var(--ink-dim); max-width:480px; margin:0 auto 30px; }
  .contact-row{ display:flex; justify-content:center; gap:14px; flex-wrap:wrap; }
  .contact-btn{
    font-family:var(--mono); font-size:13px; padding:11px 20px; border-radius:8px;
    border:1px solid var(--panel-border); color:var(--ink-dim); transition:.2s;
  }
  .contact-btn.primary{ background:var(--green); color:#06140F; border-color:var(--green); font-weight:600; }
  .contact-btn:hover{ border-color:var(--green); color:var(--green-soft); }
  .contact-btn.primary:hover{ background:var(--green-soft); color:#06140F; }
  .foot-note{ margin-top:40px; font-family:var(--mono); font-size:11.5px; color:var(--ink-faint); }

  @media (prefers-reduced-motion: reduce){
    .metric .bars span{ animation:none; transform:scaleY(1); }
    html{ scroll-behavior:auto; }
  }
</style>
</head>
<body>

<nav>
  <div class="wrap">
    <div class="brand"><span class="dot"></span> SAEED ULLAH</div>
    <div class="navlinks">
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#experience">Experience</a>
      <a href="#certifications">Certifications</a>
      <a class="cta" href="#contact">Contact</a>
    </div>
  </div>
</nav>

<header class="hero">
  <div class="wrap">
    <div class="eyebrow">Riyadh, Saudi Arabia · Open to Data &amp; BI roles</div>
    <h1>Saeed Ullah<br><span class="accent">turns raw tables into decisions.</span></h1>
    <p class="role-line">
      Detail-oriented Computer Science graduate with hands-on experience in <strong>Data Analytics, Business
      Intelligence, and Reporting</strong> — skilled in SQL, Power BI, Excel, Tableau, and R, with practical
      experience in data cleaning, transformation, visualization, and dashboard development.
    </p>
    <div class="hero-meta">
      <span class="pill">Junior Data Analyst</span>
      <span class="pill">Reporting Analyst</span>
      <span class="pill">BI Analyst</span>
      <span class="pill">Operations Analyst</span>
      <span class="pill">Power BI Developer</span>
      <span class="pill">Reporting Analyst</span>
      <span class="pill">Data Visualization</span>
      <span class="pill">Data Management Analyst</span>
      <span class="pill">Business Analyst (Entry Level)</span>
    </div>

    <div class="metrics">
      <div class="metric">
        <div class="bars"><span style="height:40%;animation-delay:.05s"></span><span style="height:70%;animation-delay:.1s"></span><span style="height:55%;animation-delay:.15s"></span><span style="height:90%;animation-delay:.2s"></span><span style="height:65%;animation-delay:.25s"></span></div>
        <div class="num">49K+</div>
        <div class="label">transaction rows queried in SQL</div>
      </div>
      <div class="metric">
        <div class="bars"><span style="height:60%;animation-delay:.05s"></span><span style="height:35%;animation-delay:.1s"></span><span style="height:80%;animation-delay:.15s"></span><span style="height:50%;animation-delay:.2s"></span><span style="height:70%;animation-delay:.25s"></span></div>
        <div class="num">7</div>
        <div class="label">data &amp; BI certifications</div>
      </div>
      <div class="metric">
        <div class="bars"><span style="height:30%;animation-delay:.05s"></span><span style="height:75%;animation-delay:.1s"></span><span style="height:45%;animation-delay:.15s"></span><span style="height:85%;animation-delay:.2s"></span><span style="height:55%;animation-delay:.25s"></span></div>
        <div class="num">25</div>
        <div class="label">end-to-end BI &amp; analytics projects</div>
      </div>
      <div class="metric">
        <div class="bars"><span style="height:50%;animation-delay:.05s"></span><span style="height:60%;animation-delay:.1s"></span><span style="height:90%;animation-delay:.15s"></span><span style="height:40%;animation-delay:.2s"></span><span style="height:75%;animation-delay:.25s"></span></div>
        <div class="num">3.02</div>
        <div class="label">CS degree GPA / 4.0</div>
      </div>
    </div>
  </div>
</header>

<section id="about">
  <div class="wrap">
    <div class="section-head">
      <h2>About</h2>
      <span class="section-tag">Profile</span>
    </div>
    <div class="about-grid">
      <div>
        <p>I'm a <strong>Computer Science graduate</strong> with hands-on experience in data analytics, business
        intelligence, and reporting. I work across <strong>Excel,Google Sheet, SQL, python, Power BI, Excel, Tableau, and R</strong>, with
        practical experience in data cleaning, transformation, visualization, and dashboard development —
        backed by a solid grasp of KPI reporting and BI concepts, plus foundational finance and accounting
        knowledge.</p>
        <p>Right now I work in a <strong>data and operations role</strong> at a travel and visa services agency,
        where I maintain trackers across high transaction volumes and turn scattered intake data into reports
        management actually reads. On the side, I handle <strong>payroll operations</strong> for a Canadian
        manufacturing company, where I built an automated Excel workbook that replaced manual recalculation
        every pay cycle.</p>
        <p>I'm a proactive learner who pays close attention to detail and likes finding the root cause behind a
        number, not just reporting it. Looking for a <strong>Junior Data Analyst, Reporting Analyst, or BI
        Analyst role in Saudi Arabia</strong> where I can take ownership of a reporting pipeline end to end.</p>
      </div>
      <div class="stack-list">
        <div class="stack-row"><span>QUERY</span><span>SQL — joins, aggregations, subqueries, data extraction</span></div>
        <div class="stack-row"><span>MODEL</span><span>Data modeling, database management, PostgreSQL, MySQL</span></div>
        <div class="stack-row"><span>VISUALIZE</span><span>Power BI, Tableau, Excel dashboards</span></div>
        <div class="stack-row"><span>CLEAN</span><span>Power Query, data validation, ETL, quality assurance</span></div>
        <div class="stack-row"><span>SPEAK</span><span>English (fluent), Arabic (intermediate), Urdu (native)</span></div>
      </div>
    </div>

    <div class="skills-grid">
      <div>
        <div class="skill-group-label">Technical Skills</div>
        <div class="tag-cloud">
          <span class="tag">SQL</span>
          <span class="tag">PostgreSQL</span>
          <span class="tag">Power BI</span>
          <span class="tag">Tableau</span>
          <span class="tag">Microsoft Excel</span>
          <span class="tag">Pivot Tables</span>
          <span class="tag">VLOOKUP / XLOOKUP</span>
          <span class="tag">Google Sheets</span>
          <span class="tag">R Programming</span>
          <span class="tag">Power Query</span>
          <span class="tag">Data Cleaning &amp; Transformation</span>
          <span class="tag">Data Visualization</span>
          <span class="tag">Dashboard Development</span>
          <span class="tag">KPI Reporting</span>
          <span class="tag">ETL Processes</span>
          <span class="tag">Data Validation &amp; QA</span>
          <span class="tag">Data Modeling</span>
          <span class="tag">Database Management</span>
          <span class="tag">Business Intelligence</span>
        </div>
      </div>
      <div>
        <div class="skill-group-label">Business &amp; Professional Skills</div>
        <div class="tag-cloud">
          <span class="tag">Data Analysis</span>
          <span class="tag">Business Analysis</span>
          <span class="tag">Trend Analysis</span>
          <span class="tag">Performance Analysis</span>
          <span class="tag">Root Cause Analysis</span>
          <span class="tag">Financial &amp; Accounting Fundamentals</span>
          <span class="tag">Process Improvement</span>
          <span class="tag">Decision Support</span>
          <span class="tag">Research &amp; Data Collection</span>
          <span class="tag">Documentation &amp; Reporting</span>
          <span class="tag">Stakeholder Communication</span>
          <span class="tag">Cross-Functional Collaboration</span>
          <span class="tag">Problem Solving</span>
          <span class="tag">Critical Thinking</span>
          <span class="tag">Attention to Detail</span>
          <span class="tag">Time Management</span>
          <span class="tag">Presentation Skills</span>
          <span class="tag">Continuous Learning</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="wrap">
    <div class="section-head">
      <h2>Projects</h2>
      <span class="section-tag">Applied analysis</span>
    </div>

    <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Mobile-Sales-Dashboard" target="_blank">
    SQL Sales &amp; Mobile-Sales-Dashboard
  </a>
</h3>
        <span class="tools">PostgreSQL · pgAdmin 4 · Power BI</span>
      </div>
      <ul>
        <li>Queried and analyzed a transactional dataset of 49,000+ sales records to identify revenue drivers, order patterns, and product-level performance.</li>
        <li>Wrote multi-table SQL queries — joins, aggregations, and window functions — to break sales down by category, time of day, and order size.</li>
        <li>Packaged the findings into a presentation-ready summary and a documented GitHub repository.</li>
      </ul>
    </div>

    <div class="project">
      <div class="project-top">
       <h3>
  <a href="https://github.com/saeedullah-tech/Loan_Repayment_Analysis" target="_blank">
   Loan Repayment Analysis
  </a>
</h3>
        <span class="tools">Power BI · DAX</span>
      </div>
      <ul>
        <li>Designed a star-schema data model from loan and repayment data to support fast, accurate filtering by loan status, tenure, and customer segment.</li>
        <li>Built DAX measures for repayment rate, overdue balance tracking, and month-over-month / year-over-year comparisons.</li>
        <li>Surfaced at-risk loan segments in an interactive dashboard built to support collections prioritization.</li>
      </ul>
    </div>

    <div class="project">
      <div class="project-top">
        <h3>Payroll Automation Workbook</h3>
        <span class="tools">Excel · Power Query</span>
      </div>
      <ul>
        <li>Built a formula-driven workbook to automate bi-weekly payroll calculations, replacing manual line-by-line computation.</li>
        <li>Added validation rules on input sheets to catch data-entry errors — missing hours, rate mismatches — before final calculation.</li>
        <li>Cut average payroll-cycle processing time through reusable formulas and a standardized template.</li>
      </ul>
    </div>

    <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Saudi-Job-Market-Analysis-Bayt.com-Dataset" target="_blank">
  Saudi Job Market Analysis
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>

     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/powerbi-car-sales-dashboard" target="_blank">
  Power BI Car Sales Dashboard
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>

     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Credit-Card-Fraud-Risk-Analysis" target="_blank">
  Credit Card Fraud Risk Analysis
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>

     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/excel-pivot-dashboard-project" target="_blank">
  Excel Dashboard Project
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>

     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Pizza-Sales-Analysis" target="_blank">
  Pizza Sales Analysis
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>
     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Sales-Analysis" target="_blank">
  Sales Analysis
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>
     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/netflixSQL-project" target="_blank">
  Netflix SQL Project
  </a>
</h3>
        <span class="tools">· SQL </span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>
     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Library-Management-System-" target="_blank">
  Library Management System
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>
     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Saudi-Job-Market-Analysis-Bayt.com-Dataset" target="_blank">
  Saudi Job Market Analysis
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>
     <div class="project">
      <div class="project-top">
        <h3>
  <a href="https://github.com/saeedullah-tech/Saudi-Job-Market-Analysis-Bayt.com-Dataset" target="_blank">
  Saudi Job Market Analysis
  </a>
</h3>
        <span class="tools">SQL · Power BI</span>
      </div>
      <ul>
        <li>Structured job-posting data across roles, sectors, and locations in the Saudi market into a relational format for analysis.</li>
        <li>Used SQL to surface trends in in-demand skills, role frequency, and sector concentration.</li>
        <li>Visualized which technical skills appeared most often across analytics and BI postings.</li>
      </ul>
    </div>
   </section>

<section id="experience">
  <div class="wrap">
    <div class="section-head">
      <h2>Experience</h2>
      <span class="section-tag">Where I've worked</span>
    </div>

    <div class="xp-row">
      <div class="xp-date">Mar 2025 — Present</div>
      <div class="xp-body">
        <h4>Data &amp; Operations Associate</h4>
        <div class="org">Travel &amp; Visa Services Agency, Riyadh</div>
        <ul>
          <li>Maintain operational trackers across visa applications, client bookings, and case status with high daily transaction volume.</li>
          <li>Consolidate data from multiple intake sources into recurring management reports.</li>
          <li>Standardized reporting templates in Excel, cutting time spent assembling weekly updates.</li>
        </ul>
      </div>
    </div>

    <div class="xp-row">
      <div class="xp-date">2025 — Present</div>
      <div class="xp-body">
        <h4>Payroll Operations Support (Part-Time, Remote)</h4>
        <div class="org">HomeOne LED, Alberta, Canada</div>
        <ul>
          <li>Process bi-weekly payroll for hourly staff, cross-checking hours, rates, and deductions.</li>
          <li>Built and maintain an automated Excel payroll workbook, reducing manual recalculation time each cycle.</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<section id="certifications">
  <div class="wrap">
    <div class="section-head">
      <h2>Certifications</h2>
      <span class="section-tag">Verified skills</span>
    </div>
    <div class="cert-grid">
      <div class="cert">Microsoft Power BI</div>
      <div class="cert">Advanced Excel</div>
      <div class="cert">SQL &amp; MySQL for Data Analysis</div>
      <div class="cert">Data Analytics &amp; Business Intelligence</div>
      <div class="cert">Introduction to Finance &amp; Accounting</div>
      <div class="cert">Front-End Web Development</div>
    </div>
  </div>
</section>

<footer id="contact">
  <div class="wrap">
    <h2>Let's talk data.</h2>
    <p>Open to Junior Data Analyst, Reporting Analyst, BI Analyst, Operations Analyst, Governance Analyst, and
    entry-level Business Analyst roles across Saudi Arabia. Based in Riyadh with a transferable Iqama.</p>
    <div class="contact-row">
      <a class="contact-btn primary" href="mailto:Saeedtech990@gmail.com">Saeedtech990@gmail.com</a>
      <a class="contact-btn" href="https://www.linkedin.com/in/saeed-ullah-83806a3a8" target="_blank" rel="noopener">LinkedIn</a>
      <a class="contact-btn" href="https://github.com/saeedullah-tech" target="_blank" rel="noopener">GitHub</a>
    </div>
    <div class="foot-note">© 2026 SAEED ULLAH — RIYADH, SAUDI ARABIA</div>
  </div>
</footer>

</body>
</html>
