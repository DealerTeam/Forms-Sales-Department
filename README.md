# Example Deal Forms

Printable forms you can use to prepare or extend printed documents from Deals.

Samples live in [`Forms/`](Forms/). Each subfolder is one Form. The list, Print Type, Page Name, and Default Formula are in [Forms/README.md](Forms/README.md). `AGENTS.md` is the procedure for creating or updating the Form record from `form.json`.

## Getting Started

These instructions will walk you through installing the Visualforce pages and customizing them to meet your needs.

### Deploy using Heroku

<a href="https://githubsfdeploy.herokuapp.com?owner=dealerTeam&repo=https://github.com/DealerTeam/Example-Deal-Forms&ref=Master">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/deploy.png">
</a>

### Installing Pages

Visualforce markup lives in [`pages/`](pages/).

1. Open the Developer Console under the settings gear

2. Under the File > New menu select Visualforce Page

3. Enter the page name (e.g. `DealMobilityInvoice4502Payor1`) and select ok

4. Paste the contents of the `.page` file from `pages/` and save (File > Save)

### Viewing Pages

To view your page(s) you will need to pass the DealID parameter.

1. Click the App Launcher icon

2. Enter Deals in the search area.

3. Click Deals.

4. Select the Deal # to open up the deal.

5. Copy the unique identifier from the URL between the slashes. **a0N1F000001xTneUAE** is the DealId in the example below. ````https://velocity-dream-6454-dev-ed.lightning.force.com/lightning/r/dealer__Deal__c/**a0N1F000001xTneUAE**/view````

6. Browse to your page appending the DealID.
````https://velocity-dream-6454-dev-ed--dealer.visualforce.com/apex/DealMobilityInvoice4502Payor1?id=a0N1F000001wlADUAY````

### Adding Pages to Forms

Reference the following help article to upload the form(s) to your org:
[Upload Visualforce Forms](https://help.dealerteam.com/System_Administration/System_Administrator_Guide/Upload_Visualforce_Forms)

Or in Cursor, name the org and the folder:

```text
Install the Laser form in Forms/deal-mobility-invoice-4502-payor-1 into <org-alias>.
Follow AGENTS.md. Use form.json for the Form record, including the Default Formula and Page Name.
```

## VA mobility invoices

Print Type Laser. Payor 2 and Payor 3 are the same page as Payor 1 with that payor's bill-to.

| Page | Use |
| --- | --- |
| `DealMobilityInvoice4502Payor1` | VA Form 21-4502 chassis invoice. Payor 1 bill-to. |
| `DealMobilityInvoice101394Payor1` | VA Form 10-1394 adaptive-equipment summary. Payor 1 bill-to. |

Defaults when Conversion Price or Conversion Cost is non-zero and that payor's deferred note matches the form number (or `Grant`). See [Forms/README.md](Forms/README.md).

## Customizing Pages

The pages can be customized to meet your needs. Outlined below are a few key areas.

###### Logo
The logo will display from the Location that is selected in the deal.
```HTML
<apex:image id="businessLogo" url="/{!dealW.logoURL}" />
```
###### Form Name
The default form name is **Quote**. To replace do a search for ````Quote```` and replace with a different name.

```HTML
<h1>Quote</h1>
```
###### Terms & Conditions
To update the terms do a search for ````Terms```` and make any necessary changes.

```html
<!-- Terms -->
```
