## 2nd Exercise: Extending SAP Sales Cloud

We will build an app which displays a list of appointments stored in SAP Sales Cloud.

Follow the tutorial [here and on the following pages](https://learning.sap.com/learning-journey/utilize-low-code-no-code-applications-and-automations-for-citizen-developers/getting-started-with-extensions-to-sap-systems-in-sap-appgyver)

If low on time, you could skip reading the first two sections "Getting Started With Extensions to SAP Systems in SAP AppGyver" and "Preparing for Creating an SAP Extension"

Here are some changes compared to the tutorial on the website:

### Step "Building a user interface"

Instead of creating a new AppGyver project for this app, use the "pages" option on the top left and "navigation" tab, to add the pages to the existing barcode app.

### Step "Creating Connections to an OData API From SAP AppGyver"

Make sure you paste the username and password for basic authentication without spaces.

A CORS issue will come up during testing in the browser, but ignore it, because the API call will work fine on the mobile app.

When creating a data variable, to set the basic auth parameters, click on the "X" under "basic authentication", then select "Object with properties" and enter the username/password. The screenshots are on the page a bit below the text describing the steps.

API endpoints for reference:

- Metadata: `https://my346234.crm.ondemand.com/sap/c4c/odata/v1/c4codataapi/$metadata`
- List of appointments: `https://my346234.crm.ondemand.com/sap/c4c/odata/v1/c4codataapi/AppointmentCollection`
- AppointmentTextCollection example: `https://my346234.crm.ondemand.com/sap/c4c/odata/v1/c4codataapi/AppointmentCollection('00163EAA5CF11EECABEA2A4417A76664')/AppointmentTextCollection`
