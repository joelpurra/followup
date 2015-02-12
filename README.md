# [FollowUp](https://github.com/joelpurra/followup)

A jQuery plugin to show and hide follow up questions in a form. The follow ups are specified through HTML5 `[data-*]` attributes.



## Usage
Include the script after jQuery has been loaded. It will check all existing form elements
and automatically initilaize follow-up questions when the page has loaded.

Note: currently only `<input type="radio" />` or `<input type="checkbox" />` can have follow up
questions, visible when the input has been checked.

Markup for a single question (form input) that has a follow up question:

```html
data-has-follow-up="sibling"
```

 "sibling" assumes the follow up question(s) containers shares the same parent element.

```html
 data-has-follow-up="selector"
 data-target="#follow-up-question-container-elsewhere"
 ```
"selector" allows addressing any other `data-target="..."` container element(s) with a jQuery style selector.

Markup for containers with multiple radio buttons inside:

```html
data-has-follow-ups=""
```

Markup for a question that is [`[required]`](http://www.w3.org/WAI/GL/wiki/Techniques/HTML5/Using_the_required_attribute_to_indicate_a_required_input_field) when it is a follow up question. Normal `[required]` attributes do not work, as they input fields are hidden if they're not triggered as follow up questions.

```html
data-is-follow-up-required="required"
```


Markup for the container of a follow up container

```html
data-is-follow-up=""
```



## Example with a group of radio buttons
Only one of the `<input type="radio" />` buttons has a follow up question. Since they are in
the same group, they will be evaulated together. Changing from yes to no will change the
visibility of the follow up question `<textarea>`.

```html
<p data-has-follow-ups="">
    Have you ever had a close encounter with a UFO (Unidentified Flying Object)?
    <label><input type="radio" name="seen-ufo" required="required" data-has-follow-up="sibling" /> Yes
        <label data-is-follow-up="">Please explain the encounter, especially what kind it was
            <textarea data-is-follow-up-required="required"></textarea>
        </label>
    </label>
    <label><input type="radio" name="seen-ufo" required="required" /> No</label>
</p>
```



## Todo
- Use with `<select>` dropdowns.
- Use with other `<input />` types and `<textarea>`?
- Use dynamic change listener - *or* - expose a function to dynamically add questions with follow ups.
- Animations when showing/hiding elements.
- Package the plugin better.



## Runtime dependencies
- [jQuery](http://jquery.com/)



## License
Copyright (c) 2012, 2013 [Joel Purra](http://joelpurra.com/)
All rights reserved.

When using FollowUp, comply to at least one of the three available licenses: BSD, MIT, GPL. Please see the `LICENSE` file for details.
