# Accessibility- [FOCUS](#2-focus)
_Source: Accesibility - Udacity Front End Web Development Nanodegree_

## 2. FOCUS
### Table Of Contents:
- a. __FOCUS (MANAGEMENT):__ What is focus (management)? 
- b. __DOM ORDER__  
- c. __TABINDEX ATTRIBUTE__ 
- d. __SKIP LINKS__ 
- e. __MANAGE FOCUS__ 
- f. __KEYBOARD DESIGN PATTERNS__ 
- g. __OFF-SCREEN CONTENT__
- h. __MODALS & KEYBOARD TRAPS__

### a. __DEFINITION__:  focus (management)
__FOCUS__= `the location on a page that receives input from the keyboard`. It shows _where keyboard events go in a page_.
- An __HTML user interface(UI)__ consists of _multiple interactive widgets_ (__input__, __buttons__ & __select__ elements), 
- Such as:`form controls`, `scrollable regions`, `links`, `dialog boxes`, `browser tabs`, that form a `hierarchy` of `automatic tab order + built-in keyboard event handling`. They are __implicitely focussable__.
- Yet, __NOT all elements are focussable__. Examples are `header`, `paragraphs`and `images`. 

__FOCUS MANAGEMENT__= Move focus around the page using your [keyboard](https://www.w3.org/TR/html5/editing.html#focus-management) to interact with the interface.
- __TAB ORDER__:  _key input_ is channeled from the system, through a hierarchy of interactive widgets, to the "active(= focused) widget:
- ```TAB```: move focus forward
- ```SHIFT  TAB```: move focus backwards
- ```Arrow keys```: to navigate inside a component
```
Don't add focus to any content a user can Not interact with.
```
#### Sources:
- [Focus Management](https://www.w3.org/TR/html5/editing.html#focus-management)
- Exception: [add focus to non-interactionable content](https://www.youtube.com/watch?time_continue=155&v=ifW_oy9hajU)

### b. DOM ORDER
The DOM order matters for FOCUS MANAGEMENT: `element.tabIndex;`
```
Tab order = same as DOM order, even if  `visual` order is changed (with CSS).
Changing the  `visual` order can cause confusion among `screen readers` and `keyboard users`, who depend on keyboard navigation. 
```
- Work with native elements is good practice for __FOCUS behaviour__, because they are automatically be inserted into the __TAB ORDER__, based on their __DOM POSITION__.
```
<button> I should </button>
<button> Be Focussed </button>
<button> Last! </button>
```
- If Visual order is changed (with CSS), it can cause confusion:
```
<button style= "float: right;"> 
I should </button>
<button> Be Focussed </button>
<button> Last! </button>
```
- To prevent confusion, the __Reading__ and __navigation order__ (code order) SHOULD BE _logical_ and _intuïtive_.

#### Sources: 
- [WebAIM checklist items](http://webaim.org/standards/wcag/checklist#sc1.3.2)

### c. TABINDEX ATTRIBUTE
- Control __FOCUS BEHAVIOUR__ with __TABINDEX ATTRIBUTE__. 
- To get tabindex value of an element: `element.tabIndex;`
- __NOTE:__ `ONLY NEEDED` for `Interactional elements` (__input__, __buttons__ & __select__ elements)
- __NOT__ for `non-interactional elements` (__HTML-tags__, such as: _headers, paragraphs or images_)
 
- These elements Must have __FOCUS__:
  - `Header links`
  - `Call to Action button`
  - `Search Input`
  - `Form Elements`
  - `Footer Links`
- These elements should __NOT have FOCUS__, instead use __SEMANTICS__:
  - `Header`
  - `Block of text (paragraph)`
  - `Image`
  
##### 1) __tabindex = "-1"__
_ [.] __NOT__ in tab order.
- [.] focus programmatically by `focus()`
- [.] Used for __Off screen content, that appear in response to a user event()__ (ex. modals).
```
HTML: <dialog id="modal" tabindex="-1"></dialog>
JS: document.querySelector(´#modal´).focus()
```
##### 2) __tabindex = "0"__
- [.] to insert __Unfocusable element__ in tab order.
- [.] focus programmatically by `focus()`
- [.] So, `keyboard events` get directed to it.
```
HTML: <div id="dropdown" tabindex="0">Settings</div>
JS: document.querySelector(´#modal´).focus()
```
##### 3) __tabindex > 0__ 
- [.] Jump to the (__IN__) front of the tab order.
- [.] If multiple elements, `lowest value`= first (in tab order).
- [.] This practice is discouraged and seen as an __anti-pattern!__

- __NOTE__: never remove the `focus indicator` from an _interactive element_ unless you're going to replace it. 
- Otherwise a keyboard user might not know which element is focused!

#### Sources: 
- [tabindex on MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex)
- [focus navigation and tabindex attribute](https://www.w3.org/TR/html5/editing.html#sequential-focus-navigation-and-the-tabindex-attribute)

### d. SKIP LINKS
- Allow `screen reader, keyboard, and switch devices users` to __navigate__ towards main pagecontent.
- It bypasses all the following elements before the main content: `navigation bar`, `sublists`, `sitebars`, `hamburger menus`.
- Skip links makes all links __hidden until focus().__
```
<!--html code-->
<a href="#main-content" class="skip-link">Skip to main content</a>
<nav>
.
.
.
</nav>
<main id="main-content" tabindex="-1">
.
.
.
</main>
```
```
/*CSS code*/
.skip-link {
  position: absolute;
  top: -40px;
  left: 0;
  background: red;
  color: white;
  padding: 8px;
  z-index: 100;
  }
.skip-link:focus {
  top: 0;
  }
  ```
#### Sources: 
- [skip links](https://webaim.org/techniques/skipnav/)
- [Focus Start point](https://developers.google.com/web/updates/2016/03/focus-start-point?hl=en)
- **[Alternate way to skip to main content.](https://webaim.org/techniques/skipnav/#headings)**

### e. MANAGE FOCUS
- To manage `Focus in Complex Components`, use the [WAI-Aria guidelines](https://www.w3.org/TR/wai-aria-practices-1.1/).
-  The __ARIA Authoring Practices__ ("_ARIA Design Patterns doc_") provides guidance in selecting which `keyboard interaction` is appropriate for complex component ("actions", such as `drop down menu`, `tree view component`. 
 
### f. KEYBOARD DESIGN PATTERNS 
- Use `keyboard design patterns` to implement __focus inside of a component__.
- EXAMPLE: __Radio pattern__`Implement Keyboard Event Listeners`
- Use __ROVING FOCUS__( `"roving tabindex"`) to make changes in: `radiogroup.js`file.
 - __first radio button__: 
 1. tabindex="0" 
 2. checked 
 3. focus()
```
<li tabindex="0" checked> //set tab index to 0 on the currently active item
<li tabindex="-1"> //set tab index to -1 for all children
<li tabindex="-1">
<li tabindex="-1">
<li tabindex="-1">
```
- The component uses a `keyboard event listener` to know which keyboard the user pressed.
- to know on which component to set next tabindex to 0
- when moving to the next element => first element: 
1. tabindex="-1" 
2. remove checked 
3. unfocus :: 
```
<li tabindex="-1"> //change tabindex to -1, remove checked
<li tabindex="0"> checked //add focus(), later remove focus() and add checked
<li tabindex="-1">
<li tabindex="-1">
<li tabindex="-1">
```
Next element: 1. tabindex="0" / 2. checked / 3. focus()
  - If  __last__ element `tab` move to __first__ element.
  - If  __first__ element `shift` + `tab` move to __last__ element.

#### Sources: 
- [ARIA Authoring Best Practices 1.0 (Radio Button)](https://www.w3.org/TR/wai-aria-practices/#radiobutton)
- [ARIA Authoring Best Practices 1.1 (Radio Group)](https://www.w3.org/TR/wai-aria-practices-1.1/#radiobutton)
- [Example](https://www.w3.org/TR/wai-aria-practices-1.1/examples/radio/radio-1/radio-1.html)
- [ARIA- Design Patterns and Widgets](https://www.w3.org/TR/wai-aria-practices/#aria_ex)
- [Video](https://www.youtube.com/watch?v=uCIC2LNt0bk)

### g. OFF-SCREEN CONTENT
- A drawer panel can lead __focus__ to `visually disappear`. 
- Overcome it by setting `display: none;` or `visibility: hidden;`

####__How to check if `OFF-SCREEN CONTENT` is `ACCESSIBLE`?__
1) __Track focus:__ to find `missing focus`, type into console: `document.activeElement;`
    - this gives a reference to the current focussed item
2) Use the __Chrome Accessibility Developer Tools Extension__ to quickly find __accessibility issues__ in your page:
    - to add an `Accessibility Properties panel` to __Elements__ inspector
    - to add an `Accessibility option` to __audits__ panel. 
#### Sources: 
- [document.activeElement](https://developer.mozilla.org/en-US/docs/Web/API/DocumentOrShadowRoot/activeElement)
- [Chrome Accessibility Developer Tools Extension](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en)

### h. KEYBOARD TRAP & MODAL
-  __KEYBOARD TRAP:__ keyboard focus is `locked or trapped at one particular page element`. 
- The user __CAN NOT__ `navigate` to and from all navigable page elements, using only a keyboard.
- Prevent a `permanent keyboard trap`.

__EXCEPTION:__ use a `temporary keyboard trap` for a __MODAL__
- Use __WebAim__ in `Modals` to _trap keyboard focus inside the modal_ until modal is closed.
- It => return focus to `last focused element` before modal open.
__HTML__:
```
<button class="modal toggle"> Open Modal </button>

<div class="modal">
  <h1> Join our newsletter </h1>
  <p> short description about the newsletter & why to join? 
  </p>
  <div class="field">
  <label for="fullname"> Full Name </label>
  <input id="fullname" type= "text">
</div>
 <div class="field">
  <label for="email"> E-mail address </label>
  <input id="email" type= "text">
</div>
<button id="signup"> Sign me up!</button>
</div>

<div class="modal overlay"></div>
```
__JAVASCRIPT__:
```
//hold previosly focussed element
let focusedElementBeforeModal;

//find the modal and its overlay
const modal document.querySelector(´modal´);
const modalOverlay document.querySelector(´modalOverlay´);

//add EventListener "click" on ModalToggle to openModal
let modalToggle document.querySelector(´modalToggle´);
modalToggle.addEventListener(´click´, openModal);

//create function openModal
function openModal(){
//save current focus
focusedElementBeforeModal= document.activeElement;

//Listen for and trap the keyword
modal.addEventListener(´keydown´, trapTabKey);

//Listen to indicators to close the modal
modalOverlay.addEventListener(´click´, closeModal);
//Sign-up button
let signupBtn.addEventListener(´click´, closeModal);

//Find all focusable children
const focusableElementString = ´a[href], area[href],
input:not([disabled]), select:not([disabled]),
textarea:not([disabled]), button:not([disabled]), iframe, object,
embed, [tabindex=´0´]), [contenteditable]´;

let focusableElements = 
modal.querySelectorAll(´focusableElementString´);

//Convert Nodelist to Array
focusableElements= Array.prototype.slice.call(focusableElements);

//Figure out first and last element in group of focusableElements
let firstTabStop = focusableElements[0];
let secondTabStop = focusableElements[focusableElements.length -1];

//Show the modal and overlay
modal.style.display = ´block´;
modalOverlay.style.display = ´block´;

//Focus firstTabStop
firstTabStop.focus();

function TapKeyPress()
//Check for TapKeyPress
if (e.keyCode === 9) {

//shift + TAB
if (e.shiftKey) {
if document.activeElement=== firstTabStop) {
e.preventDefault();
lastTabStop.focus();
}
//TAB
} else {
if document.activeElement=== lastTabStop) {
e.preventDefault();
firstTabStop.focus();
    }
  }
}

//Escape
if (e.keyCode ===27) {
closeModal();
    }
  }
}

function closeModal(){
//Hide the Modal and Overlay
modal.style.display = ´none´;
modalOverlay.style.display = ´none´;
  
//Set focus back to element before modalOpen
focusedElementBeforeModal.focus();
}
```
#### Sources: 
- [WebAIM checklist items](http://webaim.org/standards/wcag/checklist#sc2.1.2)
- [dialog](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
- [Example](https://github.com/udacity/ud891/tree/gh-pages/lesson2-focus/07-modals-and-keyboard-traps)
