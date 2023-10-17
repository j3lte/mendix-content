## RefSelector

![AppStoreIcon](/assets/MarketPlaceIcon.png)

Because we can create a better Reference / Reference Set Selector for Mendix

## Features

- Set a Reference (single) or Reference Set (multiple) by using a dropdown
  - This is similar to the [default Reference Selector](https://docs.mendix.com/refguide/reference-selector/), but not native to the [Reference Set Selector](https://docs.mendix.com/refguide/reference-set-selector/)
- Choose a Display value for your reference. Either an attribute or String expression
- Search reference by name
- Improve performance by limiting the number of objects that is shown in the client, automatically refreshing the datasource while searching
- Indicate how many objects can be loaded

## Usage

Place the widget in your page. It will look like a normal reference selector:

![preview](/assets/ref_in_page.png)

If you want to know why you would use it, I recommend checking the [Reference Selector docs](https://docs.mendix.com/refguide/reference-selector/) and [Reference Set Selector docs](https://docs.mendix.com/refguide/reference-set-selector/)

### Preview

![preview2](/assets/screenshot_not_selected.png)
![preview3](/assets/screenshot_selected.png)

### 1. General

#### 1.1 Reference
- Set your Reference. This can either be a **Reference** (1) or **Reference Set** (*)
- Optionally, set an **onChange** action. This action will be triggered when the reference is changed

#### 1.2 Data
- The **Selectable objects** is a list of objects you can choose from to put in the reference. *Make sure this is the same Entity type as the Reference. (Mendix Studio will also give you a warning if this is not the case)*
- **Max Visible options** will determine how many objects will be shown in the dropdown. If you have a lot to choose from (or objects are loading slow), lower this number to improve performance. Mendix will automatically filter the list when you start searching


### 2. UI

#### 2.1 Title
- Choose the **Title attribute** of the options you want to show in the dropdown. This attribute will also be used to search for objects.
- **Display Title** is an alternative title that can be shown in the dropdown. Do note that the search will still be done on the Title attribute

#### 2.2 Placeholder
- The **Placeholder** text that is shown when no option is selected
- The **Nothing found** text is shown when search results are empty

#### 2.3 Bottom Indicator
- When we load a list of selectable options, it could be that we only load a portion (if the amount of items shown, see General, is lower than the total). If that's the case, we show a bottom indicator in the dropdown that shows `{number shown} / {total}`. You can disable this (*by default it's enabled*)


### 3. Behavior

#### 3.1 On Select
- When an option is selected, the dropdown will close by default on single option selection and stay open on multiple option selection. You can override this behavior by setting the **'Close on Select**' option

#### 3.2 Disabled
- You can disable options from being selected by using the '**Disable option**' expression. This will still show the option in the dropdown, but it will be disabled and cannot be selected.


### 4. Validation
- The widget will handle validation messages coming from the client (for example triggered in a Nanoflow/Microflow)
#### 4.1 Required
- Besides validation messages, it will also adhere to the '**Required**' setting. If this is true, a
  - Single Reference cannot be cleared
  - Reference Set cannot be empty (you cannot deselect the last selected option)

### 5. Common
- This widget has a few common properties that can be found in most widgets:
    - Label
    - Conditional Visibility
    - Conditional Editability
    - Name

## Styling

Most of the styling of this widget is done by the component itself. However, you can override the following classes to change the styling:

```css
.widget-select {}
.widget-select__control {}
.widget-select__control.widget-select__control--menu-is-open {}
.widget-select__value-container {}
.widget-select__value-container--is-multi {}
.widget-select__placeholder {}
.widget-select__input-container {}
.widget-select__input {}
.widget-select__indicators {}
.widget-select__indicator-separator {}
.widget-select__dropdown-indicator {}
.widget-select__clear-indicator {}
.widget-select__menu {}
.widget-select__menu-list {}
.widget-select__menu-list.widget-select__menu-list--is-multi {}
.widget-select__option {}
.widget-select__option.widget-select__option--is-focused {}
.widget-select__checkbox {}
```

Note that most of this targetted styling will probably need `!important` to override the default styling.

## Demo project

[Click here](https://caffcodecontenttestapp-sandbox.mxapps.io/p/ref-selector-home) to see the widget in action

## Issues, suggestions and feature requests

This module is published as Community Supported. If you have issues, please report them on Github: [https://github.com/j3lte/mendix-content/issues](https://github.com/j3lte/mendix-content/issues)

_Need more help? Or maybe help with your Mendix project?_

[Check out CaffCode](https://caffcode.com)

## License

The MIT License (MIT)

Copyright © CaffCode 2023. All Rights Reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
