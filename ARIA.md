#Accessibility- ARIA
## 5. ARIA
a. WAI-ARIA: What can ARIA (NOT) do?
b. ARIA labelling
c. Landmarks and ARIA roles
d. ARIA realtionships 
e. Visible and Hidden content
f. ARIA live
g. ARIA relevant

- **WAI-ARIA**: Web Accessibility Initiative - Accessible Rich Internet Application.
- ARIA attributes need to have explicit values (can't be empty values).

- What ARIA can do and what can not do:
  - Can:
  
  :white_check_mark: modify Accessibility tree.
  
  - Can Not:
  
  :x: modify element behaviour.
  
  :x: modify element appearance.
  
  :x: add focus.
  
  :x: add event handling.
  
- ARIA give a semantic meaning to non semantic elements.
- ARIA can also give a new semantic meaning to a native semantic element.
  - Example:
  ```
  <button role="switch" aria-checked="true" class="toggle">
    Enable
  </button>
  ```
- ARIA can express UI patterns which doesn't exist in HTML.
  - Example: `tree widget`

- ARIA can add labels which is only accessible to assestive technology.

- ARIA can provide semantic Relationship.

- ARIA can provide live updates (aria-live).

- the [video](https://youtu.be/7vz1aakYHtw?t=50s) explains that.

### a. Role

- Definition: Short hand for a particular UI pattern.

- make sure that the role attribute is in the same element as tabindex attribute.

```
<div tabindex="0" role="checkbox" aria-checked="true" class="checkbox" checked>check me</div>
```

### b. ARIA labelling

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
  
### c. Landmarks and ARIA roles
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
  
### d. ARIA realtionships  
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


### e. Visible and Hidden content
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


### f. ARIA live
- for in time alerts to user.
- `aria-live="polite"`  : important but not urgent alert.
- `aria-live="assertive"` : important and urgent alert.

### g. ARIA relevant
- These attributes work with `aria-live`:

  - `aria-atomic` : when true assistive tech will present the entire region as a whole.
  - `aria-relevant` :indicates which type of changes should be presented to the user.
    `aria-relevant="additions"` ==> means any element added to live region is presented.
    `aria-relevant="text"` ==> means that any text content added to any descendant element is presented.
    `aria-relevant="removals"` ==> means that removal of any text or element within the live region is presented.
    `aria-relevant="all"` ==> means that additions or removals of text is presented.
    `aria-relevant="additions text"` (default).
  -  `aria-busy`
