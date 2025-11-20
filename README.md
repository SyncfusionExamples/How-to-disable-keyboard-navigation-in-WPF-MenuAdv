# How to Disable Keyboard Navigation in WPF MenuAdv
This example demonstrates how to disable keyboard navigation in the WPF [MenuAdv](https://help.syncfusion.com/wpf/menu/getting-started) control, part of the Syncfusion WPF suite. By default, MenuAdv allows navigation through menu items using keys such as **Arrow**, **Tab**, and **Enter**. In some scenarios, you may want to restrict this behavior so that navigation occurs only through mouse interaction or custom logic.

## Why Disable Keyboard Navigation?
Disabling keyboard navigation can be useful when:
- Keyboard shortcuts are reserved for other operations.
- You want to maintain a specific user experience without keyboard-based menu navigation.

## Implementation Overview
You can disable keyboard navigation in MenuAdv by handling the PreviewKeyDown event and marking specific keys as handled.

## Code Example
**XAML**
```XAML
<syncfusion:MenuAdv Height="30" Width="150" PreviewKeyDown="MenuAdv_PreviewKeyDown">
    <syncfusion:MenuItemAdv Header="File">
        <syncfusion:MenuItemAdv Header="New" />
        <syncfusion:MenuItemAdv Header="Open" />
    </syncfusion:MenuItemAdv>
    <syncfusion:MenuItemAdv Header="View">
        <syncfusion:MenuItemAdv Header="Zoom In" />
        <syncfusion:MenuItemAdv Header="Zoom Out" />
        <syncfusion:MenuItemAdv Header="Normal View" />
    </syncfusion:MenuItemAdv>
</syncfusion:MenuAdv>
```
**C#**
```C#
private void MenuAdv_PreviewKeyDown(object sender, KeyEventArgs e)
{
    switch (e.Key)
    {
        case Key.Left:
        case Key.Right:
            e.Handled = true; // Disable left/right navigation
            break;
        default:
            break;
    }
}
```

## Reference
For complete implementation details, refer to the official Syncfusion Knowledge Base: https://www.syncfusion.com/kb/11985/how-to-disable-keyboard-navigation-in-wpf-menuadv
