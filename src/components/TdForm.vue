<template>
  <div class="template">
    <h1>Todo List</h1>
    <TdInput 
      v-on:receiveTask="onTaskAdd"
    />
    <TdList :taskList="taskList"/>
  </div>
</template>

<script>
import TdInput from './TdInput'
import TdList from './TdList'

export default {
    name: 'TdForm',
    components: {
      TdInput,
      TdList,
    },
    data () {
        return {
            taskList: [],
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
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}
h1{
  color: antiquewhite ;
}

</style>