# KQL Notes

## project

Selects which columns you want to display.

Example:

```kql
SigninLogs
| project TimeGenerated, UserPrincipalName, IPAddress
```

---

## where

Filters rows from a dataset.

Example:

```kql
SigninLogs
| where ResultType != 0
```

---

## summarize

Aggregates data.

Example:

```kql
SigninLogs
| summarize count() by UserPrincipalName
```

---

## count

Counts rows.

Example:

```kql
SigninLogs
| count
```

---

## sort by

Sorts results.

Example:

```kql
SigninLogs
| sort by TimeGenerated desc
```

---

## extend

Creates a calculated column.

Example:

```kql
SigninLogs
| extend User = tostring(UserPrincipalName)
```

---

## distinct

Returns unique values.

Example:

```kql
SigninLogs
| distinct UserPrincipalName
```

---

## take

Returns a limited number of rows.

Example:

```kql
SigninLogs
| take 10
```

---

## Common KQL Workflow

```kql
SigninLogs
| where ResultType != 0
| project TimeGenerated, UserPrincipalName, IPAddress
| summarize count() by UserPrincipalName
| sort by count_ desc
```

### Explanation

1. Filter failed logins.
2. Select required columns.
3. Count sign-ins per user.
4. Sort highest to lowest.
## join

Combines data from two tables.

Example:

```kql
Costs
| join kind=inner Consumption on MeterType
```

## sum

Adds values together.

Example:

```kql
Consumption
| summarize TotalConsumed = sum(Consumed)
```
