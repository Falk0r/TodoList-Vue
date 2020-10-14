# todolist-vue ✅

<div style="text-align: center;">
<image src="https://github.com/Falk0r/TodoList-Vue/blob/main/src/assets/screenshot.png?raw=true" style="height: 400px;">
</div>

## Link to the project

>[>>TodoList-vue](https://todolist-vue.onrender.com/)


This is my first Todolist I've never code in any language and my first presentation in English ! So please, don't kidding me 😅

This app is code in __Vue.js__ and __CSS__. This project help me to understand :
* The communication between child -> parent
* The communication between parent -> child
* Create a full app with components
* Structure an app using __Atomic Design__ that I've seen one day before code this one and I would like to make in practice

## Atomic Design

<div style="text-align: center;">
<image src="https://github.com/Falk0r/TodoList-Vue/blob/main/src/assets/plan.jpg?raw=true" style="height: 300px;">
</div>

In this project, I cut the app in 3 main parts :
1. Title
2. Input to add a task
3. List of tasks
    1. task (need to update a make a components)
    2. button to delete task

## Keys point

### Pass data to a child component

To pass data to a parent, we need to use event. $emit() method. The first parameter of $emit is the event that should be listened for in the parent component. The second (optional) parameter is the data value to pass.

### For exemple in this project :
We need to pass the data in __input__ to his parent __form__.

__Form__ parent listen the event "receiveTask" emit by the child __input__ :
```javascript
    <TdInput 
      v-on:receiveTask="onTaskAdd"
    />
```
Went the event is listenning, it call the method "onTaskAdd" in the parent __Form__ :
```javascript
    data () {
        return {
            taskList: [],
        }
    },
    methods: {
        onTaskAdd (value){
            console.log(value);
          this.taskList.push(value);
      }
    }
```
This method update the taskList.

### Pass data from child to parent

In the child __input__, we create a model to link the data from the input.
```html
    <input
        type="text"
        v-model="taskToAdd"
        v-on:keyup.enter="sendTask"
    >
```
When the user push "enter" on his keyboard, it's call the methods "sendTask" 
```javascript
    data () {
        return {
            taskToAdd: '',
        }
    },
    methods: {
        sendTask(){
            this.$emit('receiveTask', this.taskToAdd);
            this.taskToAdd = "";
        }
    }
```
This method emit the event "receiveTask" listen by the parent, and send the value by the second parameter.

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

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

