# todolist-vue

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

### Pass data to a child component

### Pass data from child to parent
To pass data to a parent, we need to use event. $emit() method. The first parameter of $emit is the event that should be listened for in the parent component. The second (optional) parameter is the data value to pass.

#### For exemple in this project :
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
