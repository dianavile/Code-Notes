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

### a. ARIA DO´s and DONT´s:
- **WAI-ARIA**: `Web Accessibility Initiative` - `Accessible Rich Internet Application.`
- ARIA attributes need to have __explicit values__ (NO _"empty values"_).

- ARIAS :white_check_mark: 
  - modify Accessibility tree.
  -  give  semantic meaning to non-semantic elements.
  -  give new semantic meaning to native semantic element.
  Example:
  ```
  <button role="switch" aria-checked="true" class="toggle">
    Enable
  </button>
  ```
  - express UI-patterns not existing in HTML.
  Example: `tree widget`
  - add labels (only accessible to assistive technology).
  - provide semantic Relationship.
  -provide live updates (aria-live).
-  [video](https://youtu.be/7vz1aakYHtw?t=50s).

- ARIAS :x:
  -  modify element behaviour.
  -  modify element appearance.
  -  add focus.
  - add event handling.
  
### b. Role
- __Role__ = particular `UI pattern`.
-  The `role attribute`= in the __same element as__ `tabindex attribute`.
```
<div tabindex="0" role="checkbox" aria-checked="true" class="checkbox" checked>check me</div>
```
### c. ARIA labelling
- **aria-label** _attribute_
  - Can be used for element that has only a visual appearance.
  - override any other labelling such as `<label>`, or text content (like that for a button) except **aria-labelledby** _attribute_.
  - have the label clicking behaviour like `<label>` 
 
- **aria-labelledby** _attribute_
  - Overcome all other labelling methods.
  - refers to another element (which label it) by using a value corresponds to the id of the labelling element.
  - can take more than one element id (multiple labels) .
  - can refer to elements that are hidden for assestive technologies ( hidden for example).
  - Don't have the label clicking behaviour like `<label>` and `aria-label`.
  
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
