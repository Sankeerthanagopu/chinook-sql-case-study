Insight 5: Which Music Genres Make the Most Money?

Observation  
I wanted to find out which genres are not just popular, but actually **profitable**. So I joined the `Genre`, `Track`, and `InvoiceLine` tables to calculate total revenue generated per genre and the number of tracks each contains.

What stood out is that **some genres with fewer tracks still generated high revenue**, while others had many tracks but didn't perform as well. This suggests that certain genres, although smaller, have **very loyal or high-spending audiences**.

SQL Query Used
```sql
SELECT
    g.Name AS GenreName,
    COUNT(t.TrackId) AS NumOfTracks,
    ROUND(SUM(il.UnitPrice * il.Quantity), 2) AS TotalRevenue
FROM Genre g
JOIN Track t ON g.GenreId = t.GenreId
JOIN InvoiceLine il ON t.TrackId = il.TrackId
GROUP BY g.GenreId, g.Name
ORDER BY TotalRevenue DESC
LIMIT 10;
Business Value

Genre-Level Marketing: Know where to focus promotional campaigns and genre-specific playlists.

Revenue-Driven Licensing: Helps decide which genres to prioritize in licensing and content acquisition.

Audience Insights: Understand which genres create loyal or high-paying users — not just passive listeners.

Realization
This was a great reminder that success isn't always about quantity. A genre with fewer tracks can still dominate if its audience is engaged. It’s a quality-over-quantity story told by revenue.

Why This Insight Matters to Recruiters
I used multi-table joins and meaningful aggregations to extract business-ready insights, not just run queries. This kind of work shows how I connect data logic with strategic thinking — which is exactly what a data analyst needs to do in real companies.