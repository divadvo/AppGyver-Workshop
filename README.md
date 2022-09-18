# AppGyver Hands-on / Dry-run

## Prerequisites

Check if you can access the prerequisites page [here](https://learning.sap.com/learning-journey/utilize-low-code-no-code-applications-and-automations-for-citizen-developers/getting-started-with-no-code-in-appgyver)

- Install iOS/Android app (Download links in the link above)
- Access the [LCNC Lobby](https://n-lcnc-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby) to create a project
- (Optional): Access the [subaccount](https://cockpit.eu10.hana.ondemand.com/cockpit/#/globalaccount/ac05fa1d-9c25-4b5e-a7bc-cac28341ff8f/subaccount/deaacfd3-655b-4c94-b9fd-c0c50f63af92/). Roles: `LCNC_Developer` or `LCNC_Administrator`
- FYI: the videos show the same steps as the written guide, so you could skip the videos

## 1st Exercise: Barcode scanner

We will build an app where you can scan a barcode and get food facts about a product.

Follow the tutorial [here and on the following pages](https://learning.sap.com/learning-journey/utilize-low-code-no-code-applications-and-automations-for-citizen-developers/getting-started-with-no-code-in-appgyver)

Here are some changes compared to the tutorial on the website:

### Step "Implementing the Logic for scanning the barcode"

Try these barcodes:

| Product  | Code          | QR Code                                     | Barcode                                       |
| -------- | ------------- | ------------------------------------------- | --------------------------------------------- |
| Kit Kat  | 7613035366749 | ![7613035366749](/images/7613035366749.png) | ![7613035366749](/images/7613035366749_2.png) |
| Nestea   | 5449000017376 | ![5449000017376](/images/5449000017376.png) | ![5449000017376](/images/5449000017376_2.png) |
| Nesquick | 3387390335859 | ![3387390335859](/images/3387390335859.png) | ![3387390335859](/images/3387390335859_2.png) |

### Step "Integrating with an API"

1. The UI of the "data" tab looks a bit different now. Select "create data entity" under "Appgyver classic data entities"

![3387390335859](/images/NewDataTab.png)

2. For copy paste:

Base url: `https://world.openfoodfacts.org/api/v0`

URL: `https://world.openfoodfacts.org/api/v0/product/{barcode}.json`

### Step "Getting and Displaying the Food Product Data"

(Optional if you have time): Explore the JSON response to find some interesting data to show. Try displaying some other properties such as `image_front_url`, or list of `ingredients`.

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
