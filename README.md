# GINQO MasterItemManager
Our intention was to create an application that would help with efficiency with development, especially around Master Items. Since Master Items are frequently reused across applications, we felt a governed approach would fit best. Using our template file, Master Items can be saved for later creation. Master Items can be selected using a Qlik table then updated or deleted using this application. Finally, by default, the MasterItemManager won't affect your manually created Master Items unless specifically requested, making it a safe tool to use with in conjunction with previously defined apps.

# Getting Started
1. Download this extension on a zip file using the 'Clone or Download' button
2. Using the QMC import the zip file as an extension
3. You can now drag and drop the extension into your Qlik Sense application

![](demo.gif)

# Prerequisites
Qlik Sense Enterprise >= 3.0 
(Desktop not supported)

# Usage
1. From the Load Editor, create a Data Connection to the template excel file (provided in zip)
2. Import the Dimensions and Measures table into your script (adding REPLACE LOADs if you want to enable partial reload)
3. In your Qlik Sense Application, create one table for the template Dimensions and another for template Measures (Highly recommend qsQuickTableViewer from ChristofSchwarz and Ralf Becher for this https://github.com/ChristofSchwarz/qsQuickTableViewer)
4. Only items filtered in the table will be affected by actions from the Master Item Manager
5. You can now use the Actions on the Master Items to create your Master Items from the template file.

# The Template file
1. Must have unique ID's for Dimensions and Measures
2. It is recommended that calculated expressions (usually label expressions) are wrapped in quotes: EG: '='Sum(Dim1)'
3. It is recommended that text based expressions (usually label expressions) are wrapped in quotes: ''Label Expression Example'
4. Measures require: Expression, Name
5. Dimensions require: Field, Name

# Actions	
1. Actions (Eg: Create, Update, Delete) will only affect Master Items that are shown in the Dimensions and Measures tables.	
2. Selecting values from the tables will allow actions to be performed only on those selected.	
3. Manually defined metrics (though Qlik Sense interface) WILL NOT be affected by this tool's Create, Update, Delete actions 	

 # Extra Actions	
4. Partial Reload: If you are managing a very large Sense App and your excel template scheme has changed, you can use the partial reload option to update the schema without waiting for a full reload to finish to edit your existing Master Items.	
5. Delete All: This will delete all Dimensions/Measures, including ones defined through Qlik Sense's Interface.	
6. Export Measures/Dimensions: This will export Master Items based on the template file scheme, making it easy to copy over manually created Master Items from applications.

# Authors
GINQO

# Change Log

# Known Issues and Limitations
> Exporting of Master Items will sometimes add an additional single quote to the end of a complex expression. Just be cautious when copying back to your template spreadsheet
