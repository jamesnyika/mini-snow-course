# Data Model and Design
One of the most critical decisions you must make when designing an application is how to model the domain. Modeling means creating a mini example that represents the real world entity.

### What is a domain ?
Think of the domain as the data that described or specifies the business problem completely. It would be all the information that you need to collect to help you address the business problem.

*Here we can review examples of domains*

### What do I do with that data list ?
You must first organize the data and separate it into groups that:
* belong together
* are fine grained enough
* have additional metadata
* have the correct types - eg. you store amounts in integer or floating point fields and descriptions  in String fields

*Here we can review ServiceNow types for data.*

### Then what ?
Now you create the structures in Servicenow that will hold that domain - tables!
Tables are the primary construct of your data model. Each table requires that you specify

* A table name
* A module name ( Which menu it will appear under)
* A table it extends (If any, which table do you want to inherit fields from )
* Configuration settings and identity numbering
* Security Settings

## Week Assignment
* 
* Create a drawing or written description of your model
* Create your model in ServiceNow for next week and ensure that you put them all under the same module (menu).
* Ensure you commit your changes to your repository
