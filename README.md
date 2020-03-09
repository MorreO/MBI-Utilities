# Prerequisites
Qlik Sense Enterprise >= 3.0 
(Desktop not supported)

# Installation
1. Download this extension on a zip file using the 'Clone or Download' button
2. Access navigate to 'Extensions' under the QMC (Qlik Management Console)
3. Import the zip file

# Getting Started
1. Navigate to the Data Load Editor
2. Create a Data Connection to the template excel file (it is provided in the zip file)
3. Insert the scripts for your Dimensions and Measures tables (add REPLACE LOADs if you want to enable partial reload)
4. Back in your Qlik Sense Application, create one table for the template file's Dimensions and another for template file's Measures (Highly recommend qsQuickTableViewer from ChristofSchwarz and Ralf Becher for this https://github.com/ChristofSchwarz/qsQuickTableViewer)
5. You can now use the Actions on the Master Items to create your Master Items from the template file.

# Using the Template file
1. Dimensions and Measures must have unique ID's
2. It is recommended that calculated expressions (usually label expressions) are wrapped in single quotes: EG: '='Sum(Dim1)'
3. It is recommended that text based expressions (usually label expressions) are wrapped in single quotes: 'Label Expression Example'
4. Measures required: Expression, Name
5. Dimensions required: Field, Name

# Actions	
1. Create: Inserts Dimensions/Measures based on selections
2. Update: Updates Dimensions/Measures based on selections
3. Delete: Deletes Dimensions/Measures based on selections
4. Partial Reload: Partially reloads dataset to avoid high reload times on large apps (Need to add REPLACE LOADs in Data Load Editor)
5. Delete All: Deletes ALL Dimensions/Measures (warning: this applies also to metrics not defined through this tool)
6. Export: Exports Dimensions/Measures from your application so that you can copy them back into your template file for later use.

# Authors
Henrik Amnäs @MBI

# Change Log
* 1.01, released 2020-03-09: Increased limit of measures and dimensions from 200 to 500.

# Known Issues and Limitations
* Exporting of Master Items will sometimes add an additional single quote to the end of a complex expression. Just make sure to remove it when copying back to your template spreadsheet.
* If your Master Item contains double quotes (") and you export it and open the CSV file in excel, the double quotes will be interpreted as end of cell in Excel and will mess things up. Recommend using [ and ] instead of " in all measures.
