---
title: Exporting Accented Characters in Telerik RadPdfProcessing
description: Learn how to export accented characters like è and ò using Telerik RadPdfProcessing in Document Processing.
type: how-to
page_title: Exporting Accented Characters in RadPdfProcessing
slug: exporting-accented-characters-radpdfprocessing
tags: telerik, radpdfprocessing, document processing, accented characters, blazor
res_type: kb
ticketid: 1465340
---

## Environment

| Product | RadPdfProcessing for Document Processing |
| --- | --- |
| Version | Current |

## Description

When generating a PDF using [RadPdfProcessing](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview) in Telerik Document Processing, accented characters such as è and ò are not printed. This issue occurs even when using the library in Blazor applications or demo projects.

This KB article also answers the following questions:
- How to export accented characters using RadPdfProcessing?
- Why are accented characters not printing in PDF?
- How to fix missing accented characters in Telerik Document Processing?

## Solution

Ensure that the font used supports accented characters. Here is an updated example of how to generate a simple PDF that includes accented characters:

1. Import the necessary namespaces:
    ```csharp
    using System.Windows;
    using Telerik.Windows.Documents.Fixed.Model.Editing;
    using Telerik.Windows.Documents.Fixed.Model.Fonts;
    ```

2. Ensure the `TimesRoman` font supports accented characters. If not, try using another font that does, such as `Arial`.

3. Modify the code to generate the PDF as follows:
    ```csharp
    RadFixedDocumentEditor editor = new RadFixedDocumentEditor(document);

    editor.SectionProperties.PageSize = new Size(Unit.MmToDip(210), Unit.MmToDip(297));
    editor.ParagraphProperties.HorizontalAlignment = HorizontalAlignment.Center;
    
    // Use a font that supports accented characters
    editor.CharacterProperties.Font = FontsRepository.Helvetica;
    
    editor.InsertParagraph();
    editor.InsertRun("Test è ò");
    ```

By using a font that supports accented characters, the issue of missing characters in the PDF should be resolved.

## See AlsoZZZ

- [RadPdfProcessing Documentation](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview)
- [FontsRepository Class](https://docs.telerik.com/devtools/document-processing/api/telerik.windows.documents.fixed.model.fonts.fontsrepository)
