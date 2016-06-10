# ng-Autocomplete

A simple directive for adding google places autocomplete to a textbox element.

Updated to now use ng-model, should work much better in forms. Can now set an initial value using ng-model. Using the ng-model to set the textbox value does not trigger the autocomplete query.

Tested with angularjs-1.2.4

Uses optional directive parameters, so it won't work with <1.2. If people are interested I'll release a <1.2 version.

## Examples

+ [Example Plunkers - Simple Usage](http://plnkr.co/edit/GE34ojss9xMGm0024FvM?p=preview)

+ [Example Plunkers - Advanced Usage](http://plnkr.co/edit/GF3nM3XfYX9El2w11pGo?p=preview)

## Usage

Include the required libraries
```html
<script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?libraries=places&sensor=false"></script>
```

Declare a dependency on the `ngAutocomplete` module
``` javascript
var app = angular.module('myModule', ['ngAutocomplete']);
```

Add the directive to a textbox

``` javascript
    <input type="text"  ng-autocomplete ng-model="autocomplete" options="options" details="details"/>
```

## Documentation

+ ng-model - autocomplete textbox value

+ details - more detailed autocomplete result, includes address parts, latlng, etc. (Optional)

+ options - configuration for the autocomplete (Optional)

    + types: type,        String, values can be 'geocode', 'establishment', '(regions)', or '(cities)'
	+ bounds: bounds,     Google maps LatLngBounds Object, biases results to bounds, but may return results outside these bounds
	+ country: country    String, ISO 3166-1 Alpha-2 compatible country code. examples; 'ca', 'us', 'gb'
    + watchEnter:         Boolean, true; on Enter select top autocomplete result. false(default); enter ends autocomplete  

example:
``` javascript
options = {
types: '(cities)',
country: 'ca'
}
```

google places autocomplete info: https://developers.google.com/maps/documentation/javascript/places

## Author

**Will Palahnuk** (http://github.com/wpalahnuk)

## Credits

google places autocomplete https://developers.google.com/maps/documentation/javascript/places
