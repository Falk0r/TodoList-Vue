<template>
        <transition-group name='task-list' tag="ul">
            <li v-for="(task, index) in taskList" v-bind:key="task" class="task-list-item">
                {{task}}
                <TdListButtonSupp 
                    :taskIndex="index"
                    v-on:taskDone="deleteTask"
                />
            </li>
        </transition-group>
</template>

<script>
import TdListButtonSupp from './TdListButtonSupp';

export default {
    name: 'TdList',
    components:{
        TdListButtonSupp,
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
ul{
    width: 90%;
    font-size: 1.5rem;
    display: flex;
    flex-direction: column-reverse;
}
.task-list-item{
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: white;
    padding: 10px;
    margin: 10px 0;
}
.task-list-item{
    transition: all 1s ease;
}
 .task-list-leave-to{
    opacity: 0;
}

</style>