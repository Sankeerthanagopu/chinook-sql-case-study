# Insight 02 – Track Popularity & Revenue

## Business Question  
Which songs were purchased the most and brought in the highest revenue?

---

## SQL Query Used
```sql
SELECT 
  t.Name AS TrackName,
  COUNT(il.InvoiceLineId) AS TimesPurchased,
  SUM(il.UnitPrice * il.Quantity) AS TotalRevenue
FROM InvoiceLine il
JOIN Track t ON il.TrackId = t.TrackId
GROUP BY t.TrackId
ORDER BY TimesPurchased DESC
LIMIT 5;
```

---

## What I Did  
I joined the `InvoiceLine` and `Track` tables to check how many times each song was purchased and how much revenue they generated in total. I thought I’d find a few songs that were really popular — like “hits” — but the results were unexpected.

---

##  What I Found  
Surprisingly, most tracks had **the exact same number of purchases** and **identical revenue**. There wasn’t any song that stood out or performed significantly better. I tried checking even 50 rows — still, no big difference.

That’s when I realized:  
> Not every dataset gives you exciting trends — and that’s also an important insight.

---

##  Insight 
Even though I started this analysis to find top-selling tracks, I discovered something just as useful:  
The dataset doesn’t reflect real-world listening behavior. Most tracks are purchased in exactly the same way — so this dataset isn’t helpful for analyzing song popularity.

This taught me to **think like a real analyst**:
- Be curious
- Ask questions
- And admit when the data doesn’t answer the question — and that’s okay.

---

##  Business Value  
-  **Dataset Validation**: It's important to first check if the data has variation before trying to find trends. This saves time and prevents wrong conclusions.
-  **Analytical Honesty**: Forcing an insight can be misleading. It's more valuable to say "this data doesn't support this question" than to fake results.
-  **Smart Thinking**: This shows I don't just write SQL — I ask if the data actually makes sense for the business.

---

## Tools Used
- SQL (SQLite via DB Browser)
- Chinook Sample Database
- Markdown 

---

##  Notes  
This was a great reminder that being a data analyst isn’t just about coding — it's about thinking. I’ll revisit this kind of analysis later if I get access to better or real-world music streaming data.
