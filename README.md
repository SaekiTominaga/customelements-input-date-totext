# Convert date control to <input type=text> by Custom Elements.

[![npm version](https://badge.fury.io/js/%40saekitominaga%2Fcustomelements-input-date-totext.svg)](https://badge.fury.io/js/%40saekitominaga%2Fcustomelements-input-date-totext)

Converts `<input type=date>` in the HTML source code to `<input type=text>`. In some cases, it is troublesome to select a date decades ago in the calendar picker of the browser, so use it when you dare to set `<input type=text>` such as date of birth.

- In addition to the YYYY-MM-DD format, you can enter in the YYYY/MM/DD and YYYYMMDD formats.
- You can omit leading 0 of the month and day, such as 2000-1-3 or 2000/1/3.
- You can also enter in full-width numbers.
- If a non-existent date such as February 30 is entered, the error message specified by the `data-validation-message-date-noexist` attribute is set to [`HTMLInputElement.setCustomValidity()`](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#dom-cva-setcustomvalidity). (The specific behavior depends on the browser, but most will be displayed in a tooltip).

## Demo

- [Demo page](https://saekitominaga.github.io/customelements-input-date-totext/demo.html)

## Examples

```HTML
<input type="date" is="x-date-to-text"
  min="2000-01-01"
  max="2020-12-31"
  data-validation-message-date-noexist="This date does not exist."
  data-validation-message-date-min="Please enter a value after A.D.2000."
  data-validation-message-date-max="Please enter a value before A.D.2020."
/>
```

## Attributes

<dl>
<dt>min, max [optional]</dt>
<dd>Of the attributes that can be specified with <code>&lt;input type=date&gt;</code>, <a href="https://html.spec.whatwg.org/multipage/input.html#the-min-and-max-attributes">the <code>min</code> and <code>max</code> attributes</a> can be specified. Please refer to the HTML specification for the usage of attributes.</dd>
<dt>step</dt>
<dd><strong>Currently, it does not support <a href="https://html.spec.whatwg.org/multipage/input.html#attr-input-step"><code>step</code> attribute</a>.</strong></dd>
<dt>data-validation-message-date-noexist [required]</dt>
<dd>Error message when a non-existent date such as February 30 is entered.</dd>
<dt>data-validation-message-date-min [conditionally required]</dt>
<dd>Error message when a date past the <code>min</code> attribute value is entered.</dd>
<dt>data-validation-message-date-max [conditionally required]</dt>
<dd>Error message when a date future the <code>max</code> attribute value is entered.</dd>
</dl>
