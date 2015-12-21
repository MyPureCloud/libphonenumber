libphonenumber
==============

So, you use [intl-tel-input](https://github.com/Bluefieldscom/intl-tel-input) and a [custom build of libphonenumber](https://github.com/nathanhammond/libphonenumber) in your project. But intl-tel-input already includes libphonenumber and you only want to ship with one libphonenumber, right? This repo combines the exports and helper methods in each of the aforementioned libraries and compiles them into one single file. You can then use ``phoneUtils`` like you normally would and tell intl-tel-input to use a specific version of libphonenumber by passing the path in the options object.

https://github.com/nathanhammond/libphonenumber
+ This project was forked from here.
+ Includes a nice build script that pulls in Google's dependencies and runs the build.
+ Also includes some handy shortcut methods.

https://github.com/Bluefieldscom/intl-tel-input
+ A jQuery plugin for entering and validating international telephone numbers
+ Also exposes some handy helper methods.

To Update
--------
Copy the contents of the two build files into libphonenumber. You will have to reconcile some differences (i.e., duplicate import statements and ensuring unique method names)
  1. [intl-tel-input/utils.js](https://github.com/jackocnr/intl-tel-input/blob/master/lib/libphonenumber/src/utils.js).
  2. [nathanhammond/libphonenumber.js](https://github.com/nathanhammond/libphonenumber/blob/master/libphonenumber.js)

To Build
--------
Just run the ``build.sh`` file and make sure you have svn, git and ant installed.

Exports
-------

This library adds the global `phoneUtils` with the following methods:

```js
// exports by nathanhammond/libphonenumber
goog.exportSymbol('phoneUtils.isPossibleNumber', isPossibleNumber);
goog.exportSymbol('phoneUtils.isPossibleNumberWithReason', isPossibleNumberWithReason);
goog.exportSymbol('phoneUtils.isValidNumber', isNumberValid);
goog.exportSymbol('phoneUtils.isValidNumberForRegion', isValidNumberForRegion);
goog.exportSymbol('phoneUtils.getRegionCodeForNumber', getRegionCodeForNumber);
goog.exportSymbol('phoneUtils.formatE164', formatE164);
goog.exportSymbol('phoneUtils.formatNational', formatNational);
goog.exportSymbol('phoneUtils.formatInternational', formatInternational);
goog.exportSymbol('phoneUtils.formatInOriginalFormat', formatInOriginalFormat);
goog.exportSymbol('phoneUtils.formatOutOfCountryCallingNumber', formatOutOfCountryCallingNumber);

// exports by intl-tel-input
goog.exportSymbol('intlTelInputUtils', {});
goog.exportSymbol('intlTelInputUtils.formatNumber', formatNumber);
goog.exportSymbol('intlTelInputUtils.formatNumberByType', formatNumberByType);
goog.exportSymbol('intlTelInputUtils.getExampleNumber', getExampleNumber);
goog.exportSymbol('intlTelInputUtils.getNumberType', getNumberType);
goog.exportSymbol('intlTelInputUtils.getValidationError', getValidationError);
goog.exportSymbol('intlTelInputUtils.isValidNumber', isValidNumber);
goog.exportSymbol('intlTelInputUtils.numberType', numberType);
goog.exportSymbol('intlTelInputUtils.validationError', validationError);
goog.exportSymbol('intlTelInputUtils.numberFormat', numberFormat);
```
