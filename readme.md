# Tilt/Open Pre-Orders

## Checkout Customization Guide

We're looking forward to helping you customize your Pre-Order checkout modal! Below you'll find some tips & tricks to get you going.

## Custom CSS

To update CSS styling, visit the "Customize CSS" tab from your menu bar and click on "Embed form."

![Customize Form](https://s3-us-west-2.amazonaws.com/sandbox-matt/customize_form.png)

Styles added here will be loaded on both the checkout payment page and on the checkout confirmation page.

Here are some snippets to get you going:

### Change the button color

```
.btn {
  background-color: #c23c33;    
}    

.btn:active {
  background-color: #c23c33;
  opacity: .75;
}

.btn:hover {
  background-color: #a53730;
}

```

### Hiding checkout calculator

```
.new-checkout-summary {
  display:none;
}
```

### Updating the background color of the entire form

```
.tilt_content {
  background-color: #ADD8E6;
  border-radius: none;
}

.tilt_content_bottom {
  border-top: none;
  background-color: #ADD8E6;
}

.tilt_modal {
  border: none;
}

```

### Hiding the quantity selector

```
#quantity-fieldset {
  display:none;
}
```

## Custom JavaScript


To do things like swapping the order of fields or adding additional html elements (like text or links), you'll make the changes by writing JavaScript to be included on your checkout form.

For security reasons, we don't allow for the updating of JavaScript directly in the admin panel. To add custom JS, please email it to your dedicated Campaign Success Manager.

Our preferred format for receiving these are via [Github Gists](gist.github.com) as it allows us to maintain a history of changes to the JavaScript.

You can test your changes locally before sending by adding them to the JavaScript console in your browser. 

Try it out by visiting [this sample campaign](https://openmatt.tilt.com/custom-javascript/checkout/payment), hitting ```<Alt>-<cmd>-<J>```, and entering the following snippet. This will add a new line of text below the checkout calculator:

```
$('.new-checkout-summary').append('<p>Some new text!</p>');
```

To make for easy styling, you could also add a class:

```
$('.new-checkout-summary').append('<p class="new-text">Some new text!</p>');
```


Some other notes about custom JavaScript:

* jQuery is already loaded on the page, so feel free to make use of it :)
* You may send over JS to be added to both the checkout payment page and the checkout confirmation page.
* Feel free to include conversion pixels in your confirmation page JavaScript -- many choose to include Facebook conversion pixels, Adroll conversion pixels, etc.


Here are some additional JavaScript snippets to get you going:

### Change the label of an input

Instead of "shipping address," let's use "Where should we ship to?"

```
$('#address-fieldset h4').html('Where should we ship to?');
```

### Collect emails from international users
Since we're not shipping to international users at launch, let's create a link to a form where they can let us know of their interest.

```
$('#payment-fieldset').append('<a href="http://www.CustomForm.com" target="_blank" class="international-toggle">Not in the US?</a>');
```

### Pre-fill a name 
Let's pre-fill the name of our contriutor

```
$('#payment_fullname').val('Our Contributor!');
```

### Pre-select a custom option
Let's set the standard shirt size we ask for in a custom option to "Medium"

```
$('#payment_custom_options_size').val('Medium');
```
