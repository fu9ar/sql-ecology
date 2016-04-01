---
layout: lesson
root: .
title: Aggregation
minutes: 30
---

COUNT and GROUP BY
----
Aggregation allows us to combine results by grouping records based on value and
calculating combined values in groups.

Let’s go to the surveys table and find out how many individuals there are.
Using the wildcard simply counts the number of records (rows)

    SELECT COUNT(*) FROM Demographics

We can also total the population counted.

    SELECT COUNT(*), SUM(Population_Size) FROM Demographics

We can output this value in millions, rounded to 3 decimal
   places:

    SELECT ROUND(SUM(Population_Size)/1000000.0, 3) FROM Demographics

There are many other aggregate functions included in SQL including
`MAX`, `MIN`, and `AVG`.

> ### Challenge
>
> Write query that returns: total population, average population, and the min and max populations for all counties in the US. Can you modify it so that it outputs that for a range of population sizes?


Now, let's see how many counties are in each state. We do this
using a GROUP BY clause

    SELECT State, COUNT(*)
    FROM Demographics
    GROUP BY State

GROUP BY tells SQL what field or fields we want to use to aggregate the data.
If we want to group by multiple fields, we give GROUP BY a comma separated list.

> ### Challenge
>
> Write queries that return:
>
> 1. The population of each state
> 2. The population living in Poverty in each state
> 3. ??


##### Ordering aggregated results.

We can order the results of our aggregation by a specific column, including the
aggregated column.  Let’s count the number of counties in each state!

    SELECT State, COUNT(*)
    FROM Demographics
    GROUP BY State
    ORDER BY COUNT(State)

> ### Challenge
>
>   Write a query that returns an ordered list of the State, County, 
> and Population, ordered by the states with the highest average poverty




Previous: [SQL Basic Queries](01-sql-basic-queries.html) Next: [Joins and aliases.](03-sql-joins-aliases.html)
