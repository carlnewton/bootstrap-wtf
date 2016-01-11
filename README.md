# Bootstrap WTF
Jinja macros for creating WTForms that use Bootstrap's styles and components

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

Bootstrap WTF displays each field inside of a `form-group` class by default. It also displays labels, placeholders and form validation error messages. Any of these can be disabled for a particular field:

    {{ b_wtf.bootstrap_field(form.first_name, label=False, errors=False) }}
    {{ b_wtf.bootstrap_field(form.last_name, form_group=False, placeholder=False) }}

Or as a blanket rule for the entire form:

    {{ b_wtf.bootstrap_form(form, labels=False, placeholders=False) }}
