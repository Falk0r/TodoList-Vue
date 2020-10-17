<template>
  <div class="template">
    <TodoListNav />
    <h1>Todo List</h1>
    <TodoListInput 
      @receiveTask="onTaskAdd"
    />
    <TodoListTasks :task-list="taskList"/>
  </div>
</template>

<script>
import TodoListInput from './TodoListInput'
import TodoListTasks from './TodoListTasks'
import TodoListNav from './TodoListNav'

export default {
    name: 'TodoList',
    components: {
      TodoListInput,
      TodoListTasks,
      TodoListNav,
    },
    data () {
        return {
            taskList: [],
            user: this.$auth.user,
        }
    },
    methods: {
      onTaskAdd (value){
          this.taskList.push(value);
      }
    }
}
</script>

<style scoped>
.template{
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    width: 100%;
}
</style>