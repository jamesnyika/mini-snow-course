# Loading (and Unloading) Data Quickly
Servicenow exposes a number of different ways to load data.
* Using a REST API
* Using structured files such as CSV, XML, XLS, JSON

Each of these can use a scheduler to do so or be done on demand.

---

## Loading Data Using a REST API
ServiceNow has a number of documented examples on invoking web services such as those listed [here](https://docs.servicenow.com/bundle/istanbul-application-development/page/integrate/examples/concept/c_InboundWebServiceExamples.html)
Every invocation of REST / SOAP services in ServiceNow supports passing business data from any table to the service.

The primary methods of invoking web services are :
### From a workflow : configure a custom Rest Activity
Very similar to adding a JMS activity, a REST activity offers up different execution fields but usage is the same.

![Rest](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/RestActivity.png)

### From the REST Explorer and into a script
Using this mode of operation, we use the REST API Explorer to test an actual real life Web Service and then servicenow will generate the required code for you to place into a script. Access the REST Explorer by typing REST in the filter navigation

### Use a REST Message object to run against a service
Configure a REST message and use the 'Test' option to execute it

![Rest](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/RestMessage.png)

---

## Loading Data using Structured Files
You can import data directly into a list view in ServiceNow using XLS files. If you have or can convert your JSON/CSV/XML data to XLS first, then you can
quickly take advantage of this technique.

### Step-1 Go to the list view and right click

---


##  Unloading Data
One of the questions you might get is whether ServiceNow supports the CMIS protocol.  Servicenow does not natively support the CMIS protocol but it does offer mechanisms for pushing content/files to third party systems using FTP, HTTP(s), REST, SOAP or SCP (among other methods).

In this example we configure an [Export Set] which we tie to a schedule as well. To fulfil this use case, you would have the MID server installed in
a location where it can write to an INPUT directory for the CMS system. This way, a scheduled export can dump content to the desired directory for
consumption by the CMS

This is the preferred method of pushing this content out because it
1. Is highly scalable and is well tested.
2. It offers many different file export types (JSON, CSV, EXCEL, XML etc)
3. Flexibility and control in determining what content/data gets pushed out

Here is how you do it:

### Step-1 Configure Export Definition to define what will be exported
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Export1.png)

### Step-2 Configure Export Target to define where it will be exported
This use case requires use of the MID server so ensure that it is running or you cannot define a target.
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Export2.png)

### Step-3 Configure Export Set to tie everything together
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Export3.png)

### Step-4 Configure A Schedule (optional)
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Export4.png)

### Step-5 Review Exported File
You can run a test of the export set or wait for the scheduler to run and then locate the file under the exports/{path} you provided for the target.
Below you can see the file content of the export
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Export5.png)

---

## Other important topics related to data management

### Data Source
Data Sources provide a mechanism for defining a source of information and configuring it in ServiceNow. Once configured, a data source can be pulled from using a scheduler or on demand.

For an example see the screen below where we configure a data source for pulling FTP files from an external system. Things to notice:

ServiceNow offers multiple types of protocols from which to pull files for processing including HTTP(S), (S)FTP, SCP and attachments.
There is a choice received files that are already archived in Zip format too.

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/FTP2.png)

###  File Polling

File polling in ServiceNow is handled by combining the creation of a data source with a scheduler.

Below is an example of an LDAP User import mechanism that targets a datasource and ties it to a schedule. For a more fine grained scheduling of the action, a job must be defined and triggered.

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SImport.png)

### Tasks
1. Create some sample dummy data for one or more of your tables
2. Load the data into the table.



---

[Chapter 6 - Reconfiguring the User Interface ](../chap6/README.md)
