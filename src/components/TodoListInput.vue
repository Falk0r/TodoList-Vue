<template>
    <input
        type="text"
        v-model="taskToAdd"
        @keyup.enter="sendTask"  
        placeholder="ajouter une tâche"
        class="addTask"
    >
</template>

<script>
export default {
    name: 'TodoListInput',
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
}
</script>

<style scoped>
.addTask{
    height: 2rem;
    width: 90%;
    font-size: 1.5rem;
}
</style>