---
title: Survey
category: Information Set
order: 2
---
## Input Structure
  
A survey is a collection of Questions to be asked to the Information Set. For each entity in the dataset a result Row 
Example

```yaml
questions:  
  - type : get_value
    key : weekday  
  - type: believes 
    expression: '\"Kids\" : {1} int32 and weekday : {\"Weekend\"} string'\n
```

## Result
  
For each entity in the dataset a result row will be generated. Each entity has a set of possible states that represent a different Possible World.
 
## Example
  
> 1. Jane goes when **Weekday** is ***Weekstart*** and has ***one*** **Kid**
> 2. Peter goes when **Weekday** is ***Weekend*** and has ***two*** **Kids**
> 3. Mike goes when **Weekday** is ***Weekend*** and  has ***one*** **Kid**

And with the survey described earlier we have this results:

| Get Value (weekday) | Believes (Exp) | Entity |
| --- | --- | --- |
| Weekstart | No | Jane |
| Weekend | No | Peter |
| Weekend | Yes | Mike |