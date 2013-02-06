# jQuery SelectUnique Plugin

Given a group of select fields with the same options, SelectUnique will remove an option from the other select fields when it's selected, and put it back when it's changed.

[Demo](http://sshaw.github.com/jquery-selectunique#demo)

## Usage

SelectUnique requires jQuery 1.7.

    <script type="text/javascript" src="jquery-1.7.0.min.js"></script>
    <script type="text/javascript" src="jquery.selectunique.js"></script>

    $(selector).selectunique();

### Options

#### `ignoreOption`

    $(selector).selectunique({ 
	    ignoreOption: function(option) { return option.val() == 'ignore_me_buddy' } 
    });
   
Instruct the plugin to not manage the given option. The `option`
argument passed to the function is a jQuery object. 

### Methods

#### `refresh`

	$(selector).selectunique('refresh');

Refresh the state of the select fields given by `selector`. 
This is useful of you're adding and/or removing select fields via JavaScript.

#### `remaining`

    var opts = $(selector).selectunique('remaining');
	$.each(opts, function() { 
		console.log('text: ' + this.text + ' value: ' + this.value);
	});

An array of remaing options. I.e., options still  available for selecting. Returns an empty array if
no options are available. Each element is an `Object` with a `text`
and `value` property. 

#### `selected`

	var opts = $(selector).selectunique('selected');
	$.each(opts, function() { 
		console.log('text: ' + this.text + ' value: ' + this.value);
	});

An array of options that have been selected. Returns an empty array if
no options have been selected. Each element is an `Object` with a `text`
and `value` property. 

	

