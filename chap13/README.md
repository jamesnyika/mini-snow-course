# Business Rules
Business rules allow ServiceNow to act on data in the system when a trigger condition is met.
They can be configured in simple ways to set fields or change records, or you can configure extensive actions such as creating new fields and performingHere
more complex actions.
Here,
 we show an example of a business rules that does human task assignment for incidents automatically to a named individual on creation (on insert)

### Step 1 - Define a new business rule
Set the conditions to be only for on insert, of records on the incident table.
Do not click advanced unless you want to use scripting mode

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/HumanTask3.png)

### Step 1 - Define the action for the business rule
Set a field on the record (assigned to) to a specific person.
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/HumanTask4.png)


---

[Chapter 14 - UI Actions](../chap14/README.md)
