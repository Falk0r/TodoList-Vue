<template>
        <transition-group name='task-list' tag="ul">
            <li 
                v-for="(task, index) in taskList"
                :key="task"
                class="task-list-item"
            >
                {{task}}
                <TodoListButtonDelete 
                    :task-index="index"
                    @taskDone="deleteTask"
                />
            </li>
        </transition-group>
</template>

<script>
import TodoListButtonDelete from './TodoListButtonDelete';

export default {
    name: 'TodoListTasks',
    components:{
        TodoListButtonDelete,
    },
    props: {
        taskList: Array,
    },
    methods:{
        deleteTask(id){
            this.taskList.splice(id, 1);
        }
    }
}
</script>

<style scoped>
.task-list-item{
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: white;
    padding: 10px;
    margin: 10px 0;
    transition: all 1s ease;
}
 .task-list-leave-to{
    opacity: 0;
}
</style>