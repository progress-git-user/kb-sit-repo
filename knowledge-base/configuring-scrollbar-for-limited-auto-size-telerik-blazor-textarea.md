---
title: Setting Scrollbar for Blazor TextArea with Limited Auto Size
description: Learn how to configure a scrollbar for the Telerik Blazor TextArea component when limiting its auto-resizing functionality.
type: how-to
page_title: Configuring Scrollbar for Limited Auto Size in Telerik Blazor TextArea
slug: configuring-scrollbar-for-limited-auto-size-telerik-blazor-textarea
tags: textarea, blazor, scrollbar, auto-size, limit
res_type: kb
category: knowledge-base
ticketid: 1612943
---

## Environment

| Product           | Version      |
|-------------------|--------------|
| TextArea for Blazor | 2020.2.617 |

## Description

When using the [TextArea](https://docs.telerik.com/blazor-ui/components/textarea/overview) component for Blazor, you might need to limit its auto size area to prevent it from expanding indefinitely and instead show a scrollbar. This KB article also answers the following questions:
- How can I prevent the TextArea from resizing beyond a certain point?
- How do I add a scrollbar to the TextArea when its content exceeds the maximum height?
- Is it possible to limit the TextArea's size while maintaining user input visibility?

## Solution

To limit the auto-resizing area of the TextArea and introduce a scrollbar for overflow content, follow these steps:

1. Set a fixed height for the TextArea to define its maximum size.
2. Enable the `overflow-y` CSS property to `auto` or `scroll` to ensure a scrollbar appears when the content exceeds the TextArea's height.

### Step-by-Step Instructions

1. Add the TextArea component to your Blazor application.

```razor
<TelerikTextArea @bind-Value="@TextAreaValue" Style="height:200px; overflow-y:auto;"></TelerikTextArea>
```

2. In the above code, the `Style` attribute is used to set a fixed height (`height:200px;`) for the TextArea. This limits its vertical expansion.

3. The `overflow-y:auto;` CSS property ensures that a vertical scrollbar appears only when the content exceeds the predefined height. If you prefer the scrollbar to be always visible regardless of the content height, use `overflow-y:scroll;` instead.

4. Bind the `Value` property of the TextArea to a variable in your code-behind file to capture the user input.

```csharp
@code {
    private string TextAreaValue { get; set; }
}
```

By following these steps, you can effectively limit the auto-resizing functionality of the Telerik Blazor TextArea component and introduce a scrollbar for handling overflow content, ensuring a consistent user experience.

## Notes

- Adjusting the `height` value in the `Style` attribute allows you to control the maximum size of the TextArea according to your application's needs.
- The `overflow-y` property is crucial for managing how overflow content is displayed, with `auto` being the most flexible option as it only shows a scrollbar when necessary.

## See Also

- [Telerik Blazor TextArea - Overview](https://docs.telerik.com/blazor-ui/components/textarea/overview)
- [CSS Overflow Property](https://www.w3schools.com/css/css_overflow.asp)
