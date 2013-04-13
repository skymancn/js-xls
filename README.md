# xls

Currently a parser for XLS files.  Cleanroom implementation from the Microsoft Open Specifications.

This has been tested on some basic XLS files generated from Excel 2011 (using compatibility mode).

*THIS WAS WHIPPED UP VERY QUICKLY TO SATISFY A VERY SPECIFIC NEED*.  If you need something that is not currently supported, file an issue and attach a sample file.  I will get to it :)

## Installation

In the browser:

    <script src="xls.js"></script>

In node:

    require('xlsjs').readFile('file');

The command-line utility `xls2csv` shows how to generate a CSV from an XLS.

## Usage

See http://niggler.github.com/js-xls/ for a browser example.

## Notes

`CFB` refers to the Microsoft Compound File Binary Format, a container format for XLS as well as DOC and other pre-OOXML data formats.

The mechanism is split into a CFB parser (which scans through the file and produces concrete data chunks) and a Workbook parser (which does excel-specific parsing).

`.SheetNames` is an ordered list of the sheets in the workbook
 
`.Sheets[sheetname]` returns a data structure representing the sheet

`.Sheets[sheetname][address].val` returns the value of the cell.  Types are currently not recorded (but Number and RkNumber show up as javascript Numbers).

## License

Please consult the attached LICENSE file for details.  All rights not explicitly granted by the Apache 2.0 license are reserved by the Original Author.

All code shared between this and the XLSX project (of the same author) fall 
under the licensing of the latter project.

It is the opinion of the Original Author that this code conforms to the terms of the Microsoft Open Specifications Promise, falling under the same terms as OpenOffice (which is governed by the Apache License v2).  Given the vagaries of the promise, the Original Author makes no legal claim that in fact end users are protected from future actions.  It is highly recommended that, for commercial uses, you consult a lawyer before proceeding.

## XLSX Support

XLSX is not supported in this module.  Due to Licensing issues [that are discussed in more detail elsewhere](https://github.com/Niggler/js-xls/issues/1#issuecomment-13852286), the implementation cannot be released in a GPL or MIT-style license.  If you need XLSX support, consult [my js-xlsx project](https://github.com/Niggler/js-xlsx).

## References

 - [MS-CFB]: Compound File Binary File Format
 - [MS-XLS]: Excel Binary File Format (.xls) Structure Specification
 - [MS-ODATA]: Open Data Protocol (OData)
 - [MS-OFFCRYPTO]: Office Document Cryptography Structure
 - [MS-OLEDS]: Object Linking and Embedding (OLE) Data Structures
 - [MS-OLEPS]: Object Linking and Embedding (OLE) Property Set Data Structures
 - [MS-OSHARED]: Office Common Data Types and Objects Structures

