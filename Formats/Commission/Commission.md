# Commission File Format

This file is used to report commission invoice and detail data to an energy broker. The file should be in JSON format and include both the 
invoice details as well as the individual commission entries. The invoice details enable brokers to match up invoices and credits with the data.

## Naming

It is recommended that the file is named in the following way:
```
  [date]-[account]-[reference].json
```  
The `[date]` should be in ISO 8601 format, e.g. *yyyy-MM-dd* 
The `[account]` should be the account name, and should only contain alphanumeric and underscore _ characters
The `[reference]` should be a batch/invoice/export reference. For example if the file represents data for invoice 12345 the reference would be `12345`

### Examples:

`2020-01-01-Acme_Brokers_Ltd-Inv0001.json`  - Export for _Acme Brokers Ltd_ related to invoice Inv0001, dated 1st Jan 2020.

`2020-05-31-ZZZ_plc.json`  - Export for _ZZZ plc_ dated 31st May 2020. There is no reference in this example.

## Structure

The JSON file will have two main components; the header and the detail records, e.g:
```json
{
  "header": {
    ...
  },
  "detail": [
    ...
  ]
}
```

### Header
This section of the file is a summary of the detail rows. If the data represents an invoice/credit, it should match the amounts on that document.

```json
"header": {
  "reference": "[invoice/credit reference number/text]",
  "date": "[date in ISO 8601 format]",
  "items": 0, 
  "subtotal": 1234.56,
  "tax": 246.91,
  "total": 1481.47,
  "notes": "optional commentary on reason for invoice/document"
}
```

### Detail
This section is an array of commission record rows. Each row is a JSON object in the following format:
```json
 {
  "paymentDate": "payment-date-in-ISO8601", 
  "startDate": "contract-start-date-in-ISO8601",
  "type": "energytype, e.g. gas",
  "reference": "[mpan/mprn/other meter reference]",
  "site": "site address or reference",
  "contract": "contract number or reference",
  "commission": 1234.56
  }
```

## Sample Files

Some sample files are included in this folder.
