# ngMorph #
 
## Morphable Elements ##
This module is an attempt at packaging transitions/animations into directives that enable the reuse of visual elements by morphing them into other elements. Simply create an originating element and an end-state view, and ngMorph takes care of the rest!

![ngMorph Demo](http://imgur.com/MT9CwbV.gif)

## Demo ##
Preview available [here](http://jimobrien.github.io/ngMorph/)

## Getting Started ##
  1. Install with bower:
 
    ```sh
      bower install --save angular-morph
    ```

  2. Include the module in your project: 
  
      ```js
        angular.module('yourApp', ['ngMorph']);
      ```

## Usage ##

### Settings ###
Morphables require a settings object which you define in your controller. Settings for each morphable end-state can be found in their respective usage example below.

###Modal###

_Example:_

 ```html
   <button ng-morph-modal="settings"> Log In </button>
 ```
 
 ```js
   app.controller('AppCtrl', function ($scope) {
     $scope.settings = {
       closeEl: '.close',
       modal: {
         templateUrl: 'path/to/view.html',
         position: {
          top: '30%',
          left: '20%'
         }
       }
     }
   });
 ```
 
__Modal Settings__
 - `closeEl:` 
 - `modal:` _Required._ The modal configuration object.
 - `templateUrl:` _Required if `template` is not defined_. The path to the view template. 
 - `template:` _Required if `templateUrl` is not defined_. An HTML template string. If templateUrl is also defined, `template` will take priority.
 - `position:` _Optional._ The positioning of the end-state element. Can either be pixels or a percentage. If no unit is specified, the input will be treated as a percentage ("30" => "30%").

###Overlay (Coming Soon)###

 ```html
   <div ng-morph-overlay="settings"> ... </div>
 ```
 
 ```js
   app.controller('AppCtrl', function ($scope) {
     $scope.settings = {
       closeEl: '.close',
       overlay: {
         templateUrl: 'path/to/view.html'
       }
     }
   });
 ```
 
 __Overlay Settings__
 - `closeEl:` 
 - `overlay:` _Required._ The overlay configuration object.
 - `templateUrl:` _Required if `template` is not defined_. The path to the view template. 
 - `template:` _Required if `templateUrl` is not defined_. An HTML template string. If templateUrl is also defined, `template` will take priority.
 
 
###Expand (Coming Soon)###
 
 ```html
   <div ng-morph-expand="settings"> ... </div>
 ```
 
 ```js
   app.controller('AppCtrl', function ($scope) {
     $scope.settings = {
       closeEl: '.close',
       expand: {
         templateUrl: 'path/to/view.html'
       }
     }
   });
 ```



## What's Next ##

There is a lot of work to do before this is ready for an alpha release.. Following is a list of todos to get this repo in shape:

  - [X] Abstract functionality from the post-linking function of the `morphable` directive.
  - [X] ~~Refactor using ngAnimate and GSAP~~ (sticking with CSS transitions)
  - [ ] Add support for nested morphables (morphables within view templates)
  - [ ] Add different transitions (modal, screen overlay, expand (left, right, down, up))
  - [ ] Add before/after animation hooks.. (or broadcast events?)
  - [ ] Validate input settings
  - [ ] Add error handling
  - [ ] Write tests
  - [ ] Write docs
  - [ ] convert these items to GH issues