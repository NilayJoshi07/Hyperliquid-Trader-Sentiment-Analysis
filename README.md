# Hyperliquid-Trader-Sentiment-Analysis
To analyze how market sentiment (Fear &amp; Greed) impacts trader performance and bias
For this project, I went beyond just looking at PnL. I wanted to see how the "mood" of the market (measured by the Fear & Greed Index) actually changes how people trade on Hyperliquid.

By merging over 211,000 rows of trade data with daily sentiment scores, I’ve uncovered where traders are making money and, more importantly, where they are letting their biases take control.

### 1. Cleaning the Noise
Real-world trading data is messy. I started by aligning the dates between the historical_data.csv and the sentiment index.

**The Problem**: A few massive trades (outliers) were making the "average" profit look way higher than it actually was for a normal trader.

**The Fix**: I used a technique called capping the extremes. This didn't delete data; it just brought the "Whale" outliers back to a level where they didn't drown out the rest of the stats.

**The Result**: The average PnL stabilized from a jumpy $48.75 to a much more realistic **$31.31**.

### 2. Spotting the "Bottom Fishing" Bias
I looked at the Buy/Sell Ratio to see if traders were acting rationally.

**The Discovery**: When the market is in Extreme Fear, the Buy/Sell ratio jumps to 1.04.

**The Insight**: This is a classic behavioral bias. Even when the market is crashing, Hyperliquid traders are buying the dip more aggressively than they sell during bull runs.

### 3. Finding the "Alpha" Segment
I split the traders into segments (Low-Cap, Mid-Tier, and Whales) to see who the real performers are.

**The Surprise**: It’s not just the Whales. Mid-Tier traders are actually the most consistent, contributing 38.2% of the platform's total PnL. They seem to have the best balance of risk and reward.

## Repository Info:
I’ve automated the entire workflow in **Main_script.ipynb**.

**Trader_Performance_Analysis_Final.pdf**: A clean summary for a quick read. unfotunately couldnt ass the visualization charts even if  tried

**report_charts.png**: The core visuals showing the PnL trends and sentiment spikes.

**Trader_Analysis_Report.xlsx**: The complete statistical data.

**cleaned_trader_sentiment_data.zip**: The final, polished dataset.

## Conclusion:
Wrapping up this project, the biggest takeaway isn't just a set of numbers—it’s the clear picture of how human emotion actually moves the needle on a platform like Hyperliquid.

### My Key Takeaways:
Markets have a "Pulse": It’s easy to say traders should be rational, but the data shows they aren't. Seeing that surge in buying during Extreme Fear was a "lightbulb moment." It proves that while most people are panicking, there’s a specific group trying to time the bottom—creating exactly the kind of liquidity pockets a team like Primetrade.ai looks for.

Cleaning Data: If I hadn't used capping to cap those wild "Whale" trades, the entire report would have been a lie. It taught me that good analysis isn't just about running code; it's about making sure the data actually reflects the "typical" experience, not just the lucky 1%.

The "Quiet" Winners: I expected the massive wallets to own the leaderboard, but the Mid-Tier traders were the real stars. It’s a great reminder that the most sustainable "Alpha" usually comes from consistency, not just deep pockets.

### Where I’d Take This Next:
If I had another week with this dataset, I’d love to dig into:

**The "Reaction Time"**: Does trading volume spike the moment the Fear & Greed index drops, or is there a 4-hour lag? Finding that "sweet spot" would be huge for timing entries.

**Taking it Live**: Moving this from a Main_script.ipynb into a real-time alert system. Imagine a bot that pings a Discord channel the second the Buy/Sell ratio gets "too greedy" compared to the actual market mood.
