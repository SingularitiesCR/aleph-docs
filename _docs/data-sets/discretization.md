---
title: Discretization
category: Data Sets
order: 3
---
<blockquote>
  <h3>Variable classes</h3>
  <li><strong>Discrete</strong>: Belongs to a finite set in which every member is well defined and there are no observable values between two members.</li>
  <li><strong>Continuos</strong>: Belongs to an interval in which between two members there will always be a third member that can also be a possible value for the variable.
  <ul><li>Every <strong>Categorical</strong> variable is discrete and finite.</li></ul>
  </li>
</blockquote>

A **Data Set** is collection of variables that can be discrete or continuos. A continuos variable will probably complicate the process of grouping items (**transactions, entities, objects...**), therefor, a **discretization algorithm** will take a continuos variable and turn it into a discrete one, which is easier to handle. 

| Occupation | Age | Weight |
| ---------- | --- | ------ |
| Student | 16 | 62.0 |
| Designer | 22 | 85.0 |
| Business Analyst | 45 | 105.0 |
| Programmer | 36 | 100.5 |

Taking the previous **Data Set** as an example, there're three variables: Occupation, Age and Weight, which are Discrete, Continuos and Continuos respectively. The four entries shown in the example are really different and if there were more entries the problem could be even worse.

## What will the discretization do?
  
The discretization will take the continuos variables and create categories (**Discrete values**). Looking at the previous **Data Set**, the discretization algorithm would take the **Age** and **Weight** variables, since they are continuos and assuming there're so many more entries with different data, the algorithm would substitute the value of a continuos variable in each entry with one of the following categories:

| Variable | Categories | Interval |
| -------- | ---------- | -------- |
| **Age** | AGE_A | [15, 25] |
| | AGE_B | [32, 51] |
| **Weight** | WEIGHT_A | [52, 63] |
| | WEIGHT_B | [65, 86] |
| | WEIGHT_C | [95, 110] |

Since the categories are created taking all entries into account, the categories are created with an optimal distribution without leaving any entry out.
## Resulting Data Set

| Occupation | Age | Weight |
| ---------- | --- | ------ |
| Student | AGE_A | WEIGHT_A|
| Designer | AGE_A | WEIGHT_B |
| Business Analyst | AGE_B | WEIGHT_C |
| Programmer | AGE_B | WEIGHT_C |

The **Data Set's** variables **Age** and **Weight** have been discretized.