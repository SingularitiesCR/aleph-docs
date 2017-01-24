---
title: Classification
category: Data Sets
order: 6
---
Classification is used for grouping entities using the characteristics they have in common. The classification can be used in two different ways. The first just groups the entities in their specific groups, the second creates **classification rules** that represent the patterns found during the classification and can be used for creating a belief system.

## Random forest

The random forest takes a dataset with one entity per row, where every column is a characteristic. Columns can be **numeric** or **categorical**.
**Numeric** columns can represent infinite or finite sets of values. **Categorical** columns represent a finite set of values. It's important that all categories are well represented across the dataset, a unbalanced category can cause noise to the classifier.