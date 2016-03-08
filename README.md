# sapui5_WebWorker

This is an example on how to use the Web Worker in a SAPUI5 application.

Feel free to copy the project and use it how you like.

## This is a simple worklist app templated from the WebIDE.
### WebWorker specific code:
Worklist.controller.js : The onUpdateFinished() method starts the webworker reading all the object data in the background and storing it into a JSONModel.
Object.controller.js : In the _bindView() method we check if the webworker has already cached data for this object. If it has, then we bind the controls to the JSONModel. If not, we bind the controls to the apps main ODataModel.

### Where can we practically use this?
This scenario is just to show the idea in a dummy app. In reality, getting the object data is pretty quick, typically. However where you have a huge list of data where the OData service initially just reads the first 20 items or so (Unless there is another huge EntitySet to read on the detail/object page?), it could be nice to quick off the webworker to contiue reading the rest of the list so that when the user does scroll again its already cached....
