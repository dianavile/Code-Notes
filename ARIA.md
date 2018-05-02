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

#### ARIAS DO´s 
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

#### ARIAS DONT´s 
  -  Modify element behaviour.
  -  Modify element appearance.
  -  Add focus.
  -  Add event handling.
  
### b. Role
- __Role__ = particular `UI pattern`.
-  The `role attribute`= in __same element as__ `tabindex attribute`.
```
<div tabindex="0" role="checkbox" aria-checked="true" class="checkbox" checked>check me</div>
```
#### Resources 
 - [ARIA 1.0 roles](https://www.w3.org/TR/wai-aria-1.0/#roles).
 - [ARIA 1.1 roles (draft)](https://www.w3.org/TR/wai-aria-1.1/#roles).
 - [ARIA 1.1 practices guide (draft)](https://www.w3.org/TR/wai-aria-practices-1.1/).

### c. ARIA labelling
- **aria-label** _attribute_
  - Used for element with `visual appearance` only. 
  - Override other labelling (`<label>`) or text content (`button `) except **aria-labelledby** _attribute_.
  - Add click behaviour to `<label>` 
 
- **aria-labelledby** _attribute_
  - Overcome all other labelling methods.
  - Refers to another element (`label`), by using an id-value of labelling element.
  - More than one element id (`multiple labels`).
  - Refer to `hidden elements` for __assistive technologies__(`hidden`).
  - __NO__ click behaviour like `<label>` and `aria-label`.
  
#### Name the Elements
- Provides the label for the first (`outer`) element.
- To `hide` element from the accessibility tree, choose `"No label"`.
- `HTML labelling techniques`, `ARIA roles` and `ARIA attributes`, only work effective, if used correctly.

### d. Landmarks and ARIA roles
- Landmarks are __NOT supported__ in _older Browser versions_. 
- Instead, use `role attribute`:
-Examples: 
  ```
  <header role="banner">
  <nav role="navigation">
  <main role="main">
  <aside role="complementary">
  <footer role="contentinfo">
  <dialog role="dialog">
  ```
### e. ARIA relationships  
- **ARIA relationship attributes**
  - Refer to one/more elements on a page (to make a link between them).
  - The difference is: 1. _What does the link mean_.
                       2. _How the link is represented to users_.       
- __Attributes:__ 
  - `aria-labelledby`
  - `aria-describedby`
  - `aria-owns`
  - `aria-activedescendant`
  - `aria-posinset`
  - `aria-setsize`

#### Resources 
- [Video ARIA Attributes](https://youtu.be/e1ZmfmnB6v8?t=40s).
- [Collection of relationship attr](https://www.w3.org/TR/wai-aria-1.1/#attrs_relationships)

### f. Visible and Hidden content
- __Goal:__ finetune the user experience of users using assistive technology, to ensure that certain parts of the DOM is either: 
- __Hidden:__
  1. 
  ```
  <button style="visibility: hidden;">
  <div style="display: none;">
  <span hidden>
  ```  
Or
- __Only visible to assistive tech:__
2. `aria-hidden="true"`
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
