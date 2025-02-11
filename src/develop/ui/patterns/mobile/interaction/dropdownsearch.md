---
tags: runtime-mobileandreactiveweb;
summary: The Dropdown Search UI Pattern offers a choice of available options that the user can search.
---

# Dropdown Search

The Dropdown Search UI Pattern offers a choice of available options that the user can search. When the available options' sort order is not clear, the Dropdown Search is especially helpful.

![](<images/dropdownsearch-1-ss.png>)

**How to use the Dropdown Search UI Pattern**

In this example, we create a dropdown search for a list of employees, and when an employee is selected, a message displays their employee Id.

1. In Service Studio, in the Toolbox, search for `Dropdown Search`.

    The Dropdown Search widget is displayed.

    ![](<images/dropdownsearch-2-ss.png>)

    If the UI widget does not display, it may be because you used a ready-made app, which deletes unused widgets from the module. To make additional widgets available in your app:

    a. Go to **Module > Manage dependencies**.

    b. Search for and select the relevant Producer, for example OutSystemsUI. Ensure Show All is selected. 

    c. On the Public elements for the selected Producer displayed on the right, ensure Show All is selected.
    
    d. Search for and select the element you want to add, and click **Apply**. 
    
    e. In Service Studio, in the Toolbox, search for the widget again.

1. From the Toolbox, drag the Dropdown Search widget into the Main Content area of your application's screen.

    ![](<images/dropdownsearch-3-ss.png>)

1. Select and right-click your screen name, and select **Fetch Data from Database**.

1. To add a database entity, click the screen, and from the **Select Source** pop-up, select the relevant database entity and click **OK**.

    In this example, we select the Employee entity. 

    ![](<images/dropdownsearch-4-ss.png>)

    The **GetEmployee** aggregate is automatically created.

    ![](<images/dropdownsearch-6-ss.png>)

1. Return to your screen by double-clicking the screen name, select the Dropdown Search widget, and on the **Properties** tab, set the mandatory properties (ItemList, Value, Text).

    ![](<images/dropdownsearch-5-ss.png>)

1. Staying on the **Properties** tab, from the **Handler** dropdown, select **New Client Action**.

1. Add the relevant logic to the client action. 

    In this example, we add a Message to the client action and in the Expression Editor enter the following logic and click **DONE**. This will display the selected employee's name and their Id.

    `SelectedItem.Text + "( Employee ID: " + SelectedItem.Value + ")"`

    ![](<images/dropdownsearch-9-ss.png>)

1. You can change the Dropdown Search's look and feel by setting the (Optional) properties on the **Properties** tab.

    ![](<images/dropdownsearch-10-ss.png>)

After following these steps and publishing the module, you can test the pattern in your app. The results from this example should look something like the following:

![](<images/dropdownsearch-8-ss.png>)

## Setting the number of returned suggestions

By default, Dropdown Search returns four search results in the dropdown list. You can change this number by editing the **AdvancedFormat** property of the widget.

To increase the limit to 10 suggestions, enter `"{searchResultLimit:10}"` in **AdvancedFormat**.

![Property to set the number of suggestions](images/dropdownsearch-set-number-of-suggestions-ss.png?width=320)

## Properties

| Property | Description |
|---|---|
| ItemList (DropdownItem List): Mandatory | List of items to show in the dropdown. |
| SelectedItem (DropdownItem): Optional | Defines a preselected item from the dropdown list. |
| IsDisabled (Boolean): Optional | If True, the dropdown search is disabled. If False, the dropdown search is enabled. This is the default. |
| EmptyText (Text): Optional | Text that is displayed when no items are selected. "Select an item" is the default text.|
| SearchPrompt (Text): Optional | Text that is displayed in the Search prompt/placeholder. |
| NoResultsText (Text): Optional | Text that is displayed when there are no results. |
| AdvancedFormat (Text): Optional | Enables more options beyond what's provided through the inputs. For more options, go to [Choices library](https://github.com/jshjohnson/Choices). Default value is `{}`. You can also use fuse.js options to change the search configurations. For more information on search configurations, see [Fuse](https://fusejs.io/). <br/><br/> See also [Setting the number of returned suggestions](#setting-the-number-of-returned-suggestions) |
| ExtendedClass (Text): Optional | Adds custom style classes to the Pattern. You define your [custom style classes](../../../look-feel/css.md) in your application using CSS.<br/><br/>Examples<br/><br/> <ul><li>_Blank_ - No custom styles are added (default value).</li><li>_"myclass"_ - Adds the _myclass_ style to the UI styles being applied.</li><li>_"myclass1 myclass2"_ - Adds the _myclass1_ and _myclass2_ styles to the UI styles being applied.</li></ul>You can also use the classes available on the OutSystems UI. For more information, see the [OutSystems UI Live Style Guide](https://outsystemsui.outsystems.com/StyleGuidePreview/Styles). |
