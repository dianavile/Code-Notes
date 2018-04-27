# Accessibility- [Semantics Basics](#3-semantics-basics)

- __How to create websites for users with visual disabilities?__
- __How to use HTML effectively to create a good experience for all users?__

## 3. Semantics Basics
- a. Semantics & Assistent Technology (screen readers)
- b. Affordances
- c. Role, Name, Value
- d. The Accessibility Tree
- e. Semantics in Native HTML
- f. Naming, Labeling and Alternative text


### a. Assistent Technology (screen readers)
__Assistent Technology__ =  all `devices`, `software`, and `tools`, that help any person with a disability complete a task.

### b. Affordances
- Definition: the qualities or properties of an object that define its possible uses or make clear how it can or should be used.
- [WebAim](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)
- Screen reader can provide info for elements' **Name(label) Role State Value.**
- Browser takes DOM tree (natively semantic elements or othered with ARIA)  ==modify it to==> Accessibility tree( containing all information for screen reader Name Role State Value).

### c. Role, Name, Value
### d. The Accessibility Tree
### e. Semantics in Native HTML

### f. Naming, Labeling and Alternative text
- [WebAim](https://webaim.org/standards/wcag/checklist#g1.1)
- Element could have a visual label (name) like for radio button or text alternative like in case of images.
- There are 2 ways of labeling form inputs.
```
<label>
  <input type="radio">
  Check me
</label>
```
```
<input type="radio" id="radio-button">
<label for="radio-button">Check me</label>
```
 - Using these labeling allow user to toggle the input element by also clicking the label.
 - alt text: 1. An alternative to the image if not loaded.
             2. describe what the image about for screen reader.
             3. For logos you can assign the company name for alt attribute.
             4. For search icon you can leave alt with no value. This will skip it from accessibility tree.
             5. Any image that is meant for decoration should have an empty alt.           

* [Semantics Basics](#3-semantics-basics)
* [Navigating Content](#4-navigating-content)
* [ARIA](#5-aria)
* [Style](#6-style)
