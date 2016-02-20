# Bootstrap WTF
Jinja macros for creating WTForms that use Bootstrap's styles and components.

## Requirements

* [Bootstrap](https://github.com/twbs/bootstrap)
* [WTForms](https://github.com/wtforms/wtforms)
* [Jinja2](https://github.com/mitsuhiko/jinja2)

## Usage

Copy the `bootstrap_wtf.html` file into your project:

    /example/templates/macros/bootstrap_wtf.html

Import Bootstrap WTF into your Jinja file:

    {% import 'macros/bootstrap_wtf.html' as b_wtf %}

Convert the fields:

    {{ b_wtf.bootstrap_field(form.first_name) }}
    {{ b_wtf.bootstrap_field(form.last_name) }}

Or if you're in a hurry, convert the entire form:

    {{ b_wtf.bootstrap_form(form) }}

## Options

### bootstrap_form

| Parameter      | Default value | Description |
| -------------- | ------------- | ----------- |
| `form_groups`  | True          | Wraps each field in a Bootstrap `form-group` container. |
| `placeholders` | True          | Displays the field label text as the placeholder for each field. |
| `labels`       | True          | Displays the label for each field. |
| `errors`       | True          | Displays validation errors in a Bootstrap `alert` component for each field. |
| `horizontal`   | False         | Uses Bootstrap grid classes to display each label to the left of it's field. It is necessary to apply the `form-horizontal` class to the form for this to appear correctly. |

#### Example
Hiding placeholders and enabling the horizontal layout for all fields:

    {{ b_wtf.bootstrap_form(form, placeholders=False, horizontal=True) }}


### bootstrap_field

| Parameter      | Default value | Description |
| -------------- | ------------- | ----------- |
| `form_group`   | True          | Wraps the field in a Bootstrap `form-group` container. |
| `placeholder`  | True          | Displays the field label text as the placeholder. |
| `label`        | True          | Displays the label. |
| `errors`       | True          | Displays validation errors in a Bootstrap `alert` component. |
| `horizontal`   | False         | Uses Bootstrap grid classes to display the label to the left of the field. It is necessary to apply the `form-horizontal` class to the form for this to appear correctly. |

#### Example
Hiding the label and errors for a field:

    {{ b_wtf.bootstrap_field(form.date_of_birth, label=False, errors=False) }}
