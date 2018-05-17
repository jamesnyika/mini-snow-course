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

If you want to script more complex rules, then you need to select the Advanced checkbox on the business rules.

 Below is an example of the code for an advanced business rule. This rule performs a query, gets attachment data and then initializes
 a parser that will parse an XML file, set some fields on a new record and save the record. 

 ````
 (function executeRule(current, previous /*null when async*/) {

 	var attachGR = '';

 	gr = new GlideRecord('sys_attachment');
 	gr.addQuery('table_name', '=', current.getTableName());
 	gr.addQuery('table_sys_id', '=', current.sys_id);
 	gr.setLimit(1);
 	gr.query();
 	if (gr.next()) {

 		// Gets the attachment data
 		var gsa = new GlideSysAttachment();

 		//var bytesContent = gsa.getBytes('x_snc_dod_secops_import_stig', current.sys_id);
 		attachGR = gsa.getContent(gr);

 		//gs.info("Your thing looks like: " + attachGR);

 		//var STIGParser = new x_snc_dod_secops.STIGParser();
 		//var records = STIGParser.processRules(attachGR);
 	}

 	var ip = new HBSSParser();
 	var records = ip.processRules(attachGR);

 	current.topic = records[0];
 	current.producer_address = records[1];
 	current.message_id = records[2];
 	current.list_of_files_processed=records[3];
 	current.number_of_files_processed=records[4];
 	current.import_completed= new GlideDateTime();
 	current.update();

 })(current, previous);


 ````
---

[Chapter 14 - UI Actions](../chap14/README.md)
