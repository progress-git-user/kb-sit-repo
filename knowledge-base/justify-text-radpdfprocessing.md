---
title: Justifying Text Using RadPdfProcessing
description: Learn how to justify text lines in PDF documents created with RadPdfProcessing.
type: how-to
page_title: How to Justify Text in PDFs with RadPdfProcessing
slug: justify-text-radpdfprocessing
tags: radpdfprocessing, documentprocessing, radfixeddocumenteditor, insertrun, insertline, textalignment
res_type: kb
category: knowledge-base
ticketid: 1465325
---

## Environment

| Product | Version |
| --- | --- |
| RadPdfProcessing for Document Processing | 1.0 |

## Description

When creating PDF documents using the [RadPdfProcessing](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing) library, you may want to justify text to ensure it is evenly aligned on both the left and right margins. This KB article demonstrates how to justify lines of text using the `RadFixedDocumentEditor`.

This KB article also answers the following questions:

- How can I align text to both margins in a PDF document using RadPdfProcessing?
- Is it possible to justify text in PDFs created with RadPdfProcessing?
- What methods are available for text alignment in RadPdfProcessing?

## Solution

RadPdfProcessing does not provide a built-in method for justifying text directly. However, you can achieve text justification by manually calculating the spaces needed and adjusting the positions of words in a line. Follow these steps to justify text:

1. Determine the width of the text line you want to justify.
2. Calculate the total width of all characters and spaces in the line.
3. Find the extra space needed to justify the line by subtracting the total width of characters from the line width.
4. Divide the extra space by the number of spaces in the line to find the additional space to add between words.
5. Use the `InsertRun` method to add text with additional spaces between words as needed to fill the line width.

```csharp
// Example of manually justifying a line of text
public void JustifyTextLine(RadFixedDocumentEditor editor, string text, double lineWidth)
{
    string[] words = text.Split(new char[] { ' ' }, StringSplitOptions.RemoveEmptyEntries);
    double totalWordsWidth = 0;
    foreach (var word in words)
    {
        // Measure the width of each word
        totalWordsWidth += editor.MeasureText(word).Width;
    }

    double totalSpacesWidth = lineWidth - totalWordsWidth;
    int spacesCount = words.Length - 1;
    double extraSpacePerWord = totalSpacesWidth / spacesCount;

    for (int i = 0; i < words.Length; i++)
    {
        editor.InsertRun(words[i]);
        if (i < words.Length - 1)
        {
            // Insert additional space to justify the line
            double spaceWidth = editor.MeasureText(" ").Width + extraSpacePerWord;
            editor.InsertSpace(spaceWidth);
        }
    }
    editor.InsertLine("");
}
```

This method splits the text into words, calculates the extra space needed to justify the line, and inserts the words with additional space between them. It assumes you have a `RadFixedDocumentEditor` instance and a specific line width for justification.

## Notes

- The above solution assumes monospaced fonts for simplicity. For proportional fonts, you might need to adjust the calculation based on the actual width of each word and space.
- This method does not automatically handle hyphenation or word wrapping. You may need to implement additional logic if your text requires these features.

## See Also

- [RadPdfProcessing Documentation](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing)
- [RadFixedDocumentEditor Overview](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/editing/radfixeddocumenteditor)
- [MeasureText Method](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/editing/textmeasurement)
