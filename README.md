GoogleMapsGeocoder
==================

A PHP wrapper for the Google Maps Geocoding API v3.

Developed by [Justin Stayton](http://twitter.com/jstayton) while at
[Monk Development](http://monkdev.com).

*   [Documentation](http://jstayton.github.com/GoogleMapsGeocoder/classes/GoogleMapsGeocoder.html)
*   [Release Notes](https://github.com/jstayton/GoogleMapsGeocoder/wiki/Release-Notes)

Requirements
------------

*   PHP >= 5.2.0

Installation
------------

### Composer

The recommended installation method is through
[Composer](http://getcomposer.org/), a dependency manager for PHP. Just add
`jstayton/google-maps-geocoder` to your project's `composer.json` file:

    {
        "require": {
            "jstayton/google-maps-geocoder": "*"
        }
    }

[More details](http://packagist.org/packages/jstayton/google-maps-geocoder) can
be found over at [Packagist](http://packagist.org).

### Manually

1.  Copy `GoogleMapsGeocoder.php` to your codebase, perhaps to the `vendor`
    directory.
2.  Add the `GoogleMapsGeocoder` class to your autoloader or `require` the file
    directly.

Getting Started
---------------

We'll use the address of [Monk Development](http://monkdev.com) for this
example:

    $address = "2707 Congress St., San Diego, CA 92110";

There are two ways to set the address of a `GoogleMapsGeocoder` object. Either
the address can be passed to the constructor:

    $Geocoder = new GoogleMapsGeocoder($address);

Or the address can be set after the object is created:

    $Geocoder = new GoogleMapsGeocoder();
    $Geocoder->setAddress($address);

By default, the `format` is set to `json` and the `sensor` is set to `false`.
These values can be changed either through the constructor or after the object
is created. See the
[documentation](http://jstayton.github.com/GoogleMapsGeocoder/classes/GoogleMapsGeocoder.html)
for the complete list of API parameters that can be changed.

Once all parameters are set, the final step is to send the request to the
Google Maps Geocoding API:

    $response = $Geocoder->geocode();

The `geocode` method converts the response into a JSON associative array
(default) or `SimpleXMLElement` object depending on the specified `format`. See
the `geocode`
[documentation](http://jstayton.github.com/GoogleMapsGeocoder/classes/GoogleMapsGeocoder.html#geocode)
for making the request over HTTPS or preventing conversion (instead returning
the raw plain text response).

Feedback
--------

Please open an issue to request a feature or submit a bug report. Or even if
you just want to provide some feedback, I'd love to hear. I'm also available on
Twitter as [@jstayton](http://twitter.com/jstayton).

Contributing
------------

1.  Fork it.
2.  Create your feature branch (`git checkout -b my-new-feature`).
3.  Commit your changes (`git commit -am 'Added some feature'`).
4.  Push to the branch (`git push origin my-new-feature`).
5.  Create a new Pull Request.