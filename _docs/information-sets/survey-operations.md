---
title: Survey Operations
category: Information Set
order: 3
---

A comprehensive list of all operations.

* TOC
{:toc}

## Example

Let's use the following Information Set as an example for all Operations:
This Information Set has only one Belief System. The Belief System has the following 8 States.

![]({{ site.url }}/images/infoset-example-survey.png)

## Believes
  
Return if the observation is True within the knowledge in all of the Belief States in the Belief System.

#### YAML
```yaml
- type: believes
  expression: "nachos : {1} int32"
```

#### Real World Example
```text
Do you believe that nachos is equal to 1?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
Yes
```

## Contradicts
  
Return if the observation is False within the knowledge in all of the Belief States in the Belief System.

#### YAML
```yaml
- type: believes
  expression: "not nachos : {1} int32"
```

#### Real World Example
```text
Do you believe that nachos is not equal to 1?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
Yes
```

## Diagnose
  
A logical explanation of why each of the states of your Information Set can't accept the expression. If your expression is accepted, an empty set will be returned.

#### YAML
```yaml
- type: diagnose
  observation: 'weekday: {"Weekstart"} weekdays and burgers : {2} int32'
  number_of_conditionals: 100
  time_reference: 1458157872963 #Wed Mar 16 2016 13:51:12 GMT-0600 (CST)
```

#### Real life example
```text
What contradicts the possibility of Day being Monday and Taco equals 1?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
Because weekday is Weekend and burgers is 1 in States 0, 3, 4, 5
Because burgers is 1 in States 1, 6, 7
Because weekday is Midweek in State 2
```

## Explanation
  
The logical set of rules that create each of the states of the Information Set.
A rule explains 1 or more states.

#### YAML
```yaml
- type: explanation
```

With the [example](./survey-operations#section-example) 

#### Output
```text
State 0 is defined by:\n  If chicken is 1 then daytime is Dawning 
  If nachos is 1 then daytime is Dawning
...
State 3 is defined by:
  If burger is 1 and weekday is Weekend then daytime is Dawning  
  If nachos is 1 then daytime is Dawining
```

## Get Value
  
Retrieves the value of the Key. If there isn't consistency within all the States, null is returned.

#### YAML
```yaml
- type: get_value
  key: chicken
```

#### Real World Example
```text
What's the value of chicken?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
Chicken is equal to One
```

## Hypotesis
  
Returns if each of the belief systems will  [Believes](doc:survey-operations#section-believes) a hypothesis after being Revised by the assumption.

#### YAML
```yaml
- type: hypothesis
  assumption: "nachos : {1} int32"
  hypothesis: "chicken : {1} int32"
  number_of_conditionals: 100
  search_stabilization_percent: 0.0
  time_reference: 1458157872963
```

#### Real World Example
```text
Will nachos equal 1 be belived if tacos being 1 is added to the System?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
True
```

## Is consistent
  
Return if the expression is True in at least one Belief State.

#### YAML
```yaml
- type: is_consistent
  expression: "nachos : {1} int32"
```

#### Real World Example
```text
Is nachos equal to 1 possible in any of the possible worlds?
```

With the [example](./survey-operations#section-example) 


#### Output
```text
Yes
```

## Is probable
  
Return if the position of the Key equals Value is greater than half.

#### YAML
```yaml
- type: is_probable
  expression: "nachos : {1} int32"
```

#### Real World Example
```text
Is probable that Burgers is 1?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
Yes
```

## Mentions

Lists all keys with all its possible values and its positions. Optionally, you could specify a key.

#### YAML
```yaml
# for all keys
- type: mentions
# only for chicken
- type: mentions
  key: chicken
```

#### Real World Example
```text
What are the values of all the keys?
or
What are the values of the Chicken?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
Mentions of all keys:
  0.778 Nachos: 1 
    
  0.222 Weekday: Weekend
  0.444 Weekday: Weekstart
  0.333 Weekday: Midweek
  
  0.778 Burgers: 1
  
  1.000 Chicken: 1
  
  0.778 Daytime: Dawning
  0.222 Daytime: Morning
  
  0.444 Day: Wednesday
  0.222 Day: Tuesday
  0.333 Day: Friday
  
  0.778 Drinks: 1
```

## Multiple Choice
  
Of a list of possible values, Yes or No are marked if the Information Set believes its value is possible. If the value is unknown, no answer will be returned.

#### YAML
```yaml
- type: multiple_choice
  key: burgers
  values:
    - "{1} int32"
    - "{3} int32"
    - "{5} int32"
```

#### Real World Example
```text
Is Burgers equal to 1?
Is Burgers equal to 3?
Is Burgers equal to 5?
```

With the [example](./survey-operations#section-example) 

#### Output
```text
Yes
No
No
```

## Position
  

#### YAML
```yaml
- type: position
  key: chicken
  value: "{1} int32"
```

#### Real World Example
```text

```

With the [example](./survey-operations#section-example) 

#### Output
```text
1.0
```

## Time
  
Returns the time of the operation in the System. Important in Simulations, when time is altered to predict results.

#### YAML
```yaml
- type: time
```

#### Real World Example
```text
What time is it?
```
<div>
<span id="spanDate"></span>
<script>
var months = ['January','February','March','April','May','June','July',
'August','September','October','November','December'];       
var tomorrow = new Date();
document.getElementById("spanDate").innerHTML = "Results: " + months[tomorrow.getMonth()] + " " + tomorrow.getDate()+ ", " + tomorrow.getFullYear();
</script>
</div>