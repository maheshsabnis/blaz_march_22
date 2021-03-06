# JavaScript Full Stack

- Fundamental JS Programming
    - JS Requirements
        - Foundation of Modern Open JS Full Stack App development
        - Provides End-to-End support for Application development
            - Interactive Front-End with Browser
            - Server-Side Apps
    - Types
        - No explicit DataTypes
        - a Variable is declared using 'var' keyword
            - The 'var' provides a function scope for a variable
        - The Type is parsed by JS Parser which is already available in browser 
            - Parsed Types as 
                - number, string, boolean,  object, function 
            - Parsed Type to extract values from the right-hand-side expression    
        - Standard JS Objects
            - window
                - represents a currently loaded window
                - Eventing to manage the JS Execution in the Browser
            - document
                - Currently loaded HTML DOM in current window object
                - to extract the DOM elements using 'document' object, use the window.onload event
                - Used to extract a DOM element so that the data can be read/write frm and to it
                    - UI Elements
                        - input: for Accepting Data and Selecting data
                            - text, radio, check, button
                            - property system
``` html
<input type="text" value="3" id="txt1" name="txt" class="c">
```
                                - input: the HTML tag
                                - type: the type of UI that will be shown on browser
                                - value: the data that can be entered in textbox and can be read from textbox
                                - id: the Unique identity of UI element in DOM
                                - name: the identity ti post the data to server using HTML Form 
                                - class: used to apply CSS Styes on HTML element, alternatively used to define a element group  
                    - The 'document' object's methods to extract UI element from DOM
                        - getElementById('id'); return an instance of single HTML element
                        - getElementsByTagName('TAG-NAME'), returns collection of HTML elements having name property value
                            - e.g. 
                                - document.getElementsByTagName('input'), return collection of input elements
                        - getElementsByClass('class-name'), returns collection of HTML elements having same class name property value        
                        - addEventListener(p1,p2,p3);
                            - USed to attach an event with UI element
                            - p1: the event name, e.g. click, change, blur, mouseenter, mouseleave, keyup, etc.
                            - p2: the function that will be executed when an event is raised
                            - p3: the boolean value to keep the event attached with UI element                      
            - Array (Not Directly accessible, but available as type)
                - The only Standard Collection Data Structure in JS
            - Number, String, Boolean, Date (Not Directly accessible, but available as type) 
            - console
                - Represents the out object to present the data to End-User
                    - console.log()   
                    - console.error()                 
    - Functions
    - DOM Interaction with JS
        - input elements    
            - Text
            - Button
        - collection elements
            - Provides a group of same UI
            - generated statically using HTML elements and its parent child relationship
            - generated dynamically using loops provided using JavaScript Programming
                - for..loop
                - for..in loop
                    - simplification of for..loop   
    - The JS 'Array'
        - The most powerful collection data structure in JS
        - In JS, this is an  'Array' class aka Type, which has following basic JS Methods
            - push(), pop(), data management methods
            - sort(), the data re-arrange methods
            - shift(), unshift() methods, to remove and add data in top of the array (at indexes from 0)
            - indexof(), read an element's existance in array
            - lastIndexOf(), the index of element from top to bottom but the last appearance of element
    - The JS literal objects aka JSON Object
        - a Key:Value pair that holds the Text-Based Data
        - The 'key' is literal identification and value can be 
            - primptive datatype e.g. number, string, date, object, array
            - a Function
            - var obj = {
                key:value
            };           
        - The literal object is global for the current JS function /  file as a Singleton Object   
        - within the object, literal (or keys) are accessed using 'this' object
        - The JS Provides an  'Object' class with following important methods
            - Object.keys(literal-object)
                - Used to read all keys of literal object
            - Object.values(literal-object)
                - Used to read value of each key in object
    - The 'string' type
        - The Data Structure that is used to store textual data
        - Case Sensitive
        - Internally it is treated as Character Array
        - Availability of most of the JS Array methods available to string  
        - String Object
            - length the property that shows length
            - indexOf(), lastIndexOf(), substring(), slice(), toUpperCase(), toLowerCase(), etc.     
            - The slice() and substring() both are same but the slice() can read from first (+ve) and last (-ve)positions where as the substring() always starts from first position            
    - Math object
        -  Useful object to reduce the complexity of client-side calculations those are executed on browser
            - Provides a ready to use Mathematical functions those are useful for data processing on client-side based on calculations                         
    - Date object
        - Used process dates based on settings
        - Date() object, the JS Class, this must be instantiated
            - var d = new Date(format);
                - yyyy, mm (0 to 11, where 0 is January and 11 is December), dd
            - get methods
                - getDate(), getFullYear(), getMonth(), getHours(), getMinutes(), getSeconds(), getMilliseconds()
            - set methods        
                 - setDate(), setYear(), setMonth(), setHours(), setMinutes(), setSeconds(), setMilliseconds()    
    - JavaScript Function Objects
        - These are the functions those will be used as follows
            - A Standard Traditional Function with reusable code
            - A Class with Public and Private scope for its contents
                - Started introducing new Libraries and Frameworks
            - An Immediately Invocable Function Expression (IIFE) aka Module                  
        - 3 Types of Functions
            - Reference Functions, a full function implementation is stored in an object
                - var MyObject = function(){...........}
                    - the Reference function contains public functions/members prfixed using 'this'
                        - var MyObject = function(){ this.fn1=function(){......};} 
                            - The 'fn1' is public function, the 'this' is scope that represents 'MyObject' itself   
                        - Offers a 'prototype' property
                            - This is used to extend the object by adding new function(s) in it
                            - MyObject.prototype.fn2 = function()  {........}    
            - Close function aka function
                - This is function body that returns an 'Object Literal' aka '{}' as the publicly exposed contents from the function 
                    - function MyObject(){
                        return {
                            Key1:value1,
                            Key2:value2,
                            ....
                        }
                    }           
                    - The Return is exposed as public contents from the MyObject
            - IIFE
                - A Module Implementation to define a scope of variable, function in a limited block
                    - (function(){.......})();
                        - Self-Executable JavaScript
                    - var MyObject =  (function(){.......})();
                        - MyObject is a Module             

