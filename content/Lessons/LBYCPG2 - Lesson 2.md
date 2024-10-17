---
draft: false
tags: [LBYCPG2]
title: Joints and Aggregation
date: 2024-10-17, 22:17
---

## Sources

1. SQL Joints (Lecture Slides)
2. SQL Aggregation (Lecture Slides)

## Joints

*Joins* combine rows from different tables through related columns. They allow for the retrieval and presentation of related data.

> [!NOTE]
> Types of Joints
>
> 1. **Inner Join:** Only returns rows with matching values.
> 2. **Left (Outer) Join:** Returns all rows from the left table and the matching rows from the right table. If no matches, NULL in the right table.
> 3. **Right (Outer) Join:** Returns all rows from the right table and the matching rows from the left table. If no matches, NULL in the left table.
> 4. **Full (Outer) Join:** Returns all rows from both table. Returns NULL in either when one is not matching with any.
> 5. **Cross Join:** Returns the combinations of all rows in both tables.

## Aggregation

*Aggregate functions* perform calculations on a set of values and generates a result.

> [!NOTE]
> Types of Aggregation
>
> 1. **COUNT():** Counts the number of rows.
> 2. **SUM():** Provides the sum of a numeric column.
> 3. **AVG():** Provides the average of a numeric column.
> 4. **MIN():** Finds the minimum in a column.
> 5. **MAX():** Finds the maximum in a column.
> 6. **GROUP BY():** Groups rows with the same values in a specified column.
