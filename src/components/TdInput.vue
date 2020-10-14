<template>
    <input
        type="text"
        v-model="taskToAdd"
        v-on:keyup.enter="sendTask"  
        placeholder="ajouter une tâche"
    >
</template>

<script>
export default {
    name: 'TdInput',
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
input{
    height: 2rem;
    width: 90%;
    font-size: 1.5rem;
}

</style>