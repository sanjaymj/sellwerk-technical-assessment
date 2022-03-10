# sellwerk-technical-assessment

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Start local json server
```
json-server --watch db.json
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Project Description
* The overall goal of the project is to implement a basic TODO app with CRUD functionality. 
* The app currently loads a few TODOs by making a GET request to the endpoint ```/todos```. These TODOs are rendered on the home screen when the app is started.
* Each TODO item has a unique id, a description and a status. The status can be NEW, COMPLETED or DELETED.

## Task Description
* The user should be able to create a new TODO by entering a description in the text box and clicking on the ADD button. The applicatoin should make a POST request to ```/todos``` to persist a new TODO. This newly created TODO should now be visible in the UI.
* The user should get an overview of the completed and total tasks. For example if 5 out of 15 tasks have status COMPLETED, the user should see ```5 out 15 tasks completed```.
* The user should be able to delete TODOs by clicking the delete button. Deleted TODOs should no longer be displayed. On pressing the delete button, the delete endpoint from json-server has to be called to delete the item.
* The user should be able to change the status of a NEW TODO to COMPLETED by clicking on COMPLETE button. On pressing the Complete button, the PUT endpoint from json-server has to be called to edit status of an item.
* TODOs with status COMPLETED should have a visual appearance to indicate that the TODO is already COMPLETED. 

## Nice to haves
* Add simple tests to check basic functionalities.
* The user should also be able to edit the text of an existing TODO.( This should happen on pressing the edit button)
* Use Vuex to handle data and state management.

