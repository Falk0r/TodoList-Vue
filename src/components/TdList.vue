<template>
    <ul>
        <li v-for="(task, index) in taskList" :key="index">
            {{task}}
            <TdListButtonSupp 
                :taskIndex="index"
                v-on:taskDone="deleteTask"
            />
        </li>
    </ul>
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
            console.log("id de la tache : " + id);
            this.taskList.splice(id, 1);
        }
    }
}
</script>

<style scoped>
ul{
    background-color: white;
    width: 90%;
    font-size: 1.5rem;
}
li{
    padding: 10px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

</style>