# Homegear-Ref

Official repository for the Homegear Reference

# Style Guidelines / HTML Elements to Use

Note that a lot of the reference entries do not follow this guideline. Help would be appreciated to apply it to all files.

## General

* Component names: `b`
* Inline code: `em`

## Variables

* Names: `em`
* Types: `em`. Always start with a capital letter. Types are: `Array`, `Boolean`, `Float`, `Integer`, `String`, `Struct` and `Variant`. For `Array` also specify the element type. E. g.: `Array<String>`.
* Homegear-specific types: `em` followed by `a` with a link to the type.
* String values in `exampleValue`: Without single or double quote `"`.

## RPC Methods:

* Names: `em` followed by `a` with a link to the method. The method's name has to be followed by braces: `()`. E. g. `<em><a href="#setValue">setValue()</a></em>`.