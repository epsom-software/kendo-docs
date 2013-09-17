---
title: kendo.ui.Button
meta_description: Configuration, methods and events of the Kendo UI Button
slug: api-web-button
relatedDocs: gs-web-button-overview
tags: api,web,button
publish: true
---

# kendo.ui.Button

## Configuration

### enable `Boolean` *(default: true)*

Indicates whether the Button should be enabled or disabled. By default, it is enabled, unless a `disabled="disabled"` attribute is detected.

#### Example

	<button id="button" type="button">Foo</button>
	<script>
	$("#button").kendoButton({
		enable: false
	});
	</script>

### imageUrl `String`

Defines a URL, which will be used for an `img` element inside the Button. The URL can be relative or absolute. In case it is relative, it will be evaluated with relation to the web page URL.

The `img` element can be added automatically by the widget, or an existing element can be used, if it has a `k-image` CSS class applied.

#### Example

	<button id="button" type="button">Edit</button>
	<script>
	$("#button").kendoButton({
		imageUrl: "/images/edit-icon.gif"
	});
	</script>

#### Example with an existing img element

	<button id="button" type="button">
		<img class="k-image" alt="Edit" /> Edit
	</button>
	<script>
	$("#button").kendoButton({
		imageUrl: "/images/edit-icon.gif"
	});
	</script>

### spriteCssClass `String`

Defines a CSS class (or multiple classes separated by spaces), which will be used for a `span` element inside the Button with a background image.
In case you want to use an icon from the Kendo UI theme sprite background image, you need to define two classes - `k-icon` and the respective icon CSS class.

The `span` element can be added automatically by the widget, or an existing element can be used, if it has a `k-sprite` CSS class applied.

#### Example

	<button id="button" type="button">Edit</button>
	<script>
	$("#button").kendoButton({
		spriteCssClass: "k-icon k-edit"
	});
	</script>

#### Example with an existing span element

	<button id="button" type="button">
		<span class="k-sprite"></span> Edit
	</button>
	<script>
	$("#button").kendoButton({
		spriteCssClass: "k-icon k-edit"
	});
	</script>

## Methods

### enable

Enables or disables the Button.

#### Parameters

##### toggle `Boolean`

Indicates whether the Button should be enabled or disabled. Truthy and falsy arguments are accepted. If no argument is supplied, the Button will assume `true` and will be enabled.

#### Example

	<button id="button" type="button">Edit</button>
	<script>
	$("#button").kendoButton();
	var button = $("#button").data("kendoButton");
	// disable button
	button.enable(false);
	// enable button
	button.enable(true);
	</script>

## Events

### click

Fires when the button is clicked with the mouse, touched on a touch device, or ENTER (or SPACE) is pressed while the button is focused.

#### Example - subscribe to the "click" event during initialization

	<button id="button" type="button">Edit</button>
	<script>
	$("#button").kendoButton({
		click: function() {
			alert("button clicked");
		}
	});
	</script>

#### Example - subscribe to the "click" event after initialization

	<button id="button" type="button">Edit</button>
	<script>
	$("#button").kendoButton();
	var button = $("#button").data("kendoButton");
	button.bind("click", function() {
		alert("button clicked");
	});	
	</script>