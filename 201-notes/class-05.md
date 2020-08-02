# HTML Chapter 5: “Images” (pp.94-125)
Images are great to set the tone of the site. Make sure they are relevant, convey info, fit color pallette, and are instantly recognizable. Some images you need to pay for, like stock images. All images are subject to copyright. Images should be in a separate file in your directory and clearly labeled. 

Use `<img src"file path" alt="actuate description of photo read by screen readers" title="title goes here" height="100" width="100" />` to add a photo. Images in block level elements appear in new line. If image is inside inline element, they are inline with the text. 

**3 Rules for Creating Images**
- Save image in the right format (jpeg, gif, etc.)
- Save images at the right size (height/width)
- Measure images in pixels

Check resolution 

Images with many different colors - use JPEG
Images with few colors or large areas of the same color - use PNG or GIF
Animated GIFs are used to create simple animations.
Can check the size of images by opening them in a new tab. The tab will say the height and width in pixels. 

In HTML5, use `<figure>` and `<figcaption>` to add photos.

```html
<figure>
    <img src="example.com" alt="example photo" />
    <br/>
    <figcaption> This goes under the photo</figcaption>
</figure>
```

# HTML Chapter 11: “Color” (pp.246-263)
Color can bring pages to life!
- foreground color `<color>`. This is text color. Measured in RGB, HEX and Color names
- background color `<background-color>` Measured in RBG and HEX and Color names

Every color on a computer screen is mixing amounts of red, green and blue. Color picker tool is used to find a color. 

#### Colors:
- RGB Values- 0 to 255 
    - rgb(102, 205, 170)
- HEX codes uses hexadecimal code
    - #66cdaa
- Color names - limited options
    - MediumAquaMarine
- HSL(A) colors - Hue shown 0 to 360, saturation is a percentage between 0% to 100%, lightness is between 0% to 100%. 

**CSS3 Opacity**
- Measured between 0 and 1.
- `opacity: 0.5;` - 50% opacity
- RGBA and HEXA adds an alpha which is also opacity. Measured 0 to 1. RGBA value will only affect the element on which it is applied (not the child elements).

- Hue
- Saturation - amount of grey in the color
- Brightness- how much black is in the color. Max brightness, no black in color. 

#### Contrast
- low contrast - light grey. Text hard to read in low contrast.
- high contrast - black. Text is easier to read. Not good for a lot of text.
- medium contrast - dark grey. Good for a lot of text. 

# HTML Chapter 12: “Text” (pp.264-299)
#### Typeface Terminology 
- serif - have details on end of main strokes 
- sans-serif - straight ends to letters. good for low res screens if the text is small. Makes text easier to read. 
- Monospace - every letter has a fixed width. Used for code. Makes it easier to follow. 

- Weight (might, medium, bold, black)
- Style (normal, italic, oblique)
- Stretch (Condensed, regular, extended)

Note: Browsers usually only display chosen font if it's installed on that user's computer. Like photos, there are also copyrighted fonts. When designing on a mac, check how the typeface will look on a PC. PC to mac should be fine. 

#### FONTS, FONTS, FONTS
- `font-famiy` - can have a list of fonts separated by commas. If the first font isn't installed on the users computer, the browser will try the next one. 
    - Best to chose no more than three typefaces on a page. 
- `font-size` can be measured in pixels, percentages, or ems. Pixels are precise. Default size is 16px. 200%  would be 32px. Ems is equivalent to the letter 'm'. 

| Pixels | Percentages | EMS |
|-|-|-|
|  | 16px scale |  |
| h1 32px | h1 200% | h1 2em |
| h2 24px | h2 150% | h2 1.5em |
| h3 18px | h3 133% | h3 1.125em |
| body 16px | body 100% | body 100% |
|  |  | p 1em |


- `@font-face` can use this to use a font even if it isn't installed on the user's computer. Need to add a `src` to the font. **TTF, OTF, and SVG** are acceptable for most browsers.

    ```css
    @font-face {
        font-family: 'ChunkyFiveRegular';
        src: url('fonts/chunkfive.eot');
    }
    ```

- `font-weight: normal/bold;` 
- `font-style: normal/italic/oblique;`  
- `text-transform: uppercase/lowercase/capitalize;`  
- `text-decoration: none/underline/overline/line-through/blink;`  blink animates the text and makes it flash on and off.
- `line-height` leading - There is the baseline (descender) and the highest point (ascender). Line height is the vertical gap between lines of text.  
`letter-spacing`, `word-spacing` - kerning is space between each letter. Good to increase the letter spacing when heading is all uppercase. Default gap between words is usually 0.25em.
- `text-align: left/right/center/justify` - justify indicates that every line in a paragraph except the last line should be set to take up the full width of the containing box. For lots of paragraphs of text, best to left align text. 
- `vertical-align: baseline/sub/super/top/text-top/middle/bottom/text-bottom;` More commonly used for inline elements. This can also take a length that's given in pixels or ems or a percentage of the line height. 
- `text-indent` indents the first line of text within an element. Usually given in ems or pixels. It can take a negative value. This will push the text off the browser window. Even if browser window can't see it, it's still in the code. 
- CSS3 `text-shadow` takes 3 lengths and a color. Ex. `text-shadow: -1px -1px #666666;`
- `:first-letter, :first-line` - these are pseudo-elements. You can specify different values for the first letter or line of text inside an element. Ex. `p.intro:first-letter { font-size: 200% }`
- `a:link, a:visited` Shows color of link between user visits and after. 
- `:hover, :active, :focus` 
    - hover is when a user hovers, something happens. 
    - active: when a button or link is being clicked
    - focus: when the browser discovers user has already interacted with the element. Ex. when a cursor is in a form input and is ready to accept typing. 
    
