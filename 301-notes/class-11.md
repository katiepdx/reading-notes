## Styling HTML5 Forms Videos FROM https://www.youtube.com/watch?v=HiHHvTcHiEk&list=PL4cUxeGkcC9g5_p_BVUGWykHfqx6bb7qK

**HTML**
- Link to styles
- Image logo in header
- Form (title of each section is a p tag)
    - first section 
    - second section
    - fieldset - `<legend>` for title of the fieldset
    - select with options
    - submit button

**CSS**: 
- form p to get the p tags in form

**NOTE**: img png is one png with all the check box images.

**RADIO BUTTONS**
- Can't change radio buttons so hide them and replace them with out images for the button. 
- `input[type="radio"]` - select all inputs with type of radio
    - Opacity of 0 to hide them
    - SHOW user which is selected by using a pseudo class
- `label[for="male"]`, `label[for="female"]` - style both at the same time. 
    - insert img `background: url(path here) no-repeat`
    - `background-position: 0 -32px` to move the position of the img that was just imported.
    - `line-height:` - changes line height
- Get checked inputs `input:checked + label[for="male"]`, `input:checked + label[for="female"]` get all the checked labels that are male or female
    - `background-position: 0 0;` Shifts the img png to the checked swirl.
    - `color: red; `- Change the text color to red when checked.

**TEXT INPUT STYLES**
- Target fieldset `fieldset`
    - style fieldset to change the border part
- Target legend to change the title of the fieldset (this ex. is contact info). 
    - `letter-spacing: 0.1em;` changes spacing between letters
- Target specific inputs 
    - `input[type="email"], input[type="telephone"],`
        - Change font color. This will be the font color when the user types into the field.


**SELECT BOX**
- Remove default styles using appearance none
- `appearances: none;` not support across all browsers
    - Need to specify which browser by doing the following

    ```css
    <!-- chrome -->
    -webkit-appearance: none; 
    <!-- mozilla -->
    -moz-appearance: none;
    <!-- opera -->
    -o-appearance: none;
    <!-- internet explorer -->
    -ms-appearance: none;
    appearance: none;
    ```

    - `padding: top-value right-value bottom-value left-value;`
- Submit box shadow. Target submit `input[type="submit"]` box-shadow: value value value color

**VALIDATION**
- Add `<span class="tick"></span>` under each input in the fieldset (ex. email and telephone).
- When the field is valid, use pseudo class.
- `input[type="email"]:valid` - target valid input field of type email
    - Add styles.

- Target valid inputs with tick span (adjacent selector)
    - `input[type="email"]:valid + .tick` 
        - Add styles