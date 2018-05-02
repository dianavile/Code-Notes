# Accessibility- [Style](#6-style)
_Source: Accesibility - Udacity Front End Web Development Nanodegree_

### a. Working with focus styles
- The pseudo code `focus` only matchend when an element has __focus__:
```
:focus {
//Use the "outline " property to change the appeareance of the focus ring
outline: 1 pc dotted #fff; 
}
```
__NOTE__: This is a __MAJOR__ _anti-pattern_
- Without a focus indicator, a user does not know which keyboard element to interact with.

```
:focus {
outline: 0; 
}
```
Alternatives are:
1) __Give your element the same hover focussed styles__
```
button:hover,
button: focus {
background: #e91e63;
color: #fff;
text-decoration: underline;
}
```
2) __Use a specific focus pseudo class in CSS__ 
(to get a consistent indicator across browsers)
```
button: focus {
outline: 0;
box-shadow: 0 0 8px 3 px;
rgba (255, 255, 255, 0.8);
}
```
3) Delete default focus indicator, use focus style
```
.radio:focus {
outline: 0;
}

.radio:focus::before {
box-shadow: 0 o 1px 2 px #5b9dd9;
}
```
- Leave the default focus ring in place.
- If you want to change, use the :focus pseudo class to create your own styled focus indicator.
- [Exercice](https://github.com/udacity/ud891)

#### Resources 
- [WebAim-2.4.7 checklist](https://webaim.org/standards/wcag/checklist#sc2.4.7).
- [:focus](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)
- [outline](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
- [:hover-pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)
- [::before-pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
- [video- Styling for focus :focus pseudo selector](https://youtu.be/ZooEnrj8aMc).

### b. Input Modality:
```
<div class="btn"
role= "button"
tabindex="0">
Click me!
</div>
```
#### Resources 
- [`:moz-focusring` pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-focusring). __Only supported in Firefox!__
- [Proposing CSS input modality article](http://radar.oreilly.com/2015/08/proposing-css-input-modailty.html).
- [Input modality shim](https://github.com/alice/modality)(https://github.com/WICG/focus-visible).
- [video_ Styling native/non-native buttons](https://youtu.be/bfPGicTGBTI).

### c. Styling with Aria
- Styling with ARIA ==> use ARIA attribute as an attribute selector. To set the aria state properly, so it is visually reflected.
- When building custom controls be sure to include tabindex so keyboard users can easily interact with the elements.
- A huge benefit to styling with ARIA: it provides visual feedback, which can act as a safeguard when testing and debugging code.

 - __HTML not toggled:__
```
<div class="toggle"
role= "button"
aria-labelledby="muteLbl"
aria-pressed="false"
tabindex="0">
Mute
</div>
```
 - __HTML toggled:__
```
<div class="toggle pressed"
role= "button"
aria-labelledby="muteLbl"
aria-pressed="true"
tabindex="0">
Mute
</div>
```
 - __CSS toggled:__
 ```
.toggle.pressed{
// transition to
// pressed state
}
 ```
  - __CSS toggled- with aria attr:__
 ```
.toggle[aria-pressed= "true"]{
// transition to
// pressed state
}
 ```
 #### Resources 
- [CSS attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) 
- [Exercise](https://github.com/udacity/ud891)

### d. Responsive design for multiple-devices:
  - Meta viewport tag: `<meta name="viewport" content="width=device-width, initial-scale=1">`
  - In meta viewport tag: don't use `user-scalable=no` ==> prevent user from zooming the screen.
  - Use relative CSS units.
  - Use appropriate size touch targets:
    - Minimum touch target size: 48 px.
    - If touch target (`icons`) <48 px, add padding.
    - To avoid overlapping, leave margin around touch target. Minimum 32px.

#### Resources 
  - [WebAim](https://webaim.org/standards/wcag/checklist#sc1.4.4).
  
### e. Mobile Screen Readers:
Mobile Screen Readers

### f. Color & Contrast Requierements
-  Don't convey info with color alone, as 1 of 20 men and 1 in 200 women suffer from some sort of color blindness.
- Use `color` together with `text`, `underline`, `audio`, and `aria-live`.

 - __Color Contrast:__ 
   - Body text (less than 18.66px) ==> Contrast ratio minimum `4.5:1`
   - Large Text (more than 18.66px) or (24px) ==> Contrast ratio minimum `3:1`  
   - [WebAim Minimum](https://webaim.org/standards/wcag/checklist#sc1.4.3).

 - __Color Contrast ratio:__ 
   - Body text (less than 18.66px) ==> Contrast ratio minimum `7:1`
   - Large Text (more than 18.66px) or (24px) ==> Contrast ratio minimum `4.5:1`  
   - [WebAim Enhanced](https://webaim.org/standards/wcag/checklist#sc1.4.6).

 - __Accessibility Audit:__ 
   - to check contrast ratios/see recommendations/try Live at Dev tools 
   - [Chrome Accessibility Extension](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en) 
    - [WebAim](https://webaim.org/standards/wcag/checklist#sc1.4.1).
    - Experience color blindness vision, enhance use of color to convey info 
  [Nocoffee chrome extension](https://chrome.google.com/webstore/detail/nocoffee/jjeeggmbnhckmgdhmgdckeigabjfbddl?hl=en-US). 
    - Check how UI appear for high contrast users 
  [High Contrast chrome extension](https://chrome.google.com/webstore/detail/high-contrast/djcfdncoelnlbldjfhinnjlhdjlikmph?hl=en) 
  
