# FlowLine Integration Guide

## Overview

This document provides instructions for integrating and using FlowLine with your web project. FlowLine is a tool for creating and managing flow diagrams with configurable modules and connectors.

![Preview Image](https://github.com/junaidzx90/flowline-cdn/blob/main/preview.png?raw=true)

## Prerequisites

Ensure you have the following files available in your project:

- `jquery-ui.css` (local stylesheet)
- `jquery-3.6.0.min.js` (local jQuery library)
- `jquery-ui.min.js` (local jQuery UI library)

## Integration Steps

1. **Include Stylesheets**

   Add the following stylesheet links in the `<head>` section of your HTML:

   ```html
   <link rel="stylesheet" href="jquery-ui.css">
   <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/junaidzx90/flowline-cdn@v1.0.1/flowline.min.css">
   ```

2. **Create Container**

   Add a container element in your HTML where the FlowLine diagram will be rendered:

   ```html
   <div id="flowline-container"></div>
   ```

3. **Include JavaScript Libraries**

   Add the following script tags before the closing `</body>` tag of your HTML:

   ```html
   <script src="jquery-3.6.0.min.js"></script>
   <script src="jquery-ui.min.js"></script>
   <script src="https://cdn.jsdelivr.net/gh/junaidzx90/flowline-cdn@v1.0.1/flowline.min.js"></script>
   ```

4. **Initialize FlowLine**

   Add the following JavaScript code to initialize FlowLine once the document is ready:

   ```javascript
    $(document).ready(function () {
       var configurators = [
           {
               id: 'config1', // Optional
               heading: `Heading 1`,
               className: `flowline-configurator-1`,
               content: `<p style="color: hsla(39,100%,68%,1); margin:0;">Content for configurator 1...</p>`,
               positions: {
                   x: 50,
                   y: 50
               },
               connectors: [
                    {    
                        id: 'c1', // Optional
                        label: 'Menu List' 
                    },
                    { 
                        id: 'c2', // Optional
                        label: 'Menu PopUp' 
                    },
                    { 
                        id: 'c3', // Optional
                        label: 'User Alert' 
                    }
               ]
           }
       ];

       var modules = [
           {
               id: 'module2',
               heading: 'Menu Module',
               className: 'connector menu',
               content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit...',
               positions: {
                   x: 50,
                   y: 400
               }
           },
           {
               id: 'module1',
               heading: 'POPUP Module',
               className: 'connector popup',
               content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit...',
               positions: {
                   x: 300,
                   y: 400
               }
           },
           {
               id: 'module3',
               heading: 'Email Module',
               className: 'connector email',
               content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit...',
               positions: {
                   x: 550,
                   y: 400
               }
           }
       ];

       // Usage example
       const flowline = new FlowLine('#flowline-container', configurators, modules);
   });
   ```

5. **Events**

    ```javascript
    $(document).on("dragged", function(event, id){
        console.log(id);
    });
    $(document).on("dragging", function(event, id){
        console.log(id);
    });
    $(document).on("connect", function(event, object){
        console.log(object);
    });
    $(document).on("delete", function(event, id){
        console.log(id);
    });
    ```

## Customization

You can customize the `configurators` and `modules` arrays to fit your needs:

- **configurators**: Define the configuration items with unique IDs, headings, content, positions, and connectors.
- **modules**: Define the modules with unique IDs, headings, content, and positions.

## Additional Information

For more details on the FlowLine library and its options, refer to the official documentation provided with the library.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For support or questions, please contact [Contact with me](mailto:contact@easeare.com)