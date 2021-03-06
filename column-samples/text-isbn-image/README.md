# Formatting an ISBN (text column) to book cover image. Images are retrieved by calling Open Library Covers API.

## Summary
This example retrieves book cover images based on their ISBN numbers by utilizing the [Open Library Covers API](https://openlibrary.org/dev/docs/api/covers). The API works by building a cover image URL with the ISBN.

This sample retrieves the small (S) image, but there are also medium (M) and large (L) sizes available. Simply swap out the `S` in `-S.jpg` portion of the `src` attribute in the `img` element to retrieve one of the other sizes. 

![screenshot of the sample](./text-isbn-image.png)

> The values are expected to be the ISBN numbers for the books. However, this sample could easily be switched to utilize the OCLC, LCCN, OLID, or ID values for a given book.

## Sample

Solution|Author(s)
--------|---------
text-isbn-image.json | Aaron Miao

## Version history

Version|Date|Comments
-------|----|--------
1.0|November 27, 2017|Initial release
1.1|March 22, 2018|Added details about API

## Disclaimer
**THIS CODE IS PROVIDED *AS IS* WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**

---

## Additional notes
This sample can be applied to render, for example, product number to product icon/image.

<img src="https://telemetry.sharepointpnp.com/sp-dev-column-formatting/samples/isbn-image-format" />