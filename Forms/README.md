# Forms

Each subfolder is one `dealer__Form__c` sample. Record fields are in `form.json`. Rules that the files do not show are in `NOTES.md`.

Print Type `Laser` forms use a Visualforce page in [`pages/`](../pages/). The Form Page Name is `c__` plus the page name.

Install steps are in the repo root [README](../README.md). Default Formula is EvalExpression, evaluated on the Deal.

Anything with Mobility in the name requires Conversion Price or Conversion Cost to be non-zero. Leave `10-1394` out of every formula.

| Folder | Form name | Print Type | Page Name | Default Formula |
| --- | --- | --- | --- | --- |
| `deal-mobility-invoice-4502-payor-1` | Mobility Invoice 4502 Payor 1 | Laser | `c__DealMobilityInvoice4502Payor1` | `((dealer__Conversion_Price__c != 0) \|\| (dealer__ConversionCost__c != 0)) && ((dealer__Deferred_Note_1__c = "4502") \|\| (dealer__Deferred_Note_1__c = "4502 Grant"))` |
| `deal-mobility-invoice-4502-payor-2` | Mobility Invoice 4502 Payor 2 | Laser | `c__DealMobilityInvoice4502Payor2` | `((dealer__Conversion_Price__c != 0) \|\| (dealer__ConversionCost__c != 0)) && ((dealer__Deferred_Note_2__c = "4502") \|\| (dealer__Deferred_Note_2__c = "4502 Grant"))` |
| `deal-mobility-invoice-4502-payor-3` | Mobility Invoice 4502 Payor 3 | Laser | `c__DealMobilityInvoice4502Payor3` | `((dealer__Conversion_Price__c != 0) \|\| (dealer__ConversionCost__c != 0)) && ((dealer__Deferred_Note_3__c = "4502") \|\| (dealer__Deferred_Note_3__c = "4502 Grant"))` |
| `deal-mobility-invoice-10-1394-payor-1` | Mobility Invoice 10-1394 Payor 1 | Laser | `c__DealMobilityInvoice101394Payor1` | `((dealer__Conversion_Price__c != 0) \|\| (dealer__ConversionCost__c != 0)) && ((dealer__Deferred_Note_1__c = "1394") \|\| (dealer__Deferred_Note_1__c = "1394 Grant") \|\| (dealer__Deferred_Note_1__c = "10-1394 Grant"))` |
| `deal-mobility-invoice-10-1394-payor-2` | Mobility Invoice 10-1394 Payor 2 | Laser | `c__DealMobilityInvoice101394Payor2` | `((dealer__Conversion_Price__c != 0) \|\| (dealer__ConversionCost__c != 0)) && ((dealer__Deferred_Note_2__c = "1394") \|\| (dealer__Deferred_Note_2__c = "1394 Grant") \|\| (dealer__Deferred_Note_2__c = "10-1394 Grant"))` |
| `deal-mobility-invoice-10-1394-payor-3` | Mobility Invoice 10-1394 Payor 3 | Laser | `c__DealMobilityInvoice101394Payor3` | `((dealer__Conversion_Price__c != 0) \|\| (dealer__ConversionCost__c != 0)) && ((dealer__Deferred_Note_3__c = "1394") \|\| (dealer__Deferred_Note_3__c = "1394 Grant") \|\| (dealer__Deferred_Note_3__c = "10-1394 Grant"))` |

`Grant` matches any capitalization. The deferred note must be the whole value.
