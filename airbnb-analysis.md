---
layout: page
title: "Airbnb Market Analysis"
permalink: /airbnb-analysis/
---

<p>This project explores short-term rental trends using real data from <a href="http://insideairbnb.com/get-the-data.html" target="_blank">Inside Airbnb</a>. The goal is to uncover pricing patterns, revenue dynamics, guest sentiment, and neighborhood trends to better understand what drives performance on the Airbnb platform.</p>

<h2>Project Overview</h2>

<h3>Purpose</h3>
<ul>
  <li>Collect, clean, and analyze large real-world datasets</li>
  <li>Use SQL for complex business logic and performance analysis</li>
  <li>Apply Python for sentiment analysis and text mining</li>
  <li>Deliver actionable insights from raw data</li>
  <li>Combine technical skills with business intuition</li>
</ul>

<h3>Tech Stack</h3>
<ul>
  <li><strong>PostgreSQL</strong> via pgAdmin4</li>
  <li><strong>Python</strong> (pandas, TextBlob, SQLAlchemy)</li>
  <li><strong>Jupyter Notebooks</strong></li>
  <li><strong>Markdown</strong> + SQL scripts</li>
</ul>

<h3>Key Questions Answered</h3>
<ul>
  <li>Which neighborhoods and room types dominate the market?</li>
  <li>How do prices vary by neighborhood and room type?</li>
  <li>What drives revenue and review engagement?</li>
  <li>How has activity changed over time?</li>
  <li>What are the sentiment trends from guest reviews?</li>
</ul>

<h2>Visualizations & Insights</h2>

<h3>1. Average Price by Room Type and Neighbourhood</h3>
<img src="/assets/images/AveragePriceGroupedByNeighbourhood_RoomType.png" alt="Average Price by Room Type and Neighbourhood">
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/AveragePricebyRoomTypeandNeighbourhood/Sheet1" target="_blank">View interactive chart</a></p>
<p><em>Note: The unusually high average prices in some neighborhoods are due to extreme outliers. These have not been excluded from the current visualization but are noted for context.</em></p>
<ul>
  <li>Entire home/apartment listings dominate the market and carry the highest average nightly price. Shared rooms are rare and priced significantly lower.</li>
  <li>SoHo and Williamsburg offer a strong balance of availability, guest satisfaction, and pricing power — signaling market strength.</li>
</ul>

<h3>2. Market Activity Projection (into 2026)</h3>
<img src="/assets/images/MarketActivityByDate.png" alt="Market Activity by Date">
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/AirBNBMarketActivityProjectioninto2026/Sheet1" target="_blank">View interactive chart</a></p>
<ul>
  <li>Listing activity remains strong throughout the year with predictable dips in winter.</li>
  <li>Midtown Manhattan continues to see strong booking behavior despite premium pricing — a magnet for both tourists and professionals.</li>
</ul>

<h3>3. Average Airbnb Listing Price by Neighbourhood</h3>
<img src="/assets/images/Price_GroupedbyNeighbourhood.png" alt="Average Price by Neighbourhood">
<p><a href="https://public.tableau.com/app/profile/sebastian.marrero/viz/AverageAirBNBListingPricebyNeighbourhood/Sheet1" target="_blank">View interactive chart</a></p>
<ul>
  <li>Brooklyn offers affordability with high listing volume, while Manhattan commands higher average prices.</li>
  <li>A few high-performing hosts account for disproportionate revenue — reinforcing market concentration.</li>
</ul>


<h2>Additional Insights</h2>

<h3>Revenue and Pricing Trends</h3>
<ul>
  <li>Listings with low availability (high bookings) significantly outperform others in terms of estimated annual revenue.</li>
  <li>The top-earning listings can bring in over $100,000/year, primarily those that are both expensive and nearly fully booked.</li>
  <li>Superhosts charge, on average, ~$25 more per night than non-superhosts. However, they also receive more reviews per month, suggesting guests are willing to pay a premium for reliability and service.</li>
</ul>

<h3>Booking Behavior and Activity</h3>
<ul>
  <li>Listings with more reviews per month are strong proxies for consistently booked listings and often align with higher revenue earners.</li>
</ul>

<h3>Guest Sentiment Analysis</h3>
[Explore Full Sentiment Analysis Report (HTML)](/assets/html/AirBNBAnalysis_SentimentAnalysis.html)

<ul>
  <li>The average sentiment across all reviews was highly positive (~0.75 on a scale from -1 to 1), reinforcing the strength of the NYC Airbnb experience.</li>
  <li>SoHo, Park Slope, and Greenpoint had the most positively reviewed listings, while JFK-adjacent neighborhoods and Harlem had more negative feedback related to noise, cleanliness, or host communication.</li>
  <li>Keywords in positive reviews often included: “clean,” “responsive host,” “great location,” and “comfortable bed.”</li>
  <li>Negative reviews flagged recurring issues like: “dirty,” “noisy,” “bugs,” and “cancellation.”</li>
  <li>Listings with high sentiment and high review count are rare — but they’re ideal for identifying top-tier performers.</li>
</ul>

<h3>Additional Insights</h3>
<ul>
  <li>Some listings are priced very high but underperform in sentiment or review count — potentially indicating poor value perception.</li>
  <li>The most reviewed listing in the dataset had over 600 reviews, significantly above average, and priced competitively in the $90–$120 range.</li>
</ul>




<h3>How to Reproduce</h3>
<ol>
  <li>Clone the repo: <code>git clone https://github.com/SebastianMarrero/AirBNBAnalysis.git</code></li>
  <li>Install required Python packages</li>
  <li>Set up PostgreSQL and import datasets</li>
  <li>Run the notebook: <code>jupyter notebook notebooks/airbnb_analysis.ipynb</code></li>
</ol>

<p><em>For full documentation, see the project's README on GitHub.</em></p>
