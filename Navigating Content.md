# Accessibility- [Navigating Content](#1-navigating-content)
_Source: Accesibility - Udacity Front End Web Development Nanodegree_

### Table Of Contents:
## 4. Navigating Content
- a. Headings
- b. Links
- c. Form Controls
- d. Landmarks

## 4. Navigating Content
- Screen Reader can make you navigate through headings, links, form controls, and landmarks.

###Screen Reader Shortcuts (OS X)
- `CMD+F5`: turn on VoiceOver 
- `TAB, Shift+TAB, arrow keys` (keyboard operation): work with VoiceOver running
- `CMD+L`: jump to address bar
- `CTRL+Option+U`: open Web Rotor / Type search term with Web Rotor open to search within Web Rotor
- `CTRL + Option + ← ↑ ↓ → `: explore content
- `CTRL + Option + CMD + H`: move __forward by heading__
- `CTRL + Option + CMD + Shift + H`: move __backward by heading__

#### Resources
- [Web AIM VoiceOver](https://webaim.org/articles/voiceover/)-full VoiceOverintroduction, including most keyboard commands available.
- __Screen Reader Shortcuts (Windows)__ [NVDA](https://www.nvaccess.org/)-open source screen reader for Windows. 
- [Web AIM Introduction to NVDA](https://webaim.org/articles/nvda/)- the basics of using NVDA to check accessibility.
_ __Screen Reader Shortcuts (Linux)__ [Orca](https://help.gnome.org/users/orca/stable/)-Gnome desktop-manager for Linux. 

#### a. Headings
- Use meaningful headings and links names.
- Use a good heading structure from `<h1>...<h6>`(for long complex content).
- in __DEV TOOL:__ Look through the HTML of a page and identify each heading's number. They look like: `<h#>`

__JavaScript headings snippet:__
```
var hs = document.querySelectorAll('h1,h2,h3,h4,h5,h6');
for (var i = 0; i < hs.length; i++) {
   console.log(hs[i].textContent.trim() + " " +  
               hs[i].tagName,
               hs[i]);
}
```
#### Resources (WebAIM checklist items)
- [Writing Usefull Alt Text](https://webaim.org/techniques/alttext/)
- [1.3.2](http://webaim.org/standards/wcag/checklist#sc1.3.2)
- [2.4.10](http://webaim.org/standards/wcag/checklist#sc2.4.10)
- [1.3.1](http://webaim.org/standards/wcag/checklist#sc1.3.1)
- [2.4.1](http://webaim.org/standards/wcag/checklist#sc2.4.1)
- [2.4.6](http://webaim.org/standards/wcag/checklist#sc2.4.6)

#### b. Links
- Use descriptive link text 
__Example:__ instead of using _"learn more"_ links text use `:learn more about bla bla".`

#### c. Form Controls
- [link Anti-patterns video](https://youtu.be/SiblO4dfYBg)

#### d. Landmarks
- Navigate by landmarks:
`<header>`
`<nav>`
`<main>`
`<section>`
`<article>`
`<aside>`
`<footer>`
