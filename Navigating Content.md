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
- WebAIM's article on Using VoiceOver to evaluate Web Accessibility has a full introduction to VoiceOver from the point of view of evaluating accessibility, including most keyboard commands available.
- Screen Reader Shortcuts (Windows)
If you don't have a Mac device, NVDA is a free, open source screen reader available for Windows. WebAIM's introduction to NVDA covers the basics of using NVDA to check accessibility.
- Screen Reader Shortcuts (Linux)
If you only use Linux, Orca is available in the Gnome desktop manager, although this screen reader is much more rarely used and suffers from poor support by web browsers.

#### a. Headings
- Use meaningful headings and links names.
- Use a good heading structure from h1 to h6 (for long complex content).

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
