# atlanta-cafe-market-analysis
Atlanta Cafe Market Analysis

A data project analyzing cafe market density and demand across Gwinnett County and the Atlanta/Emory/Georgia Tech corridor, built to practice the kind of market analysis used in credit risk assessment and site selection.

What this is

I pulled data on 116 cafes across two Georgia markets using the Google Places API, then analyzed demand patterns using review volume as a proxy for consumer traffic. The goal was simple: figure out where cafe demand is actually strong, and where it just looks strong on the surface.

The finding

My first pass showed Midtown Atlanta with the highest average demand per cafe in the dataset, nearly 4x every other neighborhood. The obvious read: Midtown is underserved and could support more cafes.

That conclusion didn't hold up. When I checked the median instead of the average, the number dropped from 1,327 reviews per cafe to 226, a 6x gap. That kind of gap usually means a few outliers are carrying the whole average. Looking at individual cafes confirmed it: three specific spots (all sitting directly on Peachtree St, Midtown's main corridor) were pulling thousands of reviews each, while every other Midtown cafe performed in a completely normal range.

The real takeaway wasn't "Midtown needs more cafes." It was that street-level location, not neighborhood label, is what actually drives outsized demand. A simple average almost led me to the wrong conclusion. Checking the underlying distribution is what caught it.

I think about this the same way a lender would look at a company's revenue growth: the top-line number can look great and still be driven by one client or one location that won't repeat. You have to check what's underneath it before you trust it.

What's in this repo


cafe_market_data.csv — the cleaned dataset (116 cafes: name, address, coordinates, rating, review count, price level, neighborhood, region)
analysis.ipynb — the Colab notebook with data pull, cleaning, and pivot analysis
cafe-finder.html — an interactive tool built on this same dataset (see below)


Cafe Finder

Built a small tool on top of the dataset that recommends cafes by location and use case (Study/Lock In, Coffee Chats, Sweet Treats, Hang & Vibe), plus proximity to Georgia Tech, Emory, or your current location.

Try it live: [add your GitHub Pages link here once enabled]

Worth noting: there's no review text in this dataset, so the use-case categories are inferred from review volume and rating patterns, not actual sentiment analysis. That's a real limitation, and the next version of this project would pull actual review text through Google's Place Details API to build these categories on real signal instead of a proxy.

Tools used

Python, pandas, Google Places API, Google Sheets (pivot analysis), HTML/CSS/JavaScript (recommendation tool)

Why I built this

I'm a Data Science and BBA student interested in the intersection of finance, data, and decision-making. This started as a way to practice pulling and analyzing real market data, and turned into a good exercise in not trusting the first number I saw. That instinct, checking what's actually driving a metric before acting on it, is something I want to keep building on.
