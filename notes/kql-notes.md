# KQL Notes

## project

Selects which columns you want to display.

Example:

```kql
SigninLogs
| project TimeGenerated, UserPrincipalName, IPAddress
```

## where

Filters rows from a dataset.

Example:

```kql
SigninLogs
| where ResultType != 0
```## summarize

Aggregates data.

Example:

```kql
SigninLogs
| summarize count() by UserPrincipalName
```

## count

Counts rows.

Example:

```kql
SigninLogs
| count
```

## sort by

Sorts results.

Example:

```kql
SigninLogs
| sort by TimeGenerated desc
```

## extend

Creates a calculated column.

Example:

```kql
SigninLogs
| extend User = tostring(UserPrincipalName)
```
