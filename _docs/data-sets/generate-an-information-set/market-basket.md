---
title: Market Basket
category: Data Sets
order: 5
---

* TOC
{:toc}

<blockquote>
  <h3>Association</h3>
  <p>A set of items that appear certain amount of times inside a Data Set.</p>
</blockquote>

The **Market Basket** algorithms mine the Data Sets in order to find associations, or patterns, and expose them as **rules**.

## Association Mining

The **association mining** is the process where a Data Set is analysed, or mined, to find frequent associations. **Frequent** associations are relative to the goals of the user; an association is frequent if its appearances in the Data Set are higher than a **threshold** defined by the user.

## What are Association Rules?

An **association rule** is a set of attributes that define an association between two different **item sets**. Example:

| Antecedent | Consequent | Confidence | Coverage | Support | Lift |
| ---------- | ---------- | ---------- | -------- | ------- | ---- |
| Bread, Beer | Cheese, Bacon | 1 | 0.5 | 125 | 1.5 |

This rule can also be read as: **If an entity A picks the items Bread and Beer, then, it will pick the items Cheese and Bacon with a 100% confidence.**
The association rule is composed by:
* **Antecedent**: An item set that responds **"What does the rule need?"**.
* **Consequent**: An item set that responds **"What does the rule produce?"**.
* **Confidence**: A number between 0 and 1 that express how **exclusive** is the consequent to this rule. If the confidence equals 1 then the consequent exists only for this rule.
* **Coverage**: Shows how much is the percentage representation of this rule in the Data Set.
* **Support**: Shows in how many transactions this rule appears.
* **Lift**: Expresses the independency between antecedent and consequent. If the lift is greater than 1, it means that this rule is useful for future predictions.

## Association Rules Mining configuration

The configuration of the association mining changes depending on the algorithm used to mine the Data Set, but there're common variables:
* **Threshold**: The minimum amount of times an association should appear in the Data Set.
* **Minimum transactions**: The minimum amount of transactions an entity should have in order.
* **Minimum confidence**: The minimum confidence a rule should have in order to be accepted.
* **Delta**: A threshold to define a top rule.
* **Maximum Rules**: The maximum amount of rules to be generated.

> **Top rule**: It is a rule with **maximum** confidence. The maximum confidence is not necessarily 1(**or 100%**), but instead it is `1 - delta`.

## Mining process
  
The **association rule** mining process is divided in 2 steps:
1. Association mining.
2. Rule generation.
The association mining can be done with different algorithms like *Apriori, Eclat, FP-Growth* or any of their variations. Then the **association rules** algorithm takes these associations and generates rules.

## FP-Growth VS. TNR
  
The Aleph system has two options for **Association Rule** mining.

### FP-Gowth + Association Rule Algorithms

<blockquote class="success">
  <h3>Pros</h3>
  <li>Works well with multiple entities.</li>
  <li>Gives the possibility to choose between <strong>deep</strong> and <strong>shallow</strong> mining.</li>
  <li>Shallow mining is faster.</li> 
  <li>Deep mining generates all the possible rules and that could lead to better results.</li>
</blockquote>

<blockquote class="danger">
  <h3>Cons</h3>
  <li>It is slower than TNR.</li>
  <li>It doesn't work well with very long transactions</li>
</blockquote>

### TNR (Top K Non Redundant Rules)

<blockquote class="success">
  <h3>Pros</h3>
  <li>It is Faster.</li>
  <li>Works well with long transactions</li>
</blockquote>

<blockquote class="danger">
  <h3>Cons</h3>
  <li>It doesn't work well with multiple entities.</li>
</blockquote>

### Conclusion

Depending on the Data Set, one algorithm will perform better than the other.