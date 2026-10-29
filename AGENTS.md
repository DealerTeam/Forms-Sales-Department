# Forms-Sales-Department

Samples live in `Forms/<slug>/`. Each folder is one `dealer__Form__c`. Read that folder's `form.json` and `NOTES.md`. Match an existing form by Name before creating one. Keep the Default Formula from `form.json`. Do not replace it with `TRUE`.

`form.json` ships `dealer__Active__c` as `false`. Turn it on only after the form is verified, and only in a sandbox unless the user names production.

## Laser

Print Type `Laser`. Visualforce markup lives in `pages/`. Form record fields live in `Forms/<slug>/`. The Form Page Name is in `form.json` (`c__` plus the page name).

Install the page in the org first (`README.md`). Then create or update `dealer__Form__c` from `form.json`. Leave `dealer__PDFFileName__c` and `dealer__DocumentContentId__c` off the create body.

## PDF

Print Type `PDF`. Use the `dealerteam-pdf-forms` skill from the `dealerteam-client` plugin. Do not restate that skill and do not add a second copy of it to this repo.

Each folder can hold:

- `fillable.pdf` — the file the user uploads
- `source.pdf` — the flat original, when this repo authored the fields
- `mapping.json` — PDF field name to merge expression
- `fdf_code.json` — merge JSON array written to `dealer__FDF_Code__c`
- `form.json` — Form record fields, without FDF Code
- `NOTES.md` — rules the files do not show

When `fillable.pdf`, `mapping.json`, and `fdf_code.json` are already in the folder, skip the skill's authoring steps. Ask which org. Create or update `dealer__Form__c` from `form.json`, with `fdf_code.json` stringified into `dealer__FDF_Code__c`.

When those three files are missing, follow the skill to author the PDF and the merge JSON. Still create the record from `form.json`.

Leave `dealer__Page_Name__c`, `dealer__PDFFileName__c`, and `dealer__DocumentContentId__c` off the create body. Page Name is for Laser forms. The file name and document id are set by the upload and differ by org.

Then give the user the record URL and `fillable.pdf`. They upload it on the Form record. There is no upload API. Afterward, confirm `dealer__PDFFileName__c` and `dealer__DocumentContentId__c` are set, and that the merge JSON still matches `fdf_code.json` by field name.
