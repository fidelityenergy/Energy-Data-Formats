# Energy Data Formats
This repository documents common file formats for data transfer for UK Energy companies

## Background

We are a UK Energy Broker and receive commission from energy suppliers for customers we've signed up. As well as invoices
we receive data files with detailed backup of each contract and the commission payable on it.

The problem is that there are no common formats for the exchange of data and every supplier has a different format: sometimes
multiple _different_ file formats for a single supplier each month, even for the same energy type. 

This has a direct cost implication for us, and since these formats often change without warning, our processes either fail, or
worse still, import the wrong values. This is costing us time, money and goodwill with our own customers.

## Solution

This repository is to document a common format that any UK Energy supplier can use, without cost, to export their data. This
can then be used by any UK Energy Broker to import, verify and process these transactions.

Our aims are:
 - to keep the specification as simple as possible
 - to require as few data fields as possible, to make it simple to implement
 - include optional fields that will help processing the data
 - gain industry acceptance and use of the format
 
## Suppliers Using The Formats

At present the formats are under development so no suppliers will be present here. Any supplier interested in using the formats should
[submit a new issue](/conficient/Energy-Data-Formats/issues/new) to this repository and we will add you to the list of supporters.

[Hall of Fame](Hall_of_Fame.md)

## Repository Layout

The `Formats` folder contains each format 
