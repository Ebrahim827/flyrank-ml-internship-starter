# Making the Content Refresh Queue work with AI

## 1. The ML Task Type
This is a **Classification** task. The AI looks at a website page and puts it into one of two buckets: **Class 1** (traffic is dropping and it needs a rewrite) or **Class 0** (the page is doing fine, leave it alone). Once the AI calculates how confident it is about each page, we sort them to make our top-ranked list.

## 2. Target Variable and Proxy
The **Target** we are trying to predict is `trend_direction`. Our **Proxy** for a page needing a rewrite is when that trend is labeled as **down**. This is our clear signal that a page is losing its grip on Google and needs a human to step in and fix it.

## 3. The Success Metric
We are using a metric called **Precision@50**. 
* **Why this matters:** The writing team only has enough hours in the week to look at 50 pages. If our AI picks 50 pages, we want as many of them as possible to be actually broken. We care way more about keeping false alarms out of our top 50 than we do about general test scores.

## 4. The Real Content Action
The output connects directly to a real business action. The final list goes straight to the content manager's editorial calendar. They take the top 50 broken pages identified by the AI and hand them to copywriters with explicit instructions to update old statistics, add fresh links, and rewrite declining sections of text.

## 5. Why This is an ML Problem and Not Just a Rule
A simple, fixed rule like "flag every page older than 6 months" doesn't work well in real life. Some old pages retain high historical authority and stay popular for years without any changes, while brand new pages can suddenly crash because of a surprise Google algorithm update. This is a true machine learning and analysis problem because search performance is non-linear. AI beats manual rules because it can check clicks, impressions, rankings, and page age all at the exact same time to spot the real patterns of decay that a simple rule would miss.
