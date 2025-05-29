<template>
    <!-- html -->
    <form @submit.prevent="submitTask" action="" class="input-group mb-3">
        <input v-model="task" type="text" class="form-control" placeholder="Enter your task" required>
        <button type="submit" class="btn btn-primary">Add task</button>
    </form>

</template>

<script>
/* js */
export default {
    data() {
        return {
            // variabili
            task: ''
        }
    },
    methods: {
        // funzioni
        submitTask(){
            // aggiungere il task inserito alla lista dei task
            console.log(this.task);
        }
    }
}


</script>

<style scoped></style>