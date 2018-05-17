# Data Export
Servicenow does not natively support the CMIS protocol but it does offer mechanisms for pushing content/files to third party systems
using FTP, HTTP(s), REST, SOAP or SCP (among other methods).

In this example we configure an [Export Set] which we tie to a schedule as well. To fulfil this use case, you would have the MID server installed in
a location where it can write to an INPUT directory for the CMS system. This way, a scheduled export can dump content to the desired directory for
consumption by the CMS

This is the preferred method of pushing this content out because it
1. Is highly scalable and is well tested.
2. It offers many different file export types (JSON, CSV, EXCEL, XML etc)
3. Flexibility and control in determining what content/data gets pushed out

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

[Chapter 13 - Business Rules](../chap13/README.md)
