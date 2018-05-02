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
  ```
  <button style="visibility: hidden;">
  <div style="display: none;">
  <span hidden>
  ```  
Or
- __Only visible to assistive tech:__
`aria-hidden="true"`
1. element positioned absolute far off the screen. `position: absolute; left: -1000;`
2. `aria-label`
3. `aria-labelledby` or `aria-describedby` reference a hidden element.

### g. ARIA live
for in time alerts to user.
- ARIA live has three important values:
- `aria-live="off"(default)`: updates to region is not represented to user, unless assistence technology is currently focused to that region.  
- `aria-live="polite"` : (background change) alert = important, not urgent.
```
<div class="chat-history" arialive="polite">
We are head of in...!
</div>
```
- `aria-live="assertive"`: alert = important & urgent.
```
<div class="alertbar" arialive="assertive">
Could not connect!
</div>
```
- __Include ARIA live attributes in initial Page load__
- Try different type of changes to see what works on different platforms (screen readers).

#### Resources 
- [Example ARIA Live](http://udacity.github.io/ud891/lesson5-semantics-aria/19-aria-live/)

### h. ARIA relevant
- The following __attributes__ work with `aria-live`:
- They finetune _what is communicated to the user when the live region changes_:

#### 1) __ARIA-ATOMIC:__ true assistive tech presents the _entire region as a whole_.( `aria-atomic`)
```
<span  aria-labelledby= "birthdayLbL" 
       aria-live= "polite" 
       aria-atomic= "true">
<input type="number" id="day" value="18"> 
<input type="number" id="month" value="10">
<input type="number" id="year" value="1983">
</span>
```        
- __NOTE:__ Only need to be specified if __true__, if false= by default.

#### 2) __ARIA-RELEVANT:__indicates _type of changes needed to be presented_ to the user. ( `aria-relevant`)
  - `aria-relevant="additions"` ==> _any element added to live region_ is presented.
  - `aria-relevant="text"` ==> _any text content added to any descendant element_ is presented.
  - `aria-relevant="removals"` ==> _removal of any text/ element within the live region_ is presented.
  - `aria-relevant="all"` ==> _text additions or -removals_ is presented.
  - `aria-relevant="additions text"` _(default)_.


#### 3) __ARIA-BUSY:__
  - `aria-busy`
