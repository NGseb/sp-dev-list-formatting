# Creating Red-Amber-Green (RAG) bars based on date ranges

## Summary
This example creates colored data bars on the current field based on `DueDate` and `StartDate` fields compared to the current date/time. The bar fills towards 100% as "Today" approaches the due date. A percentage width is determined based on the total number of days between the StartDate of the item and the DueDate of the item.

![screenshot of the sample](./screenshot.png)

Unlike some of the other examples, this one applies formatting to one field by looking at the value inside other fields. Note that `DueDate` and `StartDate` are referenced using the `[$FieldName]` syntax where FieldName is the internal name of the field. This example also takes advantage of a special value that can be used in date/time fields - `@now`, which resolves to the current date/time, evaluated when the user loads the list view.

>Note that the Today column shown above is not used in the format. It's provided for reference so that you can see how the format was applied with the given dates.

The colors used are determined by the classes applied:

|Condition|Class|
|---|---|
|DueDate <= Now|sp-field-severity--severeWarning|
|Number of days passed between StartDate & DueDate > 70% of the total days|sp-field-severity--warning|
|Else|sp-field-severity--good|

If the `DueDate` has not yet passed, the width of the bar is determined using this formula (where 86,400,000 is the number of milliseconds in a day):

`((Number(DueDate - @now) / 86400000)/(Number(DueDate - StartDate) / 86400000)) * 100`

This calculates the percentage of days that have passed from the total number of days between the `StartDate` and the `DueDate`.

Additionally, the value of the field (`@currentField`) is displayed when there is a value.

## Sample

Solution|Author(s)
--------|---------
date-range-rag.json | [Christopher Parker](https://twitter.com/ChrispyBites)

## Version history

Version|Date|Comments
-------|----|--------
1.0|June 13, 2018|Initial release
1.1|July 25, 2018|Updated to include amber class

## Disclaimer
**THIS CODE IS PROVIDED *AS IS* WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**

## Additional notes

- [Use column formatting to customize SharePoint](https://docs.microsoft.com/en-us/sharepoint/dev/declarative-customization/column-formatting)

<img src="https://telemetry.sharepointpnp.com/sp-dev-list-formatting/column-samples/date-range-rag" />