# OpenFin-Frameless_Example

This project explains how to create an OpenFin Frameless Window with a custom title-bar.  OpenFin allows you to remove the standard O/S from from a window, however this also reoves the standard window controls normally expected by an end user.  This project includes a custom title bar that returns the controls to the user.

The Project enables the first generation of the OpenFin Layout service.  A child window can be created by clicking on the 'Child Window' button on the main page, which will snap/dock to the parent if dragged adjacent to the window.  The cutom title bar also includes an example 'Undock' button, alternativly the window can be undocke by using the 'CTRL' + 'Shift' + 'u' global hotkey.

## Installing and running the project

Installing:

     npm install

Running

    npm start

## Removing the Frame from a window

The standard frame can be removed from an applications main window using the Application Configuration file (See: https://developers.openfin.co/docs/application-configuration) by setting `"frame" : false`, in this example the applicatiopn configuration can be found in /public/config/app.json

The frame can be removed from child windows by using the frame parameter in the Window Options object (https://developer.openfin.co/docs/javascript/stable/Window.html#~options) passed into the Window create method (https://developer.openfin.co/docs/javascript/stable/tutorial-Window.create.html) (This project does not current have an example of this)

## Creating the Title frame

This project uses CSS to create the tile bar, and defines a Drag Region using the `-webkit-app-region: drag;` parameter and control buttons using the OpenFin API.

## Adding a draggable region

The Draggable region in the demo is defined in public/app/css/main.css in the #titleBar, the area is defined as draggable by adding `-webkit-app-region: drag;` to the element

## Adding a minimize button

The Minimize example in this project is found in /public/scripts/main.js, it utilizes the OpenFin API Window.minimize() method (https://developer.openfin.co/docs/javascript/stable/tutorial-Window.minimize.html)

## Adding a restore button

The Restore example in this project is found in /public/scripts/main.js, it utilizes the OpenFin API Window.restore() method (https://developer.openfin.co/docs/javascript/stable/tutorial-Window.restore.html)

## Adding a Maximise button

The Maximise example in this project is found in /public/scripts/main.js, it utilizes the OpenFin API Window.maximize() method (https://developer.openfin.co/docs/javascript/stable/tutorial-Window.maximize.html)

## Adding a Close button

The Close example in this project is found in /public/scripts/main.js, it utilizes the OpenFin API Window.close() method (https://developer.openfin.co/docs/javascript/stable/tutorial-Window.close.html)

## Adding a Undock button

The Undock example in this project is found in /public/scripts/main.js, it utilizes the OpenFin API layouts.snapAndDock.undockWindow() method (https://cdn.openfin.co/docs/services/layouts/1.2.0/api/modules/snapanddock.html#undockwindow).  To enable the Layouts API you either need to build the npm package into your project (see https://github.com/HadoukenIO/layouts-service this is the recomended method), or add the following to your HRML page: `<script src="https://cdn.openfin.co/services/openfin/layouts/1.2.0/openfin-layouts.js"></script>`

The Layouts v1 service has been superceded by a new generation Native OpenFin Layouts, please contact support@openfin.co for more information.
