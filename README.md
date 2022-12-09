# SisenseSampleApplication
Application preconfigured to support three primary ways of Sisense embedding (Iframe, Embed SDK, SisenseJS)
Sisense Sample Application ReadMe

The purpose of this sample application is to demonstrate the three primary ways in which Sisense can be embedded. Below are instructions and examples on how to embed dashboards/widgets created in your Sisense trial environment. For additional documentation and examples on embedding Sisense visit Sisense Embed Playground or Developer Documentation. 

Table of Contents 

Embedding Iframe - The quickest & easiest way to embed Sisense dashboards in your web application is with an iFrame element. Sisense has built in support for this mode of embedding, with query parameters you can append to the dashboard's URL to adjust the UI for your embedding needs.

EmbedSDK - The Embed SDK is a suite of Javascript APIs delivered as a Javascript library for consumption by the host app.
As an abstracted embedded interface that wraps an iFrame element, it comes packed with features to programmatically:
Render a Sisense iFrame element or hook to an existing one
Subscribe to various events fired within Sisense
Execute commands like adding/removing filters or exporting dashboards
Access information about the state of the Sisense application within the iFrame
The Embed SDK expands the basic capabilities of iFrames by utilizing postMessage communication between Sisense and the host page.
This technique is commonly used for basic integration, but the SDK takes out all the hassle and risk involved in manually implementing this, significantly speeding up development/integration.
SisenseJS - Sisense.js is a JavaScript library that enables you to embed Sisense components in web pages without the use of iFrames.
By embedding the SisenseJS library, you can:
Load Sisense runtime anywhere, without iFrames
Load dashboards in runtime
Render all/part/new widgets in any DOM container
Embed Sisense visualizations into your mobile applications
This page describes the SisenseJS library’s functionality and how you can leverage it to embed widgets into your site or application.
 
Sisense Iframe - 
Open the dashboard/widget you would like to embed via Iframe. 
In either the dashboard/widget select the 3 dot menu in the upper right hand corner. Select “Embed Code”

Copy - “​​src="https://domain.sisensepoc.com/app/main/dashboards/DashboardID?embed=true"

Open Folder “Sisense Sample Application” 
Open file “iframe.html” 
Locate code snippet “<iframe width="100%" height="450px" position:"right" frameborder="0" src="SISENSE EMBED URL"></iframe>”
Paste src snippet copied in the “SISENSE EMBED URL”.
Save Code. 

Sisense without defined authentication will use cookies. Open Sisense Console and authenticate. Launch either via localhost or from your Sisense Trial Server the iframe.html Content is expected to load in browser. 



Sisense EmbedSDK - 
Open EmbedSDK.html
Locate Block 

We will be updating the URL with your Sisense Trial Server address. 
We will also be updating the “dashboard:” with your DashboardID (located in sisense url and or the embed manager documented above. 
Locate  <script src="https://example.com/js/frame.js"></script>
Update URL with your Sisense trial address. 
You can save this code and open in browser to test.
Configuring Filter Button
To pass values from parent account to the embedded content we will be updating the JAQL. For additional information on how to use JAQL with Sisense please see Sisense JAQL for Developers. 
The Sisense EmbedSDK code snippet has an event handler listening for events to apply filters to Sisense content. We have added a button to the sample application that will execute this event. This Button’s code is in the EmbedSDK.html file. <button id="changeFilterButton" class="btn">Last Quarter's Sales</button>
To update the JAQL locate the code snippet. 

Update the “title” to the exact name of the filter in the dashboard we will be using. If you have not added a filter, add a filter to the dashboard. For information on how to add a dashboard filter see Sisense Dashboard Filters. 
Update the “dim” with the table name and column name you are filtering on. 
Within “Example” You can add a single dimension to filter on. You are not limited to this with EmbedSDK, we are just doing one value for the example application. We have more robust examples for EmbedSDK filters on the Embed Playground documented in the introduction and or in Github.
Save Code and Launch Page in Browser for testing. 
SisenseJS - 
Open the SisenseJs.html 
Locate     <script type="text/javascript" src="https://example.sisensepoc.com/js/sisense.js"></script> <!-- replace with your Sisense server address -->
Update with your Sisense Server Trial environment. 
Locate and update with your Sisense Trial Environment server address.   
 // replace with your Sisense Sisense.connect('https://example.sisensepoc.com')
 Locate  app.dashboards.load('dashboardid') and update with your dashboard ID/ 
Locate 

Update Widget id’s with the Widget ID’s you would like to see on the dashboard. 
Save and launch page from browser to test. 
Examples Should Look like the following
SISENSE IFRAME

Sisense EmbedSDK

 
SISENSEJS 

 
