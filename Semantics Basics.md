# Accessibility- [Semantics Basics](#3-semantics-basics)

- __How to create websites for users with visual disabilities?__
- __How to use HTML effectively to create a good experience for all users?__

## 3. Semantics Basics
- a. [Semantics & Assistent Technology](#3-assistent-technology)
- b. [Affordances](#3-affordances)
- c. [Role Name State Value](#3-role-name-state-value)
- d. [The Accessibility Tree](#3-the-accessibility-tree)
- e. [Semantics in Native HTML](#3-semantics-in-native-HTML)
- f. [Naming Labeling and Alternative text](#3naming-labeling-and-alternative-text)


### a. Assistent Technology 
__Assistent Technology__ =  all `devices`, `software`, and `tools`, that _help any person with a disability complete a task_.
- __Examples:__ _screen reader, braille display, magnification,voice controll, switch access, sip & puff, eyetracking, but also
robotic devices, browser zoom, customed designed game controller and add-on chrome extension._ 
- For all these technologies, __programmatic expressed semantics__ are needed.

### b. Affordances
- __Affordances:__ the qualities (`properties`) of an object, that defines its use.
- __Examples:__ _buttons, sliders, sroll-downs, playback controls, price limites_ 
- `Choose an option`
- `Enter a line of text`
- `Enter a specific date`
- `Yes/No option`
- `Perform an action`

### c. Role, Name, Value
__How to access the visual information of the User Interface (UI)?__ 
- Information need to be expressed in such a way that it is _accesible programmatically by assistence technology_.
- Markup is used in a way that `facilitates accesibility`, so a _Screen reader can provide info for __Elements___': 
- __ROLE__= _What type? ex. Edit Text
- __NAME__= What name(label)? ex. your e-mail address
- __STATE__ = What state?
- __VALUE__= What value?

#### SOURCES: [WebAim](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)

### d. The Accessibility Tree
- Considering the A11y tree when writing your HTML will help in making your sites more accessible.
- The browser transforms __DOM tree__ (`natively semantic elements` or `othered with ARIA`) into the __Accessibility tree__ (=all information for screenreader: `Name`, `Role`, `State` and `Value`). 
- It can be done, for much of the __DOM__ has `implicit semantic meaning`. It uses __standard HTML native elements__ that are automatically recognized by browsers on a variety of platforms.
-Using the __proper semantic elements__ will make your life much easier when addressing accessibility concerns.

- __Example__: 
- `Main`
- `Form`
- `Radio Button`: name= "round trip", state= "selected"
- `Edit Text`: name = "full name"
- `Combo box`:  value= "no preference", name: "Seat type", state= "collapsed"
- `Button`: name= "search"
```
<main>
//<div class= "card">
<form>
  //<div class= "trip selector">
  //<div class= "row">
  //<div class= "inline control col-2">
  <label for="seatType"> SteatType </label>
  <select name="seatType" id= "seatType">
  <option value="0">No preference</option>
  <option value="1">Aisle seat</option>
   <option value="2">Window seat</option>
  </select>
//</div>

   //<div class= "inline control submit-form col-1">
    <button type= "submit" id= "submitBtn">Search</button>
    //</div>
  //</div>
  //</div>
  </form>
//</div>
</main>
```
__NOTE:__ information will be _reduced to the most important information only_: `Name`, `Role`, `State` and `Value`.

### e. Semantics in Native HTML
```
<label>
<input type="radio" checkedName= "tType"  value= "0">
Round Trip
</Label>
```
#### SOURCES:
- [WebAIM Guideline 1.1](http://webaim.org/standards/wcag/checklist#g1.1)
- [label](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) demonstrates two !label" options with it's labelling.
- [label](https://www.w3.org/TR/html5/forms.html#category-label) The W3C list of types of elements for a "label" tag.

### f. Naming, Labeling and Alternative text
- Using proper labeling not only helps accessibility but it makes the element easier to target for all users!
- There are 2 ways of __labeling form inputs__.
- Element could have a: 
1. `visual label (name)` _name="radio button"_ or a
```
<label>
  <input type="radio">
  Check me
</label>
```
2. `text alternative` _images_.
```
<input type="radio" id="radio-button">
<label for="radio-button">Check me</label>
```
- Using these labeling allows users to `toggle the input element` by also _clicking the label_.

__Alt text:__ 
1. Use an alternative text to the image, if not loaded.
2. Describe what the image about for screen reader.
3. Logos =  assign the company name.
4. Search icon = empty alt. (This will skip it from accessibility tree.)
5. Any image meant for decoration = empty alt.          
