# Changing Expectations- the MVO model

### The MVO-modal consists of:
- Modal (DATA)
- Octopus (Functionality, Filtering)
- View (DOM)


### Modal
A `Modal` = code the __object + properties__ inside.

### Octopus
An `Octopus`= bind the `Modal` and `View`code together.
In here you find the code logic (
- 1) functionality 
- 2) filtering of Modal code into View

### View
A `view`code = code the __object + methods__

__NOTE:__ The View code NEVER changes the Modal directly. All changes related to code functionality are made within the octopus.

This is to:
1) not mess up the code
2) leave actual data unchanged
3) in this way the modal gives the view only the code functionality it needs.

In short: The `octopus`code, is the __BINDER CODE__, to get the data from the Modal to the VIEW code.
Always separate Modal and View, and use the Octopus to connect the functionality and filtering of the Modal into the View Code Part.
