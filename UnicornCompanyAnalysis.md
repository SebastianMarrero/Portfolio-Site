---
layout: page
title: "Unicorn Company (Start-up) Analysis"
permalink: /unicorn-analysis/
---
<p><a class="btn" href="https://github.com/SebastianMarrero/Unicorn_SQL_Project" target="_blank">View on GitHub</a></p>


<p>This project analyzes global unicorn startups using venture capital, industry, and geographic data. It explores success patterns through SQL-driven metrics like funding concentration, ROI efficiency, and valuation trends. Visual insights are provided using Tableau dashboards, while SQL and Python power the backend data wrangling.</p>

<h2>Project Overview</h2>

<h3>Purpose</h3>
<ul>
  <li>Analyze startup success patterns using real-world venture capital and funding data</li>
  <li>Identify top-performing industries, investors, and regions</li>
  <li>Uncover trends in valuation growth, ROI efficiency, and geographic clustering</li>
  <li>Apply SQL for complex business logic and analysis</li>
  <li>Integrate Python for preprocessing and automation</li>
</ul>

<h3>Tech Stack</h3>
<ul>
  <li><strong>MySQL</strong> via MySQL Workbench</li>
  <li><strong>Python</strong> (pandas, SQLAlchemy, pymysql)</li>
  <li><strong>Tableau Public</strong> for data visualization</li>
  <li><strong>Jupyter Notebooks</strong> for data cleaning</li>
</ul>

<h3>Key Questions Answered</h3>
<ul>
  <li>Which countries and cities produce the most unicorns?</li>
  <li>Which industries dominate unicorn creation?</li>
  <li>How do valuations trend over time?</li>
  <li>Which investors are most active and most successful?</li>
  <li>How efficient are unicorn companies based on ROI?</li>
</ul>

<h2>Visualizations</h2>

<h3>1. Top Ten Industries by Unicorn Company Count</h3>
<img src="{{ site.baseurl }}/assets/images/TopTenIndustries.sql.png" alt="Top Ten Industries">
<ul>
  <li>Internet Software and Fintech are the most prolific industries, accounting for the largest shares of unicorn creation.</li>
  <li>Industry dominance shifted over the decade, with new sectors like HealthTech and AI emerging in later years.</li>
</ul>
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/TopTenIndustriesbyUnicornCompanyCount/Sheet1" target="_blank">View interactive chart</a></p>

<h3>2. Top Ten Countries by Unicorn Company Count</h3>
<img src="{{ site.baseurl }}/assets/images/TopTenCountries.png" alt="Top Ten Countries">
<ul>
  <li>The United States leads in unicorn company count by a wide margin, followed by China and India.</li>
  <li>Silicon Valley's dominance is reflected in the concentration of unicorns headquartered in San Francisco.</li>
</ul>
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/TopTenCountriesbyUnicornCompanyCount/Sheet1" target="_blank">View interactive chart</a></p>

<h3>3. Average Valuation by Year</h3>
<img src="{{ site.baseurl }}/assets/images/AverageValuationbyYear.png" alt="Average Valuation by Year">
<ul>
  <li>The average unicorn valuation has steadily increased, peaking for companies founded between 2010–2015.</li>
  <li>Valuations reflect broader funding availability and tech sector momentum.</li>
</ul>
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/UnicornCompanyAverageValuationbyYear/Sheet1" target="_blank">View interactive chart</a></p>

<h3>4. Return on Investment Ratio (Top 20 Unicorns)</h3>
<img src="{{ site.baseurl }}/assets/images/ROIRatio.sql.png" alt="Return on Investment Ratio">
<ul>
  <li>Canva, Stripe, and Dunamu top the ROI chart, indicating strong capital efficiency and performance.</li>
  <li>High ROI companies often come from SaaS and fintech sectors with scalable, low-cost structures.</li>
</ul>
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/ReturnonInvestmentRatio-Top20UnicornCompanies/Sheet1" target="_blank">View interactive chart</a></p>

<h3>5. Most Successful Investors in Unicorn Companies</h3>
<img src="{{ site.baseurl }}/assets/images/MostSuccessfulInvestors.sql.png" alt="Most Successful Investors">
<ul>
  <li>Sequoia, Accel, and Andreessen Horowitz are among the most active unicorn investors.</li>
  <li>Top investors combine volume with high average valuations, indicating strategic selection of ventures.</li>
</ul>
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/MostSuccessfulInvestorsinUnicornCompanies-Top20/Sheet2#1" target="_blank">View interactive chart</a></p>


<h2>Additional Insights</h2>

<h3>Market Overview</h3>
<ul>
  <li>The United States dominates the unicorn landscape by a wide margin, with China and India following behind.</li>
  <li>San Francisco leads globally for city-based unicorn concentration, highlighting Silicon Valley’s continued importance.</li>
  <li>Unicorn formation accelerated significantly after 2010, corresponding with the rise of mobile technology and venture capital expansion.</li>
</ul>

<h3>Valuation and Funding Trends</h3>
<ul>
  <li>ByteDance, SpaceX, and Stripe are among the most highly valued companies, significantly skewing overall valuation averages.</li>
  <li>While some unicorns have raised enormous funding rounds, high fundraising does not always correlate with highest valuation.</li>
  <li>Certain companies (e.g., Canva, Figma) demonstrated exceptionally high valuation relative to funding raised — signaling strong capital efficiency.</li>
</ul>

<h3>Investor Activity and Performance</h3>
<ul>
  <li>Sequoia Capital, Accel, and Andreessen Horowitz are among the most active unicorn investors based on company count.</li>
  <li>However, being prolific doesn’t always mean producing top valuations: Some smaller investors show stronger average valuation per company invested in.</li>
  <li>The "Most Impactful Investors" combine both high company count and strong average valuations, with Sequoia and Tiger Global emerging as standouts.</li>
  <li>Investor repeatability is common among top VC firms — with frequent participation in multiple unicorns across different industries.</li>
</ul>

<h3>Capital Efficiency and ROI Metrics</h3>
<ul>
  <li>Basic ROI calculations (Valuation ÷ Funding Value) show that Canva, Stripe, and Dunamu are among the highest-performing unicorns relative to investment.</li>
  <li>Companies with high ROI scores often belong to SaaS or fintech sectors, reflecting scalable business models with low marginal costs.</li>
  <li>Some companies with extremely high funding (e.g., Uber) show lower ROI ratios due to high burn and operational expenses.</li>
</ul>

<h3>Industry Evolution and Trends</h3>
<ul>
  <li>Internet Software was the dominant sector for unicorn creation during the early 2010s.</li>
  <li>More recently, sectors like Artificial Intelligence, Blockchain, and HealthTech have gained momentum.</li>
  <li>Fintech remained resilient across all periods, consistently producing unicorns even during market downturns.</li>
</ul>


<h2>How to Reproduce</h2>
<ol>
  <li>Clone the repo: <code>git clone https://github.com/SebastianMarrero/Unicorn_SQL_Project.git</code></li>
  <li>Run SQL scripts via MySQL Workbench</li>
  <li>Process data using Python (optional)</li>
  <li>Build visualizations using Tableau Public</li>
</ol>

<p><em>For full documentation, see the project's README on GitHub.</em></p>
