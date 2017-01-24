---
title: Clustering
category: Data Sets
order: 2
---
Clustering is the process of grouping multiple objects (**transactions, entities, people...**) resulting in groups that contain objects similar to each other.

![](images/clustering.png)

Some Data Sets can be clustered by their own variables. Example:

| Name | Country | Favourite Bread |
| ---- | ------- | --------------- |
| John | U.S.A. | Ciabatta |
| Amanda | U.S.A | Ciabatta |
| Peter | Canada | Panini |
| Anna | Canada | Panini |

This is a very simple situation where the Data Set could be clustered by **Country**, **Favourite Bread** or even both. The problem gets harder when more variables are added to the Data Set and even if some variables had very distinctive values, they might not be **optimal**.

<blockquote>
  <h3>Why should I use a Clustering algorithm instead of just cluster by an specific variable?</h3>
  <p>The clustering algorithms analyse the Data Set and finds the appropriate <strong>combination</strong> of variables that will be used as the <strong>optimal</strong> clustering key.</p>
</blockquote>

With the **Aleph System** there are [soft or hard](#soft-vs-hard) and [set or bag](#set-vs-bag) clustering algorithms, these algorithms are used to created new **Data Sets** to be processed to create an [Information Set](/information-set/what-is-an-information-set) using **Market Basket** algorithms, therefor, they work better with transactional data.

## Soft vs Hard

Before the **clustering** process starts, it's important to define how **exclusive** does the user want the entities to be. 

<blockquote>
  <h3>Entity exclusivity</h3>
  <p>Referring to clusters, the exclusivity of an entity means if an entity belongs to a <strong>single</strong> cluster or <strong>multiple</strong>.</p>
</blockquote>

The difference between **hard** and **soft** lies in the exclusivity of an entity.

* **Soft**: An entity can be a **member** of multiple clusters and a value of how **probable** is that the entity belongs to the cluster.
* **Hard**: An entity is **exclusive** to a cluster.

## Set vs Bag
  
When a **Data Set** is been mined through **Market Basket**, the algorithm only cares about the items of the transaction and if they are frequent or not; during the **clustering** process, some entities can be grouped by their **transaction patterns**, but depending on the type of the chosen algorithm, it'll take more variables into account. These types are **Set** or **Bag**.
> **Set**: Only cares if an item is in the transactions of an entity.
> **Bag**: Checks the amount of an item in the transaction.

Example:

| Entity | Item | Amount |
| ------ | ---- | ------ |
| A | Bread | 2 |
| B | Bread | 3 |
| C | Bread | 500 |
| D | Bread | 550 |

According to the previous table, if a **clustering algorithm** of the type **set** analyses this Data Set, the resulting **cluster** would be `{A, B, C, D}`, but if the algorithm was of the type **bag**, the resulting clusters would be `{A, D}` and `{B, C}`.

<blockquote>
  <h3>Combined configuration</h3>
  <p>The algorithms aren't exclusively <strong>Soft, Hard, Set or Bag</strong>, but instead they are a combination of <i>(Soft or Hard) X (Set or Bag)</i>.
  </p>
</blockquote>