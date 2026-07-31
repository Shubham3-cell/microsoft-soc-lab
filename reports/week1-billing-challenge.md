# KQL Billing Challenge

## Challenge

Calculate the total utility bill using data from two tables.

## Concepts Learned

- join
- extend
- summarize
- sum

## Final Query

```kql
Costs
| join kind=inner Consumption on MeterType
| extend Bill = Consumed * Cost
| summarize TotalCost = sum(Bill)
```

## What I Learned

- How to combine two tables using join
- How to create calculated columns using extend
- How to aggregate data using summarize
- How to troubleshoot KQL syntax errors
