Insight 3:  Which Countries Bring the Most Revenue?

Observation  
After analyzing the distribution of customers by country and the total amount they spent, I noticed that the USA tops both the customer count and total revenue — which wasn’t surprising. But something interesting came up: many countries had only **one customer**, yet still showed notable revenue.

That means a few individual users in those countries might be high-spenders — or we might simply be **under-investing in those regions**. There's clear potential if we dig deeper into such overlooked markets.

SQL Query Used
```sql
SELECT 
    c.Country,
    COUNT(DISTINCT c.CustomerId) AS NumofCustomers,
    SUM(i.Total) AS Totalrevenue
FROM Customer c
JOIN Invoice i ON c.CustomerId = i.CustomerId
GROUP BY c.Country
ORDER BY Totalrevenue DESC
LIMIT 10;

Business Value

Market Prioritization: Knowing which countries bring in the most revenue helps focus sales and marketing resources more effectively.

Growth Opportunities: Countries with just one or two customers but decent revenue could be untapped goldmines.

Localized Strategies: This insight helps build strategies for regional support, pricing models, and user engagement.

Realization
It’s easy to chase more users, but sometimes, understanding where your most valuable users are located gives better returns. Quantity doesn’t always beat quality when it comes to customers.

Why This Insight Matters to Recruiters
This shows my ability to ask thoughtful questions, write clean SQL to answer them, and interpret the results from a business lens. I’m not just pulling data — I’m learning to see what matters.
