<template>
    <button class="done"
        :index="taskIndex"
        @click="sendDone"
    >
        Done
    </button>
</template>

<script>
export default {
    name: 'TdListButtonSupp',
    props:{
        taskIndex: Number,
    },
    methods:{
        sendDone(){
            this.$emit('taskDone', this.taskIndex);
        }
    }
}
</script>

<style scoped>
.done{
    font-size: 1.25rem;
    min-width: 4em;
    min-height: 2em;
    background-color: lightgreen;
    border: none;
    border-radius: 5%;
}
.done:hover{
    background-color: green;
    color: whitesmoke;
}

</style>