- HTML 5 API
    - HTML 5 =  HTML Tags + Inline CSS + Inline JavaScript
        - Input Elements with new attributes
            - Input Elements: number, date, time, month, week, email
            - Attributes: placeHolder, min, max, minLength, maxLength, pattern, required, disabled, readonly
    - HTML 5 API System
        - It is a set of JavaScript Classes those are used for following
            - Storage
                - localStorage
                    - Browser's storage to store the data in JSON form
                    - Non-Volatile data, means the data will be available when the same site is loaded
                        - This uses the 'Same Origin Policy'
                         - The data will be available for the page for the specific site only
                         - e.g. is data is created using xyz.com, the it will be always available for xyz.com, other web site will not be able to access to access it
                - sessionStorage
                    - Browser's storage to store the data in JSON form
                    - Volatile data, means the data will be lost when the browser is closed
                    - This uses the 'Same Origin Policy'
                        - The data will be available for the page for the specific site only
                        - e.g. is data is created using xyz.com, the it will be always available for xyz.com, other web site will not be able to access to access it 
                    - methods
                        - setItem(key, data)
                        - getItem(key)
                        - clear(), delete all data    
                - indexedDB
                    - Database in Browser like RDMBS
                - WebSQL
                    - Available for Chrome
            - Drag-Drop
                - Interactive and Non-Interactive Elements
                    - Interactive, elements those are open to accept data from End-User and change its properties e.g. inpue:text all input elements. They are not having support for Mouseenter and MouseLeave events   
                    - Non-Interactive elements, they does not Read any values from End-User bust can write or show values to end-user (they are read-only elements). They have MouseLeave and MouseEnter events supported, e.g. Table, Div, span, paragraph, etc. 
                - Events used for Dynamic Updates in HTML DOM using following events
                    - dragstart
                        - event.dataTransfer Object
                            - Used to store the data of element being dragged 
                    - drop
                         - event.dataTransfer Object
                            - Used to pick the data of element being dropped 
                    - dragover
                - property
                    - draggable
                        - applied to element to inform to HTML DOM that this element will be dragged      
            - Graphics
            - Media
            - Files
            - Device Sensors         
- CSS and CSS Frameworks
    - Understanding CSS as a Concept
    - Using and Applying CSS on HTML Elements Statically and Dynamically
        - Applying Styles to TAG
            - Browser internally invokes 'document.getElementsByTagName("tag")' and applies styles to all matching tags
                - This is known as 'TAG-SELECTOR'
        - Applying Styles to HTML elements based on its 'id'
            - Browser internally invokes 'document.getElementById("id")'   and applies style to it
                - This is known as 'id selector'
                    - #{id}     
        - Define a Style class and apply it to 'class' attribute of HTML elements
            - .{CLASS-NAME}{..define styles...}
            - This is known as 'class selector'
    - CSS in depth CSS 3
        - Various Selectors   
            - Tag + Type
                - e.g. input[type="text"] all elements of input:text only
                       input.c1 all input elements with class as c1 
            - Element After
            - Element with Specific Position
                  - tr:nth-child
                    - tr:last-child
            - Element with specific value applied for an attribute of the HTML Element  
                - Value Starts With
                    - ^ symbol is used to apply style if attribute value starts specific valiu
                    - e.g.  
                        - <div class="The First Div"></div>
                        - div[class^=The]
                            - The class value starts with 'First'  
                - Value Ends With 
                    - $ Symbol
                    
                    - e.g.  
                        - <div class="The First Div"></div>
                        - div[class$=Div]
                            - The class value starts with 'Div'  
                - Value ate any position  
                    -  * Symbol
                    - e.g.  
                        - <div class="The First Div"></div>
                        - div[class*=Div]
                            - The class value has 'Div' at any position  
        - Styles for
            - Text
            - Tables
                - We can apply styles on specific Rows/Cells
                    - tr:nth-child
                    - tr:last-child
            - Borders
            - Margin
            - Fonts
            - Links
            - Alignments
            - Opacity
            - Dropdown     
        - CSS Definition and applying CSS on HTML Elements based on the Events
            - The CSS 3 detects Mouse Events on HTML Elements and then apply styles on it
                - Syntax
                    .{CLASS-NAME}:{EVENT-NAME}    
        - An Enhancements into the HTMl DOM Position for applying Styles based on the Element Position of element in DOM
            - element1~element2
                - All element2 those are coming after element1
            - element1>element2
                - All element2 those are children of element1    

- ES 6 aka Modern JavaScript
- Server-Side App Development using Node.js
- Front-End Interactive UI apps using React.js
- Microsoft Services
- Cloud App Development and Deployment 