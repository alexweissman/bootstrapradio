# Bootstrapradio 0.1

### By Alex Weissman

Copyright (c) 2014

An attractive, container-free implementation of radio-style selector buttons for Twitter Bootstrap.  Compatible with Font Awesome icons.

### Screenshot


![Bootstrapradio](/screenshots/bootstrapradio.png "Bootstrapradio")

### Usage

#### Markup

Bootstrapradio uses HTML5 `button` elements and a hidden `input` element to implement a radio-style selector.  To initialize, simply create your button elements with the `bootstrapradio` class and the values and text you'd like each to represent.
Each unique `name` represents a different radio button group.  

````
<button type="button" class="bootstrapradio" name="primary_group" value="epicurist" title='Epicurist'>
    <i class='fa fa-fw fa-cutlery'></i>
</button>
<button type="button" class="bootstrapradio" name="primary_group" value="futurist" title='Futurist'>
    <i class='fa fa-fw fa-space-shuttle'></i>
</button>
````

The plugin automatically creates a hidden `input` field with the same name as the group, and updates this field when the selection is changed.

Use the `data-selected` attribute to set a button to initially be selected (`true` or `false`).

````
<button type="button" class="bootstrapradio" name="primary_group" value="epicurist" title='Epicurist' data-selected='true'>
    <i class='fa fa-fw fa-cutlery'></i>
</button>
<button type="button" class="bootstrapradio" name="primary_group" value="futurist" title='Futurist' data-selected='false'>
    <i class='fa fa-fw fa-space-shuttle'></i>
</button>
````

Use the `data-size` attribute to set the size of an option ('xs', 'sm', 'md', or 'lg').  The default size is 'xs'.

````
<button type="button" class="bootstrapradio" name="primary_group" value="epicurist" title='Epicurist' data-selected='true' data-size='lg'>
    <i class='fa fa-fw fa-cutlery'></i>
</button>
````

Use the standard HTML `disabled` property to disable an option:

````
<button type="button" class="bootstrapradio" name="primary_group" value="epicurist" title='Epicurist' disabled>
    <i class='fa fa-fw fa-cutlery'></i>
</button>
````

Get the currently selected value just the same way as you'd get the value of any input field:

````
console.log($("input[name='primary_group']").val());
````

This makes it easy to submit the selected value in a form along with other elements.

#### Javascript

You can also initialize a Bootstrapradio set through jQuery, by calling `bootstrapradio` on one or more of the buttons:

````
// Initialize
$("button[name='beverage']").bootstrapradio();

// Initialize with default value
$("button[name='beverage']").bootstrapradio({
    'default': "beer"
});
````

You can get or set the currently selected value by calling the 'value' method:

````
// Get the value
console.log($("button[name='beverage']").bootstrapradio('value'));

// Change the value
$("button[name='beverage']").bootstrapradio('value', "beer");

````

You can enable or disable a specific option by calling the 'disabled' method on the corresponding element:

```` 
$("button[name='beverage'][value='beer']").bootstrapradio('disabled', 'true');
````

If you disable an element while it is selected, it will become automatically de-selected and the value of the radio group will revert to the empty string.
Notice that 'true' and 'false' are strings.


## Dependencies

### Javascript/CSS (included in this repository)
- jQuery 1.10.2
- Bootstrap 3.0.2

