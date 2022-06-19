# FluentUI-for-Teams theme

Building Power Apps canvas apps for Microsoft Teams can include some tedious tasks, as there is no theme included in the Power Apps studio and even Microsoft's new [Creator kit](https://docs.microsoft.com/power-platform/guidance/creator-kit/overview) doesn't offer Microsoft Teams specific Fluent UI components.

This sample

* provides you with a reference Power Apps canvas app that includes a customized `themes.json` to manipulate the default style of controls to blend into the look & feel of Microsoft Teams. It includes

  * [Button](#button)
  * [Checkbox](#checkbox)
  * [Dropdown](#dropdown)
  * [Combobox](#combobox)
  * [Datatable](#datatable)
  * [Datepicker](#datepicker)
  * [Icons](#icons)
  * [Listbox](#listbox)
  * [Radiobutton](#radiobutton)
  * [Rating](#rating)
  * [Slider](#slider)
  * [Textlabel](#textlabel)
  * [Textinput](#textinput)
  * [Toggle](#toggle)
* exemplifies [canvas components](#components) for
  * [Carousel](#carousel-component)
  * [Coachmark](#coachmark-component)
  * [Combobox](#combobox-component)
  * [Datepicker & Calendar](#datepicker-component)
  * [Donut Chart](#donut-chart-component)
  * [Dropdown](#dropdown-component)
  * [Likert scale](#likert-component)
  * [Sidebar navigation](#sidebar-navigation-component)
  * [TextInput](#textinput-component)
  * [Toast](#toast-component)
* gives you examples on how [screens](#screens) could look like
  * [List](#list-screen)
  * [Empty list](#empty-list-screen)
  * [Chart](#chart-screen)
* reflects all styles in [3 modes](#microsoft-teams-themes): default, dark, and high-contrast.

## Demo

![Fluent UI for Teams walkthrough](assets/FluentUiforTeams.gif)

## Context

The app is context aware in terms of language (example in navigation, works in English and German) and Teams theme. Users can override the context by selecting a different language and theme in the app. (This also serves development and debugging purposes.)

## Microsoft Teams themes

Teams' Desktop and Web client support default, dark and high contrast theme, the mobile client supports default and dark theme. The app reacts dynamically on a theme change as all colors as `gblAppColors` and the styles as `gblAppStyles` for or all controls are stored in the App's **OnStart** property.

## Controls

This is an overview of all controls how they are now defined in the `themes.json` file. This work is based on the [Teams UI toolkit](https://docs.microsoft.com/microsoftteams/platform/concepts/design/design-teams-app-ui-templates), which is based on [Fluent UI](https://fluentsite.z22.web.core.windows.net/0.63.0) and also guides developers to more likely pass the App source validation of their Microsoft Teams applications.

All controls respect the font and color schema regarding the states **rest**, **hover**, **pressed**, and **disabled**.

> However, styling these controls even in the `themes.json` has its limits, for example you can't manipulate the background color of the calendar in the DatePicker control. This is why I also created canvas components and included these in the sample. You can find information on what ist not stylable neither out-of-the-box in Power Apps Studio nor with manipulation of `themes.json` in each section below.

I tried to get as close as possible to achieve that *Teams native* look, still not every desirable modification is supported.

### Button

![button](assets/button.gif)

A drop shadow is not stylable for the button control, however you can achieve it with an **HTML control** in inject CSS inline:

``` CSS

"<div style='margin:10px;width:"&btn_1.Width&"px;height:"&btn_1.Height &"px;background-color:#;box-shadow:3px 3px 6px 3px  rgba(0,0,0,0.14); border-radius:4px'></div>"

```

### Checkbox

![Checkbox](assets/Checkbox.gif)

### Dropdown

![Dropdown](assets/Dropdown.gif)

The Dropdown should have a primary-colored line at the bottom, this is not achievable out-of-the box, I created a [Dropdown component](#dropdown-component) for this design requirement.

### Combobox

![Combobox](assets/Combobox.gif)

The Combobox should have a primary-colored line at the bottom, this is not achievable out-of-the box, I created a [Combobox component](#combobox-component) for this design requirement.

### Datatable

![Datatable](assets/Datatable.gif)

### Datepicker

![Datepicker](assets/Datepicker.gif)

The DatePicker is a bit stylable, however the background color of the calendar can't be changed, which doesn't look good in dark mode or high contrast mode. I built a [Datepicker component](#datepicker-component) to tackle this.

### Icons

![Icons](assets/Icons.gif)

### Listbox

![Listbox](assets/Listbox.gif)

### Radiobutton

![Radiobutton](assets/Radiobutton.gif)

### Rating

![Rating](assets/Rating.gif)

### Slider

![Slider](assets/Slider.gif)

The slider looks as it should, still I created some components that make use of it: Check out [Likert component](#likert-component) and [Donut chart component](#donut-chart-component)

### Textlabel

![Textlabel](assets/Textlabel.gif)

### TextInput

![Textinput](assets/Textinput.gif)

The Textinput should have a primarycolored line at the bottom, this is not achievable out-of-the box, I created a [Textinput component](#Textinput-component) for this design requirement.

### Toggle

![Toggle](assets/Toggle.gif)

## Components

The provided components refer to the custom theme with custom properties.

### Carousel component

![Carousel component]()

### Coachmark component

![Coachmark component]()

### Combobox component

![Combobox component]()

### Donut chart component

![Donut chart component]()

### Datepicker component

![Datepicker component]()

### Dropdown component

![Dropdown component]()

### Likert component

![Likert component]()

### Textinput component

![Textinput component]()

### Toast component

![Toast component]()

### Sidebar navigation component

![Sidebar navigation component]()

## Screens

### List screen

![List screen](assets/ListScreen.png)

#### Empty list screen

![List screen empty](assets/ListScreenEmpty.png)

### Chart screen

I also manipulated the primary palette which determines which colors are shown in charts.

![Chart screen](assets/ChartScreen.png)
