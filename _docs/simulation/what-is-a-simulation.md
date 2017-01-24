---
title: What is a Simulation?
category: Simulation
order: 1
---
A simulation consists of going through a dataset in chronological order and analyzing it using Aleph. For every transaction, the simulation first creates a predictive **belief system** using all the available previous transactions. Then it compares the current transaction to what the **belief system** predicted, and finally it adds the current transaction to the **belief system**. This parts of the process are called **stages**. The stages are  **Pre-Visit**, **Intra-Visit** and **Post-Visit**. A visit represents a transaction, like the visit of a customer to a store. 
A simulation can run for one specific entity or a cluster or group of them.

<blockquote>
	<h3>Statistics</h3>
	<p>The simulation returns a large amount of valuable statistics. These represents things like how correct were the predictions of the <strong>belief system</strong> or how quickly did the <strong>belief system</strong> learn a customer's patterns. You can use the statistics to tune your dataset and your parameters.</p>
</blockquote>

## Pre-Visit
  
The **Pre-Visit** includes everything that happens in between two transactions. It represents the time in between when a customer leaves a store and when he comes back. During this stage is where Aleph takes all the transaction a customer has ever participated in and creates a belief system. This belief system represents all the customer's shopping patterns.

## Intra-Visit
  
It includes what happens during transaction itself. The belief system takes every item in the transaction and compares it to the prediction. The simulation can also take into account the chronological order in which the items of the transaction are. At the end, a new belief system is created with a union of the current belief System and the current transaction.

## Post-Visit
  
The post visit includes all the statistic analysis that happens once the transaction is over.

## Surveys
  
[Survey Operations](/information-sets/survey-operations) and [Survey](/information-sets/survey) can be used inside the simulation to analyze the state and the characteristics of a belief system in a specific point in time. This can be very useful because surveys can show how a customer has changed and also how the belief systems predictions change as it receives more data. 
There can be a survey for **Pre-Visit**, **Intra-Visit** and **Post-Visit**. The questions get asked every time the simulation is in that stage.

```yaml
location : pre_visit
questions:  
  - type : get_value
    key : weekday
```