# Accessibility- [Semantics Basics](#3-semantics-basics)
##3. Semantics Basics

### a. Affordances
- Definition: the qualities or properties of an object that define its possible uses or make clear how it can or should be used.
- [WebAim](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)
- Screen reader can provide info for elements' **Name(label) Role State Value.**
- Browser takes DOM tree (natively semantic elements or othered with ARIA)  ==modify it to==> Accessibility tree( containing all information for screen reader Name Role State Value).

### b. Labeling, Naming, and Alternative text
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


## 4. Navigating Content
- Screen Reader can make you navigate through headings, links, form controls, and landmarks.
- It is important to use meaningful headings and links names.
- Also use a good heading structure from h1 to h6 (for long complex content).
- descriptive link text example: 
instead of using "learn more" links text use :learn more about bla bla".
- [link Anti-patterns video](https://youtu.be/SiblO4dfYBg)
- Landmarks: you can navigate by landmarks
`<header>`
`<nav>`
`<main>`
`<section>`
`<article>`
`<aside>`
`<footer>`

## 5. ARIA
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
 
## 6. Style
### a. Focus style
- [WebAim](https://webaim.org/standards/wcag/checklist#sc2.4.7).
- [video shows different styling for focus using :focus pseudo selector](https://youtu.be/ZooEnrj8aMc).
- [video shows different styling reaction between native and non native buttons](https://youtu.be/bfPGicTGBTI).
- Styling with ARIA ==> using ARIA attribute as an attribute selector. This made a good verification that I set the aria state properly.
- Responsive website:
  - [WebAim](https://webaim.org/standards/wcag/checklist#sc1.4.4).
  - meta viewport tag: `<meta name="viewport" content="width=device-width, initial-scale=1">`
  - In meta viewport tag: don't use `user-scalable=no` ==> prevent user from zooming the screen.
  - Use relative CSS units.
  - Use appropriate size touch targets.Minimum touch target size is 48 px.
  - If the touch target(like icons) is smaller, add padding to it.
  - To avoid overlapping make sure to leave margin around touch target with minimum 32px.
- Color Contrast:
  - [WebAim Minimum](https://webaim.org/standards/wcag/checklist#sc1.4.3).
  -It states that: Body text (less than 18.66px) ==> Contrast ratio minimum `4.5:1`
                   Large Text (more than 18.66px) or (24px) ==> Contrast ratio minimum `3:1`
                   
  - [WebAim Enhanced](https://webaim.org/standards/wcag/checklist#sc1.4.6).
   -It states that: Body text (less than 18.66px) ==> Contrast ratio minimum `7:1`
                    Large Text (more than 18.66px) or (24px) ==> Contrast ratio minimum `4.5:1`
 - You can use {Chrome Accessibility Extension}(https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en) to make Accessibility Audit to check contrast ratios and see recommendations and try them live at Dev tools.
- 1 of 20 men and 1 in 200 women suffer from some sort of color blindness.
  - Don't convey info with color alone.
  - You can use color together with text, underline, audio, and aria-live.
  - [WebAim](https://webaim.org/standards/wcag/checklist#sc1.4.1).
  - You can use [Nocoffee chrome extension](https://chrome.google.com/webstore/detail/nocoffee/jjeeggmbnhckmgdhmgdckeigabjfbddl?hl=en-US) to experience color blindness vision and enhance use of color to convey info.
  - Use [High Contrast chrome extension](https://chrome.google.com/webstore/detail/high-contrast/djcfdncoelnlbldjfhinnjlhdjlikmph?hl=en) and check how your UI appear for high contrast users.