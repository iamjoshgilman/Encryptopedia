---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Splunk]] | [[000 - Cybersecurity Materials]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Commands for Aggregation and Grouping Splunk]]  
---

## Stats command with `by` clause:

Command | Description
--- | ---
`stats values(<field1>) by <field2>` | Displays unique values of `<field1>` for each unique value of `<field2>`.
`stats count by <field>` | Counts the number of events for each unique value of `<field>`.
`stats sum(<field1>) by <field2>` | Sums the values of `<field1>` for each unique value of `<field2>`.
`stats avg(<field1>) by <field2>` | Computes the average of `<field1>` for each unique value of `<field2>`.
`stats max(<field1>) by <field2>`, `stats min(<field1>) by <field2>` | Finds the maximum or minimum of `<field1>` for each unique value of `<field2>`.

## Chart command with `over` and `by` clauses:

Command | Description
--- | ---
`chart count by <field1>` | Creates a chart with the count of events for each unique value of `<field1>`.
`chart sum(<field2>) by <field1>` | Creates a chart with the sum of `<field2>` for each unique value of `<field1>`.
`chart avg(<field2>) by <field1>` | Creates a chart with the average of `<field2>` for each unique value of `<field1>`.
`chart count over <field1> by <field2>` | Creates a chart with the count of events for each unique value of `<field1>`, split by `<field2>`.

## Timechart command with `span` clause:

Command | Description
--- | ---
`timechart count` | Creates a timechart with the count of events over time.
`timechart sum(<field>)` | Creates a timechart with the sum of `<field>` over time.
`timechart avg(<field>)` | Creates a timechart with the average of `<field>` over time.
`timechart span=1h count` | Creates a timechart with the count of events over time, with a span of 1 hour.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (08:35 pm) 
Last Modified Date: June 23rd 2023 (08:35 pm)
