# Accessibility- [ARIA](#5-aria)
_Source: Accesibility - Udacity Front End Web Development Nanodegree_

### Table Of Contents: ARIA
- a. WAI-ARIA: ARIA DO´s and DONT´s
- b. Role
- c. ARIA labelling
- d. Landmarks and ARIA roles
- e. ARIA realtionships 
- f. Visible and Hidden content
- g. ARIA live
- h. ARIA relevant

#### Resources 
- [ARIA 1.0 spec](https://www.w3.org/TR/wai-aria/)
- [ARIA 1.1 spec](https://www.w3.org/TR/wai-aria-1.1/)
- [Example](http://udacity.github.io/ud891/lesson5-semantics-aria/02-why-aria/index.html)

### a. ARIA DO´s and DONT´s:
- **WAI-ARIA**: `Web Accessibility Initiative` - `Accessible Rich Internet Application.`
- ARIA attributes need to have __explicit values__ (NO _"empty values"_).

- ARIAS DO´s :white_check_mark: 
  - modify Accessibility tree.
  -  give  semantic meaning to non-semantic elements.
  -  give new semantic meaning to native semantic element.
  Example:
  ```
  <button role="switch" aria-checked="true" class="toggle">
    Enable
  </button>
  ```
  -Express UI-patterns (not existing in HTML).
  Example: `tree widget`
  -Add labels (only accessible to assistive technology).
  -Provide semantic Relationship.
  -Provide live updates (aria-live).
  -[video](https://youtu.be/7vz1aakYHtw?t=50s).

- ARIAS DONT´s :x:
  -  Modify element behaviour.
  -  Modify element appearance.
  -  Add focus.
  -  Add event handling.
  
### b. Role
- __Role__ = particular `UI pattern`.
-  The `role attribute`= in the __same element as__ `tabindex attribute`.
```
<div tabindex="0" role="checkbox" aria-checked="true" class="checkbox" checked>check me</div>
```
#### Resources 
 -[ARIA 1.0 roles](https://www.w3.org/TR/wai-aria-1.0/#roles).
 -[ARIA 1.1 roles (draft)](https://www.w3.org/TR/wai-aria-1.1/#roles).
 -[ARIA 1.1 practices guide (draft)](https://www.w3.org/TR/wai-aria-practices-1.1/).

### c. ARIA labelling
- **aria-label** _attribute_
  - Used for element with visual appearance only. 
  - Override other labelling (`<label>`) or text content (`button `) except **aria-labelledby** _attribute_.
  - add click behaviour to `<label>` 
 
- **aria-labelledby** _attribute_
  - Overcome all other labelling methods.
  - refers to another element (which label it) by using a value corresponds to the id of the labelling element.
  - can take more than one element id (multiple labels) .
  - can refer to elements that are hidden for assestive technologies ( hidden for example).
  - Don't have the label clicking behaviour like `<label>` and `aria-label`.
  
#### Name the Elements
- In each case, provide the label for the first, or outermost, element.
- If the element would be hidden from the accessibility tree, choose "No label".
- HTML labelling techniques, and ARIA roles and attributes, must be used correctly in order to be effective.

### d. Landmarks and ARIA roles
- Landmarks may not have support in browsers' old versions. So we need to use role attribute with them.
  -Examples: 
  ```
  <header role="banner">
  <nav role="navigation">
  <main role="main">
  <aside role="complementary">
  <footer role="contentinfo">
  <dialog role="dialog">
  ```
### e. ARIA realtionships  
- **ARIA relationship attributes**
  - They take a reference to one or more elements on the page to make a link between them.
  - The difference is: 1. _What link means_.
                       2. _How represented to users_.
       
- Attributes: 
  - `aria-labelledby`
  - `aria-describedby`
  - `aria-owns`
  - `aria-activedescendant`
  - `aria-posinset`
  - `aria-setsize`
    
- [Video](https://youtu.be/e1ZmfmnB6v8?t=40s) explains it.
- [Collection of relationship attr](https://www.w3.org/TR/wai-aria-1.1/#attrs_relationships)

### f. Visible and Hidden content
- For the seek of fine tuning the experience of users using assistive tech.
- To ensure that certain parts of the DOM is either: 
  - hidden to assistive tech.
  Or
  - Only visible to assistive tech.
- Hidden:
  1. 
  ```
  <button style="visibility: hidden;">
  <div style="display: none;">
  <span hidden>
  ```
  2. `aria-hidden="true"`
- Only visible to assistive tech:
  1. element positioned absolute far off the screen. `position: absolute; left: -1000;`
  2. `aria-label`
  3. `aria-labelledby` or `aria-describedby` reference a hidden element.

### g. ARIA live
- for in time alerts to user.
- `aria-live="polite"`  : important but not urgent alert.
- `aria-live="assertive"` : important and urgent alert.

### h. ARIA relevant
- These attributes work with `aria-live`:
  - `aria-atomic` : when true assistive tech will present the entire region as a whole.
  - `aria-relevant` :indicates which type of changes should be presented to the user.
  - `aria-relevant="additions"` ==> means any element added to live region is presented.
  - `aria-relevant="text"` ==> means that any text content added to any descendant element is presented.
  - `aria-relevant="removals"` ==> means that removal of any text or element within the live region is presented.
  - `aria-relevant="all"` ==> means that additions or removals of text is presented.
  - `aria-relevant="additions text"` (default).
  - `aria-busy`
