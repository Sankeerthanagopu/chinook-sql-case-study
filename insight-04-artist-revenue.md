Insight 4: Which Artists Are Bringing in the Most Revenue?

Observation  
I was curious to see which artists were actually driving revenue. So I connected tracks with their respective albums and artists, and then linked that with actual purchases using the `InvoiceLine` table.

What I found was fascinating — some artists with **fewer albums or tracks** were still among the top earners. That tells us something powerful: it's not just about volume. **Artist quality, popularity, or loyal fanbases** might matter more than the number of songs they release.

SQL Query Used
```sql
SELECT 
    ar.Name AS ArtistName,
    COUNT(DISTINCT a.AlbumId) AS NumOfAlbums,
    COUNT(t.TrackId) AS NumOfTracks,
    ROUND(SUM(il.UnitPrice * il.Quantity), 2) AS TotalRevenue
FROM Artist ar
JOIN Album a ON ar.ArtistId = a.ArtistId
JOIN Track t ON a.AlbumId = t.AlbumId
JOIN InvoiceLine il ON t.TrackId = il.TrackId
GROUP BY ar.ArtistId, ar.Name
ORDER BY TotalRevenue DESC
LIMIT 10;
Business Value

Top Performers: Identifying high-revenue artists can guide partnerships, promotions, and contract negotiations.

Content Strategy: Platforms can prioritize featured sections and curated playlists with these artists to increase engagement.

Revenue Forecasting: Predict which future album releases might perform well based on artist history.

Realization
The data showed that success isn’t always about releasing the most content — it's about engagement, demand, and timing. That’s a lesson applicable across many industries.

Why This Insight Matters to Recruiters
This insight involves combining four tables, applying aggregations, and thinking beyond the query: What does this mean to the business? It shows I can manage complexity, ask the right questions, and explain data in a way that's actionable — which is exactly what a business analyst or data professional is expected to do.