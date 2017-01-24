---
title: Trend Analysis
category: Data Sets
order: 8
---

## What is a trend?
  
When a collection of data follows a certain **pattern** through periods of time is called **trend**.

Specifically in the **Aleph System**, the trend is calculated over a numerical variable related to a **key** and a period of **time**. This trend will indicate if an **item, or key,** has a **down, stable or up** trend according to the numerical variable through the time periods.

## How does it work?

<blockquote>
  <h3>What is an Entity?"</h3>
  <p>An <strong>Entity</strong> is the top parent in the Data hierarchy; it can be the <strong>ID</strong> of a client, provider, department, person, company...; it depends on the Data Set. The Entity can be the same for all the entries if it's not important for the user to identify who owns certain data.</p>
</blockquote>

| Entity | Key | Time (Year-Month-Day) | Sales (Numerical variable) |
| ------ | --- | --------------------- | -------------------------- |
| A | Milk | 2015-01-01 | 1000 |
| A | Bread | 2015-01-15 | 750 |

Taking the previous **Data Set** as example and assuming more rows exist until July 2016; the **Trend Analysis** will group all the entries in the Data Set by **Entity** and **Key**. Then, it'll recalculated the **numerical variable** according to the chosen **time period**.

> **Time periods** are lapses of the same duration, therefor, an user can choose if the data will be analysed **Daily, Weekly, Monthly, Quarterly, Semesterly or Yearly**

Once the numerical variable is recalculated, the algorithm proceeds to calculated the **deltas**. The Delta is the difference from a current time period and the last one. Then, an average of the deltas is calculated and with the result the trend is decided using the following rules:
* If the average delta is lower than **-0.95** the trend is considered **DOWN**.
* If the average delta is higher than **0.05** the trend is considered **UP**.
* Else, the trend is considered **STABLE**.

Then the results are joint to the original Data Set and this creates a new Data Set.

## Resulting Data Set

| Entity | Key | Time | Sales | Trend_Sales_Monthly |
| --- | --- | --- | --- | --- |
| A | Milk | 2015-01-01 | 1000 | DOWN |
| A | Bread | 2015-01-15 | 750 | STABLE |
| A | Juice | 2015-02-20 | 850 | UP |
| A | Milk | 2015-02-02 | 500 | DOWN |

## Data Set requirements
  
Before running a **trend analysis**, the user should check the following requirements:
1. The Data Set has at least one **Time** variable to differentiate the periods.
2. The Data Set has at least one **Numerical** variable to calculate the deltas.
3. The Data Set has a **Key, or Item,** for a better understanding of the process.

<blockquote class="success">
	<h3>Benefits of a trend analysis</h3>
	<li> The user will know the behaviour of an item according to a numerical variable.</li>
  <li>It can be used to cluster or classify the Data Set.</li>
  <li>It can be used to filter the Data Set.</li>
</blockquote>