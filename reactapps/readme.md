# React.js

- Library by Facebook
- React Project Creation
    - Using React CLI, a Project Ready Approach for working with React
    - Using Configuration with React's Object Model and WebPack
        -  WebPack, a Module Bundler that performs following
            - Using JS Object Model
            - Using CSS Files, SASS File with the help of Loaders
                - Loader: The Engine to Load Files in Node.js Runtime for WebPack
            - DevServer
                - Provide Inbuilt Node.js server to Host the React Application and Load Dependencies
        - https://www.webnethelper.com/2021/10/reactjs17x-creating-application-with.html

- React CLI
    - The 'create-react-app' CLI Project
        - npm install -g create-react-app
    - Create React Project
        - create-react-app [PROJECT-NAME]
    - React Object Model Packages
        - react
            - Base Object Model
        - react-dom
            - Manage Rendering
            - Virtual DOM
            - JSX
    - React CLI Scipts (Only for CLI Project)
        - react-scripts build
        - react-scripts text
        - react-scripts eject                              

# React Object Model

- The 'react' package
    - The 'Component' Concept
        - An Autonomous object that contains following
            - User Interface (UI) using HTML (JSX) elements
            - the Data Members aka State Properties
                - Used to pass and accept to and from UI
                - Define rendering of HTMl UI aka DOM
            - methods
                - Logic
                - These can be bound with Events of HTML Elements to Update Data members and hence DOM Rendering
    - Component Types
        - Class Components, the class derived from Component&lt;P,S&gt; Base class (NOTE: This was available upto React 15 as a Main Concept, the class component is ES 6 class,but from React 16.0+ onwards, it so not preferred to use class components )   
          - React Team is not retiring or deprecating Class Components, but new development is happening with functional components   
        - Functional Components
            - Popular from React 16.0+
            - Recommended by React Community
            - Uses a Standard Function concept of JavaScript
                - No need to learn any new syntax
            - 3 Types or Syntaxes of Functional Components
                - JavaScript Function that returns HTML
                    - e.g.
                        - function MyComponent()
                          {
                            return (`HTML UI`);
                          }         
                - The Function Expression that returns HTML 
                    - e.g.
```` javascript                    
                        - const MyComponent=()=>{  return (`HTML UI`);}
````                        
                - The Constant Function Expression That contains HTML UI
                    - e.g.
```` javascript                    
                        - const MyComponent=({`HTML UI`});        
````                        
        - The Component Name is used as a Custom HTML Tag
            - e.g. If Component Name is MyComponent then it will be used for rendering as 
```` html
<MyComponent/>
````
        - The Component MUST be exported as ES 6 Module
```` javascript        
            - function MyComponent()
              {
                return (`HTML UI`);
              }  
              export default MyComponent;
````              

        - Programmable types of Components
            - Stateless Components
                - Component that does not have any data members and does not render HTML based on data, instead its has a static HTML for rendering
            - Stateful Component
                - Used for Line-of-Business (LOB) Apps
                - It has Data Members for managing HTML rendering
                - It has Methods with logic and also methods those will be executed for UI Element's events e.g. click, change, etc.      
        - What is 'State'?
            - It is data that is used and manipulated by component to define HTML rendering
            - It is used to show data to UI to 
            - It is data accepted from UI
            - The 'state' is local to component, the state property will be live only in declaring component 
            - State is handled using following 2 Objects
                - useState()
                    - a Hook, a function, that will define data property and also contains a method that is used to update the data property and hence the UI that is bound with the data property   
```` javascript
 const MyComponent =()=>{
 let [x,setX] = useState(0);
  return (
      <input type="text" value={x} onchange={(evt)=>{setX(parseInt(evt.target.value))}}/>
  );
 }

````
   
    - The 'x' is a Data Member that will be bound with the UI element
    - The 'setX' is a callback function that will be used to update the value of 'x'
    - The '0' is initial value of 'x'
    - The 'x' is bound with 'input' element and when the input element is changed using 'onchange' event the value entered into the 'input' element will be updated in 'x' 

    - What is the 'useState()' uses the 'complex JSON object'
    - e.g.

```` javascript
 const MyComponent =()=>{
 let [person,setPerson] = useState({PersonId:0,PersonName:''}});
  return (
      Person Id: 
        <input type="text" value={person.PersonId} onchange={(evt)=>{setX({...person, PersonId:parseInt(evt.target.value)})}}/>
   Person Name: 
        <input type="text" value={person.PersonName} onchange={(evt)=>{setX({...person, PersonName:evt.target.value})}}/>
  );
 }
````

    - The State update will 'MUTATE' the same object with individual proeprties
        - {...person} 

    - The 'props'   
        - The object which an 'immutable' object that is used to transfer data across components in case of Parent-Child Component relationships
        - The Object is Readonly
        - The object is live throughout the life of the React Application 

```` javascript
const MyChildComponent=(props)=>{
    render(
        <input type="text" value={props.val}/>
    )
} 
````

    - The 'val' is a property that is dynamically created for the 'MyChildComponent' by its parent
    - e.g.

```` javascript
 const MyComponent =()=>{
 let [x,setX] = useState(0);
  return (
      <input type="text" value={x} onchange={(evt)=>{setX(parseInt(evt.target.value))}}/>
      <br/>
      {/* The 'val' is a dynamic JSX attribute created by React Object Model for 'props' object
       to pass data from Parent component to child component*/}
      <MyChildComponent val={x}/>
  );
 }
````

    - the 'val = {x}' is the data passed from MyChomponet to MyChildComponent 
    - The 'props' can also be used to emit data from child component to parent component 
        - This is Parent-Child communication

    - The 'React.Context'
        - A better way to pass data across component
        - The 'props' contains the state of data throughout the component tree
        - The 'Context' is from Parent to Specif Child Component       
- Layout Components
```` html
    - <Fragment/>
    - <></>
````            
    - Provide default layout for Component's UI, instae of using div tag