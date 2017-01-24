---
title: What is an information set?
category: Information Set
order: 1
---
## Basics

An Information Set is an assembly of different Entity Belief Systems. A Believe System is  constructed by all different Modal States that describes your data and its behavior by each of your entities

<blockquote class="success">
	<h3>Benefits</h3>
	<li>Easy way to comprehend your data behavior like relationships across your products.</li>
  <li>You can query your data with using custom surveys to quickly access key features.</li>
  <li>Ability to learn or forget some key aspect of the data to show alternative behavior.</li>
  <li>A nicer way to see a row dataset with the power of machine learning.</li>
</blockquote>

## Belief System
  
Is the collection of All the modal states related to a particular entity. An Entity can be a person, a company, a cluster of a particular entities. 

## Modal State
  
A Modal State is a possible world that represents your data in a consistent state according with the behavior obtain in the Machine Learning process

## Representation

An information set can be represented in various ways. Example, since an Information Set holds constrains referring to a Data Set and contains these constrains as Belief States, each state can be seen as a stack column with a set of conditionals linked to it.

![](/images/infoset-example.png)

[block:code]
{
  "codes": [
    {
      "code": "* Burgers and Bread => Soda\n* Pizza => Beer",
      "language": "text",
      "name": "State 1"
    },
    {
      "code": "* Burgers => Soda\n* Fries and Bread => Beer",
      "language": "text",
      "name": "State 2"
    },
    {
      "code": "* Burgers and Pizza => Beer",
      "language": "text",
      "name": "State 3"
    }
  ]
}
[/block]